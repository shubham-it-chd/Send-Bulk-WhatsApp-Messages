# Send-Bulk-WhatsApp-Messages
Using console script you send bulk message to anyone through your browser.
//connect with whats app web, open participant to whom you want to send message.. then just run below script in your console
 count = 1;
 function myFunc()
{
  
    messageBox = document.querySelectorAll("[contenteditable='true']")[1];
  
    message = `MyMessage`; // Replace My Message with your message use   to add spaces to your message
  
    counter = 50; // Replace 5 with the number of times you want to send your message
  
    for (i = 0; i < counter; i++) {
		count = count+1;
        event = document.createEvent("UIEvents");
        messageBox.innerHTML = `*${count}.*` + message.replace(/ /gm, ''); // test it
        event.initUIEvent("input", true, true, window, 1);
        messageBox.dispatchEvent(event);
  
        eventFire(document.querySelector('span[data-icon="send"]'), 'click');
    }
}  
var eventFire = (MyElement, ElementType) => {
    var MyEvent = document.createEvent("MouseEvents");
    MyEvent.initMouseEvent
     (ElementType, true, true, window, 0, 0, 0, 0, 0, false, false, false, false, 0, null);
    MyElement.dispatchEvent(MyEvent);
};
const interval = setInterval(function() {
   myFunc()
 }, 5000);

