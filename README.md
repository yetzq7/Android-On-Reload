# Android-On-Reload
A basic tutorial on how to get fully working mobile on Reload for 16.00+
NOT MADE FOR PATYHUB VERSIONS!

### Versions Tested: 17.30, 17.50, 18.40, 19.01, 19.10, 24.20, 23.00, 23,50, 27.11, 28.30 and more!


## What you need:
- **A brain**
- **Reload Backend**
- **exchange-code.js command - [view here](https://github.com/Project-Reload/Reload-Backend/blob/main/DiscordBot/commands/User/exchange-code.js)**
- **Login page - my template can be viewed [here]()


## Step 1 - Get the Android manifest from your APK


**To get the manifest, you need to check assets\Cloud in your decompiled apks folder**
-
![img](https://i.ibb.co/5XGLc9XS/image.png)
-

**It should look like this:**
```
{"AppName":"FortniteContentBuilds","BuildVersion":"++Fortnite+Release-19.10-CL-18675304","Platform":"Android","ManifestPath":"Builds/Fortnite/Content/CloudDir/MpLk_vMfcRflZaV62UGbtZMWTmmPVg.manifest","ManifestHash":"d1518f35fc444f46c257d5e22b75c0399474ae89"}
```

## Step 2 - Updating the manifest path and hash on Reload

**Note:** this is an external login, you must be at the find my account screen to be able to do it, after you see it go to your login page and enter the code. After that it will redirect you to your game (must be open) and then you can hit find my account and then back out of it and it should log you in!
