# Spotify-PKCE-Example

"Quick" (? 😅) attempt at demonstrating the code to do Spotify's "new" PKCE authentication flow. Permitting apps with no backend to make requests to the Spotify API.

Find the source code at https://github.com/hcientist/Spotify-PKCE-Example and a demo at https://hcientist.github.io/Spotify-PKCE-Example

## Highest level summary of the flow

1. You have to register as a developer with spotify and then add an app. This will give you a `client id` and a `client secret`. You'll need the `client id` for this code/demo.
    * note: you have to know what your `redirect uri` is going to be when you register the app. You can always change it later, and you can have multiple. Consider choosing `http://127.0.0.1:5500/index.html` as one of your `redirect URIs` if you plan to clone this repo and run with vscode live server.
1. deploy this demo by any means, e.g.
    * launch a (local, typically) development server such as with vscode live server or possibly pythons one-liner `python -m http.server 5500`
    * copy this project's `index.html` to an existing server you have access to
1. open the index.html as hosted in your server choice from the previous step in a browser
1. Begin this demo by entering your `client id` and `redirect uri` into the corresponding input controls
1. Click the `Get Spotify Auth Code` button. This will redirect the tab with the demo to the Spotify login page. Login with your Spotify credentials. and grant permission to this demo app to access spotify on your behalf.
1. After granting permission, you will be redirected back to the index.html page of this project, but in a way that the index.html will have an authorization code from spotify
1. with this authorization code, the demo has the prerequisites to request an access token from spotify. Click the `Get Token` button to get one.
1. Once you have an access token, you can use it to make requests to the spotify api. You can use the 3 example items under `Have token, make api request(s)` to test this out.
