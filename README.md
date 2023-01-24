### GTM-iFrame-Tracking

```js
<script>
setTimeout(function(){
var message = JSON.stringify ({
event: 'purchase',
id: '{{ event.id }}'
});
parent.postMessage (message, 'https://www.parenturl.com');
}, 2500);
</script>

<script>
window.addEventListener('message', function(message) {
  if (message.origin.indexOf('iframeurl.com') > 1) {
 
  var data = JSON.parse(message.data);
  var dataLayer = window.dataLayer = window.dataLayer || [];
 
  dataLayer.push({
      'event': data.event,
      'id': data.id
    });
}});
</script>
```
