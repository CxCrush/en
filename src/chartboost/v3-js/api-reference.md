## API Reference

### Methods
```javascript
sdkbox.PluginChartboost.restrictDataCollection(shouldRestrict);
```
> Set to restrict Chartboost's ability to collect personal data from the device.
When this is set to YES. IDFA and ip address will not be collected by the SDK or the server.
This method should be called before init

```javascript
sdkbox.PluginChartboost.init(jsonconfig);
```
> initialize the plugin instance.

```javascript
sdkbox.PluginChartboost.show(name);
```
> show ad by specifying ad name.

```javascript
sdkbox.PluginChartboost.setListener(listener);
```
> creates the an optional listener.

```javascript
sdkbox.PluginChartboost.isAnyViewVisible();
```
> check to see if any views are visible.

```javascript
sdkbox.PluginChartboost.isAvailable(name);
```
> is the specified ad available?

```javascript
sdkbox.PluginChartboost.cache(name);
```

```javascript
sdkbox.PluginChartboost.setAutoCacheAds(shouldCache);
```
> set to enable and disable the auto cache feature (Enabled by default).

```javascript
sdkbox.PluginChartboost.getAutoCacheAds();
```
> get the current auto cache behavior (Enabled by default).

```javascript
sdkbox.PluginChartboost.closeImpression();
```
> close any visible Chartboost impressions (interstitials, more apps, rewarded
video, etc..) and the loading view (if visible).

<pre>
deprecated >= 2.3.x
</pre>

```javascript
sdkbox.PluginChartboost.setStatusBarBehavior(behavior);
```
> set to control how the fullscreen ad units should interact with the status bar.
(CBStatusBarBehaviorIgnore by default).

```javascript
sdkbox.PluginChartboost.didPassAgeGate(pass);
```
> confirm if an age gate passed or failed. When specified Chartboost will wait for
call before showing the IOS App Store.

```javascript
sdkbox.PluginChartboost.setShouldPauseClickForConfirmation(shouldPause);
```
> decide if Chartboost SDK should block for an age gate.

```javascript
sdkbox.PluginChartboost.handleOpenURL(url, sourceApp);
```
> opens a "deep link" URL for a Chartboost Custom Scheme.

```javascript
sdkbox.PluginChartboost.setCustomID(customID);
```
> set a custom identifier to send in the POST body for all Chartboost API server requests.

```javascript
sdkbox.PluginChartboost.getCustomID();
```
> get the current custom identifier being sent in the POST body for all Chartboost
API server requests.

```javascript
sdkbox.PluginChartboost.setShouldRequestInterstitialsInFirstSession(shouldRequest);
```
> decide if Chartboost SDK should show interstitials in the first session.

```javascript
sdkbox.PluginChartboost.setShouldDisplayLoadingViewForMoreApps(shouldDisplay);
```
> decide if Chartboost SDK should show a loading view while preparing to display
the "more applications" UI.

```javascript
sdkbox.PluginChartboost.setShouldPrefetchVideoContent(shouldPrefetch);
```
> decide if Chartboost SDK will attempt to fetch videos from the Chartboost API
servers.


### Listeners
```javascript
onChartboostCached(name);
```
> there is cached content

```javascript
onChartboostShouldDisplay(name);
```
> should Chartboost display

```javascript
onChartboostDisplay(name);
```
> Charboost ad has displayed

```javascript
onChartboostDismiss(name);
```
> Chartboost ad has been dismissed

```javascript
onChartboostClose(name);
```
> Chartboost is not running

```javascript
onChartboostClick(name);
```
> Chartboost ad was clicked on

```javascript
onChartboostReward(name, reward);
```
> Chartboost reward was given

```javascript
onChartboostFailedToLoad(name, e);
```
> Chartboost failed to load

```javascript
onChartboostFailToRecordClick(name, e);
```
> Chartboost failed to record click

```javascript
onChartboostConfirmation();
```
> Chartboost confirmation

```javascript
onChartboostCompleteStore();
```
> Chartboost complete store


