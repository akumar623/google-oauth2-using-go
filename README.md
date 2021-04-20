# Getting started with OAuth2 in Go
In this project we will create a simple web page with Google login using oauth2 Go package.

##Google Project, OAuth2 keys
For this project to work you will need to create Google OAuth2 keys 
* Go to [Google Cloud Platform](https://console.developers.google.com/). 
* Create new project or use an existing one
* Go to Credentials
* Click "Create credentials"
* Choose "OAuth client ID"
* Add authorized redirect URL, in our case it will be localhost:8080/callback
* Get client id and client secret
* Save it in a safe place

##How OAuth2 works with Google
* Obtain OAuth 2.0 credentials from the Google API Console.
* Obtain an access token from the Google Authorization Server.
* Send the access token to an API.
* Refresh the access token, if necessary.

##Structure
Entire code is in a single main.go file. We will register 3 URL handlers:
* /
* /login
* /callback

##Initial handlers and OAuth2 config
```golang
go get golang.org/x/oauth2
go get cloud.google.com/go/compute/metadata
```

#Environment Variables
Save Google Client ID and Client secret into environment variables. The program uses os.Getenv in the code to fetch the Client ID and Client secret.

In case you of Z Shell,  
```Unix
nano ~/.zshrc
```

Add the following lines
```Unix
export GOOGLE_CLIENT_ID="Your Client ID that would typically ends with .apps.googleusercontent.com"
export GOOGLE_CLIENT_SECRET="Your Client secret"
```
