# Dubya Home Solutions Landing Page - Maintenance & Customization Guide

Welcome! This comprehensive guide will help you maintain, update, and customize the Dubya Home Solutions landing page. Whether you're updating text content, fixing links, or adding new pages, this guide breaks everything down into simple, manageable steps.

---

## Table of Contents

1. [Getting Started](#getting-started)
2. [Understanding the Page Structure](#understanding-the-page-structure)
3. [Updating Text Content](#updating-text-content)
4. [Modifying Tailwind CSS Classes](#modifying-tailwind-css-classes)
5. [Fixing and Managing Links](#fixing-and-managing-links)
6. [Creating and Linking Privacy & Terms Pages](#creating-and-linking-privacy--terms-pages)
7. [Customizing Colors and Styling](#customizing-colors-and-styling)
8. [Troubleshooting Common Issues](#troubleshooting-common-issues)

---

## Getting Started

### What You'll Need

- A text editor (we recommend **Visual Studio Code**, which is free)
- The `index.html` file from the Dubya Home Solutions project
- Basic understanding of HTML tags (don't worry—we'll explain everything!)

### How to Open and Edit Files

1. **Open Visual Studio Code** (or your preferred text editor)
2. **Open the index.html file**: Go to `File > Open File` and select your `index.html`
3. **Make your changes** by following the specific instructions below
4. **Save your file**: Press `Ctrl+S` (Windows) or `Cmd+S` (Mac)
5. **View your changes**: Open the file in your web browser to see updates in real-time

---

## Understanding the Page Structure

Before making changes, let's understand how this landing page is organized. The page is divided into clear sections:

### Main Sections of the Landing Page

```
1. HEADER & NAVIGATION (sticky at top)
   ├── Logo with "Dubya" text
   ├── Desktop navigation menu
   ├── Mobile menu (hamburger icon)
   └── "Get Estimate" button

2. HERO SECTION (large banner at top)
   ├── Main headline
   ├── Subheading
   ├── Description text
   ├── Call-to-action buttons
   └── Scroll indicator

3. FEATURES SECTION (#features)
   ├── Section heading
   ├── Three feature cards
   │   ├── Expert Craftsmanship
   │   ├── Reliable Service
   │   └── Local Expertise
   └── Each card has icon, title, description, and bullet points

4. BENEFITS SECTION (#benefits)
   ├── Section heading
   ├── Three benefit cards
   │   ├── Durable Protection
   │   ├── Clean Water
   │   └── Enhanced Security
   └── Each card has icon, title, description, and statistics

5. CTA SECTION (Call-to-Action)
   ├── Background image
   ├── Headline
   ├── Description
   └── Button to schedule consultation

6. TESTIMONIALS SECTION (#testimonials)
   ├── Section heading
   ├── Four customer testimonials
   │   ├── Customer name and location
   │   ├── Star rating
   │   └── Review text
   └── Customer initials in colored circles

7. ABOUT US SECTION (#about)
   ├── Heading
   ├── Two-column layout
   │   ├── Text content (left)
   │   └── Image (right)
   └── Company history and values

8. FAQ SECTION (#faq)
   ├── Section heading
   ├── Five expandable questions
   │   ├── Question text
   │   └── Answer text (hidden until clicked)
   └── Toggle icons

9. FINAL CTA SECTION
   ├── Headline
   ├── Description
   └── Button

10. FOOTER
    ├── Company info and social media
    ├── Quick links
    ├── Services links
    ├── Contact information
    ├── Legal links (Privacy, Terms, Blog)
    └── Copyright information
```

---

## Updating Text Content

Text content is the easiest part to update. Here's how to find and modify text throughout the page.

### 1. Updating the Header Logo Text

**Location**: Line ~30 in the header navigation

**Current Code**:
```html
<span class="text-2xl font-bold text-white hidden sm:inline">Dubya</span>
```

**How to Update**:
- Find the word "Dubya" inside the `<span>` tag
- Replace it with your company name
- Example: `<span class="text-2xl font-bold text-white hidden sm:inline">Your Company</span>`

**What These Classes Do**:
- `text-2xl` = Makes text larger (size 2 extra large)
- `font-bold` = Makes text bold/thick
- `text-white` = Makes text white
- `hidden sm:inline` = Hides on mobile, shows on small screens and up

---

### 2. Updating the Hero Section Headline

**Location**: Lines ~140-144 (inside the hero section)

**Current Code**:
```html
<h1 class="text-5xl sm:text-6xl lg:text-7xl font-bold tracking-tight mb-6 leading-tight">
    <span class="block text-white">Dubya Home</span>
    <span class="block gradient-primary bg-clip-text text-transparent">Solutions</span>
</h1>
```

**How to Update**:
1. First line (`Dubya Home`) - Replace with your first headline
2. Second line (`Solutions`) - Replace with your second headline (this one has the red gradient color)

**Example**:
```html
<h1 class="text-5xl sm:text-6xl lg:text-7xl font-bold tracking-tight mb-6 leading-tight">
    <span class="block text-white">Your Company</span>
    <span class="block gradient-primary bg-clip-text text-transparent">Name Here</span>
</h1>
```

**What These Classes Do**:
- `text-5xl sm:text-6xl lg:text-7xl` = Different sizes for different screen sizes
  - `text-5xl` = Regular screens
  - `sm:text-6xl` = Small screens and up
  - `lg:text-7xl` = Large screens and up
- `gradient-primary` = Red gradient color (defined in the `<style>` section)
- `bg-clip-text text-transparent` = Makes the gradient show through the text

---

### 3. Updating the Hero Section Subheading

**Location**: Lines ~147-149

**Current Code**:
```html
<p class="text-xl md:text-2xl text-gray-300 mb-8 font-medium leading-relaxed max-w-3xl mx-auto">
    Elevating Lowcountry Homes with Expert Care
</p>
```

**How to Update**:
- Replace the text "Elevating Lowcountry Homes with Expert Care" with your tagline
- Keep the HTML tags the same

**Example**:
```html
<p class="text-xl md:text-2xl text-gray-300 mb-8 font-medium leading-relaxed max-w-3xl mx-auto">
    Your New Tagline Goes Here
</p>
```

---

### 4. Updating Feature Cards

**Location**: Lines ~180-230 (three feature cards)

Each feature card has this structure:

```html
<div class="card-hover bg-gray-900 rounded-xl p-8 border border-gray-700 hover:border-red-500">
    <div class="w-16 h-16 rounded-xl gradient-primary flex items-center justify-center mb-6 shadow-lg">
        <!-- Icon SVG here -->
    </div>
    <h3 class="text-2xl font-bold mb-4">Expert Craftsmanship</h3>
    <p class="text-gray-300 leading-relaxed mb-4">
        Your description here...
    </p>
    <ul class="space-y-2 text-gray-400">
        <li class="flex items-center"><span class="text-yellow-400 mr-2">•</span> Bullet point 1</li>
        <li class="flex items-center"><span class="text-yellow-400 mr-2">•</span> Bullet point 2</li>
        <li class="flex items-center"><span class="text-yellow-400 mr-2">•</span> Bullet point 3</li>
    </ul>
</div>
```

**How to Update**:

**Step 1: Update the Title**
- Find: `<h3 class="text-2xl font-bold mb-4">Expert Craftsmanship</h3>`
- Replace: `Expert Craftsmanship` with your feature title

**Step 2: Update the Description**
- Find: `<p class="text-gray-300 leading-relaxed mb-4">Your description here...</p>`
- Replace the description text (keep the tags)

**Step 3: Update Bullet Points**
- Find each: `<li class="flex items-center"><span class="text-yellow-400 mr-2">•</span> Bullet point</li>`
- Replace: The text after `•` with your bullet point

**Example**:
```html
<h3 class="text-2xl font-bold mb-4">Quality Installation</h3>
<p class="text-gray-300 leading-relaxed mb-4">
    We provide top-notch installation services with attention to detail.
</p>
<ul class="space-y-2 text-gray-400">
    <li class="flex items-center"><span class="text-yellow-400 mr-2">•</span> Professional team</li>
    <li class="flex items-center"><span class="text-yellow-400 mr-2">•</span> Quality materials</li>
    <li class="flex items-center"><span class="text-yellow-400 mr-2">•</span> Warranty included</li>
</ul>
```

---

### 5. Updating Testimonials

**Location**: Lines ~430-530 (four testimonial cards)

Each testimonial has this structure:

```html
<div class="card-hover bg-gray-900 rounded-xl p-8 border border-gray-700 hover:border-red-500">
    <div class="flex items-center mb-4">
        <div class="flex-shrink-0">
            <div class="w-12 h-12 rounded-full bg-gradient-primary flex items-center justify-center text-white font-bold text-lg">MJ</div>
        </div>
        <div class="ml-4">
            <h3 class="text-lg font-bold">Margaret Johnson</h3>
            <p class="text-sm text-gray-400">Homeowner, Charleston</p>
        </div>
    </div>
    <!-- Star rating goes here -->
    <p class="text-gray-300 leading-relaxed">
        "Your testimonial text here..."
    </p>
</div>
```

**How to Update**:

**Step 1: Update Customer Initials**
- Find: `<div class="w-12 h-12 rounded-full bg-gradient-primary flex items-center justify-center text-white font-bold text-lg">MJ</div>`
- Replace: `MJ` with the customer's initials (e.g., `JD` for John Doe)

**Step 2: Update Customer Name**
- Find: `<h3 class="text-lg font-bold">Margaret Johnson</h3>`
- Replace: `Margaret Johnson` with the customer's name

**Step 3: Update Location**
- Find: `<p class="text-sm text-gray-400">Homeowner, Charleston</p>`
- Replace: `Homeowner, Charleston` with appropriate title and location

**Step 4: Update Testimonial Text**
- Find: `<p class="text-gray-300 leading-relaxed">"Your testimonial text here..."</p>`
- Replace the text (keep the quotation marks)

**Example**:
```html
<div class="w-12 h-12 rounded-full bg-gradient-primary flex items-center justify-center text-white font-bold text-lg">JD</div>

<h3 class="text-lg font-bold">John Davis</h3>
<p class="text-sm text-gray-400">Business Owner, Savannah</p>

<p class="text-gray-300 leading-relaxed">
    "Amazing service and incredible attention to detail. Highly recommend!"
</p>
```

---

### 6. Updating FAQ Questions and Answers

**Location**: Lines ~585-680 (five FAQ items)

Each FAQ item has this structure:

```html
<div class="faq-item bg-gray-900 rounded-xl border border-gray-700 overflow-hidden hover:border-red-500 transition-colors duration-300">
    <button class="faq-question w-full px-8 py-6 flex items-center justify-between cursor-pointer hover:bg-gray-800 transition-colors duration-300">
        <span class="text-lg font-bold text-white text-left">What areas do you serve?</span>
        <svg class="faq-icon w-6 h-6 text-red-500 flex-shrink-0 transition-transform duration-300" fill="none" stroke="currentColor" viewBox="0 0 24 24" stroke-width="1.5">
            <path stroke-linecap="round" stroke-linejoin="round" d="M19 14l-7 7m0 0l-7-7m7 7V3"></path>
        </svg>
    </button>
    <div class="faq-answer hidden px-8 pb-6 text-gray-300 border-t border-gray-700">
        <p class="leading-relaxed">
            Your answer text here...
        </p>
    </div>
</div>
```

**How to Update**:

**Step 1: Update the Question**
- Find: `<span class="text-lg font-bold text-white text-left">What areas do you serve?</span>`
- Replace: `What areas do you serve?` with your question

**Step 2: Update the Answer**
- Find: `<p class="leading-relaxed">Your answer text here...</p>`
- Replace the text (keep the tags)

**Example**:
```html
<span class="text-lg font-bold text-white text-left">Do you offer emergency services?</span>

<p class="leading-relaxed">
    Yes! We provide 24/7 emergency support for all our clients.
</p>
```

---

### 7. Updating Footer Text

**Location**: Lines ~710-800 (footer section)

**Company Description**:
- Find: `<p class="text-gray-400 leading-relaxed mb-6">Elevating Lowcountry homes with expert care, reliable service, and local expertise.</p>`
- Replace with your company description

**Copyright Year**:
- Find: `&copy; 2025 Dubya Home Solutions. All rights reserved.`
- Update the year and company name as needed

**Example**:
```html
<p class="text-gray-400 leading-relaxed mb-6">
    Your Company - Providing excellent service to the community since 2020.
</p>

<p class="text-gray-500 text-sm">
    &copy; 2025 Your Company Name. All rights reserved.
</p>
```

---

## Modifying Tailwind CSS Classes

Tailwind CSS uses utility classes to style elements. Here's how to understand and modify them without breaking the design.

### Understanding Tailwind Classes

Tailwind classes follow a pattern: `property-value`. Here are common ones used in this page:

| Class | What It Does | Examples |
|-------|-------------|----------|
| `text-white` | Text color | `text-white`, `text-gray-300`, `text-red-500` |
| `bg-gray-900` | Background color | `bg-gray-900`, `bg-red-600` |
| `p-8` | Padding (space inside) | `p-8`, `p-4`, `p-12` |
| `mb-6` | Margin bottom (space below) | `mb-6`, `mb-4`, `mb-12` |
| `text-2xl` | Font size | `text-lg`, `text-2xl`, `text-5xl` |
| `font-bold` | Font weight | `font-bold`, `font-medium` |
| `rounded-xl` | Rounded corners | `rounded-lg`, `rounded-xl` |
| `border` | Border | `border`, `border-gray-700` |
| `hover:bg-gray-800` | Hover effect | Changes on mouse over |
| `md:flex` | Responsive | Shows on medium screens and up |

### Common Responsive Breakpoints

These prefixes control how elements look on different screen sizes:

- **No prefix** = Mobile (small screens)
- **`sm:`** = Small screens (640px+)
- **`md:`** = Medium screens (768px+)
- **`lg:`** = Large screens (1024px+)
- **`xl:`** = Extra large screens (1280px+)

**Example**: `hidden md:flex`
- On mobile: Hidden
- On medium screens and larger: Displays as flex

### How to Change Colors

The page uses a color scheme with specific colors. Here's where to find and change them:

**Primary Colors Used**:
- Red/Coral: `#FF5A5F` (used for buttons and accents)
- Yellow/Gold: `#FFD166` (used for highlights)
- Dark Gray: `#1A1A1A`, `#2D2D2D` (used for backgrounds)
- Light Gray: `#E64A4F` (used for hover states)

**To Change Button Color**:

1. Find the button class: `btn-primary`
2. Look in the `<style>` section (lines ~20-80)
3. Find: 
```css
.btn-primary {
    background-color: #FF5A5F;
    transition: all 300ms ease-out;
}

.btn-primary:hover {
    background-color: #E64A4F;
    transform: scale(1.05);
    box-shadow: 0 20px 25px -5px rgba(255, 90, 95, 0.3);
}
```

4. Replace `#FF5A5F` with your desired color (use hex color codes)
5. Replace `#E64A4F` with a darker version for the hover effect

**Example - Changing to Blue**:
```css
.btn-primary {
    background-color: #0066CC;  /* Changed to blue */
    transition: all 300ms ease-out;
}

.btn-primary:hover {
    background-color: #0052A3;  /* Darker blue for hover */
    transform: scale(1.05);
    box-shadow: 0 20px 25px -5px rgba(0, 102, 204, 0.3);
}
```

### How to Change Text Colors

**To change all white text to a different color**:

Find the class and replace:
- `text-white` → `text-yellow-300` (changes text to yellow)
- `text-gray-300` → `text-gray-400` (changes to darker gray)

**Example**: Changing feature card titles from white to yellow
```html
<!-- Original -->
<h3 class="text-2xl font-bold mb-4">Expert Craftsmanship</h3>

<!-- Modified -->
<h3 class="text-2xl font-bold mb-4 text-yellow-400">Expert Craftsmanship</h3>
```

### How to Change Spacing

Tailwind uses a scale for spacing (4px increments):
- `p-2` = 8px padding
- `p-4` = 16px padding
- `p-6` = 24px padding
- `p-8` = 32px padding
- `p-12` = 48px padding

**To add more space inside a card**:
```html
<!-- Original -->
<div class="card-hover bg-gray-900 rounded-xl p-8 border border-gray-700">

<!-- More space inside -->
<div class="card-hover bg-gray-900 rounded-xl p-12 border border-gray-700">
```

### How to Change Rounded Corners

- `rounded-lg` = Slightly rounded
- `rounded-xl` = More rounded
- `rounded-full` = Completely circular

**Example**: Making buttons more rounded
```html
<!-- Original -->
<a href="#" class="btn-primary text-white px-6 py-2 rounded-lg font-bold">

<!-- More rounded -->
<a href="#" class="btn-primary text-white px-6 py-2 rounded-full font-bold">
```

### How to Change Sizes

**To make a heading larger**:
```html
<!-- Original -->
<h2 class="text-4xl md:text-5xl font-bold">Heading</h2>

<!-- Larger -->
<h2 class="text-5xl md:text-6xl font-bold">Heading</h2>
```

**To make buttons wider/taller**:
```html
<!-- Original -->
<a href="#" class="btn-primary text-white px-10 py-4 rounded-lg">

<!-- Wider and taller -->
<a href="#" class="btn-primary text-white px-16 py-6 rounded-lg">
```

- `px` = horizontal padding (left and right)
- `py` = vertical padding (top and bottom)

---

## Fixing and Managing Links

Links are crucial for navigation. Let's identify and fix all the links in your page.

### Understanding Link Structure

A basic link looks like this:
```html
<a href="destination-url">Link Text</a>
```

- `<a>` = Anchor tag (creates a link)
- `href` = Where the link goes
- `Link Text` = What users see and click

### All Links Currently in the Page

Here's a complete list of every link in the Dubya landing page and where to find them:

#### Navigation Links (Header)

**Location**: Lines ~30-50

```html
<a href="#features" class="text-gray-300 hover:text-white transition-colors duration-300 font-medium">Features</a>
<a href="#benefits" class="text-gray-300 hover:text-white transition-colors duration-300 font-medium">Benefits</a>
<a href="#testimonials" class="text-gray-300 hover:text-white transition-colors duration-300 font-medium">Testimonials</a>
<a href="#faq" class="text-gray-300 hover:text-white transition-colors duration-300 font-medium">FAQ</a>
<a href="#about" class="text-gray-300 hover:text-white transition-colors duration-300 font-medium">About</a>
```

**What They Do**: These links jump to different sections on the same page
- `#features` = Jumps to Features section
- `#benefits` = Jumps to Benefits section
- etc.

**These are working correctly** - no changes needed unless you rename the sections.

#### Call-to-Action Links (External)

**Location**: Multiple locations throughout the page (Lines ~60, ~155, ~320, ~750)

```html
<a href="https://dubyaseamlesssystems.com/get-estimate" class="btn-primary text-white px-6 py-2 rounded-lg font-bold text-sm">Get Estimate</a>
```

**What They Do**: These send users to an external website

**To Update**:
1. Find: `https://dubyaseamlesssystems.com/get-estimate`
2. Replace with: Your actual URL for the estimate form
3. Example: `https://yourwebsite.com/contact` or `https://yourwebsite.com/request-quote`

**All Locations to Update**:
- Line ~60: Desktop header button
- Line ~68: Mobile menu button
- Line ~155: Hero section main button
- Line ~160: Hero section secondary button
- Line ~320: CTA section button
- Line ~750: Final CTA button

**How to Update All at Once** (in most text editors):
1. Press `Ctrl+H` (Windows) or `Cmd+H` (Mac) to open Find & Replace
2. Find: `https://dubyaseamlesssystems.com/get-estimate`
3. Replace with: Your new URL
4. Click "Replace All"

---

### Footer Links

**Location**: Lines ~710-800

#### Quick Links (Left Column)

```html
<a href="#features" class="text-gray-400 hover:text-white transition-colors duration-300">Features</a>
<a href="#benefits" class="text-gray-400 hover:text-white transition-colors duration-300">Benefits</a>
<a href="#testimonials" class="text-gray-400 hover:text-white transition-colors duration-300">Testimonials</a>
<a href="#faq" class="text-gray-400 hover:text-white transition-colors duration-300">FAQ</a>
<a href="#about" class="text-gray-400 hover:text-white transition-colors duration-300">About Us</a>
```

**Status**: These are internal links (same page) - working correctly

#### Services Links (Middle Column)

```html
<a href="#" class="text-gray-400 hover:text-white transition-colors duration-300">Home Solutions</a>
<a href="#" class="text-gray-400 hover:text-white transition-colors duration-300">Expert Craftsmanship</a>
<a href="#" class="text-gray-400 hover:text-white transition-colors duration-300">Reliable Service</a>
<a href="#" class="text-gray-400 hover:text-white transition-colors duration-300">Local Expertise</a>
<a href="https://dubyaseamlesssystems.com/get-estimate" class="text-gray-400 hover:text-white transition-colors duration-300">Get Estimate</a>
```

**Status**: The first four links use `href="#"` which means they don't go anywhere
- **Option 1**: Leave as is (they won't break anything)
- **Option 2**: Update to point to service pages (if you create them)
- **Option 3**: Update to external URLs if you have separate service pages

**Example - If you have service pages**:
```html
<a href="home-solutions.html" class="text-gray-400 hover:text-white transition-colors duration-300">Home Solutions</a>
```

#### Contact Link

```html
<a href="mailto:info@dubyallc.com" class="text-gray-400 hover:text-white transition-colors duration-300 flex items-center">
    <svg class="w-5 h-5 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24" stroke-width="1.5">
        <path stroke-linecap="round" stroke-linejoin="round" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"></path>
    </svg>
    info@dubyallc.com
</a>
```

**To Update**:
1. Find: `info@dubyallc.com` (appears twice - in href and as text)
2. Replace with your email address

**Example**:
```html
<a href="mailto:youremail@company.com" class="text-gray-400 hover:text-white transition-colors duration-300 flex items-center">
    <svg class="w-5 h-5 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24" stroke-width="1.5">
        <path stroke-linecap="round" stroke-linejoin="round" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"></path>
    </svg>
    youremail@company.com
</a>
```

---

### Social Media Links

**Location**: Lines ~740-755

```html
<a href="#" class="w-10 h-10 rounded-lg bg-gray-800 hover:bg-red-600 flex items-center justify-center transition-colors duration-300" aria-label="Facebook">
    <i class="fab fa-facebook-f text-white"></i>
</a>
<a href="#" class="w-10 h-10 rounded-lg bg-gray-800 hover:bg-red-600 flex items-center justify-center transition-colors duration-300" aria-label="Instagram">
    <i class="fab fa-instagram text-white"></i>
</a>
<a href="#" class="w-10 h-10 rounded-lg bg-gray-800 hover:bg-red-600 flex items-center justify-center transition-colors duration-300" aria-label="Twitter">
    <i class="fab fa-twitter text-white"></i>
</a>
<a href="#" class="w-10 h-10 rounded-lg bg-gray-800 hover:bg-red-600 flex items-center justify-center transition-colors duration-300" aria-label="LinkedIn">
    <i class="fab fa-linkedin-in text-white"></i>
</a>
```

**Current Status**: All use `href="#"` - they don't go anywhere

**To Update**:

Replace each `href="#"` with your social media URLs:

```html
<!-- Facebook -->
<a href="https://facebook.com/yourpage" class="w-10 h-10 rounded-lg bg-gray-800 hover:bg-red-600 flex items-center justify-center transition-colors duration-300" aria-label="Facebook">
    <i class="fab fa-facebook-f text-white"></i>
</a>

<!-- Instagram -->
<a href="https://instagram.com/yourprofile" class="w-10 h-10 rounded-lg bg-gray-800 hover:bg-red-600 flex items-center justify-center transition-colors duration-300" aria-label="Instagram">
    <i class="fab fa-instagram text-white"></i>
</a>

<!-- Twitter -->
<a href="https://twitter.com/yourprofile" class="w-10 h-10 rounded-lg bg-gray-800 hover:bg-red-600 flex items-center justify-center transition-colors duration-300" aria-label="Twitter">
    <i class="fab fa-twitter text-white"></i>
</a>

<!-- LinkedIn -->
<a href="https://linkedin.com/company/yourcompany" class="w-10 h-10 rounded-lg bg-gray-800 hover:bg-red-600 flex items-center justify-center transition-colors duration-300" aria-label="LinkedIn">
    <i class="fab fa-linkedin-in text-white"></i>
</a>
```

---

### Legal Links (Privacy, Terms, Blog)

**Location**: Lines ~795-800

```html
<li><a href="privacy.html" class="text-gray-400 hover:text-white transition-colors duration-300 text-sm">Privacy Policy</a></li>
<li><a href="terms.html" class="text-gray-400 hover:text-white transition-colors duration-300 text-sm">Terms of Service</a></li>
<li><a href="blog.html" class="text-gray-400 hover:text-white transition-colors duration-300 text-sm">Blog</a></li>
```

**Current Status**: These point to local files (`privacy.html`, `terms.html`, `blog.html`)

**These files don't exist yet** - we'll create them in the next section.

---

## Creating and Linking Privacy & Terms Pages

Now let's create the Privacy Policy and Terms of Service pages and link them properly.

### Step 1: Create the Privacy Policy Page

**What to Do**:

1. Open your text editor (Visual Studio Code)
2. Create a new file: `File > New File`
3. Copy and paste the code below
4. Save as: `privacy.html` in the same folder as `index.html`

**Privacy Policy Template**:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Privacy Policy - Dubya Home Solutions">
    <title>Privacy Policy | Dubya Home Solutions</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            font-family: 'Inter', sans-serif;
        }
        
        html {
            scroll-behavior: smooth;
        }
        
        .gradient-primary {
            background: linear-gradient(135deg, #FF5A5F 0%, #FF7A7F 100%);
        }
    </style>
</head>
<body class="bg-gray-900 text-white">
    <!-- Header Navigation -->
    <header class="sticky top-0 z-50 bg-gray-900 bg-opacity-95 backdrop-blur-md border-b border-gray-800">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <nav class="flex items-center justify-between h-20">
                <div class="flex items-center space-x-2">
                    <div class="w-10 h-10 rounded-lg gradient-primary flex items-center justify-center">
                        <span class="text-white font-bold text-xl">D</span>
                    </div>
                    <a href="index.html" class="text-2xl font-bold text-white hidden sm:inline">Dubya</a>
                </div>
                <a href="index.html" class="text-gray-300 hover:text-white transition-colors duration-300 font-medium">Back to Home</a>
            </nav>
        </div>
    </header>

    <!-- Main Content -->
    <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 py-24">
        <h1 class="text-5xl font-bold mb-8">Privacy Policy</h1>
        
        <div class="prose prose-invert max-w-none space-y-8">
            <section>
                <h2 class="text-3xl font-bold mb-4 mt-8">Introduction</h2>
                <p class="text-gray-300 leading-relaxed">
                    Dubya Home Solutions ("we," "our," or "us") is committed to protecting your privacy. This Privacy Policy explains how we collect, use, disclose, and safeguard your information when you visit our website.
                </p>
            </section>

            <section>
                <h2 class="text-3xl font-bold mb-4 mt-8">Information We Collect</h2>
                <p class="text-gray-300 leading-relaxed">
                    We may collect information about you in a variety of ways. The information we may collect on the site includes:
                </p>
                <ul class="list-disc list-inside text-gray-300 space-y-2 ml-4">
                    <li>Personal identification information (name, email address, phone number, etc.)</li>
                    <li>Information about your home and service needs</li>
                    <li>Payment information</li>
                    <li>Usage data and browsing behavior</li>
                </ul>
            </section>

            <section>
                <h2 class="text-3xl font-bold mb-4 mt-8">How We Use Your Information</h2>
                <p class="text-gray-300 leading-relaxed">
                    We use the information we collect in the following ways:
                </p>
                <ul class="list-disc list-inside text-gray-300 space-y-2 ml-4">
                    <li>To provide and improve our services</li>
                    <li>To contact you about your service requests</li>
                    <li>To send promotional communications (with your consent)</li>
                    <li>To comply with legal obligations</li>
                </ul>
            </section>

            <section>
                <h2 class="text-3xl font-bold mb-4 mt-8">Data Security</h2>
                <p class="text-gray-300 leading-relaxed">
                    We implement appropriate technical and organizational measures to protect your personal information against unauthorized access, alteration, disclosure, or destruction.
                </p>
            </section>

            <section>
                <h2 class="text-3xl font-bold mb-4 mt-8">Contact Us</h2>
                <p class="text-gray-300 leading-relaxed">
                    If you have questions about this Privacy Policy, please contact us at:
                    <br><br>
                    <strong>Email:</strong> <a href="mailto:info@dubyallc.com" class="text-red-500 hover:text-red-400">info@dubyallc.com</a>
                </p>
            </section>

            <section>
                <p class="text-gray-400 text-sm mt-12 pt-8 border-t border-gray-700">
                    Last updated: 2025
                </p>
            </section>
        </div>
    </div>

    <!-- Footer -->
    <footer class="bg-gray-950 border-t border-gray-800 py-12 mt-24">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
            <p class="text-gray-500 text-sm">
                &copy; 2025 Dubya Home Solutions. All rights reserved.
            </p>
        </div>
    </footer>
</body>
</html>
```

---

### Step 2: Create the Terms of Service Page

**What to Do**:

1. Open your text editor
2. Create a new file: `File > New File`
3. Copy and paste the code below
4. Save as: `terms.html` in the same folder as `index.html`

**Terms of Service Template**:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Terms of Service - Dubya Home Solutions">
    <title>Terms of Service | Dubya Home Solutions</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            font-family: 'Inter', sans-serif;
        }
        
        html {
            scroll-behavior: smooth;
        }
        
        .gradient-primary {
            background: linear-gradient(135deg, #FF5A5F 0%, #FF7A7F 100%);
        }
    </style>
</head>
<body class="bg-gray-900 text-white">
    <!-- Header Navigation -->
    <header class="sticky top-0 z-50 bg-gray-900 bg-opacity-95 backdrop-blur-md border-b border-gray-800">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <nav class="flex items-center justify-between h-20">
                <div class="flex items-center space-x-2">
                    <div class="w-10 h-10 rounded-lg gradient-primary flex items-center justify-center">
                        <span class="text-white font-bold text-xl">D</span>
                    </div>
                    <a href="index.html" class="text-2xl font-bold text-white hidden sm:inline">Dubya</a>
                </div>
                <a href="index.html" class="text-gray-300 hover:text-white transition-colors duration-300 font-medium">Back to Home</a>
            </nav>
        </div>
    </header>

    <!-- Main Content -->
    <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 py-24">
        <h1 class="text-5xl font-bold mb-8">Terms of Service</h1>
        
        <div class="prose prose-invert max-w-none space-y-8">
            <section>
                <h2 class="text-3xl font-bold mb-4 mt-8">Agreement to Terms</h2>
                <p class="text-gray-300 leading-relaxed">
                    These Terms of Service constitute a legally binding agreement made between you ("User," "you," or "your") and Dubya Home Solutions ("Company," "we," "us," or "our"), concerning your access to and use of the website and all related applications, software, tools, and services provided by Company.
                </p>
            </section>

            <section>
                <h2 class="text-3xl font-bold mb-4 mt-8">Use License</h2>
                <p class="text-gray-300 leading-relaxed">
                    Permission is granted to temporarily download one copy of the materials (information or software) on Dubya Home Solutions' website for personal, non-commercial transitory viewing only. This is the grant of a license, not a transfer of title, and under this license you may not:
                </p>
                <ul class="list-disc list-inside text-gray-300 space-y-2 ml-4">
                    <li>Modify or copy the materials</li>
                    <li>Use the materials for any commercial purpose or for any public display</li>
                    <li>Attempt to decompile or reverse engineer any software</li>
                    <li>Remove any copyright or other proprietary notations from the materials</li>
                </ul>
            </section>

            <section>
                <h2 class="text-3xl font-bold mb-4 mt-8">Limitation of Liability</h2>
                <p class="text-gray-300 leading-relaxed">
                    In no event shall Dubya Home Solutions or its suppliers be liable for any damages (including, without limitation, damages for loss of data or profit, or due to business interruption) arising out of the use or inability to use the materials on Dubya Home Solutions' website.
                </p>
            </section>

            <section>
                <h2 class="text-3xl font-bold mb-4 mt-8">Accuracy of Materials</h2>
                <p class="text-gray-300 leading-relaxed">
                    The materials appearing on Dubya Home Solutions' website could include technical, typographical, or photographic errors. Dubya Home Solutions does not warrant that any of the materials on our website are accurate, complete, or current. We may make changes to the materials contained on our website at any time without notice.
                </p>
            </section>

            <section>
                <h2 class="text-3xl font-bold mb-4 mt-8">Links</h2>
                <p class="text-gray-300 leading-relaxed">
                    Dubya Home Solutions has not reviewed all of the sites linked to our website and is not responsible for the contents of any such linked site. The inclusion of any link does not imply endorsement by us of the site. Use of any such linked website is at the user's own risk.
                </p>
            </section>

            <section>
                <h2 class="text-3xl font-bold mb-4 mt-8">Modifications</h2>
                <p class="text-gray-300 leading-relaxed">
                    Dubya Home Solutions may revise these Terms of Service for our website at any time without notice. By using this website, you are agreeing to be bound by the then current version of these Terms of Service.
                </p>
            </section>

            <section>
                <h2 class="text-3xl font-bold mb-4 mt-8">Governing Law</h2>
                <p class="text-gray-300 leading-relaxed">
                    These Terms and Conditions of use and any dispute or claim arising out of, or relating to them, shall be governed by and construed in accordance with the laws of South Carolina, and you irrevocably submit to the exclusive jurisdiction of the courts located in that state.
                </p>
            </section>

            <section>
                <h2 class="text-3xl font-bold mb-4 mt-8">Contact Us</h2>
                <p class="text-gray-300 leading-relaxed">
                    If you have any questions about these Terms of Service, please contact us at:
                    <br><br>
                    <strong>Email:</strong> <a href="mailto:info@dubyallc.com" class="text-red-500 hover:text-red-400">info@dubyallc.com</a>
                </p>
            </section>

            <section>
                <p class="text-gray-400 text-sm mt-12 pt-8 border-t border-gray-700">
                    Last updated: 2025
                </p>
            </section>
        </div>
    </div>

    <!-- Footer -->
    <footer class="bg-gray-950 border-t border-gray-800 py-12 mt-24">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
            <p class="text-gray-500 text-sm">
                &copy; 2025 Dubya Home Solutions. All rights reserved.
            </p>
        </div>
    </footer>
</body>
</html>
```

---

### Step 3: Verify Links Are Working

**What to Check**:

1. Open `index.html` in your browser
2. Scroll to the footer
3. Look for the "Legal" section with links to Privacy Policy, Terms, and Blog
4. Click on "Privacy Policy" - it should open `privacy.html`
5. Click on "Terms of Service" - it should open `terms.html`
6. Click "Back to Home" on either page - should return to `index.html`

**If Links Don't Work**:

Make sure all three files are in the **same folder**:
```
your-project-folder/
├── index.html
├── privacy.html
├── terms.html
└── blog.html (optional)
```

---

### Step 4: Optional - Create a Blog Page

If you want to add a blog page, follow the same process:

1. Create a new file called `blog.html`
2. Use the same header and footer structure as privacy.html
3. Add your blog content in the middle section
4. Save in the same folder as index.html

The link in the footer already points to `blog.html`, so it will work automatically once you create the file.

---

## Customizing Colors and Styling

Let's look at how to change the overall color scheme of your site.

### Understanding the Color System

The page uses colors defined in the `<style>` section (lines ~20-80). Here are the main color definitions:

```css
.gradient-primary {
    background: linear-gradient(135deg, #FF5A5F 0%, #FF7A7F 100%);
}

.btn-primary {
    background-color: #FF5A5F;
}

.btn-primary:hover {
    background-color: #E64A4F;
}

.btn-secondary {
    background-color: #FFD166;
    color: #1A1A1A;
}

.btn-secondary:hover {
    background-color: #FFC843;
}
```

### Color Reference

Current colors used:
- **Primary Red**: `#FF5A5F` (main buttons, accents)
- **Dark Red**: `#E64A4F` (button hover state)
- **Yellow/Gold**: `#FFD166` (secondary buttons, highlights)
- **Darker Yellow**: `#FFC843` (yellow hover state)
- **Dark Gray**: `#1A1A1A`, `#2D2D2D` (backgrounds)

### How to Change the Primary Color

**Step 1**: Locate the style section (lines ~20-80)

**Step 2**: Find all instances of the primary color `#FF5A5F`

**Step 3**: Replace with your color

**Example - Changing from Red to Blue**:

```css
/* Original */
.gradient-primary {
    background: linear-gradient(135deg, #FF5A5F 0%, #FF7A7F 100%);
}

.btn-primary {
    background-color: #FF5A5F;
}

.btn-primary:hover {
    background-color: #E64A4F;
}

/* Changed to Blue */
.gradient-primary {
    background: linear-gradient(135deg, #0066CC 0%, #0099FF 100%);
}

.btn-primary {
    background-color: #0066CC;
}

.btn-primary:hover {
    background-color: #0052A3;
}
```

### How to Find Hex Color Codes

1. Go to **https://www.colorpicker.com/**
2. Choose your color
3. Copy the hex code (example: `#FF5A5F`)
4. Use it in your CSS

### Changing the Accent/Highlight Color

The yellow/gold color (`#FFD166`) is used for highlights and secondary buttons.

**To change it**:

```css
/* Original */
.btn-secondary {
    background-color: #FFD166;
    color: #1A1A1A;
}

.btn-secondary:hover {
    background-color: #FFC843;
}

/* Changed to Green */
.btn-secondary {
    background-color: #10B981;
    color: #FFFFFF;
}

.btn-secondary:hover {
    background-color: #059669;
}
```

### Changing Background Colors

The page uses gray backgrounds. To change them:

Find in the HTML:
- `bg-gray-900` = Very dark gray
- `bg-gray-800` = Dark gray
- `bg-gray-700` = Medium gray

Replace with:
- `bg-slate-900` = Slate color
- `bg-zinc-900` = Zinc color
- `bg-neutral-900` = Neutral color

Or use any Tailwind color:
- `bg-blue-900`
- `bg-green-900`
- `bg-purple-900`

**Example**:
```html
<!-- Original -->
<section class="py-24 bg-gray-900">

<!-- Changed to blue -->
<section class="py-24 bg-blue-900">
```

---

## Troubleshooting Common Issues

### Issue 1: Links Not Working

**Problem**: Clicking a link doesn't go anywhere

**Solutions**:

1. **Check the URL is correct**
   - Make sure `href="..."` has a valid URL
   - External links should start with `https://`
   - Local links should end with `.html`

2. **Check file names match exactly**
   - If link says `privacy.html`, the file must be named exactly `privacy.html` (case-sensitive on some systems)
   - Files must be in the same folder

3. **Fix anchor links**
   - `href="#features"` should match a section with `id="features"`
   - Check spelling and capitalization

**Example - Fixing a broken link**:
```html
<!-- Broken -->
<a href="privacyy.html">Privacy</a>  <!-- Typo in filename -->

<!-- Fixed -->
<a href="privacy.html">Privacy</a>
```

---

### Issue 2: Text Appears Cut Off or Overlapping

**Problem**: Text doesn't fit properly or overlaps with other elements

**Solutions**:

1. **Check padding and margins**
   - Add more padding with classes like `p-12` (instead of `p-8`)
   - Add margin below with `mb-8` (instead of `mb-4`)

2. **Check line breaks**
   - Make sure you're not accidentally removing `<br>` tags
   - Keep text inside proper `<p>` tags

**Example**:
```html
<!-- Before - text crowded -->
<div class="p-4 mb-2">
    <p>Your text here</p>
</div>

<!-- After - more space -->
<div class="p-8 mb-6">
    <p>Your text here</p>
</div>
```

---

### Issue 3: Colors Look Wrong

**Problem**: Colors don't display correctly after changes

**Solutions**:

1. **Hard refresh browser cache**
   - Press `Ctrl+Shift+R` (Windows) or `Cmd+Shift+R` (Mac)
   - This clears the browser's memory of the old colors

2. **Check hex color format**
   - Hex colors must start with `#` and have 6 characters
   - Example: `#FF5A5F` ✓
   - Example: `FF5A5F` ✗ (missing #)

3. **Verify CSS is saved**
   - Make sure you saved the file after making changes
   - Look for unsaved indicator (usually a dot) in your editor

---

### Issue 4: Mobile Menu Not Working

**Problem**: Hamburger menu doesn't open on mobile

**Solutions**:

1. **Check JavaScript is enabled**
   - The mobile menu uses JavaScript (lines ~850-900)
   - Make sure you didn't accidentally delete or modify the script

2. **Check screen size**
   - Mobile menu only shows on screens smaller than 768px
   - Try resizing your browser window to test

3. **Check for console errors**
   - Press `F12` to open Developer Tools
   - Look for red error messages
   - Fix any JavaScript errors

---

### Issue 5: Buttons Don't Respond to Clicks

**Problem**: Buttons appear but don't work

**Solutions**:

1. **Check href attribute**
   ```html
   <!-- Wrong - no href -->
   <a class="btn-primary">Click me</a>
   
   <!-- Correct -->
   <a href="https://example.com" class="btn-primary">Click me</a>
   ```

2. **Make sure it's an `<a>` tag**
   - Links must use `<a>` tags with `href`
   - If you want a button that looks like a link, use `<button>` with JavaScript

3. **Check for typos in URL**
   - Make sure URL is spelled correctly
   - Test by copying the URL directly into your browser

---

### Issue 6: Styling Changes Don't Appear

**Problem**: You changed CSS but the page looks the same

**Solutions**:

1. **Save the file**
   - Press `Ctrl+S` (Windows) or `Cmd+S` (Mac)
   - Look for the save indicator in your editor

2. **Refresh the browser**
   - Press `F5` or `Ctrl+R`
   - Or hard refresh: `Ctrl+Shift+R`

3. **Check you edited the right file**
   - Make sure you're editing `index.html`, not a backup
   - Check the file path in your editor

4. **Check for conflicting CSS**
   - If using Tailwind CSS, make sure you're using valid class names
   - Typos in class names won't work: `text-whiteee` ✗

---

### Issue 7: Page Layout Breaks on Mobile

**Problem**: Page looks wrong on phones or tablets

**Solutions**:

1. **Check responsive classes**
   - Mobile first: default classes apply to mobile
   - Add breakpoint prefixes for larger screens: `md:`, `lg:`, `xl:`
   - Example: `block md:flex` = block on mobile, flex on medium+ screens

2. **Check viewport meta tag**
   - Should be in `<head>`: `<meta name="viewport" content="width=device-width, initial-scale=1.0">`
   - Don't remove or modify this line

3. **Test on real devices**
   - Use browser DevTools (F12) to test different screen sizes
   - Or test on actual phone/tablet

---

### Issue 8: FAQ Accordion Not Expanding

**Problem**: FAQ questions don't expand to show answers

**Solutions**:

1. **Check JavaScript is present**
   - Lines ~850-900 contain the FAQ JavaScript
   - Make sure this code is still in the file

2. **Check HTML structure**
   - Each FAQ item needs: `.faq-item`, `.faq-question`, `.faq-answer`
   - Check you didn't accidentally modify these class names

3. **Check for JavaScript errors**
   - Press `F12` and look at Console tab
   - Fix any red error messages

---

### Issue 9: Images Not Loading

**Problem**: Images appear as broken icons

**Solutions**:

1. **Check image URLs**
   - If using external images (from Unsplash, etc.), check URL is correct
   - If using local images, make sure file exists in correct folder

2. **Check file paths**
   - Local images: `src="image-name.jpg"`
   - External images: `src="https://example.com/image.jpg"`

3. **Check image format**
   - Supported formats: `.jpg`, `.png`, `.gif`, `.webp`
   - Make sure file extension matches actual file type

---

### Issue 10: Form Not Submitting

**Problem**: Contact form or estimate form doesn't work

**Note**: The current page doesn't have a built-in form—it links to an external service (`https://dubyaseamlesssystems.com/get-estimate`)

**If you want to add a form**:

1. Use a form service like:
   - Formspree (https://formspree.io)
   - Netlify Forms
   - Your own backend

2. Create the form HTML:
```html
<form action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
    <input type="text" name="name" placeholder="Your Name" required>
    <input type="email" name="email" placeholder="Your Email" required>
    <textarea name="message" placeholder="Your Message" required></textarea>
    <button type="submit">Send</button>
</form>
```

3. Replace `YOUR_FORM_ID` with your actual form ID from the service

---

## Best Practices for Maintenance

### Regular Maintenance Checklist

**Monthly**:
- [ ] Test all links work correctly
- [ ] Check page loads quickly
- [ ] Verify contact information is current
- [ ] Review testimonials for accuracy

**Quarterly**:
- [ ] Update company information if changed
- [ ] Review and update service descriptions
- [ ] Check social media links work
- [ ] Update copyright year in footer

**Annually**:
- [ ] Review and update Privacy Policy
- [ ] Review and update Terms of Service
- [ ] Check for broken external links
- [ ] Consider design refresh if needed

### Backup Your Files

Before making major changes:

1. Create a backup folder
2. Copy all your HTML files into it
3. Label with date: `backup-2025-01-15`

This way, if something breaks, you can restore the original.

### Version Control (Optional)

If you're comfortable with it, use Git:

```bash
git init
git add .
git commit -m "Initial landing page"
git commit -m "Updated testimonials"
```

This tracks all changes and lets you revert if needed.

---

## Quick Reference Guide

### Common Changes and Where to Find Them

| Change Needed | Location | Line Numbers |
|---|---|---|
| Company name | Header, Footer | ~30, ~710 |
| Hero headline | Hero section | ~140-144 |
| Hero tagline | Hero section | ~147-149 |
| Feature titles | Features section | ~180-230 |
| Feature descriptions | Features section | ~180-230 |
| Testimonials | Testimonials section | ~430-530 |
| FAQ questions | FAQ section | ~585-680 |
| FAQ answers | FAQ section | ~585-680 |
| Contact email | Footer | ~795 |
| Social media links | Footer | ~740-755 |
| Button links | Throughout | ~60, ~155, ~320, ~750 |
| Colors | Style section | ~20-80 |

### Useful Tailwind Classes

```
Text Sizes:     text-sm, text-lg, text-xl, text-2xl, text-3xl, text-4xl, text-5xl
Text Colors:    text-white, text-gray-300, text-red-500, text-yellow-400
Background:     bg-gray-900, bg-gray-800, bg-red-600
Padding:        p-4, p-6, p-8, p-12
Margin:         m-4, mb-6, mt-8, mx-auto
Borders:        border, border-gray-700, rounded-lg, rounded-xl
Responsive:     sm:, md:, lg:, xl: (prefixes for screen sizes)
Display:        flex, block, hidden, grid
Hover:          hover:text-white, hover:bg-red-600
```

---

## Getting Help

### Resources

1. **Tailwind CSS Documentation**: https://tailwindcss.com/docs
2. **HTML Reference**: https://developer.mozilla.org/en-US/docs/Web/HTML
3. **CSS Reference**: https://developer.mozilla.org/en-US/docs/Web/CSS
4. **Color Picker**: https://www.colorpicker.com/
5. **Font Awesome Icons**: https://fontawesome.com/

### Common Questions

**Q: Can I use this on multiple devices?**
A: Yes! All files are yours to use. Just keep them in the same folder.

**Q: Can I change the fonts?**
A: Yes! The page uses "Inter" font. To change it, modify line ~15 in the `<link>` tag and update the `font-family` in the `<style>` section.

**Q: Can I add more sections?**
A: Yes! Copy any existing section, update the content, and add an ID for navigation.

**Q: Is this mobile-friendly?**
A: Yes! The page uses responsive design. It automatically adjusts for phones, tablets, and desktops.

**Q: Can I add animations?**
A: Yes! Tailwind includes animation classes. Add `animate-bounce`, `animate-pulse`, etc. to elements.

---

## Conclusion

You now have a comprehensive guide to maintain and customize your Dubya Home Solutions landing page. Remember:

1. **Always save your changes** (`Ctrl+S` or `Cmd+S`)
2. **Hard refresh the browser** (`Ctrl+Shift+R`) to see changes
3. **Keep all files in the same folder**
4. **Test on mobile devices** to ensure responsive design works
5. **Back up your files** before making major changes

Good luck with your website! If you need further assistance, refer back to this guide or consult the resources listed above.

---

**Last Updated**: 2025
**Document Version**: 1.0