# Alessia8
A multi-project repo for simple experimental web technology (Alessia Orro Number 8 in Europen Champion Italian Volleyball Team)

*basicnodetseslint* has its own readme.

## easywebcomps
This is an experimental project to demonstrate how dead simple is to make web components with plain in-HTML JavaScript and how to improve the performance with lit-html.
This is not even a NodeJS project, it is just a pure HTML/JavaScript page just to demonstrate the fundamental concept of working with web components.
Simply open these HTML files with [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer).

- **index.html** - the my-counter web component was implemented plain JavaScript using Shadow Dom and a custom template and slots.

- **index-litshadowslots.html** - uses Lit from unpkg.com and implements shadow DOM. The webpage links Bootstrap 5, too from CDN, but it is not trivial to use Bootstrap in shadow DOM via CDM. You can use fetch the CSS and use lits unsafeCSS to apply in every custom element. So definitely doable, but then it's way easier then to create a Node project with Vite and TypeScript as [demonstrated](https://white-pond-01b194d03.azurestaticapps.net/) in [cristina10#tslitstrap](https://github.com/nemethmik/cristina10#tslitstrap)
    - Adding Bootstrap support was easier than I had thought
    ```html
        <link id=bootstrap href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3" crossorigin="anonymous">
        <script type="module">
            import { LitElement, html, css, render } from "https://unpkg.com/lit-element/lit-element.js?module"

            class BLitElement extends LitElement {
                connectedCallback() {
                    super.connectedCallback()
                    let linkElem = document.getElementById("bootstrap")
                    if(linkElem && linkElem.href && linkElem.href.includes("bootstrap")) {
                        //console.log("Bootrap link element found",linkElem)
                        linkElem = linkElem.cloneNode(true)
                        linkElem.removeAttribute("id") // To keep the bootstrap ID globally unique 
                    } else {
                        console.warn("Bootrap link element not found; creating a default link. Add an id=bootstrap to your link element.")
                        linkElem = document.createElement("link")
                        linkElem.setAttribute("rel", "stylesheet")
                        linkElem.setAttribute("href", "https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css")
                    }
                    this.shadowRoot.appendChild(linkElem)
                }
            }
    ```
    This *BLitElement* is then should be used as base class for classes which want Bootstrap styling.

- **index-litlightdom.html** - uses Lit from unpkg.com, too, but implements Ligth DOM web component, so slots are not supported.
This is a major reason most developer workshops are reluctant to adopt web components. When you need composition you are forced to use Shadow DOM, which is an unnecessary hurdle for most applications and projects. React JSX supports composable structures in Light DOM, which is not possible with Web Components.

