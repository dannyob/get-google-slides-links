# get-google-slide-links

It always drives me a little crazy when I'm watching a google slide
presentation on a video conference, but I can't click on the links.

Here's a short program that will extract all the links from a slideshow, and
spit them out onto the terminal so you can cut and paste them into the video
conference chat, click on them yourself, send them as a summary to folks, etc.


You'll need to install `google-api-python-client`, `google-auth` and `google-auth-oauthlib`.

## Usage


```sh

python get-google-slide-links.py [URL-or-Presentation-ID]

Where an URL like
https://docs.google.com/presentation/d/1iamaGooglePresentationIDburiedinaURL/edit
or a raw "1iamaGooglePresentationIDburiedinaURL" value will both work.

```

## Credentials

The code needs a `credentials.json` file which is a JSON-formatted file that contains the client ID, client secret, and other information needed for your application to use OAuth 2.0 to authenticate with Google APIs. The file is generated when you create a new OAuth 2.0 client ID in the Google Cloud Console.
 
 The content of a typical `credentials.json` file looks like this:
 
 ```json
 {
   "installed": {
     "client_id": "YOUR_CLIENT_ID.apps.googleusercontent.com",
     "project_id": "YOUR_PROJECT_ID",
     "auth_uri": "https://accounts.google.com/o/oauth2/auth",
     "token_uri": "https://oauth2.googleapis.com/token",
     "auth_provider_x509_cert_url": "https://www.googleapis.com/oauth2/v1/certs",
     "client_secret": "YOUR_CLIENT_SECRET",
     "redirect_uris": [
       "urn:ietf:wg:oauth:2.0:oob",
       "http://localhost"
     ]
   }
 }
 ```
 
 Please note that you need to replace the placeholders `YOUR_CLIENT_ID`, `YOUR_PROJECT_ID`, and `YOUR_CLIENT_SECRET` with the actual values from your Google Cloud Console.
 
 Here are the steps to obtain the `credentials.json` file:
 
 1. Go to the Google Cloud Console: https://console.cloud.google.com/
 
 2. Create a new project or select an existing one.
 
 3. In the left-hand navigation panel, go to "APIs & Services" > "Dashboard."
 
 4. Click "Enable APIs and Services" and enable the "Google Slides API."
 
 5. Go to "APIs & Services" > "Credentials." 
 
 6. Click "Create credentials" and select "OAuth client ID." (You may have to create a consent page at this stage)
 
 7. Select "Desktop app" as the application type.
 
 8. Fill in the required information (if prompted) and click "Create."
 
 9. You should see a dialog with your client ID and client secret. Click "OK."
 
 10. On the "Credentials" page, you should see your new OAuth 2.0 client ID. Click the download icon on the right side of the client ID to download the `credentials.json` file.
 
 11. Save the `credentials.json` file to the same directory as your Python script.
 
 Remember to keep the `credentials.json` file secure, as it contains sensitive information that can be used to authenticate with your Google APIs.
 
