# Environmental Variable Model
Environmental Variables can be useful for storing specific key/value pairs of data for use in your app. Almost all areas of FileMaker can be setup to respond to environmental variables.

Setting up environments in FileMaker can lead to some key benefits:
- Separation of Concerns: decoupling configuration data from your app allows for easy portability and only injecting the data into your app when its needed.
- Ability to easily separate between different servers, for example dev/staging/production.
- Obfuscate and secure sensitive key data, like API and email credentials, especially using FileMaker's native encryption functions.
- Ease of recall, instead of using complicated If/Else If/Else scripting or Case() calculations, just get the variable you need and it is already set appropriately.

## Key Type of Environmental Variables
### System Environmental Variables
Under normal circumstances, the system environment is outside of the purview of FileMaker, so it's rarely accessed or required. In FileMaker, some functions like Get(TemporaryPath) can tap into these types of variables.

To adapt or set your own system variables in your FileMaker "System" envelope, you may set a few things like:
- Web Path: a path to the server /conf folder
- Host Details: such as a toggle for turning off certain aspects of the app if the system is hosted in one region versus another.
- Turning off a function based on the system geographical location.

### User Environmental Variables
User system variables are normally things specific to the logged in user. In the case of FileMaker this could be either the system user, authenticated directory user or FileMaker user. Some functions like Get(UserName) serve this purpose in FileMaker.

You might use User Variables for things like:
- Determining if a user has access to certain parts of your app.
- Timezone and language settings for a user.

### Runtime Process Variables
Runtime Variables are the most used type of Environmental Variable in FileMaker apps. For example, many of the Get() functions could be considered runtime variables. Runtime functions are usually temporary, and could be considered "Session" variables as well. 

Runtime Variables are also modular, meaning that you could set different runtime variables for separate parts of your apps. 