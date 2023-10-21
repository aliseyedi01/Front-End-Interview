## Next

> What the Next.js ?

- **React Framework**
  - It is a popular React Framework
- **Server-rendered App**
  - Is allow developers to build server-rendered React Application
- **SEO-friendly**
  - It provides an easy way to create dynamic , SEO-friendly websites with minimal configurations

> What are the Benefit of Next.js ?

- **Server-side Rendering:**
  - Boosts performance and SEO with server-side rendering.
- **Code Splitting & Lazy Loading:**
  - Accelerates page load times using automatic code splitting and lazy loading.
- **Built-in API Support:**
  - Simplifies backend development with built-in API routes and serverless functions.
- **Easy Deployment:**
  - Streamlines deployment, especially with platforms like Vercel.
- **Strong Community:**
  - Benefits from a robust community and active development for ongoing support and updates.

## Render

### Page

#### SSG

> What is the SSG in next.js ?

- **Generation on Server**
  - Static site generation is the process of generating a website's HTML, CSS, and JavaScript files before a client requests them.
- **Served as Static Files**
  - The generated content of the website is pre-built and served as static files

> How Work SSG in next.js ?

1. The developer creates Next.js pages and defines the static content for each page.
2. The developer runs the `next build` command to generate the static HTML files for the pages.
3. The developer deploys the static HTML files to a web server.
4. When a user visits a page on the web server, the web server serves the static HTML file to the user's browser.

> What is the getStaticProps function in next.js ?

- **Definition:**
  - **Fetch Data at Build Time:**
    - Function to fetch data during Next.js application build process.
  - **Pass Data as Props:**
    - Provides fetched data as props on the server-side to page component.
  - **Revalidate Options:**
    - `getStaticProps` supports `revalidate` option for cache refresh.
- **Usefulness:**
  - **Generic Static Pages:**
    - Pre-render dynamic data for static pages like blogs or products, improving performance
  - **Dynamic Static Pages:**
    - Create dynamic static pages without losing static site benefits.
- **Benefits:**
  - **Performance Optimization:**
    - Static pages are faster due to no server-side rendering per request.
  - **Improved SEO:**
    - Search engines can index static pages, boosting website's search ranking.
  - **Reduced Server Load:**
    - Static pages lower server costs and enhance scalability.

```jsx
export async function getStaticProps() {
  const blogPosts = await fetch("https://my-api.com/blog_posts").then((response) =>
    response.json(),
  );

  return {
    props: {
      blogPosts,
    },
  };
}

export default function BlogPage({ blogPosts }) {
  return (
    <div>
      <h1>Blog Posts</h1>
      <ul>
        {blogPosts.map((post) => (
          <li key={post.id}>
            <a href={`/blog/${post.id}`}>{post.title}</a>
          </li>
        ))}
      </ul>
    </div>
  );
}
```

#### SSR

> What is SSR in Next.js?

- **Stand For**
  - Server Side Rendering
- **Render on Server**
  - It allow the rendering of react components on the server
- **Work**
  - With SSR, the initial HTML content is generated on the server and sent to the client, improving performance and SEO.
- **Built-In API**
  - It provides a built-in API for server-side rendering, making it easy to implement this feature in your applications.

> What is the SSR in next.js ?

- **Stand For**
  - Server Sider Rendering
- **Benefit**
  - Improved performance
  - SEO benefits
  - Improved user experience
- **Work**
  1. The client makes a request to the server for a page.
  2. The server generates the HTML for the page and sends it to the client.
  3. The client renders the HTML and displays the page to the user.

#### ISR

> What is the ISR in next.js ?

- **Stand For:**
  - Incremental Static Regeneration (ISR)
- **Update Page Without Rebuilding:**
  - Enables updating static pages at runtime without rebuilding the entire application.
- **Static and Dynamic Content:**
  - ISR allows a mix of static and dynamic content in Next.js applications, enhancing flexibility.
- **Revalidation Time:**
  - Next.js defines a revalidation time for each page, automatically regenerating the page when requested after the revalidation time has passed.

> How Work ISR in next.js ?

1. The client makes a request to the server for a page.
2. The server checks to see if the page has already been generated as a static file.
   - If the page has been generated as a static file, the server serves the static file to the client.
   - If the page has not been generated as a static file, the server generates the page dynamically and sends it to the client.
3. The client renders the page and displays it to the user.

#### CSR

> What is the CSR in next.js ?

- **Stand For:**
  - Client-Side Rendering (CSR)
- **Definition**
  - **Render on Browser**
    - In CSR, the rendering process occurs in the user's browser rather than on the server.
  - **Initial Page Load:**
    - During the initial page load, a basic HTML layout is sent to the client, and the content is filled in via JavaScript after the page loads.
  - **JavaScript Dependency:**
    - Requires JavaScript to be enabled in the client's browser for content rendering and interactivity.
- **Benefit**
  - **Dynamic Updates:**
    - Allows dynamic updates without full-page reloads,
  - **Improve performance**
    - It can be useful for improving performance and reducing load times,
  - **User Experience**
    - enhancing user experience in web applications.

> How Work CSR in next.js ?

1. The client makes a request to the server for the initial HTML and CSS of the page.
2. The server sends the initial HTML and CSS to the client.
3. The client renders the initial HTML and CSS.
4. The client fetches any additional data that is needed for the page.
5. The client updates the page based on the additional data.

> What is use case of CSR in next.js ?

- **Real-time chat applications:**
  - CSR allows users to see new messages being sent and received in real time, without having to reload the page.
- **News websites:**
  - CSR allows news websites to update their content in real time as new stories are published.
- **Social media platforms:**
  - CSR allows social media platforms to provide a more dynamic and interactive user experience, such as allowing users to see their news feeds update in real time and interact with other users' posts in real time.
- **Infinite scrolling:**
  - CSR can be used to implement infinite scrolling, so that users can see new content loaded onto the page as they scroll down.

#### Different

> What are the differences between SSR and SSG ?

- **Generation Process:**
  - **SSG:**
    - Generates HTML pages at build time.
  - **SSR:**
    - Renders HTML pages on the server for each request.
- **Content Flexibility:**
  - **SSG:**
    - Fetches data during build for dynamic content.
  - **SSR:**
    - Fetches data on each request, enabling real-time content.
- **Performance:**
  - **SSG:**
    - Fast initial loading with pre-built static pages.
  - **SSR:**
    - Slightly slower initial loading due to server-side rendering.
- **Deployment:**
  - **SSG:**
    - HTML files deployable on CDNs for global access.
  - **SSR:**
    - Requires server processing for each request, limiting deployment options.
- **Caching:**
  - **SSG:**
    - Supports caching for reduced server load.
  - **SSR:**
    - Limited caching due to frequent data fetching.
- **Use Cases:**
  - **SSG:**
    - Content-heavy websites with relatively static content.
  - **SSR:**
    - Applications needing real-time data and dynamic user experiences.

| **Aspect**      | **SSG**                                          | **SSR**                                                           |
| --------------- | ------------------------------------------------ | ----------------------------------------------------------------- |
| **Generation**  | Builds HTML at build time.                       | Renders HTML on server per request.                               |
| **Flexibility** | Fetches data at build, supports dynamic content. | Fetches data per request, enabling real-time content.             |
| **Performance** | Fast initial loading with static pages.          | Slightly slower initial loading due to server-side rendering.     |
| **Deployment**  | Static HTML deployable on CDNs.                  | Requires server processing, limiting deployment options.          |
| **Caching**     | Supports caching for reduced server load.        | Limited caching due to frequent data fetching.                    |
| **Use Cases**   | Content-heavy sites with static content.         | Applications needing real-time data and dynamic user experiences. |

> What are the differences between SSR and CSR ?

- **HTML Generation:**
  - **CSR:**
    - Server generates HTML before sending it to the client.
  - **SSR:**
    - Client generates HTML after the page has loaded.
- **SEO and Performance:**
  - **CSR:**
    - Good performance, less SEO-friendly.
  - **SSR:**
    - Best performance, excellent SEO benefits.
- **Development and Maintenance:**
  - **CSR:**
    - Easier development and maintenance.
  - **SSR:**
    - More challenging development, but offers superior performance and SEO.
- **Use Cases:**
  - **CSR:**
    - Dynamic content websites like e-commerce and social media platforms.
  - **SSR:**
    - Static content websites like blogs and landing pages.

| **Aspect**          | **SSR**              | **CSR**               |
| ------------------- | -------------------- | --------------------- |
| **HTML Generation** | Server-side          | Client-side           |
| **Performance**     | Good                 | Best                  |
| **SEO**             | Excellent            | Good                  |
| **Development**     | Challenging          | Easier                |
| **Use Cases**       | Static content sites | Dynamic content sites |

> What is the difference between getStaticProps and getServerSideProps in Next.js?

- **Pre-rendering Page:**
  - **getStaticProps:**
    - Used for pre-rendering pages at build time.
  - **getServerSideProps:**
    - Used for pre-rendering dynamic pages on the server at runtime.
- **HTML Generation:**
  - **getStaticProps:**
    - Generates static HTML files during the build process.
  - **getServerSideProps:**
    - Generates HTML on every incoming request.
- **Data Fetching and Rendering:**
  - **getStaticProps:**
    - Data fetching and page rendering occur during build time.
  - **getServerSideProps:**
    - Data fetching and page rendering occur for every request.
- **Use Cases:**
  - **getStaticProps:**
    - Best suited for static content or content that does not change frequently.
  - **getServerSideProps:**
    - Suitable for pages with data that frequently changes or requires user-specific data.
- **Page Load Performance:**
  - **getStaticProps:**
    - Results in faster page loads since the HTML is generated in advance.
  - **getServerSideProps:**
    - Slower compared to `getStaticProps` as it generates HTML dynamically for each request.

| Aspect                 | `getStaticProps`           | `getServerSideProps`        |
| ---------------------- | -------------------------- | --------------------------- |
| **Pre-rendering Type** | Static generation          | Server-side rendering       |
| **HTML Generation**    | Static files at build time | Dynamic on each request     |
| **Data Fetching**      | Build time                 | Runtime for every request   |
| **Use Cases**          | Static content             | Dynamic or user-specific    |
| **Page Load Speed**    | Faster (pre-generated)     | Slower (dynamic generation) |

### Component

#### Server

#### Client

## Route

### Static

### Dynamic

> What is the dynamic Routing in next.js ?

- **Customized Page Serving:**
  - Dynamic routing in Next.js enables the server to deliver distinct pages based on the specific URL requested by the user.
  - This customization allows for tailored content presentation, enhancing user experience and interaction.

> How Create a Dynamic Route ?

- **Create by file system**
  - dynamic routing can be implemented using the file system
- **Brackets in the file name**
  - Pages can be designed with brackets in the file name, indicating dynamic segments.
  - These segments are then utilized as parameters in the URL, allowing for dynamic content generation based on user input or specific criteria.

## Data Fetching

> How do you handle data fetching in NextJS?

- **Server-Side**
  - **`getStaticProps`**
    - Fetches data at build time and provides it as props to the page by `getStaticProps`
  - **`getServerSideProps`**
    - Fetches data on each request, allowing dynamic content based on user interactions.
- **Client-Side**
  - **Axios / Fetch**
    - Data can be fetched using libraries like `axios` or the native `fetch` API.
  - **useEffect / useState**
    - React hooks such as `useEffect` or `useState` can be employed for managing client-side data fetching.

## Component

### Link

> What is the Link Component in next.js ?

- **Definition**
  - **Component Extends HTML Element**
    - Link is a built-in React component that extends the HTML a element to
  - **Client-side Navigations Page**
    - It use for client-side navigation between pages in a Next.js application.
  - **Preload in Background**
    - It automatically preloads the linked page in the background, improving the user experience
- **Usage**
  - **Instead a Tag**
    - Link wraps anchor tags `<a>` and allows users to navigate by clicking.
    - It accepts the `href` prop indicating the destination page.

## Performance

> How can Optimize the performance of Next.js ?

### SEO

> How does Next.js handle SEO optimization?

- **Approach**
  - **Static Site Generation (SSG):**
    - Next.js pre-renders React apps as static HTML, improving SEO by faster loading and search engine crawlability.
  - **Server-Side Rendering (SSR):**
    - Next.js renders React apps on the server, generating static HTML for SSR pages, ensuring crawlability and personalized content display.
  - **Incremental Static Regeneration (ISR):**
    - Next.js incrementally generates static pages, updating content dynamically.
    - Ensures search engines always have the latest version.
  - **Automatic Code Splitting:**
    - Next.js splits code into smaller, on-demand bundles, enhancing performance and SEO by reducing page load times.
  - **Image Optimization:**
    - Next.js automatically optimizes images, improving page loading speed and SEO performance.
  - **Built-in SEO Meta Tags:**
    - Next.js supports common SEO meta tags (title, description), aiding search engine visibility.

### Code Splitting

> How does Next.js handle code splitting?

- **How**
  - **Automatically Split**
    - Next.js automatically splits your code into smaller chunks, called “chunks,”
  - **Split Based Routes and Components**
    - Code splitting occurs based on the specific routes and components utilized in your application.
- **Benefit**
  - **Faster Loading Times**
    - Enables faster loading times and improved performance because users only download the code necessary for the current page, enhancing user experience.

## Style

### CSS Module

### CSS-in-JS

### Global CSS

### Different

> What are the different options for styling NextJS apps?

- **CSS Modules:**
  - Next.js supports CSS Modules, enabling modular CSS with local scoping.
  - Prevents global style conflicts by default scoping class names locally.
- **Styled-jsx:**
  - Next.js supports styled-jsx, allowing scoped styles as JavaScript objects.
  - Styles are encapsulated at the component level, ensuring modularity and encapsulation.
- **CSS-in-JS Libraries:**
  - Next.js integrates well with CSS-in-JS libraries like styled-components, Emotion, and @emotion/styled.
  - Enables writing styles directly in JavaScript files, providing dynamic styles and theming.
- **Preprocessor Languages:**
  - Next.js allows the use of preprocessor languages like Sass, Less, and Stylus.
  - Configurable setups enable seamless integration of these languages for styling.
- **Tailwind CSS:**
  - Tailwind CSS, a utility-first framework, integrates easily with Next.js projects.
  - Offers pre-designed utility classes for rapid development and easy customization.
- **Global Styles:**
  - Global CSS files can be imported in `pages/_app.js` in Next.js.
  - Global styles are applied uniformly across the entire application.
- **CSS Frameworks:**
  - Next.js is compatible with popular CSS frameworks such as Bootstrap and Material-UI.
  - These frameworks provide pre-designed components, simplifying the creation of responsive and visually appealing interfaces.

| **Styling Method**      | **Description**                     | **Scoping**          |
| ----------------------- | ----------------------------------- | -------------------- |
| **CSS Modules**         | Modular, local scoping.             | Local                |
| **Styled-jsx**          | Scoped styles as JS objects.        | Component            |
| **CSS-in-JS Libraries** | Write styles in JS files.           | Component            |
| **Preprocessors**       | Sass, Less, Stylus.                 | Component            |
| **Tailwind CSS**        | Utility-first CSS framework.        | Global and Component |
| **Global Styles**       | Global CSS in `pages/_app.js`.      | Global               |
| **CSS Frameworks**      | Pre-designed components and styles. | Global               |

## Compiler

> What is the Complier of next.js ?

- **SWC**
  - The Next.js Compiler, written in Rust using SWC
  - SWC allows Next.js to transform and minify your JavaScript code for production.
- **Bebel**
  - SWC replaces Babel for individual files and Terser for minifying output bundles.
  - Next.js Compiler is 17x faster than Babel and enabled by default since Next.js version 12
  - If you have an existing Babel configuration or are using unsupported features, your application will opt-out of the Next.js Compiler and continue using Babel.

### SWC

> What is SWC in next.js ?

- **Stand For**
  - Scalable Webpack Compiler
- **Definition**
  - **Compiler & Bundler**
    - Is a fast and lightweight Rust-based JavaScript compiler and bundler.
- **Support**
  - **Lasted JS Feature**
    - Supports all of the latest JavaScript features, so you can use them without having to worry about compatibility.
  - **Bebel transformations**
    - It also has its own built-in support for most common Babel transformations.
- **Usage**
  - **Next.js**
    - Is used by Next.js to transpile and bundle your application's code into a single file that can be efficiently loaded by the browser.

## Module Bundler

> What is the Modules ?

- **Break Up Application**
  - developers break up their application into modules, components, and functions that can be used to build larger pieces of their application.
- **Modules Issues**
  - Exporting and importing these internal modules, as well as external third-party packages, creates a complex web of file dependencies.

> What is the Bundling ?

- **Resolve And Merging Modules**
  - Is the process of resolving the web of dependencies and merging (or ‘packaging’) the files (or modules) into optimized bundles for the browser
- **Reducing Number of Requests**
  - Goal of bundling is reducing the number of requests for files when a user visits a web page.

> What is the Module Bundler of next.js ?

- **Module Bundler**
  - **Definition**
    - A tool that combines multiple JavaScript modules into a single file.
    - Improves the performance of web applications by reducing the number of HTTP requests that need to be made to load the application.
  - **Next.js**
    - Turbopack is module bundler of next.js
    - A fast and efficient module bundler designed specifically for Next.js applications.

### Turbopack

> What is the Turbopack in next.js ?

- **Module Bundler**
  - Turbopack is a fast and efficient module bundler designed specifically for Next.js applications.
- **Work**
  - It works by analyzing the Next.js application and identifying the dependencies between the different modules.
  - It then bundles the modules together into a single file, taking into account the order in which the modules are used and the different environments in which the application will be deployed.

### Different

> What is the difference between compiling and bundling in web development?

- **Purpose**
  - **Compiling**
    - Is transforming code into something parable by browsers
  - **Bundling**
    - Is Resolving your applications dependency and reducing the number of files

## Authentication

> How can you handle authentication in Next.js?

- **Doesn't Have Built-in Support:**
  - Next.js does not come with built-in authentication features.
- **Libraries:**
  - Integration with libraries like NextAuth.js or Firebase Authentication is straightforward.
  - These libraries offer robust authentication APIs tailored for Next.js applications.
  - Alternatively, developers can implement custom authentication logic using techniques like cookies or JWT tokens.

## Internationalization

> How Handle Internationalization (i18n) in Next.js ?

- **App Router**
  - **Built-in**
    - Configure routing and content rendering for supporting multiple languages.
    - It involves adapting your site for different locales, including translated content (localization) and internationalized routes.
  - **Libraries**
    - next-Intl , i18n-next
- **Page Router**
  - **Built-in**
    - Next.js has built-in support for internationalized (i18n) routing since v10.0.0.
    - You can specify a list of locales, the default locale, and domain-specific locales.
    - Next.js will automatically handle the routing based on the specified locales.
  - **Libraries**
    - next-Intl , i18n-next
