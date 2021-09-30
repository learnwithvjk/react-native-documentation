## Using Expo CLI:

#### NOTE: Expo CLI is abstracted and limited CLI If the project grows bigger its better to use React Native CLI

> Installing Expo CLI
```
npm install -g expo-cli
```

> Starting a project

##### if 1st time use of expo it is recommended to install node 12.13:
```
nvm install 12.13
```
##### initializing the project
```
nvm use 12.13
expo init ${ projectName }
```

#### Starting a project:

using NPM:

```
npm start
```
using Expo:

```
expo-cli start
```

#### Switchin between Tunnel / LAN / Local :

GO to http://localhost:19000/ and use the Connection TAB on lower bottom

### ISSUES:

#### 1. Network Response Time Out Error (create-react-native-app) (expo):
 
Linux (Ubuntu)
In Ubuntu Run In terminal

sudo ufw status verbose  To view open port if you cannot found 19000 port open then you need to open port using

sudo ufw allow 19000/tcp
and then again run

sudo ufw allow 19001/tcp

