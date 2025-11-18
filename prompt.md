You are an expert technical recruiter AND a senior frontend engineer.

## GOAL

Build a **single-page Tailwind HTML resume site** for **Julian Shaw** that:

1. Uses **only HTML + CSS (Tailwind)** – no JavaScript.
2. Presents **two tailored resume views**:
   - **Control Systems / QA Engineer** version.
   - **Software Developer / Full Stack Engineer** version.
3. Allows a user to:
   - **View** each version directly on the page (nicely formatted, recruiter-friendly).
   - **Download** each version as a PDF via clear buttons/links.
4. Uses content from the following existing resume files:
   - `resume2024Nov.pdf`  → general Engineering / IT background.
   - `resume2024QA.pdf`   → Control Systems / QA–focused version.
   - `resumeNew.pdf`      → Software Developer / Full Stack–focused version.

You have access to these files in the workspace. Open and **extract the relevant content** from them.

---

## ROLE & BEST PRACTICES

Act as:

- An **expert recruiter** who knows what works for:
  - ATS (Applicant Tracking System) parsing.
  - Tech hiring managers (clarity, impact, concise).
- A **senior frontend engineer** using Tailwind for a clean, modern, responsive layout, with **no JS**.

Apply **best-practice resume principles**:

- Strong **headline and professional summary**.
- Clear **core skills / tech stack**.
- Concise **experience section** with:
  - Impactful bullet points.
  - Action verbs and measurable outcomes where possible.
- Education and certifications clearly listed.
- Avoid walls of text; use white space, hierarchy, and consistent formatting.

---

## CONTENT & MAPPING

Use the resume PDFs as follows:

1. **Software Developer Version**
   - Primary source: `resumeNew.pdf` (Full Stack / Angular / .NET / Azure).
   - Supplement with relevant IT content from `resume2024Nov.pdf` if useful.
   - Emphasise:
     - Full Stack dev (Angular, .NET, TypeScript, C#, SQL, Python).
     - Cloud & DevOps (Azure, GitHub Actions, CI/CD).
     - Microservices, architecture, Agile/Scrum.
     - Recent roles: CTRC Services, Real Digital International, Zeolite Technology, Carib Condominiums, Bookerja.com, etc.
   - Optimise wording for **software dev roles** (UK & remote-friendly).

2. **Control Systems / QA Version**
   - Primary source: `resume2024QA.pdf`.
   - Supplement with relevant control systems / engineering / QA content from `resume2024Nov.pdf`.
   - Emphasise:
     - Control systems engineering (DCS, PLC, Honeywell, ABB, Aramco).
     - Estimating, QA/ISO, GAMP, Lean Sigma.
     - Project engineering on oil & gas / process plants.
   - Optimise wording for **Control Systems / QA / Automation** roles.

3. **Shared sections**
   - Name, contact details, education, key certifications (AEC, CSM, Microservices, generative AI, etc.) can be reused and styled consistently across both views.

---

## UX & LAYOUT REQUIREMENTS

- Use **Tailwind CSS via CDN** (e.g. `<script src="https://cdn.tailwindcss.com"></script>` in the `<head>`).
- **No JavaScript at all** – any “switching” between versions must use **HTML + CSS only**.
- Make the page:

  - **Responsive / mobile-first**.
  - Easily **printable** (looks good when printed or “Save as PDF” from browser).
  - Clean, professional, with good spacing and readable typography.

### Page Structure

Create a single `index.html` file with:

1. **`<head>`**
   - Proper `<title>` like: `"Julian Shaw – Resume"`.
   - Meta tags for viewport and description.
   - Tailwind CDN.
   - Minimal custom CSS inside `<style>` if needed (e.g. for print styles or tab behavior using `:checked`).

2. **Top Header / Hero**
   - Full-width section with:
     - Name: **Julian Shaw** (prominent).
     - One-line branding: e.g.
       “Full Stack Developer & Control Systems Engineer”.
     - Contact info: email, phone, location.
   - Place a compact **view switcher** here (see below).

3. **Version Switcher (CSS-only tabs)**
   - Implement two **tabs** using **only HTML + CSS**, for example:
     - Radio inputs + labels, styled as tabs:
       - Tab 1: “Software Developer CV”.
       - Tab 2: “Control Systems / QA CV”.
     - Use the `:checked` state to show/hide the corresponding content panel.
   - No JS – use Tailwind classes and minimal custom CSS for the tab behavior.

4. **Resume Content Panels**
   - Two main content areas (one **per version**), each with:
     - Professional Summary.
     - Key Skills / Core Competencies.
     - Technical Skills / Tools.
     - Professional Experience (reverse chronological).
     - Education.
     - Certifications.
   - Only one panel visible at a time based on the selected tab.

5. **Download Section**
   - For each version (inside its panel or just under the tabs), add a **clear download button**:
     - “Download Software Developer CV (PDF)”
       - `href="./files/JulianShaw_SoftwareDeveloper.pdf"` (use this path; I will provide the actual file).
     - “Download Control Systems / QA CV (PDF)”
       - `href="./files/JulianShaw_ControlSystemsQA.pdf"`.
   - Use Tailwind to style these as primary buttons (rounded, hover state, etc.).
   - Also provide a small text link under each button: “Open in browser” using the same URL (so clicking opens the PDF).

   > IMPORTANT: Use these **exact file names and relative paths** in the `<a>` tags so I can simply drop the PDFs into a `files/` folder later.

---

## DESIGN GUIDELINES

- **Color palette**:
  - Professional and understated (e.g. slate/gray for text, accent color like indigo or teal for highlights).
- **Typography**:
  - Use Tailwind’s defaults: `font-sans`, `text-sm`–`text-base` body, `text-xl`–`text-2xl` headings.
- **Layout**:
  - Content constrained in a centered container (`max-w-4xl mx-auto px-4`).
  - Use Tailwind Flex/Grid for skills and experience sections.
- **Sections styling**:
  - Use cards with subtle borders / shadows for each main section.
  - Bullet lists for responsibilities/achievements, not long paragraphs.
- **Accessibility**:
  - Use semantic HTML (`<header>`, `<main>`, `<section>`, `<h1>`–`<h3>`, `<ul>`, `<li>`).
  - Proper `<label>`s associated with radio inputs for tabs.
  - Sufficient color contrast.

---

## IMPLEMENTATION DETAILS

1. **File Output**
   - Return a **single HTML file** named `index.html`.
   - Include all Tailwind usage in the HTML (no separate CSS file, except for a `<style>` block in the `<head>` if needed).

2. **No JavaScript**
   - Do NOT include `<script>` tags except the Tailwind CDN.
   - All interactivity (tab switching) must be achieved via CSS selectors (`:checked`, `:target`, etc.).

3. **Content Quality**
   - Rewrite bullet points slightly where needed to:
     - Emphasise impact.
     - Use active verbs.
     - Avoid redundancy.
   - Tailor the wording separately for each version (Software Dev vs Control Systems / QA), while keeping facts accurate.

Return ONLY the final `index.html` code in a single fenced code block, ready to drop into a project and open in the browser.
