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
//Get the Mixpanel Distinct Id or any User Id of choice
let distinct_id = "2385616";
mixpanel.init('303d87650d7ad5a7c4c5380c9d276cd4', {
    loaded: function(mixpanel) {
        distinct_id = mixpanel.get_distinct_id();
    }
});
//Set the OneSignal External User ID to Mixpanel Distinct Id
OneSignal.push(function() {
  // Check if the current site visitor is subscribed (no player id is created until the user subscribes to push
  OneSignal.isPushNotificationsEnabled(function(isEnabled) {
    if (isEnabled) {
      console.log("Push notifications are enabled!");
      OneSignal.setExternalUserId(distinct_id);
      //Set Mixpanel OneSignal User Id property to Distinct Id or any User Id
      mixpanel.people.set({
        $onesignal_user_id: distinct_id
      });
    } else {
      console.log("Push notifications are not enabled yet.");   
    }
  });
});
</head>
hi
