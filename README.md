# Mini styles

A small CSS library with shared tokens, explicit element defaults, and opt-in component classes.

## Styles

Use the complete stylesheet (`mini-styles/styles.css`) or SCSS entry point (`src/styles/index.scss`). Component partials depend on the shared tokens and base reset; they are not standalone stylesheets.

The entry point loads tokens, reset, element defaults, layout, then components. All rules live in `@layer mini`. Normal unlayered application styles can override them.

The reset applies border-box sizing and removes margins and padding globally, including pseudo-elements. Base styles provide defaults for the body, h1–h6, paragraphs, links, lists, description lists, blockquotes, and horizontal rules. Add defaults for other content elements as needed.

## Naming and customization

- Classes and custom properties use the `mini-` prefix.
- Component modifiers use `--`, such as `.mini-btn--danger`.
- Spacing tokens are `--mini-space-sm` (0.25rem), `--mini-space-md` (0.5rem), `--mini-space-lg` (1rem), and `--mini-space-xl` (2rem). The first three replace `--mini-space-2`, `--mini-space-3`, and `--mini-space-4`, respectively.
- Override global tokens on `:root` or a containing element to customize colors, fonts, spacing, and radius.
- Buttons expose `--mini-btn-accent`, `--mini-btn-accent-hover`, `--mini-btn-bg`, `--mini-btn-bg-hover`, `--mini-btn-fg`, and `--mini-btn-border` for local customization.

## Layout

Layout classes live in `src/styles/_layout.scss` and are opt-in:

- `.mini-page` centers a page or container with a maximum width of 44rem and page padding.
- `.mini-header` adds a double bottom rule and spacing, with muted direct-child paragraphs.
- `.mini-section` adds section spacing and a bottom rule beneath direct-child h2 headings.
- `.mini-row` arranges items in a wrapping flex row with a shared gap.

## Components

- `.mini-btn` styles native buttons. Combine `.mini-btn--danger` and `.mini-btn--outline` for a danger outline button; the order of classes in HTML does not matter. Use the native `disabled` attribute for disabled behavior.
- `.mini-card` provides a bordered container.
- `.mini-form` spaces field groups. `.mini-label`, `.mini-input`, `.mini-select`, and `.mini-textarea` also work outside it.
- Apply `.mini-input` to text-like inputs such as text, email, password, search, tel, URL, and number. Do not apply it to checkboxes, radios, ranges, files, or input buttons.

## Demo and build

Run `npm install`, then `npm run build` to generate expanded and minified CSS in `dist`. Open `demo/index.html` to view the components and content defaults. Use `npm run dev` to rebuild expanded CSS when SCSS changes.
