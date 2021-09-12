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
