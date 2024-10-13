# Hello World
## This is my site
### Here are a lot of funny things

Here is a fun fact:

Who invented the granola bar?
MIT's website credits inventor Stanley
 Mason with creating the first granola bar. 
 This is the guy who invented the first disposable 
 contoured diaper, the squeezable ketchup bottle, 
 and the dental floss dispenser, so it's not hard to 
 picture him coming up with the granola bar.


**Bear**

*Meow*

>Karhu loikkasi joen yli
>>Kissa maukaisi

##### Shopping list
1. Tomato
2. Milk
3. Butter
4. Bread
    1. Wholegrain
5. Coffee

There are `many` different things

 ![Pat and Mat](/assets/images/pat&mat.jpg)

This site was built using [GitHub Pages](https://pages.github.com/)

---

### Lähetä viesti Teams :D

<form id="teamsForm">
    <label for="message">Message:</label>
    <input type="text" id="message" name="message" required>
    <button type="submit">Send</button>
</form>

<script>
    const webhookUrl = 'https://prod-230.westeurope.logic.azure.com:443/workflows/ef1e6e481c444bacbd6e1b55273703cf/triggers/manual/paths/invoke?api-version=2016-06-01&sp=%2Ftriggers%2Fmanual%2Frun&sv=1.0&sig=pPgEdvhkHxB1zwp1-O8gRMvv42k9m2EJfUfY8i9BPUU';

    document.getElementById('teamsForm').addEventListener('submit', function(e) {
        e.preventDefault();

        const message = document.getElementById('message').value;

        fetch(webhookUrl, {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json'
            },
            body: JSON.stringify({
                text: message
            })
        })
         
        .then(response => {
            if (response.ok) {
                alert('Message sent!');
            } else {
                alert('Error sending message');
            }
        })
        .catch(error => {
            console.error('Error:', error);
            alert('Error sending message');
        });
    });
</script>
