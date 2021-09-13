# Forms

## Present a user with a search form field

    <form>
        <p><label>Search <input type="search" name="query"></label></p>
        <p><button type="submit">Submit</button></p>
    </form>

## Form to provide contact information

    <form>
        <fieldset>
            <legend>Contact Information</legend>
            <p><label>E-mail address <input type="email" name="email"></label></p>
            <p><label>Web site <input type="url" name="website"></label></p>
            <p><label>Telephone number <input type="tel" name="phone"></label></p>
        </fieldset>
        <p><button type="submit">Submit</button></p>
    </form>

Specify your own error massage by adding title attribute to input field.

    <input type="url" name="website" title="That doesn't look like a valid web address.">

## Date and Time

datetime

    <form>
        <p><label>Appointment Date and Time <input type="datetime" name="dateAndTime"></label></p>
        <p><button type="submit">Submit</button></p>
    </form>

date and time

    <form>
        <fieldset>
            <legend>Appointment Request</legend>
            <p><label>Date <input type="date" name="date"></label></p>
            <p><label>Time <input type="time" name="time"></label></p>
        </fieldset>
        <p><button type="submit">Submit</button></p>
    </form>

min and max , can limit the range of input field

    <form>
        <fieldset>
            <legend>Appointment Request</legend>
            <p><label>Date <input type="date" name="date" min="2011-03-15" max="2012-03-14"></label></p>
            <p><label>Time <input type="time" name="time" min="08:00" max="18:00"></label></p>
        </fieldset>
        <p><button type="submit">Submit</button></p>
    </form>

number input

    <form>
        <p><label>Quantity <input type="number" name="quantity"></label></p>
        <p><button type="submit">Submit</button></p>
    </form>

Step attribute to specify the amount by which the value should be incremented.

    <form>
        <p><label>Quantity (must order in pairs of 2) <input type="number" name="quantity" min="2" max="20" step="2"></label></p>
        <p><button type="submit">Submit</button></p>
    </form>

## Select a number from a range

    <form>
        <p><label>Volume <input type="range" name="volume" min="0" max="10" step=".5" value="5"></label></p>
    </form>

## select a color

    <form>
        <p><label>Background color <input type="color" name="bg"></label></p>
        <p><label>Foreground color <input type="color" name="fg"></label></p>
        <p><button type="submit">Submit</button></p>
    </form>

## Combo box

Use the HTML5 datalist element to create a list of suggestions using the option element, and associate the list with an input element via the list attribute

    <form>
        <p><label>Donation amount <input type="text" name="donation" list="donations"></label></p>
        <datalist id="donations">
            <option value="10.00">10.00</option>
            <option value="25.00">25.00</option>
            <option value="50.00">50.00</option>
        </datalist>
        <p><button type="submit">Submit</button></p>
    </form>

## Require a form field

required attribute on any form field that must be completed in order to submit the form.

    <form>
        <fieldset>
            <legend>Login</legend>
            <p><label>Username <input type="text" name="username" required></label></p>
            <p><label>Password <input type="password" name="pwd" required></label></p>
        </fieldset>
        <p><button type="submit">Submit</button></p>
    </form>

## Focus in form field

    <form>
        <p><label>Search <input type="search" name="query" autofocus></label></p>
        <p><button type="submit">Submit</button></p>
    </form>

## Display hint

placeholder attribute is used to specify instructional text when the user is not focused in the form field

    <form>
        <fieldset>
            <legend>Contact Information</legend>
            <p><label>E-mail address <input type="email" name="email" placeholder="user@domain.com"></label></p>
            <p><label>Web site <input type="url" name="website" placeholder="http://www.domain.com/"></label></p>
            <p><label>Telephone number <input type="tel" name="phone" placeholder="123-123-1234"></label></p>
        </fieldset>
        <p><button type="submit">Submit</button></p>
    </form>

## Prevent autocompletion tools

Set the HTML5 autocomplete attribute to "off" for any individual input field.

    <form>
        <fieldset>
            <legend>Login</legend>
            <p><label>Username <input type="text" name="username"></label></p>
            <p><label>Password <input type="password" name="pwd" autocomplete="off"></label></p>
        </fieldset>
        <p><button type="submit">Submit</button></p>
    </form>

## Restrict the value of an input field

Use the HTML5 pattern attribute to specify a regular expression that will be used to validate the user’s input

    <form>
        <p><label>Telephone number <input type="tel" name="phone" pattern="[2-9][0-9]{2}-[0-9]{3}-[0-9]{4}" title="North American format: XXX-XXX-XXXX"></label></p>
        <p><button type="submit">Submit</button></p>
    </form>

Use the Modernizr JavaScript library to add support of HTML5 input types and attributes work in browsers that do not support HTML5.
