# 🕵️‍♂️ CSI: Accessibility — Case File #804: The Banana Serial Killer

> *"We have a crime: a user attempts to use a website and cannot complete a task. The dev team claims everything is fine So... what happened?"*

Official repository for the forensic web app used as a live case study and demonstration for the talk **"CSI: Accesibilidad"** (presented in Spanish).

This interface simulates a fictional police forensic database loaded with **deliberate critical accessibility flaws**. It is specifically designed to demonstrate what automated tools catch (and what slips past them) compared to manual testing, keyboard inspection, and assistive technologies.

---

## 🔍 What is the Talk About?
In this session, we step into the shoes of accessibility detectives to follow the trail of clues using:
* **DevTools & Accessibility Tree (A11y Tree):** Inspecting under the hood of the browser.
* **Keyboard Navigation (`Tab`, `Shift+Tab`, `Enter`, `Space`):** Uncovering hidden focus traps and non-interactive components.
* **Screen Readers:** Testing the real user experience beyond metrics.
* **Automated Audit Tools (Lighthouse, axe-core, WAVE):** Understanding their false sense of security and blind spots.

Because in accessibility, we don't look for someone to blame... well, okay, sometimes we do. 😉

---

## 📂 Repository Content
* `index.html`: The main demo application ("The Victim / Forensic Terminal") packed with 10 strategic accessibility flaws and a built-in **Speaker Hints Mode**.

---

## 🕵️‍♂️ Key Accessibility "Crimes" Included

1. **Flaw #1 (Fake 100% Lighthouse Score):** Inputs with `alt` and `aria-label` attributes containing junk text (`qwertyuiop...`). Automated tools give a 100% green pass because the attributes exist, but screen readers output gibberish.
2. **Flaw #2 (Destroyed Focus Indicator):** Global `*:focus { outline: none !important; }` CSS rule, rendering keyboard navigation completely invisible.
3. **Flaw #3 (Label-less Form Controls):** Input fields lacking associated `<label>` elements or semantic `id`/`for` bindings.
4. **Flaw #4 (Fake Buttons):** Actionable controls built with `<div>` elements and `onclick` handlers instead of semantic `<button>` tags, preventing keyboard execution.
5. **Flaw #5 (Inaccessible Modals):** Dialog overlay lacking a proper focus trap and `Escape` key support.
6. **Flaw #6 (Severe Contrast Violations):** Text badges with contrast ratios as low as `1.2:1` to `1.8:1`.
7. **Flaws #7A & #7B (Inaccessible Images):** Misleading `alt` descriptions (`alt="image.jpg"`) and completely missing `alt` attributes.
8. **Flaw #8 (Broken ARIA Components):** A custom toggle switch using `role="switch"` without `aria-checked` states or keyboard event listeners.
9. **Flaw #9 (Ambiguous Link Text):** Links reading *"click here"* or *"here"* that lack context when navigated via screen reader rotor/link lists.
10. **Flaw #10 (Broken Heading Hierarchy):** Disordered document structure skipping directly across `H5`, `H1`, `H3`, and `H2`.

---

## 🚀 How to Use This Demo in Your Presentation

1. Clone or download this repository to your local machine.
2. Open `index.html` in any modern web browser (Chrome, Firefox, Safari, Edge).
3. **Speaker Mode Feature:** Click the floating button in the bottom right corner (**`🕵️ Activar Pistas Ponente`**). This will toggle high-visibility dashed outlines and floating diagnostic badges over every flaw for live audience guidance.

---

## 📄 License
This project is open-source and available under the [MIT License](LICENSE). Feel free to use, modify, or adapt it for your own talks and accessibility workshops!