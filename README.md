# astro-md-img

Repro for issue where markdown content collection doesn't bundle image from markdown body on `astro build`.

Markdown files in `/src/content/posts/` are in "posts" content collection. They reference images in `/src/assets/images/` in different ways:

- `foo.md`:
  - ✅ frontmatter thumbnail image reference `/src/assets/images/200.jpg` gets bundled to `/dist/_astro/200.*.jpg`
  - ❌ md body image reference `/src/assets/images/404.jpg` doesn't get bundled
- `bar.md`:
  - ✅ frontmatter thumbnail image reference `../../assets/images/202.jpg` gets bundled to `/dist/_astro/202.*.jpg`
  - ✅ md body image reference `../../assets/images/302.jpg` gets bundled to `/dist/_astro/302.*.jpg`
