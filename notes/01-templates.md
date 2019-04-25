# Templates

To describe the HTML portion of a web application, Ember uses declarative templates based on [Handlebars.js](https://handlebarsjs.com/) markup.

For now, we'll just focus on one of these files: `app/templates/application.hbs`. Markup you put in this template will be shown anytime your app is on the screen, regardless of URL (we'll get into URLs later).

## Starting with regular HTML and CSS

For now, paste the following HTML in `app/templates/application.hbs`

<details>

<summary>Click to show HTML</summary>

```html
<nav
  class="bg-indigo-darkest border-indigo-darkest border-r-2 pt-2 text-purple-lighter flex-none hidden sm:block"
>
  <a
    href="/li"
    class="cursor-pointer rounded-lg p-2 pl-4 block no-underline opacity-25 opacity-100 ember-view"
  >
    <div
      class="bg-white h-12 w-12 flex items-center justify-center text-black text-2xl font-semibold rounded-lg mb-1 overflow-hidden"
    >
      <img
        src="https://gravatar.com/avatar/0ca1be2eaded508606982feb9fea8a2b?s=200&amp;d=https://upload.wikimedia.org/wikipedia/commons/thumb/c/ca/LinkedIn_logo_initials.png/240px-LinkedIn_logo_initials.png"
        alt="LinkedIn"
      />
    </div> </a
  ><a
    href="/ms"
    class="cursor-pointer rounded-lg p-2 pl-4 block no-underline opacity-25 ember-view"
  >
    <div
      class="bg-white h-12 w-12 flex items-center justify-center text-black text-2xl font-semibold rounded-lg mb-1 overflow-hidden"
    >
      <img
        src="https://gravatar.com/avatar/0ca1be2eaded508606982feb9fea8a2b?s=200&amp;d=https://upload.wikimedia.org/wikipedia/commons/thumb/4/44/Microsoft_logo.svg/200px-Microsoft_logo.svg.png"
        alt="Microsoft"
      />
    </div>
  </a>
  <div class="cursor-pointer p-4">
    <div
      class="bg-white opacity-25 h-12 w-12 flex items-center justify-center text-black text-2xl font-semibold rounded-lg mb-1 overflow-hidden"
    >
      <svg
        class="fill-current h-10 w-10 block"
        xmlns="http://www.w3.org/2000/svg"
        viewbox="0 0 20 20"
      >
        <path
          d="M16 10c0 .553-.048 1-.601 1H11v4.399c0 .552-.447.601-1 .601-.553 0-1-.049-1-.601V11H4.601C4.049 11 4 10.553 4 10c0-.553.049-1 .601-1H9V4.601C9 4.048 9.447 4 10 4c.553 0 1 .048 1 .601V9h4.399c.553 0 .601.447.601 1z"
        ></path>
      </svg>
    </div>
  </div>
</nav>

<section
  class="bg-indigo-darker text-purple-lighter flex-none w-64 pb-6 hidden sm:flex flex-col"
>
  <header class="text-white mb-2 mt-3 px-4 flex justify-between">
    <div class="flex-auto">
      <h1 class="font-semibold text-xl leading-tight mb-1 truncate">
        LinkedIn
      </h1>

      <div class="flex items-center mb-6">
        <svg class="h-2 w-2 fill-current text-green mr-2" viewbox="0 0 20 20">
          <circle cx="10" cy="10" r="10"></circle>
        </svg>
        <span class="text-white opacity-50 text-sm">Mike North</span>
      </div>
    </div>

    <div>
      <svg
        class="h-6 w-6 fill-current text-white opacity-25"
        viewbox="0 0 20 20"
      >
        <path
          d="M14 8a4 4 0 1 0-8 0v7h8V8zM8.027 2.332A6.003 6.003 0 0 0 4 8v6l-3 2v1h18v-1l-3-2V8a6.003 6.003 0 0 0-4.027-5.668 2 2 0 1 0-3.945 0zM12 18a2 2 0 1 1-4 0h4z"
          fill-rule="evenodd"
        ></path>
      </svg>
    </div>
  </header>

  <nav class="mb-8 flex-1">
    <div class="px-4 mb-2 text-white flex justify-between items-center">
      <h2 class="opacity-75 text-lg">Channels</h2>

      <button aria-label="Join channel" role="button" class="text-white">
        <svg
          class="fill-current h-4 w-4 opacity-50"
          xmlns="http://www.w3.org/2000/svg"
          viewbox="0 0 20 20"
        >
          <path
            d="M11 9h4v2h-4v4H9v-4H5V9h4V5h2v4zm-1 11a10 10 0 1 1 0-20 10 10 0 0 1 0 20zm0-2a8 8 0 1 0 0-16 8 8 0 0 0 0 16z"
          ></path>
        </svg>
      </button>
    </div>

    <a
      href="/li/general"
      class="py-1 px-4 text-white no-underline block opacity-75 bg-teal-dark ember-view"
    >
      <span aria-hidden="true">#</span> general
    </a>
  </nav>

  <footer class="mx-4 mb-2 text-white">
    <button class="text-white rounded bg-grey-dark hover:bg-red-darker p-2">
      Logout
    </button>
  </footer>
</section>

<main class="flex-1 flex flex-col bg-white overflow-hidden">
  <header class="border-b flex px-6 py-2 items-center flex-none">
    <div>
      <h3 class="text-grey-darkest mb-1 font-extrabold">
        #general
      </h3>

      <h4 class="text-grey-dark text-sm truncate">
        foo bar baz (professional)
      </h4>
    </div>

    <form
      class="ml-auto md:block border border-grey rounded-lg pl-3 pr-2 py-1 flex flex-row-reverse items-center"
    >
      <label for="search" class="sr-only">Search messages</label>

      <input
        placeholder="Search"
        class="appearance-none"
        id="search"
        type="search"
      />

      <button aria-label="Submit search">
        <svg
          class="fill-current text-grey h-4 w-4"
          xmlns="http://www.w3.org/2000/svg"
          viewbox="0 0 20 20"
        >
          <path
            d="M12.9 14.32a8 8 0 1 1 1.41-1.41l5.35 5.33-1.42 1.42-5.33-5.34zM8 14A6 6 0 1 0 8 2a6 6 0 0 0 0 12z"
          ></path>
        </svg>
      </button>
    </form>
  </header>

  <div class="py-4 flex-1 overflow-y-scroll" role="list">
    <!---->
  </div>

  <footer class="pb-6 px-4 flex-none">
    <form
      class="flex w-full rounded-lg border-2 border-grey overflow-hidden"
      aria-labeledby="message-label"
    >
      <h1 id="message-label" class="sr-only">
        Message Input
      </h1>

      <button
        class="text-3xl text-grey border-r-2 border-grey p-2"
        aria-label="File menu"
        type="button"
      >
        <svg
          class="fill-current h-6 w-6 block"
          xmlns="http://www.w3.org/2000/svg"
          viewbox="0 0 20 20"
        >
          <path
            d="M16 10c0 .553-.048 1-.601 1H11v4.399c0 .552-.447.601-1 .601-.553 0-1-.049-1-.601V11H4.601C4.049 11 4 10.553 4 10c0-.553.049-1 .601-1H9V4.601C9 4.048 9.447 4 10 4c.553 0 1 .048 1 .601V9h4.399c.553 0 .601.447.601 1z"
          ></path>
        </svg>
      </button>

      <label for="message" class="sr-only">Message</label>

      <input
        id="message-input"
        value
        class="w-full px-4"
        placeholder="Message #general"
        autofocus
        type="text"
      />

      <button
        disabled
        class="font-bold uppercase opacity-50 bg-grey-dark text-white border-teal-dark p-2"
      >
        SEND
      </button>
    </form>
  </footer>
</main>
```

</details>

and the following in `app/styles/app.css`

<details>
<summary>Click to show CSS</summary>

```css
@import 'tailwind.css';

.hover-target .show-on-hover {
  opacity: 0;
  filter: alpha(opacity=0);
}
.hover-target:hover .show-on-hover,
.hover-target .show-on-hover:focus,
.hover-target .show-on-hover:active {
  opacity: 1;
  filter: alpha(opacity=1);
}

.sr-only {
  clip-path: inset(50%);
  clip: rect(1px, 1px, 1px, 1px);
  height: 1px;
  margin: -1px;
  overflow: hidden;
  padding: 0;
  position: absolute;
  width: 1px;
}
```

</details>

Now visit `http://localhost:4200`. You should see something on the screen like this

<p align='center'>

<img src="./img/app.png" width=800>

</p>
