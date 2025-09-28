# Django Template Inheritance Guide

## Overview
This project now uses Django template inheritance to reduce code duplication and make it easy to create new pages with consistent styling and navigation.

## Template Structure

### Base Template (`templates/base.html`)
The base template contains all the common elements that appear on every page:
- HTML structure and meta tags
- CSS and JavaScript includes
- Sidebar navigation
- Header with user profile
- Common JavaScript functionality

### Child Templates
Child templates extend the base template and only contain page-specific content.

## Available Blocks

### 1. `{% block title %}`
Sets the page title in the browser tab.
```html
{% block title %}Page Name | Tip Top{% endblock %}
```

### 2. `{% block page_title %}`
Sets the header content (main heading and subtitle).
```html
{% block page_title %}
<h1>Page Title</h1>
<p>Page description or subtitle</p>
{% endblock %}
```

### 3. `{% block content %}`
Contains the main page content.
```html
{% block content %}
<!-- Your page content here -->
<div class="container">
    <h2>Welcome to the page</h2>
    <p>This is the main content area.</p>
</div>
{% endblock %}
```

### 4. `{% block extra_css %}`
For additional CSS specific to the page.
```html
{% block extra_css %}
<style>
    .custom-class {
        color: var(--primary);
    }
</style>
{% endblock %}
```

### 5. `{% block extra_js %}`
For additional JavaScript specific to the page.
```html
{% block extra_js %}
<script>
    // Page-specific JavaScript
    console.log('Page loaded!');
</script>
{% endblock %}
```

## How to Create a New Page

### Step 1: Create Template File
Create a new HTML file in the `templates/` directory.

### Step 2: Extend Base Template
```html
{% extends 'base.html' %}
```

### Step 3: Override Required Blocks
```html
{% extends 'base.html' %}

{% block title %}New Page | Tip Top{% endblock %}

{% block page_title %}
<h1><i class="fas fa-icon text-primary"></i> New Page</h1>
<p>Description of your new page</p>
{% endblock %}

{% block content %}
<!-- Your page content here -->
<div class="card">
    <div class="card-header">
        <h3>Welcome</h3>
    </div>
    <div class="card-body">
        <p>This is your new page content.</p>
    </div>
</div>
{% endblock %}
```

## Example Templates

### Dashboard (`templates/dashboard.html`)
- Extends base template
- Contains dashboard-specific content (cards, charts, activity)
- Includes chart initialization JavaScript

### Advertisements (`templates/ads/ads_list.html`)
- Extends base template
- Contains ads listing
- Includes custom CSS for Bootstrap compatibility

### Example Page (`templates/example_page.html`)
- Demonstrates template inheritance
- Shows how to use all available blocks
- Includes documentation and examples

## Benefits

### ✅ **Code Reusability**
- No more copying HTML structure
- Consistent navigation across all pages
- Easy to maintain common elements

### ✅ **Easy Maintenance**
- Update header/sidebar in one place
- Consistent styling across all pages
- Centralized JavaScript functionality

### ✅ **Quick Development**
- Create new pages in minutes
- Focus on content, not structure
- Consistent user experience

### ✅ **Scalability**
- Easy to add new pages
- Maintains consistency as project grows
- Professional development workflow

## Best Practices

### 1. **Always Extend Base Template**
```html
{% extends 'base.html' %}
```

### 2. **Use Semantic Block Names**
- `title` for page title
- `page_title` for header content
- `content` for main content
- `extra_css` for additional styles
- `extra_js` for additional scripts

### 3. **Keep Content Focused**
- Only include page-specific content
- Let base template handle common elements
- Use blocks for customization

### 4. **Consistent Styling**
- Use CSS variables from base template
- Maintain the sky blue and purple color scheme
- Follow existing design patterns

## CSS Variables Available

The base template provides these CSS variables for consistent styling:
- `--primary`: Steel Blue (#4682B4)
- `--secondary`: Slate Blue (#6A5ACD)
- `--accent`: Indigo (#4B0082)
- `--text-color`: Text color
- `--card-bg`: Card background
- `--sidebar-bg`: Sidebar background

## Navigation

The sidebar navigation is automatically included and includes:
- Dashboard
- Wallet
- Surveys
- Games
- Watch Ads
- Billing
- Transactions
- Redeem

## Future Development

When adding new pages:
1. Create the template extending `base.html`
2. Override the necessary blocks
3. Add any page-specific CSS/JavaScript
4. Update your Django views to render the template

This system makes it easy to maintain a professional, consistent website as your project grows!
