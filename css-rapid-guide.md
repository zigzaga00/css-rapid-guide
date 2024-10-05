## **CSS Rapid Guide | From Basics to Advanced**

Welcome to our CSS guide, where we'll take you on a journey from the fundamentals to advanced techniques.

CSS, or Cascading Style Sheets, is a core tool for web developers, allowing you to bring visual appeal and structure to your web pages. Whether you're designing simple layouts or intricate user interfaces, CSS provides the flexibility and control to transform your projects.

In this guide, we will:

- Start with **CSS Basics**, where you'll learn how to add CSS to your project, understand key concepts like rules, declarations, selectors, and how CSS works behind the scenes with specificity and inheritance.
- Progress to more **Advanced Features**, such as responsive design, CSS animations, transitions, grid layouts, flexbox, and media queries to enhance your designs across different screen sizes and devices.
- Explore **Practical Examples** throughout, using real-world code snippets to solidify your understanding.
- Build an **Example Frontend for a Tea-Selling Business**, focusing on crafting a beautiful, modern user interface that not only looks attractive but also enhances the user experience. Along the way, we’ll demonstrate how CSS can be used to create visually engaging layouts, style components, and make web pages more interactive.

With plenty of code examples, tips, and hands-on practice, you’ll gain a deep understanding of how to use CSS to style your web projects effectively.

>[!IMPORTANT]
>Reading these notes is obviously a good start point with css, but to get the most out of this journey we recommend you use an IDE such as [visual studio code](https://code.visualstudio.com/) to code along and develop the example project

### **CSS Basics**

CSS (Cascading Style Sheets) is a powerful tool for enhancing the look and feel of web projects. This section will introduce the fundamentals of CSS, covering how to add CSS, rules and declarations, selectors, the cascade, specificity, inheritance, combinators, and more. By the end, you'll have a solid foundation to make your projects visually appealing.

#### **1. Different Ways to Add CSS to a Project**

There are three main ways to apply CSS to a web project:

1. **Inline CSS**  
   CSS can be applied directly to an HTML element using the `style` attribute.
   ```html
   <p style="color: blue;">This is a blue paragraph.</p>
   ```
>[!NOTE]
>Inline CSS is not generally recommended since with larger projects it becomes very difficult to manage and understand the styling

2. **Internal CSS**  
   CSS is written inside a `<style>` tag within the `<head>` section of an HTML document.
   ```html
   <head>
       <style>
           p {
               color: blue;
           }
       </style>
   </head>
   ```

3. **External CSS**  
   CSS is written in a separate `.css` file and linked to the HTML document using the `<link>` tag.
   ```html
   <head>
       <link rel="stylesheet" href="styles.css">
   </head>
   ```
>[!TIP]
>We tend to favor *external* css files since they can be easily reused in different projects and once they have been loaded the browser can *cache* them rather than needing to keep reloading them

---

#### **2. Rules and Declarations**

A CSS rule consists of a **selector** and a **declaration block**.  
Example:
```css
p {
    color: blue;
    font-size: 16px;
}
```
- The **selector** (`p`) targets the element you want to style.
- The **declaration block** (inside the `{}`) contains **declarations**.  
   Each declaration consists of a **property** and a **value**, separated by a colon (`:`).

In the example above:
- `color` is a property, and `blue` is the value.
- `font-size` is a property, and `16px` is the value.

>[!TIP]
>We can see this in a simple way | the **selector** is *what* to style whilst the **declaration** is *how* to style it

---

#### **3. Applying Colors and Fonts**

To style text, you can change colors and fonts.  

- **Applying Color:**
  ```css
  body {
      background-color: #f0f0f0;
      color: #333;
  }
  ```

- **Applying Font-Family:**  
  CSS allows you to apply different fonts. You can either use web-safe fonts or import custom fonts from sources like Google Fonts.

  **Using Google Fonts:**
  1. Go to [Google Fonts](https://fonts.google.com/).
  2. Choose a font, then copy the provided `<link>` tag.
  3. Add it to the `<head>` of your HTML document.
  
  ```html
  <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
  ```

  4. Apply the font in your CSS:
  ```css
  body {
      font-family: 'Roboto', sans-serif;
  }
  ```

---

#### **4. Selectors**

CSS selectors target elements in the HTML to apply styles. There are several types of selectors:

- **Element Selector**: Targets a specific HTML element.
  ```css
  h1 {
      color: red;
  }
  ```

- **Class Selector**: Targets elements with a specific class. A period (`.`) is used before the class name.
  ```css
  .highlight {
      background-color: yellow;
  }
  ```

- **ID Selector**: Targets an element with a specific ID. An ID is unique to a single element, and a hash (`#`) is used before the ID name.
  ```css
  #main-title {
      font-size: 24px;
  }
  ```

- **Attribute Selector**: Targets elements based on attributes.
  ```css
  input[type="text"] {
      border: 1px solid #ccc;
  }
  ```

- **Universal Selector**: Targets all elements.
  ```css
  * {
      margin: 0;
      padding: 0;
  }
  ```

---

#### **5. Understanding the Cascade and Specificity**

- **The Cascade**: In CSS multiple *rules* can apply to one *element* This is the *cascade* CSS uses a "cascading" logic, meaning rules are applied based on their order and importance. If multiple rules apply to an element, the rule that comes last takes precedence, unless overridden by specificity or importance.

- **Specificity**: Different selectors have different levels of importance.
  - ID selectors are more specific than class selectors.
  - Class selectors are more specific than element selectors.
  - Inline styles have the highest specificity.

  **Example of Specificity Order:**
  ```css
  p {
      color: blue; /* Least specific */
  }
  .text {
      color: green; /* More specific */
  }
  #main {
      color: red; /* Most specific */
  }
  ```

>[!TIP]
>We can simply see **cascade** as the idea that multiple *rules* can apply to one *element* and **specifity** as being the way css deals with conflicts which occur when there is more than one rule affecting one element

---

#### **6. Understanding Inheritance**

Certain CSS properties are inherited from parent elements. For example, properties like `color`, `font-family`, and `line-height` are inherited.

**Example of Inheritance:**
```html
<div style="color: red;">
    <p>This text will be red.</p>
</div>
```
In the above example, the paragraph inherits the red color from the parent `div`.

---

#### **7. Using Combinators**

Combinators describe the relationship between selectors.

- **Adjacent Sibling (`+`)**: Targets an element that directly follows another element.
  ```css
  h1 + p {
      margin-top: 0;
  }
  ```

- **General Sibling (`~`)**: Targets all elements that are siblings of a specified element.
  ```css
  h1 ~ p {
      color: gray;
  }
  ```

- **Child (`>`)**: Targets direct child elements.
  ```css
  div > p {
      font-weight: bold;
  }
  ```

- **Descendant (space)**: Targets all elements inside another element.
  ```css
  div p {
      color: green;
  }
  ```

---

#### **8. Summary of Properties and Selectors**

- **Properties**: You can style elements by changing properties such as `color`, `font-size`, `background`, `margin`, `padding`, etc.
  
- **Selectors**: Use various types of selectors (element, class, ID, attribute, universal) to apply styles to specific parts of your HTML.

---

#### **9. Quick Review**

- CSS can be applied inline, internally, or externally.
- A CSS rule consists of a selector and declarations (property and value pairs).
- You can change colors and fonts using properties like `color` and `font-family`.
- Selectors allow you to target elements in different ways, including by class, ID, and attributes.
- The cascade, specificity, and inheritance govern how CSS rules are applied.
- Combinators help define relationships between elements for more precise styling.

--- 

By mastering these basics, you're well on your way to creating visually appealing web projects! We will next look at the start of our tea business website...

---

### **ZZT Project**

We first of all need some basic *html* to style.

```html=
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>ZZT</title>
    <link rel="icon" href="favicon.ico" type="image/x-icon">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Anton&display=swap" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100..900;1,100..900&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="main.css">
</head>

<body>
    <main>
        <section id="product-overview">
            <h1>Top Tea From ZZ</h1>
        </section>
        <section id="plans">
            <h1 class="section-title">Choose Your Plan</h1>
            <p>
                Pick a Plan which Suits You!
            </p>
        </section>
    </main>
</body>

</html>
```

>[!NOTE]
>We have included a *favicon* to make it look better - if you are not using one then just omit the *link* to it

---

Now we can start to style it using the *external* css file called *main.css* which we have linked to in the *head* section of our *html*

```css=
body {
    font-family: 'Montserrat', sans-serif;
}

#product-overview {
    background: #ff1b68;
}

.section-title {
    color: #2ddf5c;
}

#product-overview h1 {
    color: white;
    font-family: 'Anton', sans-serif;
}
```

![zzt1](/images/1.png)

---

Let us now break down this CSS code piece by piece, referring to the basic concepts covered in our basics section.

#### 1. **Styling the Body**
```css
body {
    font-family: 'Montserrat', sans-serif;
}
```
- **Selector**: `body` is an **element selector** that targets the entire HTML document's body.
- **Property & Value**: 
  - `font-family: 'Montserrat', sans-serif;` sets the font for all the text inside the body. Here, the custom font **'Montserrat'** is being applied.
  - The `sans-serif` is a fallback font in case the browser cannot load **Montserrat**.
  
This line ensures that the font used across the entire webpage has a modern, clean look. The use of **Google Fonts** for 'Montserrat' provides a custom style, demonstrating how to include external fonts as discussed earlier.

---

#### 2. **Styling the Product Overview Section**
```css
#product-overview {
    background: #ff1b68;
}
```
- **Selector**: `#product-overview` is an **ID selector**. It applies styles to the element with the ID `product-overview`.
  - The `#` symbol indicates that this is an ID selector, which has a **higher specificity** than class or element selectors.

- **Property & Value**: 
  - `background: #ff1b68;` sets the background color of this section to **#ff1b68**, a vibrant pink.
  
This section highlights the concept of **specificity** and shows how we can style specific sections (like product overview) with unique designs, in this case, a colorful background.

---

#### 3. **Styling the Section Title**
```css
.section-title {
    color: #2ddf5c;
}
```
- **Selector**: `.section-title` is a **class selector**. It applies styles to any element that has the class `section-title`.
  - The `.` symbol denotes a class selector, which is **less specific than an ID selector**.
  
- **Property & Value**: 
  - `color: #2ddf5c;` changes the text color to **#2ddf5c**, a bright green.
  
This applies the green color to text elements with the class `section-title`, emphasizing the use of **classes** to style multiple elements that share a common purpose (e.g., section headers).

---

#### 4. **Styling the Heading in Product Overview**
```css
#product-overview h1 {
    color: white;
    font-family: 'Anton', sans-serif;
}
```
- **Selector**: `#product-overview h1` is a **descendant selector**, which targets any `<h1>` element inside the `#product-overview` section.
  - This uses the **descendant combinator** to apply styles to the `<h1>` tag only if it’s within the element with the ID `product-overview`.

- **Properties & Values**:
  - `color: white;` sets the text color to **white**, ensuring it stands out against the pink background.
  - `font-family: 'Anton', sans-serif;` changes the font for the `<h1>` header to **Anton**, a bold and impactful custom font from Google Fonts, with a fallback to `sans-serif`.

This part demonstrates how **combinators** work by targeting specific child elements (`h1`) within a parent element (`#product-overview`), allowing for precise styling control.

---

### **Summary of Concepts**
- **Selectors**: The code uses **element**, **ID**, **class**, and **descendant** selectors to apply styles at various levels of specificity.
- **Font-Family**: Google Fonts are used to enhance typography by importing custom fonts ('Montserrat' and 'Anton').
- **Colors**: Text and background colors are applied using **color** and **background** properties, with hex color codes for precise styling.
- **Specificity**: The use of ID and class selectors highlights how specificity affects which styles get applied when there are multiple rules.
- **Combinators**: The `#product-overview h1` example demonstrates the **descendant combinator**, allowing styles to target child elements within a specific parent.

This start point styling our tea selling website sets up a styled HTML document with a visually distinct product overview section and customizable text headers, laying the foundations for our future development.
