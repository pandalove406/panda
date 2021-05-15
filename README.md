<head>
  <script src="https://cdn.onesignal.com/sdks/OneSignalSDK.js" async=""></script>
  <script>
    window.OneSignal = window.OneSignal || [];
    OneSignal.push(function() {
      OneSignal.init({
        appId: "196b5f96-8737-49c7-809c-36ce0c27b04c",
      });
    });
  </script>
  OneSignal.push(function() {         
  OneSignal.sendTag("PHONE NUMBER", "9447320535", function(tagsSent) {
    // Callback called when tags have finished sending
  });
});
</head>
hi
