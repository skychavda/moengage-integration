## MoEngage Integraion with NextJs

### What is MoEngage
MoEngage is a online tool for push notification where you can integrate its SDK in your Android, IOS or Web app and schedule the notificaitons from its dashboard more on this [here](https://docs.moengage.com/docs)

### Steps to integrate with NextJs project.

1. First take the write the moengage script and initialization code in `pages/_document.js` file. Then replace the App Id with your App Id from dashboard: `Dashboard --> Settings --> App --> General`
Here is a code snippet
```
<script dangerouslySetInnerHTML={{__html:`(function(i,s,o,g,r,a,m,n){i.moengage_object=r;t={};q=function(f){return function(){(i.moengage_q=i.moengage_q||[]).push({f:f,a:arguments})}};f=['track_event','add_user_attribute','add_first_name','add_last_name','add_email','add_mobile','add_user_name','add_gender','add_birthday','destroy_session','add_unique_user_id','moe_events','call_web_push','track','location_type_attribute'],h={onsite:["getData","registerCallback"]};for(k in f){t[f[k]]=q(f[k])}for(k in h)for(l in h[k]){null==t[k]&&(t[k]={}),t[k][h[k][l]]=q(k+"."+h[k][l])}a=s.createElement(o);m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m);i.moe=i.moe||function(){n=arguments[0];return t};a.onload=function(){if(n){i[r]=moe(n)}}})(window,document,'script','https://cdn.moengage.com/webpush/moe_webSdk.min.latest.js','Moengage')`}}>
        </script>

        <script dangerouslySetInnerHTML={{__html:`
          Moengage = moe({
            app_id:"XXXXXXXXXXX", (Your api key)
            debug_logs: 1
          });`}}>
        </script>
```
More on this integration you will find [documentation](https://docs.moengage.com/docs/web-sdk-integration)

2. Add `serviceworker.js` into your public folder you will find this file in my public folder
3. If you want to check that MoEngage is perfectly integrate in your application add this extension to your browser [extension](https://docs.moengage.com/docs/moengage-assist-chrome-extension) where you can find several tabs like `Baisc info, service worker, web push, etc..`. If your integration is succesfull then in `service worker` tab your serviceworker path will shown and in `web push` tab `push token` is generated.

That's it. Happy coding 😊
