# AI Test Code Generator (Chrome extension)

A Manifest V3 Chrome extension that writes test automation code for the page you're looking at. Select elements on any live page, pick a framework and language, and it generates Page Objects or step definitions from the real DOM, not from a guess.

## How it works

1. Open the side panel from the toolbar icon.
2. Click elements on the page; a content script captures their `outerHTML`.
3. Choose the target: **Selenium, Playwright, Cypress or Puppeteer** in **Java, C#, Python or TypeScript**, or a preset such as *Selenium-Java Page Object*, *Cucumber feature*, *Cucumber + Selenium-Java steps* or *Cypress Page Object*.
4. The captured DOM and a framework-specific prompt go to the selected model; the answer is rendered in a chat view with syntax highlighting.

- **Providers:** Groq and OpenAI (chat completions), chosen per session with a model picker.
- **Token warning:** a configurable threshold warns before sending a very large DOM selection.
- API keys are stored in `chrome.storage`, never in the source.

## Install (developer mode)

1. Clone this repo.
2. Open `chrome://extensions`, enable **Developer mode**.
3. **Load unpacked** → select the repo folder.
4. Open the side panel and add your API key in settings.

## Tech

JavaScript · Chrome Extensions API (Manifest V3, side panel, content scripts, `chrome.storage`) · marked · Prism
