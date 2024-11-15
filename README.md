# Joke Teller

This project is a joke-telling app created as part of the course "JavaScript Web Projects: 20 Projects to Build Your Portfolio" by Zero To Mastery. It fetches a random programming joke from an API and uses text-to-speech functionality to read the joke out loud.

## Table of contents

- [Joke Teller](#joke-teller)
  - [Table of contents](#table-of-contents)
  - [Overview](#overview)
    - [Screenshot](#screenshot)
    - [Links](#links)
  - [My process](#my-process)
    - [Built with](#built-with)
    - [What I learned](#what-i-learned)
    - [Useful resources](#useful-resources)
  - [Author](#author)
  - [Acknowledgments](#acknowledgments)

## Overview

This project enables users to:
- Click a button to hear a random programming joke.
- Enjoy jokes read out loud using text-to-speech via the VoiceRSS API.
- Listen to jokes with safe content, as inappropriate jokes are filtered out.

### Screenshot

![](./screenshot.png)

### Links

- Live Site URL: [DT Code](https://joke-teller.dtcode.se/)

## My process

### Built with

- HTML5 for structure
- CSS3 for styling
- JavaScript (ES6+) for functionality
- JokeAPI to fetch random programming jokes
- VoiceRSS API for text-to-speech functionality

### What I learned

In this project, I learned how to use an API to fetch random jokes and implement text-to-speech functionality using VoiceRSS. I also gained experience with async/await functions and learned how to control button states to enhance user interaction.

Example code for fetching a joke and playing it with text-to-speech:

```js
async function getJokes() {
    let joke = '';
    const apiUrl = 'https://v2.jokeapi.dev/joke/Programming?blacklistFlags=nsfw,religious,political,racist,sexist,explicit';
    try {
        const response = await fetch(apiUrl);
        const data = await response.json();
        joke = data.setup ? `${data.setup} ... ${data.delivery}` : data.joke;
        // Text-to-Speech
        tellMe(joke);
        toggleButton();
    } catch (error) {
        console.log('fetch error', error);
    }
}
```

### Useful resources

- [VoiceRSS API Documentation](https://www.voicerss.org/) - This helped me understand how to use the VoiceRSS API for text-to-speech functionality.
- [JokeAPI Documentation](https://jokeapi.dev/) - This API provided the programming jokes used in the app.

## Author

- GitHub - [@dantvi](https://github.com/dantvi)
- LinkedIn - [@danieltving](https://www.linkedin.com/in/danieltving/)

## Acknowledgments

Special thanks to Zero To Mastery for providing the course and project structure.
