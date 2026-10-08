# Android-On-Reload
A basic tutorial on how to get fully working mobile login on Reload for 16.00+
NOT MADE FOR PATYHUB VERSIONS!

### Versions Tested: 17.30, 17.50, 18.40, 19.01, 19.10, 23.00, 23.50, 24,20, 27.11, 28.30 and more!


## What you need:
- **A brain**
- **Reload Backend**
- **exchange-code.js command - [view here](https://github.com/Project-Reload/Reload-Backend/blob/main/DiscordBot/commands/User/exchange-code.js)**
- **Login page - my template can be viewed [here](https://github.com/yetzq7/Android-On-Reload/blob/main/example.html)**


## Step 1 - Get the Android manifest from your APK


**To get the manifest, you need to check assets\Cloud\cloudcontent.json in your decompiled apks folder**


![img](https://i.ibb.co/5XGLc9XS/image.png)


**It should look like this:**
```
{"AppName":"FortniteContentBuilds","BuildVersion":"++Fortnite+Release-19.10-CL-18675304","Platform":"Android","ManifestPath":"Builds/Fortnite/Content/CloudDir/MpLk_vMfcRflZaV62UGbtZMWTmmPVg.manifest","ManifestHash":"d1518f35fc444f46c257d5e22b75c0399474ae89"}
```

## Step 2 - Updating the manifest path and hash on Reload

**Go to routes/main.js and scroll down until you see this:**
```
app.get("/launcher/api/public/assets/*", async (req, res) => {
    res.json({
        "appName": "FortniteContentBuilds",
        "labelName": "ReloadBackend",
        "buildVersion": "++Fortnite+Release-20.00-CL-19458861-Windows",
        "catalogItemId": "5cb97847cee34581afdbc445400e2f77",
        "expires": "9999-12-31T23:59:59.999Z",
        "items": {
            "MANIFEST": {
                "signature": "ReloadBackend",
                "distribution": "https://reloadbackend.ol.epicgames.com/",
                "path": "Builds/Fortnite/Content/CloudDir/ReloadBackend.manifest",
                "hash": "55bb954f5596cadbe03693e1c06ca73368d427f3",
                "additionalDistributions": []
            },
            "CHUNKS": {
                "signature": "ReloadBackend",
                "distribution": "https://reloadbackend.ol.epicgames.com/",
                "path": "Builds/Fortnite/Content/CloudDir/ReloadBackend.manifest",
                "additionalDistributions": []
            }
        },
        "assetId": "FortniteContentBuilds"
    });
})
```

**With the information in cloudcontent.json, you can update that part**
**In buildVersion remove what is there and add what it says in cloudcontent also remember to add -Android at the end!**
**Example:**
```
 "buildVersion": "++Fortnite+Release-19.10-CL-18675304-Android"
 ```

**In path, put the ManifestPath shown in cloudcontent.json (Replace both of them)**
**Example:**
```
"path": "Builds/Fortnite/Content/CloudDir/MpLk_vMfcRflZaV62UGbtZMWTmmPVg.manifest"
```

**Do the same for "hash": and then thats it for the backend part**

## Step 3 - Hosting the Login page

**Personally, I use [vercel](https://vercel.app) to host the login page rather than the backend itself but its really up to you**

## How it works

**This is an external login, you must be at the find my account screen to be able to do it, after you see it go to your login page and enter the code you got from the exchange code command. After that it will redirect you to your game (must be open) and then you can hit find my account and then back out of it and it should log you in!**

```
// this sends back the exchange code to the game
const uri = "com.epicgames.fortnite://authorize/?code=" + encodeURIComponent(code);


console.log("uri - ", uri);
showStatus("Redirecting you back..");

```

**Template Login Page:**
<img width="917" height="898" alt="image" src="https://github.com/user-attachments/assets/0fe0d93d-1572-465a-8815-13744b45e47e" />



