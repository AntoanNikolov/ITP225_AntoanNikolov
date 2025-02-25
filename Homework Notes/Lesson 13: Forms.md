## Building forms in HTML  

- labels are used to associate form with corresponding value  
- Input types include text fields, radio menus, checkbox, dropdown, textarea, submit  

Example of text form:
```
<p>Many field types...</p>

<form method="post" action="more.php">
  <p>
    <label for="inp01">Account:</label>
    <input type="text" name="account" id="inp01" size="40">
  </p>
  <p>
    <label for="inp02">Password:</label>
    <input type="password" name="pw" id="inp02" size="40">
  </p>
  <p>
    <label for="inp03">Nick Name:</label>
    <input type="text" name="nick" id="inp03" size="40">
  </p>
</form>
```  
## Forms and CSRF (Cross site request forgery)
- Idea is that a rogue site generates a page that posts data to a legitimate site where the user is logged in via a session cookie, the form is submitted to the legitimate site and the cookie is included, the legitimate site accepts the requiest because of the cookie value  
- CSRF Defense - the legitimate site chooses a large random number (the csrf token) and puts it in the session. The csrf token is included in the legitimate site's POST form. The site rejects the request if the csrtf token does not match the one of the session.
- Django has CSRF protection built-in