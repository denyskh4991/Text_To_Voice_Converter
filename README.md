# Text To Speech Converter
<p>The Text To Speech Converter is a web application designed to convert user-inputted text into speech using the browser's speech synthesis capabilities. Built using HTML, CSS, and JavaScript, the app features an intuitive interface where users can input text, select a voice, and listen to the text being spoken aloud.</p>

<h2>Key Features</h2>
<h3>Text to Speech Functionality</h3>
<p>The main feature of the application is its ability to convert text into speech. After the user inputs their text and selects a voice from the dropdown, they can click the "Listen" button to hear the text spoken aloud.</p>
<h3>User Interface</h3>
<h4>Text Input</h4>
<p>A large textarea allows users to input any text they want converted to speech. It has a placeholder that disappears once the user starts typing. <h4>Voice Selection</h4> A dropdown menu provides access to a list of available voices that the user can choose from to hear the text in different accents or languages.</p>
<h4>Control Button</h4>
<p>The app includes a "Listen" button that triggers the speech synthesis. The button is designed with an icon to visually indicate its function.</p> 
<h3>Visual Design</h3>
<p></p>The app has a sleek and modern look, with a gradient background of deep blue and purple shades. Key elements like the button and the app title are highlighted in pink for contrast and emphasis. 
<h3>Responsive Design</h3>
<p>The app is responsive, meaning it adapts to various screen sizes, ensuring usability on both desktop and mobile devices.</p>
<h2>Technical Overview</h2>
<h3>HTML Structure</h3>
<p>The HTML structure consists of a main `div` that contains a header, the textarea, the voice selection dropdown, and the "Listen" button.</p> 
<h3>CSS Styling</h3>
<p>The CSS is used to create the app’s layout and aesthetics.</p>
<h4>Background and Fonts</h4>
<p>The app uses the "Poppins" font, giving it a modern look. The background is a linear gradient with dark tones, providing a sleek contrast against the light text and controls.</p> 
<h4>Layout and Alignment</h4>
<p>All elements are centered on the page using flexbox, ensuring they are easily accessible and well-aligned.</p> 
<h3>JavaScript Functionality</h3>
<p>The interactivity of the application is powered by JavaScript, leveraging the Web Speech API for speech synthesis.</p>
<h4>SpeechSynthesisUtterance Object</h4>
<p>The `SpeechSynthesisUtterance` object is used to store the text and voice settings for speech output. The app initializes this object when the page loads.</p>

    let speech = new SpeechSynthesisUtterance();
    let voices = [];

<h4>- Voice Loading</h4>
<p>The `window.speechSynthesis.onvoiceschanged` event is triggered when the list of voices is updated. The app populates the dropdown with available voices using this function.</p>

    window.speechSynthesis.onvoiceschanged = () => {
        voices = window.speechSynthesis.getVoices();
        speech.voice = voices[0]; // Set the default voice
        voices.forEach((voice, i) => {
            voiceSelect.options[i] = new Option(voice.name, i);
        });
    };

<h4>Voice Selection</h4>
<p>When the user selects a different voice from the dropdown, the app updates the `SpeechSynthesisUtterance` object with the new voice setting.</p>

    voiceSelect.addEventListener("change", () => {
        speech.voice = voices[voiceSelect.value];
    });

<h4>Text to Speech Conversion</h4>
<p>When the "Listen" button is clicked, the app retrieves the text from the textarea, assigns it to the `SpeechSynthesisUtterance` object, and calls the `window.speechSynthesis.speak()` function to start speaking the text.</p>

    document.querySelector("button").addEventListener("click", () => {
        speech.text = document.querySelector("textarea").value;
        window.speechSynthesis.speak(speech);
    });

<h2>Conclusion</h2>
<p>The **Text To Speech Converter** is a straightforward and accessible tool that allows users to convert any text into spoken words using various voices. With its simple interface, sleek design, and responsive layout, it’s ideal for users looking to transform written text into audio for convenience, accessibility, or entertainment. The use of modern web technologies makes it both functional and enjoyable to use.</p>






