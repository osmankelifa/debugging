## hi_debugging

# A list of bugs identified:

- **Line 3** --
  **_Syntax error_**: single quote instead of double quote:
  Found error visually in code editor: the error is highlighted in red.

  `"search’` => `"search”`

- **Lines 3-6** --
  **_Syntax error_**: missing # to select ID tag.

  Found error in browser inspection tool :

  > “Uncaught TypeError: Cannot read properties of null (reading 'addEventListener’)”

- **Line 4** --
  **_Syntax error_**: missed letter:

  `querySelectr` => `querySelector`

  Found error in Dev Tools browser:

  > “script.js:4 Uncaught TypeError: document.querySelectr is not a function”

- **Line 40** --
  **_Syntax error_**: missed parenthesis after `function`, around `e`

  Found error in Dev Tools browser:

  > “Uncaught SyntaxError: Unexpected token '{' (at script.js:40:46)”

- **Line 41** --
  **_Runtime error_**: missed `e` before `preventDefault` method:

  `preventDefault();` => `e.preventDefault();`

  Found error: unexpected behavior: page refreshed by clicking on button & throughout reading documentation about preventDefault method.

- **Lines 28-37** --
  **_Logical error_**: conditions do not correspond to the task.

  From:

  ```
  if (temp > 0) {
  messageEl.textContent = 'Winter is coming...';
  } else if (temp > 0) {
  messageEl.textContent = 'Sweater weather!';
  } else if (temp > 10) {
  messageEl.textContent =
  'Put a jacket on and regret it as soon as you start moving';
  } else if (temp > 20) {
  messageEl.textContent = "Hotter outside than Taylor Swift's latest single";
  }
  ```

  To:

  ```
  if (temp < 0) {
  messageEl.textContent = 'Winter is coming...';
  } else if (temp > 20) {
  messageEl.textContent = "Hotter outside than Taylor Swift's latest single";
  } else if (temp > 10) {
  messageEl.textContent =
  'Put a jacket on and regret it as soon as you start moving';
  } else if (temp >= 0) {
  messageEl.textContent = 'Sweater weather!';
  }
  ```

- **Line 19** --
  **_Syntax error_**: Using variable inside string should be with backticks `` but not single quotes ‘’:

  \'\${temp}°C' => &#96;${temp}°C&#96;

- **Line 17** --
  **_Runtime error_**: there is no data in `data.temp`, missing key `main`.

  Error found by console.log() - checking what data structure inside variable data.

  `let temp = data.temp - 273.15;` => `let temp = data.main.temp - 273.15;`

- **Line 17** --
  **_Runtime error_**: temperature should be rounded to an integer.

  Error found visually by running the project in the browser.

  `let temp = data.main.temp - 273.15;` => `let temp = Math.round(data.main.temp - 273.15);`
# debugging
