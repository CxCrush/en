## API Reference

### Methods
```cpp
static void init ( ) ;
```
> initialize the plugin instance.

```cpp
static void setListener ( FacebookListener * listener ) ;
```
> Set listener to listen for facebook events

```cpp
static FacebookListener * getListener ( ) ;
```
> Get the listener

```cpp
static void removeListener ( ) ;
```
> Remove the listener, and can't listen to events anymore

```cpp
static void setLoginBehavior ( int loginBehavior ) ;
```
> login

```cpp
static void login ( ) ;
```
> log in

<pre>
This method calls login with a single permission: sdkbox::FB_PERM_READ_PUBLIC_PROFILE
</pre>

```cpp
static void login ( std::vector <std::string> & permissions ) ;
```

```cpp
static void requestReadPermissions ( const std::vector <std::string> & permissions ) ;
```
> log in with specific read permissions, conflict with publish permissions
https://developers.facebook.com/docs/facebook-login/permissions

```cpp
static void requestPublishPermissions ( const std::vector <std::string> & permissions ) ;
```
> log in with specific public permissions
https://developers.facebook.com/docs/facebook-login/permissions

```cpp
static void logout ( ) ;
```
> log out

```cpp
static bool isLoggedIn ( ) ;
```
> Check whether the user logined or not

```cpp
static std::string getUserID ( ) ;
```
> get UserID

```cpp
static std::string getAccessToken ( ) ;
```
> get AccessToken

```cpp
static std::vector <std::string> getPermissionList ( ) ;
```
> get permissoin list

```cpp
static void share ( const FBShareInfo & info ) ;
```
> share

```cpp
static void dialog ( const FBShareInfo & info ) ;
```
> open a dialog of Facebook app or WebDialog (dialog with photo only avaible with native Facebook app)

```cpp
static std::string getSDKVersion ( ) ;
```
> return the version of Facebook SDK

```cpp
static void api ( const std::string & path ,
                  const std::string & method ,
                  const FBAPIParam & params ,
                  const std::string & tag ) ;
```
> use Facebook Open Graph api
https://developers.facebook.com/docs/ios/graph

```cpp
static void fetchFriends ( ) ;
```
> fetch friends data from Facebook

<pre>
This data only reflects your friends that are using the app.
The number of friends defaults to 25.
</pre>

```cpp
static std::vector <FBGraphUser> getFriends ( ) ;
```
> get friends info

```cpp
static bool canPresentWithFBApp ( const FBShareInfo & info ) ;
```
> check whether can present Facebook App

```cpp
static void requestInvitableFriends ( const FBAPIParam & ) ;
```
> Get a vector of invitable friends info which can be used to build a custom friends invite dialog.

<pre>
The default set will be limited to 25 friends.
The order in which FB sorts the friends, and which ones returns vary between calls.
The returned invitation tokens are not supposed to be long-term stored and may vary between
calls for the same friends.
The application must have a canvas configuration for this API call to work.
</pre>

```cpp
static void inviteFriendsWithInviteIds ( const std::vector <std::string> & invite_ids ,
                                         const std::string & title ,
                                         const std::string & invite_text ) ;
```
> Invite friends based on the result obtained from a call to <code>requestInvitableFriends</code>

```cpp
static void inviteFriends ( const std::string & app_link_url ,
                            const std::string & preview_image_url ) ;
```
> Use the default FB dialog to invite friends.

```cpp
static void setAppId ( const std::string & appId ) ;
```
> Set the Facebook App ID to be used by the FB SDK.

```cpp
static void setAppURLSchemeSuffix ( const std::string & appURLSchemeSuffix ) ;
```
> Set the app url scheme suffix used by the FB SDK.

```cpp
static void requestGift ( const std::vector <std::string> & invite_ids ,
                          const std::string & object_id ,
                          const std::string & message ,
                          const std::string & title = "" ,
                          const std::string & additional_data = "" ) ;
```
> Ask friends for a gift

```cpp
static void sendGift ( const std::vector <std::string> & friend_ids ,
                       const std::string & object_id ,
                       const std::string & title ,
                       const std::string & message ,
                       const std::string & additional_data = "" ) ;
```
> Send friend a gift

```cpp
static void logEvent ( const std::string & eventName ) ;
```
> Log event

```cpp
static void logEvent ( const std::string & eventName , float valueToSum ) ;
```
> Log event with value

```cpp
static void logPurchase ( float mount , const std::string & currency ) ;
```
> Log purchase event


### Listeners
```cpp
void onLogin ( bool isLogin , const std::string & msg );
```

```cpp
void onSharedSuccess ( const std::string & message );
```

```cpp
void onSharedFailed ( const std::string & message );
```

```cpp
void onSharedCancel ( );
```

```cpp
void onAPI ( const std::string & key , const std::string & jsonData );
```

```cpp
void onPermission ( bool isLogin , const std::string & msg );
```

```cpp
void onFetchFriends ( bool ok , const std::string & msg );
```

```cpp
void onRequestInvitableFriends ( const FBInvitableFriendsInfo & friends );
```

```cpp
void onInviteFriendsWithInviteIdsResult ( bool result ,
                                          const std::string & msg );
```

```cpp
void onInviteFriendsResult ( bool result , const std::string & msg );
```

```cpp
void onGetUserInfo ( const FBGraphUser & userInfo );
```

```cpp
void onRequestGiftResult ( bool result , const std::string & msg ) 
```

```cpp
void onSendGiftResult ( bool result , const std::string & msg ) 
```


