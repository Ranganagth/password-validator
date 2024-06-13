# Password Validator

This is a simple HTML/CSS/JavaScript project that provides a visual validation for a password input field. It checks for the presence of an uppercase letter, a number, a special character, and a minimum length of 8 characters. Additionally, it includes a feature to toggle the visibility of the password.

## Features

- **Password Validation**: Checks for uppercase letters, numbers, special characters, and a minimum length of 8 characters.
- **Password Visibility Toggle**: Allows users to toggle the visibility of the password using an eye icon.
- **Responsive Design**: The layout is responsive and adapts to different screen sizes.

## Files

- `index.html`: The main HTML file that contains the structure of the webpage.
- `style.css`: The CSS file that styles the webpage.
- `script.js`: The JavaScript file that handles the password validation logic and the password visibility toggle.

## Usage

### HTML Structure

The HTML file (`index.html`) includes the following key sections:

1. **Password Input Field**: An input field for the password with an `oninput` event to trigger validation.
    ```html
    <input type="password" placeholder="Password" id="myPass" required oninput="textChange()">
    ```

2. **Password Visibility Toggle**: An image that toggles the visibility of the password when clicked.
    ```html
    <img class="eye-close" id="img1" src="https://i.postimg.cc/HWMtCN1m/eye-close.png" alt="eye" onclick="toggle()">
    ```

3. **Password Validation Indicators**: A set of indicators that show whether the password meets each of the validation criteria.
    ```html
    <div class="validator">
        <p id="capital"><i class="fas fa-times"></i><i class="fas fa-check"></i><span>Upper Case</span></p>
        <p id="number"><i class="fas fa-times"></i><i class="fas fa-check"></i><span>Number</span></p>
        <p id="special-char"><i class="fas fa-times"></i><i class="fas fa-check"></i><span>Special Character</span></p>
        <p id="more-than-8"><i class="fas fa-times"></i><i class="fas fa-check"></i><span>More than 8 characters</span></p>
    </div>
    ```

### Styling

The CSS file (`style.css`) styles the webpage and includes:

- Font import from Google Fonts.
- Styling for the body, container, and formbox.
- Custom styles for the password input field and visibility toggle icon.
- Styles for the validation indicators.

### JavaScript Logic

The JavaScript file (`script.js`) handles:

- **Password Visibility Toggle**: Toggles the password input type between `password` and `text` and changes the eye icon.
    ```javascript
    function toggle() {
        myFunction();
        if (state) {
            document.getElementById("myPass").setAttribute("type", "password");
            lockIcon.classList.remove("color-change");
            inner.classList.remove("inner-hover");
            state = false;
        } else {
            document.getElementById("myPass").setAttribute("type", "text");
            lockIcon.classList.add("color-change");
            inner.classList.add("inner-hover");
            state = true;
        }
    }
    ```

- **Password Validation**: Checks the password against the criteria and updates the validation indicators accordingly.
    ```javascript
    function textChange() {
        if (password.value.match(/[A-Z]/) != null)
            valid('capital', 'fa-check', 'fa-times');
        else
            invalid('capital', 'fa-check', 'fa-times');

        if (password.value.match(/[0-9]/) != null)
            valid('number', 'fa-check', 'fa-times');
        else
            invalid('number', 'fa-check', 'fa-times');

        if (password.value.match(/[!@#$%^&*]/) != null)
            valid('special-char', 'fa-check', 'fa-times');
        else
            invalid('special-char', 'fa-check', 'fa-times');

        if (password.value.length >= 8)
            valid('more-than-8', 'fa-check', 'fa-times');
        else
            invalid('more-than-8', 'fa-check', 'fa-times');
    }
    ```

## How to Run

1. **Clone the repository** (or copy the files):
    ```bash
    git clone https://github.com/Ranganagth/password-validator.git
    ```

2. **Open `index.html` in a web browser**:
    You can simply open the `index.html` file in any modern web browser to see the password validator in action.

## Dependencies

- **Font Awesome**: For the lock and validation icons.
    ```html
    <script src='https://kit.fontawesome.com/1c2c2462bf.js'></script>
    ```

## License

This project is open source and available under the [MIT License](https://opensource.org/licenses/MIT).

### Acknowledgments
- Inspiration from various CSS and design tutorials - [Codepen](https://codepen.io/).
- Icon by [icons8.com](https://icons8.com/icons/set/r)
- Inspried by work from [Coding thai](https://codepen.io/Codingthai)