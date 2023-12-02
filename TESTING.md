# Testing

## Code Validity
- HTML Validation (W3C) - [pass](https://validator.w3.org/check?uri=https://parabytes.github.io/Portfolio_Project-1.2_html-css/)
- CSS Validation (Jigsaw) - [pass](https://jigsaw.w3.org/css-validator/validator?uri=https://parabytes.github.io/Portfolio_Project-1.2_html-css/)

## Functionality Testing

The project was constantly tested for functionality and accessibility throughout the development process using the Live Server extension in VS Code, and it was first deployed on GitHub on Wednesday, the 29th of November 2023, for further testing.

### 1. Navigation Bar
**Toggle Burger Menu:**
Confirmed the toggle burger menu functions correctly on tablet and mobile devices.
Verified the expand and collapse functionality of the menu toggler.
Confirmed the standard navigation menu appears on larger devices (desktops and laptops) and hides on smaller screens.
Smooth transition and functionality across different screen sizes were observed.

### 2. Link Functionality
**Internal Links:**
All internal links within the website (Home, About Us, Our Services, Testimonials, Contact Us) navigate correctly to their respective sections.
'Request an Audit' and 'Learn More' buttons in the Hero section accurately link to the respective sections.

**External Links:**
All external links, including social media icons in the footer, correctly open the intended pages in new tabs.
The email link (mailto:info@cyphex.com) in the footer successfully opens the default mail application with the correct recipient address.

### 3. Header Section

**Logo Click Functionality:**
The company logo in the header successfully links back to the home page (index.html).

### 4. Main Content

**Hero Section:**
Text and buttons are visibly aligned and clearly legible on various devices.

**Our Clients Section:**
Company logos are displayed properly, aligned dynamically throughout different screensizes by using:

```css
grid-template-columns: repeat(auto-fit, minmax(100px, 1fr)); /* auto-fit` adjusts number of columns based on content */
grid-auto-rows: 40px;
```

It will create a new grid container in the next row whenever the screen becomes too small to display all of them in a single row. However, on normal mobile devices, there are three logos displayed at the top and one at the bottom. Because the function creates a symmetric grid, the logo in the single row is displayed on the left, not centered. This bug was fixed by setting a specific breakpoint range and changing the order of the item positions to align them in the center.

```css
@media (min-width: 360px) and (max-width: 460px) {
    .brands-container {
        grid-template-columns: repeat(3, 1fr);
    }

    .brands-container img:last-child {
        /* Position the last item in the second row, center column */
        grid-column-start: 2;
        grid-row-start: 2;
    }
}
```

**About Us Section:**
Text is well-formatted and legible across different screen sizes.

**Services Section:**
Both Physical and Virtual Penetration Testing sub-sections are laid out correctly, and dropdown contents function as intended.

### 5. Testimonials

**Slider Functionality:**
The testimonial slider operates smoothly, with radio buttons for navigation functioning properly.
It works on all regular desktop and mobile screen resolutions. However, when zooming out further, the Testimonial section will merge into the above Our Services section, causing overlap.

### 6. Contact Form

**Form Functionality:**
All input fields in the form validate inputs correctly.
The submit button works as expected, with appropriate feedback provided upon submission.

### 7. Footer Section

**Link Functionality:**
The layout and content in the footer are well-displayed on various screen sizes.

### 8. Cross-Browser and Device Compatibility
**Browser Testing:**
The website displays consistently and functions well across different browsers (Chrome, Firefox, Safari, Edge).

**Responsive Design:**
The website's responsiveness is confirmed on various devices (smartphones, tablets, laptops, desktops), maintaining layout integrity.

### 9. Accessibility Checks
**Contrast and Readability:**
Text readability and contrast between text and background are satisfactory.
Keyboard Navigation:
Website navigation using the keyboard only (Tab, Enter, Arrow keys) is seamless.

### 10. Performance Testing
**Load Time:**
The website loads efficiently with no noticeable delays.


## Performance and Accessibility Tests:

**The Lighthouse Reports Tool was used to test Performance, Accessibility Best Practice and SEO**


### Results:

- The first test showed a low performance score of 67%. This was due to the large-sized image content of the hero image and the two images in the Our Services section. Screenshot [here](presentation/performance_before.png)

- To accomplish better performance, all image files were compressed via tinypng.com and then converted to .webp.
- The size of the project folder was reduced from 6.13MB - [here](presentation/uncompressed_img.png)
o 926KB respectively - [here](presentation/compressed_img.png)
- Several more performance tests were conducted with scores between 80% and 90% - [here](presentation/performance_after.png)
A tinypng.com test was then conducted to see if there were any non-compressed image files left, which resulted in a "pass" - [here](presentation/tinypng2.png)

Further optimization could be achieved by reducing the resolution (size) of the images with GIMP or Photoshop.

The accessibility score didn't reach 100% due to the use of the .red class in the flow-text in the About Us section.

Here's a code snippet:

```html
<span class="cyphex">Cyphex</span><span class="cyphex red">Red Team</span>(<span class="cyphex red">CRT</span>)
```

The reason is the red-colored text on a black background. It could be changed easily but was intentionally left as is to make the About Us section a bit more visually interesting. The same text style was used for the hero text, but because of the different background in that section, it passed the test.

## Conclusion

This testing document showcases the commitment to ensuring website quality, functionality, and accessibility. It highlights the focus on optimizing performance and ensuring cross-browser compatibility for a seamless user experience. 

---
