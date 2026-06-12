# Edit the navigation (`docs.json`)

Everything visible in the site's menu is controlled by `docs.json`.  
If an `.mdx` page is not referenced in this file, it won't appear on the site.

---

## Structure of `docs.json`

```
navigation
  └── tabs[]              ← top tabs (Getting Started, Skills, Contexts, ...)
        └── groups[]      ← sections in the sidebar
              └── pages[] ← paths to .mdx files (without extension)
```

---

## Common cases

### Add a page to an existing group

Find the group in `docs.json` and add the path:

```json
{
  "group": "Reporting",
  "pages": [
    "skills/finding-writer",
    "skills/my-new-page"
  ]
}
```

The path = the `.mdx` filename without the extension, relative to the repo root.

### Create a new group

In the right `tab`, add a `group` object:

```json
{
  "tab": "Skills",
  "groups": [
    {
      "group": "My New Group",
      "pages": [
        "skills/my-page"
      ]
    }
  ]
}
```

### Rename a page in the menu

The title displayed in the menu comes from the `title` field in the `.mdx` file's frontmatter, not from `docs.json`.  
To change the title: edit `title:` in the file's frontmatter.

### Remove a page

1. Remove the entry from `docs.json`
2. Delete the `.mdx` file
3. If the URL was public, add a redirect in the `redirects` array:

```json
"redirects": [
  {
    "source": "/skills/old-name",
    "destination": "/skills/new-name"
  }
]
```

### Move a page to another group

Remove the path from the current group and add it to the target group. Don't touch the `.mdx` file.

---

## Edit the banner, footer, or navbar links

Everything is in `docs.json`:

- `banner.content` → text of the banner at the top of the site
- `navbar.links` → links in the navigation bar
- `footer.links` → footer sections and links
- `footer.socials` → social media icons

---

## Check that `docs.json` is valid

```bash
mintlify dev
```

If `docs.json` contains a syntax error or references a page that doesn't exist, Mintlify shows an error at startup.
