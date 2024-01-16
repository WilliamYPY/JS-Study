# Delay the Loading of JS Scripts

## Why？

If scripts are not set to load with a delay (i.e., deferred), the default behavior is that the browser will load and execute scripts as it encounters them while parsing the HTML document. 

1. **Sequential Loading and Execution**: Scripts are loaded and executed in the order they appear in the HTML. If a script is encountered, the browser must load and execute it before continuing with the parsing of the HTML.
2. **Potential Blocking of Page Rendering**: Since the browser stops parsing the rest of the HTML until the script is fully loaded and executed, this can lead to a delay in rendering the page, especially if the script is large or relies on a slow network connection.
3. **Immediate Availability of Script Functionality**: One advantage, however, is that any functions or features provided by the script are available immediately after the script is loaded, which can be important for scripts that are integral(必须的) to the page content. 

## How？

1. **`defer` Attribute**:
   - When you add the `defer` attribute to a `<script>` tag, it instructs the browser to download the script while parsing the HTML, but to wait until the HTML parsing is complete before executing it.
   - This ensures that the script doesn't block the rendering of the page and is executed only after the document is fully parsed.
   - Scripts with `defer` are executed in the order they appear in the document.
2. **`async` Attribute**:
   - The `async` attribute, like `defer`, allows the script to be downloaded asynchronously while the browser continues to parse the HTML.
   - The key difference is that an `async` script executes as soon as it is downloaded, which could be during HTML parsing. This means it could interrupt the parsing process.
   - `async` is best used for scripts that do not depend on other scripts and do not modify the DOM (e.g., analytics scripts).
3. **Dynamically Creating a DOM Script**:
   - This involves using JavaScript to create a `<script>` element and append it to the document.
   - You can control when and where this script is loaded and executed, which gives you a lot of flexibility.
   - This is often used for loading scripts that aren't critical to the initial page load, like third-party widgets or tracking scripts.
4. **`setTimeout` Method**:
   - `setTimeout` can be used to delay the execution of a script. You wrap the script or function you want to delay in a `setTimeout` call and specify a delay time in milliseconds.
   - It's important to note that `setTimeout` doesn't pause the parser but schedules the script execution to a later time.
   - This can be useful for non-essential operations that don't need to run immediately as the page loads.
5. **Placing Scripts at the Bottom of the Page**:
   - By placing `<script>` tags just before the closing `</body>` tag, you ensure that the browser first loads and renders the entire HTML document.
   - Since the scripts are loaded at the end, they won't block the rendering of the page content.
   - This is a simple and effective technique, especially for scripts that need to interact with elements on the page, as it guarantees that all the HTML elements are loaded before the script runs.