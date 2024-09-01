# template-hierarchy

In WordPress, the **template hierarchy** is the system that WordPress uses to determine which template file to use when displaying different types of content. This hierarchy is crucial for theme development as it defines how WordPress selects templates based on the URL or query being viewed.

### How the WordPress Template Hierarchy Works
When a user visits a page on a WordPress site, WordPress matches the URL with a specific type of content (such as a post, page, category, or archive). It then looks through the hierarchy to find the appropriate template file within the active theme to render that content.

### Key Components of the Template Hierarchy

1. **Home Page**
   - **`home.php`**: Used to display the homepage if it's a blog index.
   - **`front-page.php`**: Used if a static front page is set in the settings.
   - **`index.php`**: The fallback template if no other template is available.

2. **Single Post**
   - **`single-{post-type}.php`**: Used for custom post types (e.g., `single-product.php` for products).
   - **`single.php`**: Used for single posts of the default "post" type.
   - **`singular.php`**: A more general template used for any single post or page.
   - **`index.php`**: The fallback template.

3. **Pages**
   - **`page-{slug}.php`**: Used for a specific page with a matching slug (e.g., `page-about.php`).
   - **`page-{id}.php`**: Used for a specific page with a matching ID (e.g., `page-10.php`).
   - **`page.php`**: Used for all pages.
   - **`singular.php`**: General template used for any single post or page.
   - **`index.php`**: The fallback template.

4. **Category**
   - **`category-{slug}.php`**: Used for a specific category with a matching slug (e.g., `category-news.php`).
   - **`category-{id}.php`**: Used for a specific category with a matching ID (e.g., `category-5.php`).
   - **`category.php`**: Used for all category archives.
   - **`archive.php`**: Used for all archive pages.
   - **`index.php`**: The fallback template.

5. **Tag**
   - **`tag-{slug}.php`**: Used for a specific tag with a matching slug (e.g., `tag-special.php`).
   - **`tag-{id}.php`**: Used for a specific tag with a matching ID.
   - **`tag.php`**: Used for all tag archives.
   - **`archive.php`**: Used for all archive pages.
   - **`index.php`**: The fallback template.

6. **Custom Post Type Archive**
   - **`archive-{post-type}.php`**: Used for a specific custom post type archive (e.g., `archive-product.php`).
   - **`archive.php`**: Used for all archive pages.
   - **`index.php`**: The fallback template.

7. **Author**
   - **`author-{nicename}.php`**: Used for a specific author with a matching nicename.
   - **`author-{id}.php`**: Used for a specific author with a matching ID.
   - **`author.php`**: Used for all author archives.
   - **`archive.php`**: Used for all archive pages.
   - **`index.php`**: The fallback template.

8. **Date**
   - **`date.php`**: Used for date-based archives.
   - **`archive.php`**: Used for all archive pages.
   - **`index.php`**: The fallback template.

9. **Search Results**
   - **`search.php`**: Used for search result pages.
   - **`index.php`**: The fallback template.

10. **404 Error**
    - **`404.php`**: Used when no content is found (a "Page Not Found" error).
    - **`index.php`**: The fallback template.

### Example Flow of Template Hierarchy

Let's say you visit a URL that corresponds to a single post. Here's how WordPress will determine which template to use:

1. **Check for `single-{post-type}.php`**: If the post is a custom post type (e.g., product), WordPress will look for a template named `single-product.php`.
2. **Check for `single.php`**: If no custom post type template is found, it will look for `single.php`.
3. **Check for `singular.php`**: If neither of the above templates exists, WordPress will look for `singular.php`.
4. **Fallback to `index.php`**: If none of the specific templates are available, WordPress will use the `index.php` file.

### Importance for Theme Development

Understanding the template hierarchy allows theme developers to create specific templates for different content types, offering greater flexibility and control over how content is displayed on a WordPress site. This hierarchy also makes it easier to create child themes by overriding specific templates while leaving the rest of the parent theme intact.

In summary, the WordPress template hierarchy is a powerful tool for customizing the appearance and structure of a WordPress site based on different types of content and requests.
