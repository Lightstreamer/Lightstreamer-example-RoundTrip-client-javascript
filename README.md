
# Lightstreamer Round-Trip Demo Client for JavaScript #

This project includes a simple web client front-end example for the Lightstreamer RoundTrip Demo Adapter.

## Round-Trip Demo ##

<table>
  <tr>
    <td style="text-align: left">
      &nbsp;<a href="http://demos.lightstreamer.com/RoundTripDemo" target="_blank"><img src="http://www.lightstreamer.com/img/demo/screen_roundtrip.png"></a>&nbsp;
      
    </td>
    <td>
      &nbsp;An online demonstration is hosted on our servers at:<br>
      &nbsp;<a href="http://demos.lightstreamer.com/RoundTripDemo" target="_blank">http://demos.lightstreamer.com/RoundTripDemo</a>
    </td>
  </tr>
</table>

The Round-Trip Demo uses the <b>JavaScript Client API for Lightstreamer</b> to let you broadcast messages as you type, character by character, to all the browsers displaying that page. Type anything in the 5 fields. Your characters will be delivered to the server, which will send them back to all the browsers, including yours (in the bottom grid). Launch multiple instances of the demo, possibly on different browsers or different machines, to really appreciate the broadcast capabilities. 
You will type some text in a browser and see it appear in real time on another browser.<br>

The grid to the bottom reports the originating IP address and the timestamp of the last change applied to each item.<br>

<i>Note: When you publish a value your IP address is publicly displayed.</i>

The demo includes the following client-side technologies:
* A [Subscription](http://www.lightstreamer.com/docs/client_javascript_uni_api/Subscription.html) containing 5 items, subscribed to in <b>MERGE</b> mode feeding a [StaticGrid](http://www.lightstreamer.com/docs/client_javascript_uni_api/StaticGrid.html).
* The messages are sent to the Lightstreamer Server using the [LightstreamerClient.sendMessage](http://www.lightstreamer.com/docs/client_javascript_uni_api/LightstreamerClient.html#sendMessage) utility.

# Deploy #

Before you can run the demo some dependencies need to be solved:

-  Get the lightstreamer.js file from the [latest Lightstreamer distribution](http://www.lightstreamer.com/download) 
   and put it in the src/js folder of the demo (if that is the case, please create it). Alternatively you can build a lightstreamer.js file from the 
   [online generator](http://www.lightstreamer.com/distros/Lightstreamer_Allegro-Presto-Vivace_5_1_1_Colosseo_20130305/Lightstreamer/DOCS-SDKs/sdk_client_javascript/tools/generator.html).
   In that case be sure to include the LightstreamerClient, Subscription, StaticGrid, and StatusWidget modules and to use the "Use AMD" version.
-  Get the require.js file form [requirejs.org](http://requirejs.org/docs/download.html) and put it in the src/js folder of the demo.

You can deploy this demo in order to use the Lightstreamer server as Web server or in any external Web Server you are running. 
If you choose the former case please create the folders "<LS_HOME>/pages/demos/RoundTripDemo" then copy here the contents of the /src folder of this project.<br>
The client demo configuration assumes that Lightstreamer Server, Lightstreamer Adapters and this client are launched on the same machine. If you need to targeting a different Lightstreamer server please search this line:
```js
var lsClient = new LightstreamerClient(protocolToUse+"//localhost:8080","DEMO");
```
in js/lsClient.js file and change it accordingly.<br>
Anyway the [ROUNDTRIP_ADAPTER](https://github.com/Weswit/Lightstreamer-example-RoundTrip-adapter-java) and [RoundTripMetadataAdapter](https://github.com/Weswit/Lightstreamer-example-RoundTrip-adapter-java) Adapters have to be deployed in your local Lightstreamer server instance.<br>
The demo are now ready to be launched.

# See Also #

## Lightstreamer Adapters needed by this demo client ##

* [Lightstreamer Round-Trip Demo Adapter](https://github.com/Weswit/Lightstreamer-example-RoundTrip-adapter-java)

## Similar demo clients that may interest you ##

* [Lightstreamer Chat Demo Client for JavaScript](https://github.com/Weswit/Lightstreamer-example-Chat-client-javascript)
* [Lightstreamer Messenger Demo Client for JavaScript](https://github.com/Weswit/Lightstreamer-example-Messenger-client-javascript)

# Lightstreamer Compatibility Notes #

- Compatible with Lightstreamer JavaScript Client library version 6.0 or newer.