![](https://assets-global.website-files.com/5e2701b416b6d176f5007781/6344bbf42c1388b9f34a5c6f_logo-colour-stylised-2.svg)

This is a demonstration on how to use Rayguns `onBeforeSendRUM` hook.

The implementation will store RUM events in session storage until the user logs in, once authenticated - it will pull session payloads from storage, modify the user with the authenticated user, then send these off to Raygun.

## How can I run it?

There is a live demo available here:  
https://raygun-obs-demo.netlify.app/

For local testing follow these steps:
1. Clone the repo 
2. Open the repo in terminal `cd Raygun-RUM-onBeforeSend-demo` 
3. Edit `index.html` - Replace `dvdb8khopEiuj15r9fiHw` with your test API key 
4. (optional) Run a simple python server `python -m http.server 8080`
5. Open the demo

http://localhost:8080/ - if run via the python server  
file:///C:/[PATH_TO_WORKSPACE]/Raygun-RUM-onBeforeSend-demo/index.html - to run without a server

## How do I know it works?
1. Open the site in browser & open dev tools
2. Clicking the "trigger navigation" button will result in
- - User details in console (anonymous)
- - Session payloads stored under "Application > Session storage > eventData"
3. Click "Authenticate" & click "trigger navigation" again, this will result in
- - User details in console (authenticated)
- - Session payloads are purged from Session storage
- - Network requests have sent the correct payloads inside the "Network" tab
