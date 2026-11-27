04. Webflow Classes, Selectors, and Styling Fundamentals

1. Introduction

Webflow uses a class-based styling system to control the appearance and behavior of website elements.

Instead of manually styling every element individually, developers can create reusable classes and apply them to multiple elements.

Understanding classes, selectors, inheritance, and CSS cascading is essential for building consistent, maintainable, and scalable websites.

2. What Are Classes in Webflow?

A Class is a reusable styling identifier assigned to one or more HTML elements.

When a class is created and styled in Webflow, the same styling can be applied to multiple elements throughout a website.

Example:

<div class="card">
    <h2>Webflow Learning</h2>
    <p>Explore visual web development.</p>
</div>

<div class="card">
    <h2>CMS Fundamentals</h2>
    <p>Learn dynamic content management.</p>
</div>

Both elements use the same "card" class and therefore share its styling.

Benefits of Classes

- Reuse styles across multiple elements.
- Maintain consistent website designs.
- Reduce repetitive styling work.
- Simplify website maintenance.
- Improve development efficiency.

Practical use: Create a class named "card" and apply it to multiple Div Blocks.

3. Understanding Different Selectors

A selector identifies which HTML elements should receive particular CSS styles.

Webflow provides several ways to select and style elements.

3.1 Class Selector

A class selector targets all elements assigned to a particular class.

CSS syntax:

.card {
    background-color: white;
    padding: 20px;
    border-radius: 12px;
}

The period (".") represents a class selector.

Use case: Apply the same card design to multiple sections or elements.

3.2 Tag Selector

A tag selector targets all HTML elements of a particular type.

Example:

h1 {
    font-size: 40px;
    font-weight: 700;
}

p {
    line-height: 1.6;
}

In Webflow, tag selectors can be used to establish default styling for HTML elements throughout the site.

Use case: Maintain consistent default typography for headings and paragraphs.

3.3 ID Selector

An ID selector targets an element with a specific HTML ID.

Example:

<section id="hero">
    <h1>Welcome to Webflow</h1>
</section>

CSS:

#hero {
    min-height: 500px;
    background-color: lightblue;
}

The hash ("#") represents an ID selector.

Important: IDs should be unique within a webpage. They are useful for identifying specific elements, anchor links, and custom functionality.

3.4 Combo Classes

A Combo Class extends an existing class with additional styling.

For example:

<div class="button primary">Primary Button</div>
<div class="button secondary">Secondary Button</div>

CSS:

.button {
    padding: 12px 24px;
    border-radius: 8px;
}

.button.primary {
    background-color: blue;
    color: white;
}

.button.secondary {
    background-color: gray;
    color: white;
}

Here:

- "button" is the base class.
- "primary" and "secondary" are additional classes.
- Both variations inherit the shared button styling.

Use case: Create different variations of the same component without duplicating its entire styling configuration.

4. Understanding the CSS Cascade

The CSS Cascade determines which styles are applied when multiple CSS rules target the same element.

The browser considers several factors, including:

1. Origin and importance of CSS declarations.
2. Selector specificity.
3. Source order when competing declarations have equal priority.

Example

p {
    color: black;
}

.description {
    color: blue;
}

HTML:

<p class="description">Learning Webflow.</p>

The paragraph appears blue because the class selector has greater specificity than the tag selector.

Selector Specificity

For common author CSS selectors, specificity follows this general order:

Selector| Example| Specificity
Element| "p"| Low
Class| ".card"| Medium
ID| "#hero"| High
Inline style| "style="color:red""| Higher than normal selector rules

Note: This is a simplified comparison. CSS cascade layers, importance, and other rules can affect the final result.

5. Understanding Style Inheritance

Inheritance allows certain CSS properties to pass from parent elements to their children.

For example:

body {
    font-family: Arial, sans-serif;
    color: black;
}

Text elements inside the Body generally inherit these properties unless their own styles override them.

Common Inherited Properties

- Color
- Font family
- Font size
- Font weight
- Line height
- Text alignment

Common Non-Inherited Properties

- Margin
- Padding
- Border
- Width
- Height
- Background color

Practical use: Apply typography styles to a parent element and observe how its child elements inherit them.

6. Understanding Pseudo-Classes and Element States

Pseudo-classes allow developers to style elements according to their current state or position.

In Webflow, states can be configured through the Style Selector.

Common states include:

State| Purpose
None| Default element appearance
Hover| Appearance when the pointer is over an element
Pressed| Appearance while an element is being activated
Focus| Appearance when an element receives focus
Visited| Appearance of an already visited link

Example: Hover Effect

.button {
    background-color: blue;
    color: white;
    transition: background-color 0.3s ease;
}

.button:hover {
    background-color: darkblue;
}

When the user moves the pointer over the button, its background changes.

Practical use: Create a hover effect for a button or navigation link using Webflow's Style Panel.

7. Understanding Webflow Style Reusability

A well-organized styling system helps maintain consistency across an entire website.

Consider a website with multiple sections:

Website
│
├── Navbar
│   └── .container
│
├── Hero Section
│   └── .container
│       ├── .heading-primary
│       └── .button-primary
│
├── Services Section
│   └── .container
│       ├── .card
│       ├── .card
│       └── .card
│
└── Footer
    └── .container

The same classes can be reused wherever the same design pattern is needed.

Recommended Naming Practices

Use meaningful, descriptive, and consistent class names.

Recommended| Avoid
"hero-section"| "box1"
"heading-primary"| "text2"
"button-primary"| "blue-button"
"service-card"| "div-block-4"
"footer-container"| "container-new"

Avoid unnecessary duplicate classes and excessive one-off styling.

8. Hands-on Practical Exercises

Task 1: Create Reusable Classes

1. Create three Div Blocks.
2. Assign the same class named "card" to all three.
3. Apply background color and padding.
4. Add different headings and paragraphs.
5. Observe how all three elements share the same styling.

Task 2: Experiment with Combo Classes

1. Create a class named "button".
2. Add two buttons using that class.
3. Apply a Combo Class named "primary" to the first.
4. Apply another Combo Class named "secondary" to the second.
5. Customize their backgrounds and text colors.
6. Verify that shared styles remain consistent.

Task 3: Explore Tag Selectors

1. Add multiple Heading and Paragraph elements.
2. Select the Heading HTML tag.
3. Apply a default font family and size.
4. Select the Paragraph HTML tag.
5. Configure its typography.
6. Observe the impact on other elements using those tags.

Task 4: Experiment with Inheritance

1. Add a parent Div Block.
2. Place multiple text elements inside it.
3. Apply font family and text color to the parent.
4. Observe the child elements.
5. Override the color on one child.
6. Compare inherited and explicitly assigned styles.

Task 5: Create Interactive States

1. Add a Button.
2. Assign the class "button-primary".
3. Configure its default appearance.
4. Switch to the Hover state.
5. Change its background color.
6. Add a transition.
7. Preview and test the interaction.

9. Key Takeaways

- Classes provide reusable styling across multiple elements.
- Tag selectors establish default styling for HTML elements.
- ID selectors target specific elements.
- Combo Classes extend existing classes with additional styling.
- CSS specificity helps determine which competing styles apply.
- Inheritance passes selected properties from parent elements to children.
- Pseudo-classes allow styling based on element states.
- Consistent class naming improves website maintainability.

10. Practice Status

- [ ] Created and applied reusable classes.
- [ ] Explored Tag Selectors.
- [ ] Understood ID Selectors.
- [ ] Created Combo Classes.
- [ ] Understood CSS Cascade and Specificity.
- [ ] Experimented with Style Inheritance.
- [ ] Created Hover and Focus states.
- [ ] Practiced reusable styling patterns.

---

Next Topic: Understanding Webflow Units, Sizing, and Spacing Systems
