# Alessia8
A multi-project repo for simple experimental web technology (Alessia Orro Number 8 in Europen Champion Italian Volleyball Team)

*basicnodetseslint* has its own readme.

## easywebcomps
This is an experimental project to demonstrate how dead simple is to make web components with plain in-HTML JavaScript and how to improve the performance with lit-html.
This is not even a NodeJS project, it is just a pure HTML/JavaScript page just to demonstrate the fundamental concept of working with web components.
Simply open these HTML files with [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer).

- **index.html** - the my-counter web component was implemented plain JavaScript using Shadow Dom and a custom template and slots.

- **index-litshadowslots.html** - uses Lit from unpkg.com and implements shadow DOM. The webpage links Bootstrap 5, too from CDN, but it is not trivial to use Bootstrap in shadow DOM via CDM. You can use fetch the CSS and use lits unsafeCSS to apply in every custom element. So definitely doable, but then it's way easier then to create a Node project with Vite and TypeScript as [demonstrated](https://white-pond-01b194d03.azurestaticapps.net/) in [cristina10#tslitstrap](https://github.com/nemethmik/cristina10#tslitstrap)

- **index-litlightdom.html** - uses Lit from unpkg.com, too, but implements Ligth DOM web component, so slots are not supported.
This is a major reason most developer workshops are reluctant to adopt web components. When you need composition you are forced to use Shadow DOM, which is an unnecessary hurdle for most applications and projects. React JSX supports composable structures in Light DOM, which is not possible with Web Components.

