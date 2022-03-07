# Send Bulk WhatsApp Messages
**Using console script you can send messages in bulk to anyone through your browser.**
- Connect with whats app web
- Open/click on participant/friend to whom you want to send message
- Run below script in your browser console
```
 count = 1;
 function sendBulkWhatsAppMessages()
{
  
    messageBox = document.querySelectorAll("[contenteditable='true']")[1];
  
    message = `MyMessage`; // Replace MyMessage with your message use to add spaces to your message
  
    counter = 50; // Replace 5 with the number of times you want to send your message
  
    for (i = 0; i < counter; i++) {
		count = count+1;
        uiEvent = document.createEvent("UIEvents");
        messageBox.innerHTML = `*${count}.*` + message.replace(/ /gm, ''); // test it
        uiEvent.initUIEvent("input", true, true, window, 1);
        messageBox.dispatchEvent(uiEvent);
  
        eventFire(document.querySelector('span[data-icon="send"]'), 'click');
    }
}  
var eventFire = (el, elType) => {
    var mouseEvent = document.createEvent("MouseEvents");
    mouseEvent.initMouseEvent
     (elType, true, true, window, 0, 0, 0, 0, 0, false, false, false, false, 0, null);
    el.dispatchEvent(mouseEvent);
};
const interval = setInterval(function() {
   myFunc()
 }, 5000);
 ```
