# Fortify Landing Page - Maintenance & Customization Guide

A comprehensive guide for maintaining, updating, and customizing the Fortify backup solution landing page.

---

## Table of Contents

1. [Quick Start Overview](#quick-start-overview)
2. [Understanding the Page Structure](#understanding-the-page-structure)
3. [Section 1: Updating Text and Tailwind CSS Classes](#section-1-updating-text-and-tailwind-css-classes)
4. [Section 2: Fixing Broken Links](#section-2-fixing-broken-links)
5. [Section 3: Linking Privacy and Terms Pages](#section-3-linking-privacy-and-terms-pages)
6. [Common Customization Tasks](#common-customization-tasks)
7. [Troubleshooting Guide](#troubleshooting-guide)

---

## Quick Start Overview

The Fortify landing page is built with:
- **HTML**: The structure and content
- **Tailwind CSS**: A utility-first CSS framework for styling and responsive design
- **Font Awesome**: Icons (the symbols and graphics you see)
- **Vanilla JavaScript**: Interactive features like the mobile menu and FAQ accordion

**No special tools are needed!** You can edit this file with any text editor (Notepad, VS Code, Sublime Text, etc.).

### File Structure You'll Need
```
your-project-folder/
├── index.html (main landing page)
├── privacy.html (create this file)
├── terms.html (create this file)
└── blog.html (already referenced in footer)
```

---

## Understanding the Page Structure

Before making changes, let's understand how the page is organized:

### Main Sections (Top to Bottom)

| Section | Purpose | Location in Code |
|---------|---------|------------------|
| **Header Navigation** | Menu bar at top | Lines 1-50 |
| **Hero Section** | Main headline and call-to-action | Lines 51-110 |
| **Features Section** | 5 feature cards with descriptions | Lines 111-220 |
| **Benefits Section** | 3 detailed benefit areas | Lines 221-380 |
| **CTA Section** | Large call-to-action banner | Lines 381-410 |
| **About Section** | Company information | Lines 411-460 |
| **Testimonials Section** | Customer reviews | Lines 461-530 |
| **FAQ Section** | Frequently asked questions | Lines 531-650 |
| **Footer** | Links and contact info | Lines 651-750 |

### Key CSS Classes You'll See Repeatedly

```html
<!-- Large heading -->
<h1 class="text-4xl md:text-5xl lg:text-6xl font-bold">

<!-- Medium heading -->
<h2 class="text-3xl md:text-4xl lg:text-5xl font-bold">

<!-- Buttons -->
<a class="bg-gradient-to-r from-blue-500 to-purple-600 text-white px-8 py-4 rounded-lg">

<!-- Cards/Boxes -->
<div class="bg-white rounded-xl shadow-md p-8 border border-gray-100">

<!-- Responsive grid -->
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
```

**Understanding Responsive Classes:**
- `grid-cols-1` = 1 column on mobile
- `md:grid-cols-2` = 2 columns on medium screens (tablets)
- `lg:grid-cols-3` = 3 columns on large screens (desktops)

---

## Section 1: Updating Text and Tailwind CSS Classes

### 1.1 Updating Text Content

#### **Location 1: Header Logo Text**

**Current Code (Lines 23-26):**
```html
<div class="flex items-center space-x-2">
    <div class="w-10 h-10 bg-gradient-to-br from-blue-500 to-purple-600 rounded-lg flex items-center justify-center">
        <i class="fas fa-shield-alt text-white text-lg"></i>
    </div>
    <span class="text-2xl font-bold gradient-text">Fortify</span>
</div>
```

**To Change "Fortify" to Your Company Name:**
1. Find the text `Fortify` in the `<span>` tag
2. Replace it with your company name
3. Example: `<span class="text-2xl font-bold gradient-text">MyBackup</span>`

**What the Classes Mean:**
- `text-2xl` = Font size (2 times extra large)
- `font-bold` = Makes text bold
- `gradient-text` = Applies blue-to-purple gradient effect (defined in `<style>` section)

---

#### **Location 2: Hero Section Main Headline**

**Current Code (Lines 74-79):**
```html
<h1 class="text-4xl md:text-5xl lg:text-6xl font-bold text-gray-900 leading-tight tracking-tight mb-6">
    Fortify Your World: The <span class="gradient-text">Unbreakable</span> Backup Solution
</h1>
```

**To Update the Headline:**
1. Find this `<h1>` tag in your editor
2. Replace the text while keeping the HTML tags
3. Keep the `<span class="gradient-text">` tags around words you want highlighted in blue-purple

**Example of a Custom Headline:**
```html
<h1 class="text-4xl md:text-5xl lg:text-6xl font-bold text-gray-900 leading-tight tracking-tight mb-6">
    Secure Your Data: The <span class="gradient-text">Unbreakable</span> Protection
</h1>
```

**Understanding the Classes:**
- `text-4xl` → `text-5xl` → `text-6xl` = Font gets bigger on larger screens
- `leading-tight` = Reduces space between lines
- `tracking-tight` = Reduces space between letters
- `mb-6` = Margin bottom (space below the heading)

---

#### **Location 3: Hero Section Description**

**Current Code (Lines 80-85):**
```html
<p class="text-lg md:text-xl text-gray-700 leading-relaxed mb-8">
    From life's precious memories to critical business files – safeguard everything that matters with military-grade encryption, intelligent redundancy, and enterprise-level reliability. Your data deserves protection that never compromises.
</p>
```

**To Update This Text:**
1. Find this `<p>` tag
2. Replace the text between `>` and `</p>`
3. Keep all the class names the same

**Example:**
```html
<p class="text-lg md:text-xl text-gray-700 leading-relaxed mb-8">
    Protect your business with our enterprise-grade backup solution. Automatic recovery, zero data loss, and compliance built-in.
</p>
```

**Class Explanations:**
- `text-lg` → `text-xl` = Text size increases on medium screens
- `text-gray-700` = Dark gray color (900=darkest, 100=lightest)
- `leading-relaxed` = Comfortable spacing between lines
- `mb-8` = Margin bottom (8 units of space)

---

#### **Location 4: Features Section Titles and Descriptions**

**Current Code (Lines 148-165) - Example: First Feature Card:**
```html
<div class="card-hover bg-white rounded-xl shadow-md p-8 border border-gray-100 hover:shadow-xl">
    <div class="w-16 h-16 bg-gradient-to-br from-blue-400 to-blue-600 rounded-lg flex items-center justify-center mb-6 feature-icon">
        <i class="fas fa-lock text-white text-2xl"></i>
    </div>
    <h3 class="text-2xl font-bold text-gray-900 mb-4">End-to-End Encryption</h3>
    <p class="text-gray-700 leading-relaxed mb-4">
        Every file you backup is protected with military-grade AES-256 encryption...
    </p>
    <ul class="space-y-2 text-gray-700">
        <li class="flex items-center"><i class="fas fa-check text-green-500 mr-3"></i>AES-256 Bit Encryption</li>
        <li class="flex items-center"><i class="fas fa-check text-green-500 mr-3"></i>Client-Side Encryption</li>
        <li class="flex items-center"><i class="fas fa-check text-green-500 mr-3"></i>Zero-Knowledge Architecture</li>
    </ul>
</div>
```

**To Customize a Feature Card:**

1. **Change the Title:**
   ```html
   <h3 class="text-2xl font-bold text-gray-900 mb-4">Your New Feature Title</h3>
   ```

2. **Change the Description:**
   ```html
   <p class="text-gray-700 leading-relaxed mb-4">
       Your new description text here...
   </p>
   ```

3. **Update the Bullet Points:**
   ```html
   <ul class="space-y-2 text-gray-700">
       <li class="flex items-center"><i class="fas fa-check text-green-500 mr-3"></i>Your first point</li>
       <li class="flex items-center"><i class="fas fa-check text-green-500 mr-3"></i>Your second point</li>
       <li class="flex items-center"><i class="fas fa-check text-green-500 mr-3"></i>Your third point</li>
   </ul>
   ```

4. **Change the Icon:** (Optional - requires Font Awesome knowledge)
   - Current: `<i class="fas fa-lock text-white text-2xl"></i>` (lock icon)
   - Other options: `fa-shield-alt`, `fa-globe`, `fa-certificate`, `fa-sync`, `fa-undo-alt`
   - Replace `fa-lock` with your chosen icon

---

#### **Location 5: Section Headings**

**Current Code (Lines 119-127) - Features Section Header:**
```html
<div class="text-center mb-16">
    <h2 class="text-3xl md:text-4xl lg:text-5xl font-bold text-gray-900 mb-4 tracking-tight">
        Powerful Features Built for Protection
    </h2>
    <p class="text-lg text-gray-600 max-w-2xl mx-auto">
        Comprehensive backup capabilities designed to meet the most demanding security and compliance requirements
    </p>
</div>
```

**To Update Section Headings:**
1. Find the `<h2>` tag for the section you want to change
2. Replace the text inside
3. Update the subtitle in the `<p>` tag below it

**All Section Heading Locations:**
- Features: Line 121
- Benefits: Line 234
- About: Line 413
- Testimonials: Line 463
- FAQ: Line 533

---

### 1.2 Modifying Tailwind CSS Classes

#### **Understanding Tailwind Class Structure**

Tailwind uses a pattern: `property-value`

**Common Properties:**
- `text-` = Font size (text-sm, text-lg, text-2xl, text-6xl)
- `bg-` = Background color (bg-white, bg-blue-500, bg-gray-900)
- `text-` = Text color (text-gray-700, text-white, text-blue-600)
- `p-` = Padding inside (p-4, p-8, p-12)
- `m-` = Margin outside (mb-6, mt-4, mx-8)
- `rounded-` = Corner roundness (rounded-lg, rounded-xl, rounded-full)
- `shadow-` = Drop shadow (shadow-md, shadow-lg, shadow-xl)
- `border-` = Border styling (border-2, border-gray-100)

---

#### **Example 1: Making Text Larger**

**Current:**
```html
<p class="text-lg text-gray-700">Your text here</p>
```

**Sizes Available:** `text-sm`, `text-base`, `text-lg`, `text-xl`, `text-2xl`, `text-3xl`, `text-4xl`, `text-5xl`, `text-6xl`

**Make it Larger:**
```html
<p class="text-2xl text-gray-700">Your text here</p>
```

---

#### **Example 2: Changing Colors**

**Text Color Options:**
- Gray: `text-gray-100` (light) to `text-gray-900` (dark)
- Blue: `text-blue-500`, `text-blue-600`, `text-blue-700`
- Purple: `text-purple-500`, `text-purple-600`
- Green: `text-green-500`, `text-green-600`
- Red: `text-red-500`, `text-red-600`

**Current (gray text):**
```html
<p class="text-lg text-gray-700">Your text here</p>
```

**Change to Blue:**
```html
<p class="text-lg text-blue-600">Your text here</p>
```

**Background Color Options:**
- `bg-white`, `bg-gray-50`, `bg-gray-900`
- `bg-blue-500`, `bg-purple-600`, `bg-green-500`

**Current (white background):**
```html
<div class="bg-white rounded-xl shadow-md p-8">
```

**Change to Light Gray:**
```html
<div class="bg-gray-50 rounded-xl shadow-md p-8">
```

---

#### **Example 3: Adjusting Spacing (Padding & Margin)**

**Padding (inside space):**
- `p-4` = Small padding
- `p-8` = Medium padding
- `p-12` = Large padding

**Margin (outside space):**
- `mb-4` = Space below (margin-bottom)
- `mt-6` = Space above (margin-top)
- `mx-auto` = Center horizontally

**Current (medium padding):**
```html
<div class="bg-white p-8 rounded-xl">
```

**Increase to Large Padding:**
```html
<div class="bg-white p-12 rounded-xl">
```

---

#### **Example 4: Changing Button Styles**

**Current Primary Button (Lines 86-89):**
```html
<a href="https://2link2.link/gbujust10bucks" class="bg-gradient-to-r from-blue-500 to-purple-600 text-white px-8 py-4 rounded-lg font-bold text-lg hover:shadow-xl button-primary text-center">
    Start Your Free Trial
</a>
```

**Class Breakdown:**
- `bg-gradient-to-r` = Gradient background (left to right)
- `from-blue-500 to-purple-600` = Gradient colors
- `text-white` = White text
- `px-8` = Horizontal padding (left & right)
- `py-4` = Vertical padding (top & bottom)
- `rounded-lg` = Slightly rounded corners
- `font-bold` = Bold text
- `text-lg` = Large text size
- `hover:shadow-xl` = Shadow appears on hover

**To Make Button Larger:**
```html
<a href="https://2link2.link/gbujust10bucks" class="bg-gradient-to-r from-blue-500 to-purple-600 text-white px-12 py-6 rounded-lg font-bold text-xl hover:shadow-xl button-primary text-center">
    Start Your Free Trial
</a>
```

Changes made:
- `px-8` → `px-12` (wider)
- `py-4` → `py-6` (taller)
- `text-lg` → `text-xl` (bigger text)

---

#### **Example 5: Modifying Card Styling**

**Current Feature Card (Line 148):**
```html
<div class="card-hover bg-white rounded-xl shadow-md p-8 border border-gray-100 hover:shadow-xl">
```

**To Add More Shadow:**
```html
<div class="card-hover bg-white rounded-xl shadow-lg p-8 border border-gray-100 hover:shadow-2xl">
```

Changes:
- `shadow-md` → `shadow-lg` (more shadow normally)
- `hover:shadow-xl` → `hover:shadow-2xl` (bigger shadow on hover)

**Shadow Options:** `shadow-sm`, `shadow-md`, `shadow-lg`, `shadow-xl`, `shadow-2xl`

---

#### **Example 6: Responsive Design Adjustments**

**Current Responsive Classes (Line 74):**
```html
<h1 class="text-4xl md:text-5xl lg:text-6xl font-bold text-gray-900">
```

**What This Means:**
- `text-4xl` = Default size on mobile
- `md:text-5xl` = Larger on medium screens (tablets)
- `lg:text-6xl` = Even larger on large screens (desktops)

**Breakdown of Screen Sizes:**
- **Mobile** = Default (no prefix)
- **Tablet** = `md:` prefix (medium)
- **Desktop** = `lg:` prefix (large)
- **Large Desktop** = `xl:` prefix (extra large)

**To Change Responsive Sizes:**
```html
<!-- Original -->
<h1 class="text-3xl md:text-4xl lg:text-5xl">

<!-- Make everything bigger -->
<h1 class="text-4xl md:text-5xl lg:text-6xl">

<!-- Make everything smaller -->
<h1 class="text-2xl md:text-3xl lg:text-4xl">
```

---

#### **Example 7: Grid Layout Adjustments**

**Current Features Grid (Line 129):**
```html
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
```

**What This Means:**
- `grid-cols-1` = 1 column on mobile
- `md:grid-cols-2` = 2 columns on tablets
- `lg:grid-cols-3` = 3 columns on desktops
- `gap-8` = Space between items

**To Change Grid Layout:**
```html
<!-- Show 4 items per row on desktop instead of 3 -->
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">

<!-- Increase gap between items -->
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-12">

<!-- Show 2 items on desktop instead of 3 -->
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-2 gap-8">
```

---

### 1.3 Common Text Updates Checklist

Use this checklist to find and update all the key text areas:

- [ ] **Company Name** (Header logo, Footer)
  - Line 26: `<span class="text-2xl font-bold gradient-text">Fortify</span>`
  - Line 689: Footer logo section

- [ ] **Hero Headline** (Line 74)
  - `<h1 class="text-4xl...">Fortify Your World...`

- [ ] **Hero Description** (Line 80)
  - `<p class="text-lg...">From life's precious memories...`

- [ ] **Hero CTA Button Text** (Line 86)
  - `Start Your Free Trial`

- [ ] **Features Section Title** (Line 121)
  - `Powerful Features Built for Protection`

- [ ] **Feature Cards** (Lines 148-220)
  - 5 feature cards with titles and descriptions

- [ ] **Benefits Section Titles** (Line 234)
  - `Transformative Benefits for Your Peace of Mind`

- [ ] **About Section** (Line 413)
  - Company story and statistics

- [ ] **Testimonials** (Line 463)
  - Customer quotes and names

- [ ] **FAQ Questions** (Line 533)
  - Frequently asked questions

- [ ] **Footer Text** (Line 651)
  - Company description and links

---

## Section 2: Fixing Broken Links

### 2.1 Understanding Links in This Landing Page

**What is a Link?**
A link is code that takes users to a different page or website. In HTML, links use the `<a>` tag:

```html
<a href="WHERE-TO-GO">LINK TEXT</a>
```

- `href` = The destination (URL or file path)
- Link text = What users see and click on

---

### 2.2 All Links Currently in the Page

**Let's find every link and what it does:**

#### **Navigation Menu Links (Header)**

**Location: Lines 31-37**

```html
<a href="#features" class="text-gray-700 hover:text-blue-600...">Features</a>
<a href="#benefits" class="text-gray-700 hover:text-blue-600...">Benefits</a>
<a href="#about" class="text-gray-700 hover:text-blue-600...">About</a>
<a href="#testimonials" class="text-gray-700 hover:text-blue-600...">Testimonials</a>
<a href="#faq" class="text-gray-700 hover:text-blue-600...">FAQ</a>
<a href="https://2link2.link/gbujust10bucks" class="bg-gradient-to-r...">Get Started</a>
```

**What These Do:**
- `href="#features"` = Jump to Features section (the `#` means same page)
- `href="#benefits"` = Jump to Benefits section
- `href="#about"` = Jump to About section
- `href="#testimonials"` = Jump to Testimonials section
- `href="#faq"` = Jump to FAQ section
- `href="https://2link2.link/gbujust10bucks"` = External link to signup page

**Status:** ✅ Internal navigation links work fine. The external signup link works if the URL is correct.

---

#### **Mobile Menu Links (Lines 44-50)**

```html
<a href="#features" class="text-gray-700 hover:text-blue-600...">Features</a>
<a href="#benefits" class="text-gray-700 hover:text-blue-600...">Benefits</a>
<a href="#about" class="text-gray-700 hover:text-blue-600...">About</a>
<a href="#testimonials" class="text-gray-700 hover:text-blue-600...">Testimonials</a>
<a href="#faq" class="text-gray-700 hover:text-blue-600...">FAQ</a>
<a href="https://2link2.link/gbujust10bucks" class="bg-gradient-to-r...">Get Started</a>
```

**Status:** ✅ Same as desktop menu - these are fine.

---

#### **Hero Section CTA Buttons (Lines 86-93)**

```html
<!-- Primary Button -->
<a href="https://2link2.link/gbujust10bucks" class="bg-gradient-to-r from-blue-500 to-purple-600...">
    Start Your Free Trial
</a>

<!-- Secondary Button -->
<button class="border-2 border-blue-500 text-blue-600...">
    Watch Demo
</button>
```

**Issues:**
- ✅ "Start Your Free Trial" - External link (working if URL is correct)
- ⚠️ "Watch Demo" - This is a `<button>`, not a link (needs JavaScript to work)

**To Fix the "Watch Demo" Button:**

If you want it to link somewhere, change it from `<button>` to `<a>`:

```html
<!-- OLD (doesn't work as a link) -->
<button class="border-2 border-blue-500 text-blue-600...">
    Watch Demo
</button>

<!-- NEW (works as a link) -->
<a href="https://your-demo-url.com" class="border-2 border-blue-500 text-blue-600 px-8 py-4 rounded-lg font-bold text-lg hover:bg-blue-50 transition-colors duration-300">
    Watch Demo
</a>
```

---

#### **CTA Section Buttons (Lines 394-402)**

```html
<!-- Primary Button -->
<a href="https://2link2.link/gbujust10bucks" class="bg-white text-blue-600...">
    Start Free Trial Now
</a>

<!-- Secondary Button -->
<button class="border-2 border-white text-white...">
    Schedule Demo
</button>
```

**Issues:**
- ✅ "Start Free Trial Now" - External link (working if URL is correct)
- ⚠️ "Schedule Demo" - Button without link (needs JavaScript)

**To Fix:**

```html
<!-- Change from button to link -->
<a href="https://your-demo-url.com" class="border-2 border-white text-white px-8 py-4 rounded-lg font-bold text-lg hover:bg-white hover:bg-opacity-10 transition-all duration-300">
    Schedule Demo
</a>
```

---

#### **Footer Links (Lines 651-720)**

**Product Links (Line 651):**
```html
<li><a href="#features" class="text-gray-400 hover:text-white...">Features</a></li>
<li><a href="#benefits" class="text-gray-400 hover:text-white...">Benefits</a></li>
<li><a href="#" class="text-gray-400 hover:text-white...">Pricing</a></li>
<li><a href="#" class="text-gray-400 hover:text-white...">Security</a></li>
<li><a href="#" class="text-gray-400 hover:text-white...">Integrations</a></li>
```

**Issues:**
- ✅ Features & Benefits link to sections (working)
- ❌ Pricing, Security, Integrations use `href="#"` (broken - goes nowhere)

**Company Links (Line 657):**
```html
<li><a href="#about" class="text-gray-400 hover:text-white...">About Us</a></li>
<li><a href="blog.html" class="text-gray-400 hover:text-white...">Blog</a></li>
<li><a href="#" class="text-gray-400 hover:text-white...">Careers</a></li>
<li><a href="#" class="text-gray-400 hover:text-white...">Contact</a></li>
<li><a href="#" class="text-gray-400 hover:text-white...">Press</a></li>
```

**Issues:**
- ✅ About Us links to section (working)
- ⚠️ Blog links to "blog.html" (needs this file to exist)
- ❌ Careers, Contact, Press use `href="#"` (broken)

**Legal Links (Line 663):**
```html
<li><a href="privacy.html" class="text-gray-400 hover:text-white...">Privacy Policy</a></li>
<li><a href="terms.html" class="text-gray-400 hover:text-white...">Terms of Service</a></li>
<li><a href="#" class="text-gray-400 hover:text-white...">Cookie Policy</a></li>
<li><a href="#" class="text-gray-400 hover:text-white...">DPA</a></li>
<li><a href="#" class="text-gray-400 hover:text-white...">Status Page</a></li>
```

**Issues:**
- ⚠️ Privacy Policy & Terms link to files (need to be created)
- ❌ Cookie Policy, DPA, Status Page use `href="#"` (broken)

**Social Media Links (Line 639):**
```html
<a href="#" class="w-10 h-10 bg-gray-800 rounded-lg flex items-center justify-center hover:bg-blue-600...">
    <i class="fab fa-facebook-f text-gray-300"></i>
</a>
<a href="#" class="w-10 h-10 bg-gray-800 rounded-lg flex items-center justify-center hover:bg-blue-400...">
    <i class="fab fa-twitter text-gray-300"></i>
</a>
<!-- ... more social links ... -->
```

**Issues:**
- ❌ All social media links use `href="#"` (broken)

**Email Link (Line 729):**
```html
<a href="mailto:rwcampbell2@gmail.com" class="hover:text-white transition-colors duration-300">
    rwcampbell2@gmail.com
</a>
```

**Status:** ✅ Working - opens email client when clicked

---

### 2.3 Step-by-Step: Fixing All Broken Links

#### **Step 1: Fix External Links (Signup/Demo URLs)**

These links currently point to: `https://2link2.link/gbujust10bucks`

**To Update:**

1. **Find all instances** (there are 4 of them):
   - Line 38: Navigation "Get Started"
   - Line 86: Hero "Start Your Free Trial"
   - Line 394: CTA section "Start Free Trial Now"
   - Line 50: Mobile menu "Get Started"

2. **Replace the URL:**
   ```html
   <!-- OLD -->
   <a href="https://2link2.link/gbujust10bucks">

   <!-- NEW - Replace with your actual signup URL -->
   <a href="https://your-company.com/signup">
   ```

3. **Example with a real URL:**
   ```html
   <!-- If using Stripe -->
   <a href="https://checkout.stripe.com/your-checkout-id">

   <!-- If using your own signup page -->
   <a href="https://mycompany.com/get-started">

   <!-- If using a form tool like Typeform -->
   <a href="https://form.typeform.com/to/YOUR_FORM_ID">
   ```

---

#### **Step 2: Fix the "Watch Demo" Button**

**Current Code (Line 90):**
```html
<button class="border-2 border-blue-500 text-blue-600 px-8 py-4 rounded-lg font-bold text-lg hover:bg-blue-50 transition-colors duration-300">
    Watch Demo
</button>
```

**Replace With:**
```html
<a href="https://your-demo-video-url.com" class="border-2 border-blue-500 text-blue-600 px-8 py-4 rounded-lg font-bold text-lg hover:bg-blue-50 transition-colors duration-300 inline-block">
    Watch Demo
</a>
```

**Examples of Demo URLs:**
```html
<!-- YouTube video -->
<a href="https://youtube.com/watch?v=YOUR_VIDEO_ID">

<!-- Vimeo video -->
<a href="https://vimeo.com/YOUR_VIDEO_ID">

<!-- Your own demo page -->
<a href="https://mycompany.com/demo">

<!-- Loom recording -->
<a href="https://loom.com/share/YOUR_SHARE_ID">
```

---

#### **Step 3: Fix the "Schedule Demo" Button**

**Current Code (Line 401):**
```html
<button class="border-2 border-white text-white px-8 py-4 rounded-lg font-bold text-lg hover:bg-white hover:bg-opacity-10 transition-all duration-300">
    Schedule Demo
</button>
```

**Replace With:**
```html
<a href="https://calendly.com/your-username" class="border-2 border-white text-white px-8 py-4 rounded-lg font-bold text-lg hover:bg-white hover:bg-opacity-10 transition-all duration-300 inline-block">
    Schedule Demo
</a>
```

**Examples of Scheduling URLs:**
```html
<!-- Calendly -->
<a href="https://calendly.com/your-username">

<!-- Acuity Scheduling -->
<a href="https://acuityscheduling.com/schedule.php?owner_id=YOUR_ID">

<!-- Cal.com -->
<a href="https://cal.com/your-username">

<!-- Your own booking page -->
<a href="https://mycompany.com/book-demo">
```

---

#### **Step 4: Fix Footer "Pricing" Link**

**Current Code (Line 652):**
```html
<li><a href="#" class="text-gray-400 hover:text-white transition-colors duration-300">Pricing</a></li>
```

**Replace With:**
```html
<li><a href="https://mycompany.com/pricing" class="text-gray-400 hover:text-white transition-colors duration-300">Pricing</a></li>
```

Or if you want to link to a section on the same page:
```html
<li><a href="#pricing" class="text-gray-400 hover:text-white transition-colors duration-300">Pricing</a></li>
```

---

#### **Step 5: Fix Footer "Security" Link**

**Current Code (Line 653):**
```html
<li><a href="#" class="text-gray-400 hover:text-white transition-colors duration-300">Security</a></li>
```

**Replace With:**
```html
<li><a href="https://mycompany.com/security" class="text-gray-400 hover:text-white transition-colors duration-300">Security</a></li>
```

---

#### **Step 6: Fix Footer "Integrations" Link**

**Current Code (Line 654):**
```html
<li><a href="#" class="text-gray-400 hover:text-white transition-colors duration-300">Integrations</a></li>
```

**Replace With:**
```html
<li><a href="https://mycompany.com/integrations" class="text-gray-400 hover:text-white transition-colors duration-300">Integrations</a></li>
```

---

#### **Step 7: Fix Footer "Careers" Link**

**Current Code (Line 658):**
```html
<li><a href="#" class="text-gray-400 hover:text-white transition-colors duration-300">Careers</a></li>
```

**Replace With:**
```html
<li><a href="https://mycompany.com/careers" class="text-gray-400 hover:text-white transition-colors duration-300">Careers</a></li>
```

---

#### **Step 8: Fix Footer "Contact" Link**

**Current Code (Line 659):**
```html
<li><a href="#" class="text-gray-400 hover:text-white transition-colors duration-300">Contact</a></li>
```

**Replace With:**
```html
<li><a href="https://mycompany.com/contact" class="text-gray-400 hover:text-white transition-colors duration-300">Contact</a></li>
```

---

#### **Step 9: Fix Footer "Press" Link**

**Current Code (Line 660):**
```html
<li><a href="#" class="text-gray-400 hover:text-white transition-colors duration-300">Press</a></li>
```

**Replace With:**
```html
<li><a href="https://mycompany.com/press" class="text-gray-400 hover:text-white transition-colors duration-300">Press</a></li>
```

---

#### **Step 10: Fix Footer "Cookie Policy" Link**

**Current Code (Line 665):**
```html
<li><a href="#" class="text-gray-400 hover:text-white transition-colors duration-300">Cookie Policy</a></li>
```

**Replace With:**
```html
<li><a href="cookie-policy.html" class="text-gray-400 hover:text-white transition-colors duration-300">Cookie Policy</a></li>
```

**You'll need to create:** `cookie-policy.html` file

---

#### **Step 11: Fix Footer "DPA" Link**

**Current Code (Line 666):**
```html
<li><a href="#" class="text-gray-400 hover:text-white transition-colors duration-300">DPA</a></li>
```

**Replace With:**
```html
<li><a href="dpa.html" class="text-gray-400 hover:text-white transition-colors duration-300">DPA</a></li>
```

**You'll need to create:** `dpa.html` file (Data Processing Agreement)

---

#### **Step 12: Fix Footer "Status Page" Link**

**Current Code (Line 667):**
```html
<li><a href="#" class="text-gray-400 hover:text-white transition-colors duration-300">Status Page</a></li>
```

**Replace With:**
```html
<li><a href="https://status.mycompany.com" class="text-gray-400 hover:text-white transition-colors duration-300">Status Page</a></li>
```

**Or use a service:**
```html
<li><a href="https://mycompany.statuspage.io" class="text-gray-400 hover:text-white transition-colors duration-300">Status Page</a></li>
```

---

#### **Step 13: Fix Social Media Links**

**Current Code (Lines 639-655):**
```html
<a href="#" class="w-10 h-10 bg-gray-800 rounded-lg flex items-center justify-center hover:bg-blue-600 transition-colors duration-300">
    <i class="fab fa-facebook-f text-gray-300"></i>
</a>
```

**Replace All Social Links:**

```html
<!-- Facebook -->
<a href="https://facebook.com/your-page" class="w-10 h-10 bg-gray-800 rounded-lg flex items-center justify-center hover:bg-blue-600 transition-colors duration-300">
    <i class="fab fa-facebook-f text-gray-300"></i>
</a>

<!-- Twitter -->
<a href="https://twitter.com/your-handle" class="w-10 h-10 bg-gray-800 rounded-lg flex items-center justify-center hover:bg-blue-400 transition-colors duration-300">
    <i class="fab fa-twitter text-gray-300"></i>
</a>

<!-- Instagram -->
<a href="https://instagram.com/your-handle" class="w-10 h-10 bg-gray-800 rounded-lg flex items-center justify-center hover:bg-pink-600 transition-colors duration-300">
    <i class="fab fa-instagram text-gray-300"></i>
</a>

<!-- LinkedIn -->
<a href="https://linkedin.com/company/your-company" class="w-10 h-10 bg-gray-800 rounded-lg flex items-center justify-center hover:bg-blue-700 transition-colors duration-300">
    <i class="fab fa-linkedin-in text-gray-300"></i>
</a>
```

---

#### **Step 14: Verify Blog Link Works**

**Current Code (Line 657):**
```html
<li><a href="blog.html" class="text-gray-400 hover:text-white transition-colors duration-300">Blog</a></li>
```

**This link is fine IF:**
- You have a file named `blog.html` in the same folder as `index.html`

**If you don't have a blog yet:**
```html
<!-- Option 1: Link to external blog -->
<li><a href="https://blog.mycompany.com" class="text-gray-400 hover:text-white transition-colors duration-300">Blog</a></li>

<!-- Option 2: Link to Medium -->
<li><a href="https://medium.com/@your-handle" class="text-gray-400 hover:text-white transition-colors duration-300">Blog</a></li>

<!-- Option 3: Link to Substack -->
<li><a href="https://your-newsletter.substack.com" class="text-gray-400 hover:text-white transition-colors duration-300">Blog</a></li>
```

---

### 2.4 Quick Reference: All Links to Update

**Print this checklist and update each one:**

| Link | Current Value | What to Replace With | Line |
|------|---------------|----------------------|------|
| Signup (Nav) | `https://2link2.link/gbujust10bucks` | Your signup URL | 38 |
| Signup (Hero) | `https://2link2.link/gbujust10bucks` | Your signup URL | 86 |
| Demo (Hero) | Button (broken) | Your demo URL | 90 |
| Signup (CTA) | `https://2link2.link/gbujust10bucks` | Your signup URL | 394 |
| Demo (CTA) | Button (broken) | Your demo URL | 401 |
| Signup (Mobile) | `https://2link2.link/gbujust10bucks` | Your signup URL | 50 |
| Pricing | `#` | Your pricing page URL | 652 |
| Security | `#` | Your security page URL | 653 |
| Integrations | `#` | Your integrations page URL | 654 |
| Careers | `#` | Your careers page URL | 658 |
| Contact | `#` | Your contact page URL | 659 |
| Press | `#` | Your press page URL | 660 |
| Cookie Policy | `#` | `cookie-policy.html` | 665 |
| DPA | `#` | `dpa.html` | 666 |
| Status Page | `#` | Your status page URL | 667 |
| Facebook | `#` | Your Facebook page | 639 |
| Twitter | `#` | Your Twitter profile | 645 |
| Instagram | `#` | Your Instagram profile | 651 |
| LinkedIn | `#` | Your LinkedIn company | 657 |

---

## Section 3: Linking Privacy and Terms Pages

### 3.1 Understanding What We're Creating

You need to create two new HTML files that link from your main landing page:
- `privacy.html` - Privacy Policy page
- `terms.html` - Terms of Service page

These are already linked in the footer of your landing page (Lines 664-665), but the files don't exist yet.

---

### 3.2 Current Footer Links (Already in Place)

**Location: Lines 664-665**

```html
<li><a href="privacy.html" class="text-gray-400 hover:text-white transition-colors duration-300">Privacy Policy</a></li>
<li><a href="terms.html" class="text-gray-400 hover:text-white transition-colors duration-300">Terms of Service</a></li>
```

**Good News:** The links are already set up! You just need to create the files.

---

### 3.3 Step-by-Step: Create Privacy Policy Page

#### **Step 1: Create a New File**

1. Open your text editor (Notepad, VS Code, Sublime Text, etc.)
2. Create a new file
3. Save it as `privacy.html` in the same folder as `index.html`

**Your folder structure should look like:**
```
your-project-folder/
├── index.html
├── privacy.html (create this)
├── terms.html (create this)
└── blog.html
```

---

#### **Step 2: Add Basic HTML Structure**

Copy and paste this into your new `privacy.html` file:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Privacy Policy for Fortify Backup Solutions">
    <title>Privacy Policy - Fortify</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        html {
            scroll-behavior: smooth;
        }
        
        .gradient-text {
            background: linear-gradient(135deg, #3B82F6 0%, #8B5CF6 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
    </style>
</head>
<body class="bg-white text-gray-900 font-sans">
    <!-- Header Navigation -->
    <header class="sticky top-0 z-50 bg-white shadow-md">
        <nav class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-4 flex justify-between items-center">
            <!-- Logo -->
            <div class="flex items-center space-x-2">
                <div class="w-10 h-10 bg-gradient-to-br from-blue-500 to-purple-600 rounded-lg flex items-center justify-center">
                    <i class="fas fa-shield-alt text-white text-lg"></i>
                </div>
                <a href="index.html" class="text-2xl font-bold gradient-text">Fortify</a>
            </div>

            <!-- Navigation Links -->
            <div class="hidden md:flex items-center space-x-8">
                <a href="index.html" class="text-gray-700 hover:text-blue-600 transition-colors duration-300 font-medium">Back to Home</a>
            </div>

            <!-- Mobile Menu Button -->
            <a href="index.html" class="md:hidden text-gray-700 hover:text-blue-600 transition-colors duration-300 font-medium">
                Back
            </a>
        </nav>
    </header>

    <!-- Main Content -->
    <main class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 py-20">
        <h1 class="text-4xl md:text-5xl font-bold text-gray-900 mb-8">Privacy Policy</h1>
        
        <div class="prose prose-lg text-gray-700 leading-relaxed space-y-8">
            <section>
                <h2 class="text-2xl font-bold text-gray-900 mb-4">1. Introduction</h2>
                <p>
                    Fortify Backup Solutions ("we," "us," "our," or "Company") is committed to protecting your privacy. This Privacy Policy explains how we collect, use, disclose, and safeguard your information when you visit our website and use our backup services.
                </p>
            </section>

            <section>
                <h2 class="text-2xl font-bold text-gray-900 mb-4">2. Information We Collect</h2>
                <p>
                    We collect information you provide directly to us, such as when you create an account, use our services, or contact us for support. This may include:
                </p>
                <ul class="list-disc list-inside space-y-2 ml-4">
                    <li>Name and email address</li>
                    <li>Payment information</li>
                    <li>Account preferences</li>
                    <li>Communications you send us</li>
                </ul>
            </section>

            <section>
                <h2 class="text-2xl font-bold text-gray-900 mb-4">3. How We Use Your Information</h2>
                <p>
                    We use the information we collect to:
                </p>
                <ul class="list-disc list-inside space-y-2 ml-4">
                    <li>Provide, maintain, and improve our services</li>
                    <li>Process transactions and send related information</li>
                    <li>Send technical notices and support messages</li>
                    <li>Respond to your comments and questions</li>
                    <li>Comply with legal obligations</li>
                </ul>
            </section>

            <section>
                <h2 class="text-2xl font-bold text-gray-900 mb-4">4. Data Security</h2>
                <p>
                    We implement appropriate technical and organizational measures to protect your personal information against unauthorized access, alteration, disclosure, or destruction. Your data is encrypted using military-grade AES-256 encryption.
                </p>
            </section>

            <section>
                <h2 class="text-2xl font-bold text-gray-900 mb-4">5. Your Rights</h2>
                <p>
                    Depending on your location, you may have certain rights regarding your personal information, including:
                </p>
                <ul class="list-disc list-inside space-y-2 ml-4">
                    <li>The right to access your personal information</li>
                    <li>The right to correct inaccurate information</li>
                    <li>The right to request deletion of your information</li>
                    <li>The right to data portability</li>
                </ul>
            </section>

            <section>
                <h2 class="text-2xl font-bold text-gray-900 mb-4">6. Contact Us</h2>
                <p>
                    If you have questions about this Privacy Policy or our privacy practices, please contact us at:
                </p>
                <p class="font-semibold">
                    Email: <a href="mailto:rwcampbell2@gmail.com" class="text-blue-600 hover:text-blue-700">rwcampbell2@gmail.com</a>
                </p>
            </section>

            <section>
                <p class="text-sm text-gray-600">
                    Last updated: January 2025
                </p>
            </section>
        </div>
    </main>

    <!-- Footer -->
    <footer class="bg-gray-900 text-gray-300 py-16 px-4 sm:px-6 lg:px-8 mt-20">
        <div class="max-w-7xl mx-auto">
            <div class="border-t border-gray-800 pt-8">
                <div class="flex flex-col md:flex-row justify-between items-center">
                    <p class="text-gray-400 mb-4 md:mb-0">
                        &copy; 2025 Fortify Backup Solutions. All rights reserved.
                    </p>
                    <div class="flex items-center space-x-2 text-gray-400">
                        <i class="fas fa-envelope mr-2"></i>
                        <a href="mailto:rwcampbell2@gmail.com" class="hover:text-white transition-colors duration-300">rwcampbell2@gmail.com</a>
                    </div>
                </div>
            </div>
        </div>
    </footer>
</body>
</html>
```

---

#### **Step 3: Customize the Privacy Policy**

The template above is a basic privacy policy. You should customize it with:

1. **Your Company Information:** Replace "Fortify Backup Solutions" with your company name
2. **Your Email:** Replace `rwcampbell2@gmail.com` with your email
3. **Your Privacy Practices:** Update each section to reflect your actual practices
4. **Your Data Collection:** Add/remove sections based on what you actually collect

**Key Sections to Update:**

```html
<!-- Change this -->
<h1 class="text-4xl md:text-5xl font-bold text-gray-900 mb-8">Privacy Policy</h1>

<!-- To this if needed -->
<h1 class="text-4xl md:text-5xl font-bold text-gray-900 mb-8">Fortify Privacy Policy</h1>
```

---

### 3.4 Step-by-Step: Create Terms of Service Page

#### **Step 1: Create a New File**

1. Open your text editor
2. Create a new file
3. Save it as `terms.html` in the same folder as `index.html`

---

#### **Step 2: Add Basic HTML Structure**

Copy and paste this into your new `terms.html` file:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Terms of Service for Fortify Backup Solutions">
    <title>Terms of Service - Fortify</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        html {
            scroll-behavior: smooth;
        }
        
        .gradient-text {
            background: linear-gradient(135deg, #3B82F6 0%, #8B5CF6 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
    </style>
</head>
<body class="bg-white text-gray-900 font-sans">
    <!-- Header Navigation -->
    <header class="sticky top-0 z-50 bg-white shadow-md">
        <nav class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-4 flex justify-between items-center">
            <!-- Logo -->
            <div class="flex items-center space-x-2">
                <div class="w-10 h-10 bg-gradient-to-br from-blue-500 to-purple-600 rounded-lg flex items-center justify-center">
                    <i class="fas fa-shield-alt text-white text-lg"></i>
                </div>
                <a href="index.html" class="text-2xl font-bold gradient-text">Fortify</a>
            </div>

            <!-- Navigation Links -->
            <div class="hidden md:flex items-center space-x-8">
                <a href="index.html" class="text-gray-700 hover:text-blue-600 transition-colors duration-300 font-medium">Back to Home</a>
            </div>

            <!-- Mobile Menu Button -->
            <a href="index.html" class="md:hidden text-gray-700 hover:text-blue-600 transition-colors duration-300 font-medium">
                Back
            </a>
        </nav>
    </header>

    <!-- Main Content -->
    <main class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 py-20">
        <h1 class="text-4xl md:text-5xl font-bold text-gray-900 mb-8">Terms of Service</h1>
        
        <div class="prose prose-lg text-gray-700 leading-relaxed space-y-8">
            <section>
                <h2 class="text-2xl font-bold text-gray-900 mb-4">1. Acceptance of Terms</h2>
                <p>
                    By accessing and using the Fortify Backup Solutions service, you accept and agree to be bound by the terms and provision of this agreement. If you do not agree to abide by the above, please do not use this service.
                </p>
            </section>

            <section>
                <h2 class="text-2xl font-bold text-gray-900 mb-4">2. Use License</h2>
                <p>
                    Permission is granted to temporarily download one copy of the materials (information or software) on Fortify's website for personal, non-commercial transitory viewing only. This is the grant of a license, not a transfer of title, and under this license you may not:
                </p>
                <ul class="list-disc list-inside space-y-2 ml-4">
                    <li>Modify or copy the materials</li>
                    <li>Use the materials for any commercial purpose or for any public display</li>
                    <li>Attempt to decompile or reverse engineer any software contained on the website</li>
                    <li>Remove any copyright or other proprietary notations from the materials</li>
                    <li>Transfer the materials to another person or "mirror" the materials on any other server</li>
                </ul>
            </section>

            <section>
                <h2 class="text-2xl font-bold text-gray-900 mb-4">3. Disclaimer</h2>
                <p>
                    The materials on Fortify's website are provided on an 'as is' basis. Fortify makes no warranties, expressed or implied, and hereby disclaims and negates all other warranties including, without limitation, implied warranties or conditions of merchantability, fitness for a particular purpose, or non-infringement of intellectual property or other violation of rights.
                </p>
            </section>

            <section>
                <h2 class="text-2xl font-bold text-gray-900 mb-4">4. Limitations</h2>
                <p>
                    In no event shall Fortify or its suppliers be liable for any damages (including, without limitation, damages for loss of data or profit, or due to business interruption) arising out of the use or inability to use the materials on Fortify's website, even if Fortify or a Fortify authorized representative has been notified orally or in writing of the possibility of such damage.
                </p>
            </section>

            <section>
                <h2 class="text-2xl font-bold text-gray-900 mb-4">5. Accuracy of Materials</h2>
                <p>
                    The materials appearing on Fortify's website could include technical, typographical, or photographic errors. Fortify does not warrant that any of the materials on its website are accurate, complete, or current. Fortify may make changes to the materials contained on its website at any time without notice.
                </p>
            </section>

            <section>
                <h2 class="text-2xl font-bold text-gray-900 mb-4">6. Links</h2>
                <p>
                    Fortify has not reviewed all of the sites linked to its website and is not responsible for the contents of any such linked site. The inclusion of any link does not imply endorsement by Fortify of the site. Use of any such linked website is at the user's own risk.
                </p>
            </section>

            <section>
                <h2 class="text-2xl font-bold text-gray-900 mb-4">7. Modifications</h2>
                <p>
                    Fortify may revise these terms of service for its website at any time without notice. By using this website, you are agreeing to be bound by the then current version of these terms of service.
                </p>
            </section>

            <section>
                <h2 class="text-2xl font-bold text-gray-900 mb-4">8. Governing Law</h2>
                <p>
                    These terms and conditions are governed by and construed in accordance with the laws of the jurisdiction in which Fortify operates, and you irrevocably submit to the exclusive jurisdiction of the courts in that location.
                </p>
            </section>

            <section>
                <h2 class="text-2xl font-bold text-gray-900 mb-4">9. Contact Us</h2>
                <p>
                    If you have any questions about these Terms of Service, please contact us at:
                </p>
                <p class="font-semibold">
                    Email: <a href="mailto:rwcampbell2@gmail.com" class="text-blue-600 hover:text-blue-700">rwcampbell2@gmail.com</a>
                </p>
            </section>

            <section>
                <p class="text-sm text-gray-600">
                    Last updated: January 2025
                </p>
            </section>
        </div>
    </main>

    <!-- Footer -->
    <footer class="bg-gray-900 text-gray-300 py-16 px-4 sm:px-6 lg:px-8 mt-20">
        <div class="max-w-7xl mx-auto">
            <div class="border-t border-gray-800 pt-8">
                <div class="flex flex-col md:flex-row justify-between items-center">
                    <p class="text-gray-400 mb-4 md:mb-0">
                        &copy; 2025 Fortify Backup Solutions. All rights reserved.
                    </p>
                    <div class="flex items-center space-x-2 text-gray-400">
                        <i class="fas fa-envelope mr-2"></i>
                        <a href="mailto:rwcampbell2@gmail.com" class="hover:text-white transition-colors duration-300">rwcampbell2@gmail.com</a>
                    </div>
                </div>
            </div>
        </div>
    </footer>
</body>
</html>
```

---

#### **Step 3: Customize the Terms of Service**

Update the template with:

1. **Your Company Information:** Replace "Fortify Backup Solutions" with your company name
2. **Your Email:** Replace `rwcampbell2@gmail.com` with your email
3. **Your Terms:** Update each section to reflect your actual terms
4. **Your Jurisdiction:** Update the "Governing Law" section with your jurisdiction

---

### 3.5 Verify the Links Work

After creating both files, test the links:

1. **Open your `index.html` in a browser**
2. **Scroll to the footer**
3. **Click on "Privacy Policy"** - Should open `privacy.html`
4. **Click on "Terms of Service"** - Should open `terms.html`
5. **On those pages, click "Back to Home"** - Should return to `index.html`

**If links don't work:**
- Make sure all three files (`index.html`, `privacy.html`, `terms.html`) are in the same folder
- Check that file names are spelled exactly right (lowercase, no spaces)
- Make sure you saved the files with `.html` extension

---

### 3.6 Optional: Add More Policy Pages

You can create additional policy pages using the same template:

#### **Cookie Policy (`cookie-policy.html`)**

Update the footer link from:
```html
<li><a href="#" class="text-gray-400 hover:text-white transition-colors duration-300">Cookie Policy</a></li>
```

To:
```html
<li><a href="cookie-policy.html" class="text-gray-400 hover:text-white transition-colors duration-300">Cookie Policy</a></li>
```

Then create `cookie-policy.html` using the same template structure.

---

#### **Data Processing Agreement (`dpa.html`)**

Update the footer link from:
```html
<li><a href="#" class="text-gray-400 hover:text-white transition-colors duration-300">DPA</a></li>
```

To:
```html
<li><a href="dpa.html" class="text-gray-400 hover:text-white transition-colors duration-300">DPA</a></li>
```

Then create `dpa.html` using the same template structure.

---

### 3.7 Checklist: Privacy & Terms Setup

- [ ] Created `privacy.html` file in same folder as `index.html`
- [ ] Created `terms.html` file in same folder as `index.html`
- [ ] Updated email addresses in both files (changed from `rwcampbell2@gmail.com`)
- [ ] Updated company name in both files (changed from "Fortify Backup Solutions")
- [ ] Updated content to match your actual policies
- [ ] Tested links from `index.html` to both policy pages
- [ ] Tested "Back to Home" links on policy pages
- [ ] Links in footer work correctly

---

## Common Customization Tasks

### Task 1: Change the Primary Color (Blue to Another Color)

The page uses blue (`#3B82F6`) and purple (`#8B5CF6`) as primary colors. To change them:

**Find all instances of these classes:**
- `from-blue-500` and `to-purple-600` (gradient)
- `bg-blue-500` (solid blue)
- `text-blue-600` (blue text)
- `hover:text-blue-600` (blue on hover)

**Color Options in Tailwind:**
- Red: `red-500`, `red-600`, `red-700`
- Green: `green-500`, `green-600`, `green-700`
- Orange: `orange-500`, `orange-600`, `orange-700`
- Pink: `pink-500`, `pink-600`, `pink-700`
- Indigo: `indigo-500`, `indigo-600`, `indigo-700`

**Example: Change from blue to green**

Original:
```html
<a class="bg-gradient-to-r from-blue-500 to-purple-600 text-white px-8 py-4 rounded-lg">
    Start Your Free Trial
</a>
```

Updated:
```html
<a class="bg-gradient-to-r from-green-500 to-emerald-600 text-white px-8 py-4 rounded-lg">
    Start Your Free Trial
</a>
```

---

### Task 2: Change the Hero Background

**Current Code (Line 62):**
```html
<section class="hero-gradient py-20 md:py-32 lg:py-40 px-4 sm:px-6 lg:px-8">
```

**The `hero-gradient` class is defined in the `<style>` section (Lines 17-20):**
```css
.hero-gradient {
    background: linear-gradient(135deg, #F0F9FF 0%, #F3E8FF 100%);
}
```

**To Change the Background:**

1. Find this in the `<style>` section
2. Replace the hex colors with new ones

**Example: Change to a warmer gradient**
```css
.hero-gradient {
    background: linear-gradient(135deg, #FEF3C7 0%, #FED7AA 100%);
}
```

**Example: Change to a cooler gradient**
```css
.hero-gradient {
    background: linear-gradient(135deg, #E0F2FE 0%, #F0F9FF 100%);
}
```

---

### Task 3: Add a Background Image to Hero

**Current Code (Line 62):**
```html
<section class="hero-gradient py-20 md:py-32 lg:py-40 px-4 sm:px-6 lg:px-8">
```

**Add background image:**
```html
<section class="hero-gradient py-20 md:py-32 lg:py-40 px-4 sm:px-6 lg:px-8" style="background-image: url('https://your-image-url.com/image.jpg'); background-size: cover; background-position: center;">
```

**Or update the CSS:**
```css
.hero-gradient {
    background: linear-gradient(135deg, #F0F9FF 0%, #F3E8FF 100%);
    background-image: url('https://your-image-url.com/image.jpg');
    background-size: cover;
    background-position: center;
    background-blend-mode: overlay;
}
```

---

### Task 4: Change Font Sizes

**Current Headline (Line 74):**
```html
<h1 class="text-4xl md:text-5xl lg:text-6xl font-bold">
```

**Make it Smaller:**
```html
<h1 class="text-3xl md:text-4xl lg:text-5xl font-bold">
```

**Make it Larger:**
```html
<h1 class="text-5xl md:text-6xl lg:text-7xl font-bold">
```

**Font Size Scale:**
- `text-2xl` = 24px
- `text-3xl` = 30px
- `text-4xl` = 36px
- `text-5xl` = 48px
- `text-6xl` = 60px
- `text-7xl` = 72px

---

### Task 5: Add More Feature Cards

**Current Features Section (Lines 129-220):**

The section has 5 feature cards. To add a 6th card:

1. **Find where the 5th card ends (around Line 220)**
2. **Copy one of the existing cards**
3. **Paste it after the last card**
4. **Update the content**

**Template for a New Card:**
```html
<div class="card-hover bg-white rounded-xl shadow-md p-8 border border-gray-100 hover:shadow-xl">
    <div class="w-16 h-16 bg-gradient-to-br from-[COLOR1]-400 to-[COLOR2]-600 rounded-lg flex items-center justify-center mb-6 feature-icon">
        <i class="fas fa-[ICON] text-white text-2xl"></i>
    </div>
    <h3 class="text-2xl font-bold text-gray-900 mb-4">Your Feature Title</h3>
    <p class="text-gray-700 leading-relaxed mb-4">
        Your feature description here...
    </p>
    <ul class="space-y-2 text-gray-700">
        <li class="flex items-center"><i class="fas fa-check text-green-500 mr-3"></i>Your first point</li>
        <li class="flex items-center"><i class="fas fa-check text-green-500 mr-3"></i>Your second point</li>
        <li class="flex items-center"><i class="fas fa-check text-green-500 mr-3"></i>Your third point</li>
    </ul>
</div>
```

**Replace:**
- `[COLOR1]` and `[COLOR2]` with colors like `blue`, `purple`, `green`, `red`, `orange`
- `[ICON]` with Font Awesome icon name (e.g., `fa-lock`, `fa-globe`, `fa-star`)
- "Your Feature Title" with your actual feature name
- "Your feature description here..." with your description
- The bullet points with your feature points

---

### Task 6: Update Testimonials

**Current Testimonials (Lines 463-530):**

There are 4 testimonial cards. To update them:

1. **Find a testimonial card**
2. **Update the quote text**
3. **Update the person's name**
4. **Update their job title**

**Example Testimonial Card (Lines 472-489):**
```html
<div class="testimonial-card bg-white rounded-xl shadow-md p-8 border border-gray-100 hover:shadow-xl">
    <div class="flex items-center mb-4">
        <div class="flex text-yellow-400">
            <i class="fas fa-star"></i>
            <i class="fas fa-star"></i>
            <i class="fas fa-star"></i>
            <i class="fas fa-star"></i>
            <i class="fas fa-star"></i>
        </div>
    </div>
    <p class="text-gray-700 leading-relaxed mb-6">
        "Fortify saved our entire business during the ransomware attack. We recovered all our data within 15 minutes. This is absolutely essential software."
    </p>
    <div class="border-t border-gray-200 pt-4">
        <p class="font-bold text-gray-900">Michael Chen</p>
        <p class="text-sm text-gray-600">CEO, TechStartup Inc.</p>
    </div>
</div>
```

**To Update:**
```html
<div class="testimonial-card bg-white rounded-xl shadow-md p-8 border border-gray-100 hover:shadow-xl">
    <div class="flex items-center mb-4">
        <div class="flex text-yellow-400">
            <i class="fas fa-star"></i>
            <i class="fas fa-star"></i>
            <i class="fas fa-star"></i>
            <i class="fas fa-star"></i>
            <i class="fas fa-star"></i>
        </div>
    </div>
    <p class="text-gray-700 leading-relaxed mb-6">
        "Your new testimonial quote here..."
    </p>
    <div class="border-t border-gray-200 pt-4">
        <p class="font-bold text-gray-900">Customer Name</p>
        <p class="text-sm text-gray-600">Job Title, Company Name</p>
    </div>
</div>
```

---

### Task 7: Add a New Testimonial Card

**To add a 5th testimonial:**

1. **Find the last testimonial card (around Line 520)**
2. **Copy the entire `<div class="testimonial-card">` block**
3. **Paste it after the last card**
4. **Update the content**

---

### Task 8: Modify the FAQ Questions

**Current FAQ (Lines 533-650):**

**To Update a Question:**

1. **Find the FAQ item you want to change**
2. **Update the question text** (in the `<h3>` tag)
3. **Update the answer text** (in the `.faq-answer` div)

**Example FAQ Item (Lines 544-555):**
```html
<div class="faq-item bg-white rounded-xl shadow-md border border-gray-100 overflow-hidden">
    <div class="faq-question cursor-pointer px-8 py-6 hover:bg-gray-50 transition-colors duration-300 flex items-center justify-between">
        <h3 class="text-lg font-bold text-gray-900">How does Fortify protect my data?</h3>
        <i class="fas fa-chevron-down faq-icon text-blue-600 transition-transform duration-300"></i>
    </div>
    <div class="faq-answer hidden px-8 pb-6 bg-gray-50 border-t border-gray-100">
        <p class="text-gray-700 leading-relaxed">
            Fortify employs military-grade AES-256 encryption...
        </p>
    </div>
</div>
```

**To Update:**
```html
<div class="faq-item bg-white rounded-xl shadow-md border border-gray-100 overflow-hidden">
    <div class="faq-question cursor-pointer px-8 py-6 hover:bg-gray-50 transition-colors duration-300 flex items-center justify-between">
        <h3 class="text-lg font-bold text-gray-900">Your new question here?</h3>
        <i class="fas fa-chevron-down faq-icon text-blue-600 transition-transform duration-300"></i>
    </div>
    <div class="faq-answer hidden px-8 pb-6 bg-gray-50 border-t border-gray-100">
        <p class="text-gray-700 leading-relaxed">
            Your answer here...
        </p>
    </div>
</div>
```

---

### Task 9: Add a New FAQ Question

**To add a 6th FAQ question:**

1. **Find the last FAQ item (around Line 640)**
2. **Copy the entire `<div class="faq-item">` block**
3. **Paste it after the last question**
4. **Update the question and answer**

---

### Task 10: Hide/Show Sections

**To hide a section**, add `hidden` class to the `<section>` tag:

```html
<!-- Hide the entire Features section -->
<section id="features" class="py-20 md:py-28 px-4 sm:px-6 lg:px-8 bg-gray-50 hidden">
```

**To show it again**, remove the `hidden` class:

```html
<!-- Show the Features section -->
<section id="features" class="py-20 md:py-28 px-4 sm:px-6 lg:px-8 bg-gray-50">
```

---

## Troubleshooting Guide

### Issue 1: Links Don't Work

**Problem:** Clicking a link does nothing or shows an error.

**Solutions:**

1. **Check the href value:**
   ```html
   <!-- WRONG - missing protocol -->
   <a href="example.com">

   <!-- CORRECT -->
   <a href="https://example.com">
   ```

2. **Check file paths:**
   ```html
   <!-- WRONG - file in wrong location -->
   <a href="pages/privacy.html">

   <!-- CORRECT - file in same folder -->
   <a href="privacy.html">
   ```

3. **Check for typos:**
   ```html
   <!-- WRONG - typo in file name -->
   <a href="privacyy.html">

   <!-- CORRECT -->
   <a href="privacy.html">
   ```

4. **Check for spaces in file names:**
   ```html
   <!-- WRONG - space in file name -->
   <a href="privacy policy.html">

   <!-- CORRECT - no spaces -->
   <a href="privacy-policy.html">
   ```

---

### Issue 2: Styling Looks Wrong

**Problem:** Colors, sizes, or spacing look different than expected.

**Solutions:**

1. **Clear browser cache:**
   - Press `Ctrl+Shift+Delete` (or `Cmd+Shift+Delete` on Mac)
   - Clear browsing data
   - Refresh the page

2. **Check for typos in class names:**
   ```html
   <!-- WRONG - typo -->
   <div class="bg-blue-50 text-lg">

   <!-- CORRECT -->
   <div class="bg-blue-50 text-lg">
   ```

3. **Verify Tailwind CSS is loaded:**
   - Check that this line is in the `<head>`:
   ```html
   <script src="https://cdn.tailwindcss.com"></script>
   ```

4. **Check for conflicting CSS:**
   - Look for custom CSS in the `<style>` section that might override Tailwind

---

### Issue 3: Mobile Menu Doesn't Work

**Problem:** The hamburger menu icon appears but doesn't open/close.

**Solutions:**

1. **Check JavaScript is enabled:**
   - Open browser developer tools (F12)
   - Check for JavaScript errors in the console

2. **Verify the mobile menu button exists:**
   ```html
   <button class="md:hidden mobile-menu-button text-gray-700 hover:text-blue-600 transition-colors duration-300" aria-label="Toggle mobile menu">
       <i class="fas fa-bars text-2xl"></i>
   </button>
   ```

3. **Check the JavaScript code:**
   - Make sure the script at the bottom of the page is intact
   - Look for any errors in the console

---

### Issue 4: Icons Don't Show

**Problem:** You see empty boxes instead of icons.

**Solutions:**

1. **Check Font Awesome is loaded:**
   - Verify this line is in the `<head>`:
   ```html
   <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
   ```

2. **Check icon class names:**
   ```html
   <!-- WRONG - icon class doesn't exist -->
   <i class="fas fa-locked"></i>

   <!-- CORRECT - proper icon name -->
   <i class="fas fa-lock"></i>
   ```

3. **Verify internet connection:**
   - Font Awesome requires internet to load icons
   - Check your internet connection

---

### Issue 5: FAQ Accordion Doesn't Open

**Problem:** Clicking FAQ questions doesn't expand the answers.

**Solutions:**

1. **Check JavaScript is running:**
   - Open developer tools (F12)
   - Look for JavaScript errors

2. **Verify the structure:**
   ```html
   <!-- Make sure the structure is correct -->
   <div class="faq-item">
       <div class="faq-question">
           <h3>Question?</h3>
           <i class="fas fa-chevron-down faq-icon"></i>
       </div>
       <div class="faq-answer hidden">
           <p>Answer here</p>
       </div>
   </div>
   ```

3. **Check for duplicate IDs:**
   - Each FAQ item should be unique
   - Look for duplicate `id` attributes

---

### Issue 6: Page Layout Looks Broken

**Problem:** Elements are overlapping or not aligned properly.

**Solutions:**

1. **Check responsive classes:**
   ```html
   <!-- Make sure responsive prefixes are correct -->
   <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3">

   <!-- NOT -->
   <div class="grid grid-cols-1 med:grid-cols-2 lrg:grid-cols-3">
   ```

2. **Check for missing closing tags:**
   - Make sure every opening tag has a closing tag
   - Use developer tools to inspect the HTML

3. **Check viewport meta tag:**
   - Verify this is in the `<head>`:
   ```html
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   ```

---

### Issue 7: Text Doesn't Display Correctly

**Problem:** Text is cut off, overlapping, or hard to read.

**Solutions:**

1. **Check text color:**
   ```html
   <!-- If text is white on white background -->
   <p class="text-white bg-white">Text here</p>

   <!-- Change text color -->
   <p class="text-gray-900 bg-white">Text here</p>
   ```

2. **Check font size:**
   ```html
   <!-- Text might be too small -->
   <p class="text-xs">Small text</p>

   <!-- Make it larger -->
   <p class="text-base">Normal text</p>
   ```

3. **Check line height:**
   ```html
   <!-- Add line-height for better readability -->
   <p class="leading-relaxed">Your text here</p>
   ```

---

### Issue 8: Gradient Text Doesn't Show

**Problem:** Text with `gradient-text` class appears as plain text.

**Solutions:**

1. **Check the CSS is defined:**
   - Look in the `<style>` section for:
   ```css
   .gradient-text {
       background: linear-gradient(135deg, #3B82F6 0%, #8B5CF6 100%);
       -webkit-background-clip: text;
       -webkit-text-fill-color: transparent;
       background-clip: text;
   }
   ```

2. **Check browser compatibility:**
   - Gradient text works in modern browsers (Chrome, Firefox, Safari, Edge)
   - May not work in older Internet Explorer

---

### Issue 9: External Links Open in Same Tab

**Problem:** You want links to open in a new tab.

**Solution:**

Add `target="_blank"` to the link:

```html
<!-- Opens in same tab -->
<a href="https://example.com">Click here</a>

<!-- Opens in new tab -->
<a href="https://example.com" target="_blank">Click here</a>
```

---

### Issue 10: Form/Button Doesn't Submit

**Problem:** Clicking a button does nothing.

**Solutions:**

1. **Check if it's a link or button:**
   ```html
   <!-- If it should be a link -->
   <a href="https://example.com" class="button-classes">
       Click me
   </a>

   <!-- If it's a button that needs JavaScript -->
   <button onclick="doSomething()">Click me</button>
   ```

2. **Check the onclick attribute:**
   ```html
   <!-- Make sure the function exists -->
   <button onclick="myFunction()">Click me</button>

   <!-- And it's defined in JavaScript -->
   <script>
   function myFunction() {
       // Do something
   }
   </script>
   ```

---

## Best Practices for Maintenance

### 1. **Always Back Up Before Making Changes**

- Keep a copy of your original `index.html`
- Save versions: `index-v1.html`, `index-v2.html`, etc.

### 2. **Test Changes in Multiple Browsers**

- Test in Chrome, Firefox, Safari, and Edge
- Use mobile device simulators (F12 Developer Tools)

### 3. **Use a Text Editor with Syntax Highlighting**

Recommended editors:
- **VS Code** (free, most popular)
- **Sublime Text** (free trial)
- **Atom** (free)
- **Notepad++** (free)

### 4. **Keep External Links Updated**

- Review all links every 3 months
- Test that external URLs still work
- Update broken links immediately

### 5. **Monitor SEO**

- Keep meta descriptions current
- Update keywords as needed
- Ensure all links are working

### 6. **Regular Content Updates**

- Update testimonials with new customer feedback
- Refresh statistics in the About section
- Keep FAQ current with common questions

---

## Quick Reference: Common Tailwind Classes

### Sizing
```
text-sm, text-base, text-lg, text-xl, text-2xl, text-3xl, text-4xl, text-5xl, text-6xl
p-2, p-4, p-6, p-8, p-12 (padding)
m-2, m-4, m-6, m-8 (margin)
w-10, w-16, w-full (width)
h-10, h-16, h-full (height)
```

### Colors
```
text-gray-900, text-gray-700, text-gray-600, text-gray-300
bg-white, bg-gray-50, bg-gray-900
bg-blue-500, bg-blue-600, bg-purple-600
text-green-500, text-red-500, text-yellow-400
```

### Spacing
```
gap-4, gap-6, gap-8, gap-12 (space between items)
mb-4, mb-6, mb-8 (margin bottom)
mt-4, mt-6, mt-8 (margin top)
mx-auto (center horizontally)
```

### Effects
```
rounded-lg, rounded-xl (rounded corners)
shadow-md, shadow-lg, shadow-xl (drop shadow)
border-2, border-gray-100 (borders)
opacity-50, opacity-75 (transparency)
```

### Responsive
```
md: (medium screens/tablets)
lg: (large screens/desktops)
xl: (extra large screens)
```

---

## Conclusion

You now have a complete guide to maintaining and customizing your Fortify landing page. Remember:

1. **Always back up your files**
2. **Test changes thoroughly**
3. **Keep links updated**
4. **Maintain content regularly**
5. **Use the troubleshooting guide if issues arise**

For more help with Tailwind CSS, visit: https://tailwindcss.com/docs

For more help with HTML, visit: https://developer.mozilla.org/en-US/docs/Web/HTML

Good luck with your landing page!