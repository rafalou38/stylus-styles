# Pronote resizer

A dark and fancy theme for factorio zone

[![ajouter a stylus](/images/add_en.svg)](https://raw.githubusercontent.com/rafalou38/stylus-styles/master/styles/factorio.zone/style.user.css)

## applies to

```md
factorio.zone
```

## result 😎

![image d'exemple](./exemples/exemple.png)

## Style contents 🧐

<details>
<summary>For the interested 😉</summary>

```css
/* ==UserStyle==
    @name           Factorio dark UI
    @namespace      rafalou38/factorio_dark.user.css
    @author         rafalou38
    @descrtion    `A fancy dark theme for factorio zone with UI changes`
    @version        0.1.0
    @license        MIT
    ==/UserStyle== */
/* FONTS
*/

@-moz-document domain("factorio.zone") {
  @import url("https://fonts.googleapis.com/css2?family=Kdam+Thmor&family=Roboto+Mono:wght@300;400;500&display=swap");

  @font-face {
    font-family: "icons";
    src: url(https://res.cloudinary.com/dr844cxrp/raw/upload/v1621622451/icons_glfuay.ttf);
  }

  /* GENERAL STYLES
    */
  html {
    padding: 0;
  }

  body {
    background: hsl(223, 34%, 5%);
    color: #fff;
  }

  /* HEADER
    */
  header {
    height: 2rem;
    padding: 1rem 2rem;
    background: hsl(223, 34%, 10%);
    display: flex;
    align-items: center;
  }

  /* FACTORIO COLORS!!!!!
    */
  a {
    font-weight: 700;
    color: hsl(29, 89%, 55%);
  }
  a:hover,
  a:focus {
    color: hsl(29, 89%, 65%);
  }

  /* DONATE BUTTON
    */
  .donate {
    height: 2rem;
    right: 2rem;
    top: 1rem;
    display: flex;
    align-items: center;
  }
  .donate > * {
    display: flex;
    align-items: center;
  }

  /* INFO BOX
    */
  .info {
    color: #fffa;
    position: fixed;
    left: 0;
    top: 4em;
    box-sizing: border-box;
    margin: 1em;
    width: 90%;
    max-height: 0;
    overflow: hidden;
    background: hsl(223, 34%, 15%);

    transition: all 0.5s cubic-bezier(0.34, 1.56, 0.64, 1);
    border-radius: 1em;
    z-index: 3;
  }
  .info:hover {
    max-height: 500px;
    padding: 1rem 2rem;
    opacity: 1;
  }

  .info::before {
    /* reveal button */
    position: fixed;
    left: 230px;
    top: 0;
    margin: 0.5em;
    content: "?";
    font-family: "Kdam Thmor", cursive;
    font-size: 1.5em;

    display: grid;
    place-items: center;
    background: hsl(223, 34%, 15%);
    border-radius: 50%;
    width: 2em;
    height: 2em;

    transition: transform 0.5s cubic-bezier(0.34, 1.56, 0.64, 1);
  }
  .info:hover::before {
    transform: scale(1.1);
  }

  /* SIDEBAR
    */
  .control-container {
    position: absolute;
    left: 0;
    flex-direction: column;
    gap: 1em;
    height: calc(100% - 4rem);
    width: 12em;
    margin-top: 4rem;
    box-sizing: border-box;
    padding: 1em;
    margin-left: calc(-12em + 1px);
    transition: margin-left 0.5s cubic-bezier(0.16, 1, 0.3, 1);
    background: hsl(223, 34%, 15%);
    z-index: 2;
  }
  .control-container:hover {
    margin-left: 0;
  }
  .control-container > * {
    width: 100%;
  }

  .control-container::after {
    /* reveal button */
    position: absolute;

    left: 100%;
    top: 10%;
    content: "+";
    width: 2em;
    height: 2em;
    background: hsl(223, 34%, 15%);

    opacity: 0.4;

    font-family: "Kdam Thmor", cursive;
    font-size: 1.5em;

    display: grid;
    place-items: center;
    border-radius: 0 10px 10px 0;

    transition: opacity 0.5s cubic-bezier(0.16, 1, 0.3, 1);
  }
  .control-container:hover::after {
    opacity: 1;
  }

  /* CONTROL ITEMS
    */
  .control-label {
    color: hsl(223, 0%, 63%);
  }

  select {
    width: 100%;
    border: none;
    background: hsl(223, 34%, 30%);
    padding: 0.5em;
  }
  select:hover {
    border: none;
    background: hsl(223, 34%, 40%);
    padding: 0.5em;
  }

  /* IP BOX
    */
  .control-item:nth-child(6) {
    content: "";
    position: fixed;
    right: 0;
    top: 4.5em;
    margin: 0;
    width: min-content;
    height: 3em;
    border-radius: 5px 0 0 5px;
    padding: 0;
    overflow: initial;
    background: hsl(223, 34%, 15%);
    border: 5px solid hsl(223, 34%, 10%);
    border-right: none;
    box-sizing: border-box;
    display: flex;
    justify-content: center;
    flex-direction: row;
  }
  #socket-info {
    height: max-content;
    display: block;
    margin: auto;
    background: transparent;
    border: none;
    width: min-content;
    padding: 0;
    padding-left: 0.5em;
    transition: all 0.5s linear;
    max-width: 360px;
  }
  #socket-info:empty {
    max-width: 0;
    padding: 0;
  }
  .control-item:nth-child(6):before {
    content: "IP";
    background: hsl(223, 34%, 10%);
    width: 3em;
    flex-shrink: 0;
    display: grid;
    place-items: center;
  }

  .control-item:nth-child(6) > label {
    position: absolute;
    top: 0;
    bottom: 0;
    right: 0;
    left: 0;
  }

  /* START/STOP BUTTONS
    */
  .control-item:nth-child(5) {
    position: fixed;
    right: 0;
    bottom: 0;
    width: 4em;
    height: 4em;
    margin: 1em;
    padding: 0;
  }
  .control-item:nth-child(5) > button {
    width: 0;
    height: 0;
    line-height: 100vh;
    margin: 0;
    padding: 0;
    display: grid;
    place-items: center;
  }
  .control-item:nth-child(5) > button::before {
    position: absolute;
    right: 0;
    line-height: normal;
    color: #fff;
    font-family: "icons", arial;
    font-size: 1.5em;
    width: 64px;
    height: 64px;
    display: grid;
    place-items: center;
    border-radius: 4em;
    transition: all 0.1s cubic-bezier(0.16, 1, 0.3, 1);
    pointer-events: all;
  }
  .control-item:nth-child(5) > #start-button::before {
    content: "\e800";
    background: green;
  }
  .control-item:nth-child(5) > #start-button:hover::before {
    content: "start \00A0\e800";
    width: 128px;
  }

  .control-item:nth-child(5) > #stop-button::before {
    content: "\e801";
    background: red;
  }

  .control-item:nth-child(5) > #stop-button:hover::before {
    content: "stop \00A0\e801";
    width: 128px;
  }

  /* MODS
    */
  #mods-list {
    padding: 1em;
    background: hsl(223, 34%, 20%);
  }
  #mods-list label {
    display: flex;
    gap: 0.25em;
    margin-right: 0.25em;
  }

  /* SELECT BUTTONS
    */
  #upload-link,
  #mods-upload-link {
    color: hsl(191, 89%, 55%);
  }
  #delete-link,
  .mod-delete-link > a {
    color: hsl(0, 89%, 55%);
  }
  #download-link {
    color: hsl(123, 89%, 55%);
  }
  #mods-pick {
    font-size: 0;
  }
  #mods-pick::after {
    font-size: 0.8rem;
    content: "[edit]";
  }

  /* COMMANDS INPUT
    */
  body > .input-container {
    margin: 5px 15px;
    display: flex;

    border-radius: 0.25em;
    overflow: hidden;
  }

  body > .input-container > input {
    margin: 0;
    height: 2.5em;
    padding-left: 1em;
    border-radius: 0 0.25em 0.25em 0;
    border: none;
    background: hsl(223, 34%, 25%);
    box-sizing: border-box;
    font-family: "Roboto Mono", monospace;
  }

  body > .input-container > input[disabled] {
    opacity: 0.7;
  }

  body > .input-container > input:focus {
    background: hsl(223, 34%, 30%);
  }

  body > .input-container::before {
    content: ">";
    font-size: 1.5em;
    height: 2.5rem;
    width: 2.5rem;
    border-radius: 0;
    background: hsl(223, 34%, 15%);

    display: grid;
    place-items: center;
  }

  /* CONSOLE
    */
  .output-container {
    padding: 1em;
    padding-bottom: 0;
  }
  .output-area {
    border-radius: 0.25em 0.25em 0 0;
    background: hsl(223, 34%, 20%);
    font-family: "Roboto Mono", monospace;
  }

  /* CONSOLE LABELS
    */
  .output-area > div:before {
    content: "        ";
    padding: 0.25em;
    box-sizing: border-box;
    margin-right: 0.5em;
    border-bottom-left-radius: 0.25em;
    color: white;
  }
  .output-area > div:last-child {
    margin-bottom: 2em;
  }

  .output-info {
    color: dodgerblue;
  }
  .output-console {
    color: limegreen;
  }
  .output-log {
    color: #dadada;
  }

  .output-info::before {
    background: hsl(224, 73%, 51%);
  }
  .output-log::before {
    background: hsl(29, 89%, 55%);
  }
  .output-console::before {
    background: #393;
  }

  .output-info:not(.output-info + .output-info)::before {
    content: "info    ";
    border-top-left-radius: 0.25em;
    margin-top: 0.5em;
  }
  .output-log:not(.output-log + .output-log)::before {
    content: "log     ";
    border-top-left-radius: 0.25em;
    margin-top: 0.5em;
  }
  .output-console:not(.output-console + .output-console)::before {
    content: "console ";
    border-top-left-radius: 0.25em;
    margin-top: 0.5em;
  }

  .output-console:not(.output-console + .output-console) {
    /* first of a group*/
    margin-top: 1em;
    z-index: 1;
    position: relative;
  }
  .output-info:not(.output-info + .output-info) {
    /* first of a group*/
    margin-top: 1em;
    z-index: 1;
    position: relative;
  }
  .output-log:not(.output-log + .output-log) {
    /* first of a group*/
    margin-top: 1em;
    z-index: 1;
    position: relative;
  }
}
```

</details>

## Like 👍 🌟

If you like this style like with the **star** in the top right and **share** with your friends.

<br>
<br>
<br>
<br>

[![revenir a la liste](/images/revenir%20a%20la%20liste.svg)](https://github.com/rafalou38/stylus-styles/)
