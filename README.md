# Cocoapods-Cheatsheet

Useful commands etc. for Cocoapods

### Installation 

| Command | Description |
| ----------- | ----------- |
| pod init | creates a Podfile for the current directory if none currently exists |
| pod install | Downloads all dependencies defined in Podfile and creates an Xcode Pods library project in ./Pods |
| pod update | Updates the Pods identified by the specified pod names. If no pod names are specified it updates all the Pods ignoring the contents of the Podfile.lock. This command is reserved to the update of dependencies and pod install should be used to install changes to the Podfile. |
| pod outdated | Shows the outdated pods in the current Podfile.lock, but only those from spec repos, not those from local/external sources. |
| pod deintegrate | Deintegrate your project from CocoaPods. Removing all traces of CocoaPods from your Xcode project.If no xcodeproj is specified, then a search for an Xcode project will be made in the current directory. |
| pod env | Display pod environment. |

### Browse

| Command | Description |
| ----------- | ----------- |
| pod search | Searches for pods, ignoring case, whose name, summary, description, or authors match QUERY. If the --simple option is specified, this will only search in the names of the pods. |
| pod list | Lists all available pods. |
| pod try | Downloads the Pod with the given NAME (or Git URL), install its dependencies if needed and opens its demo project. If a Git URL is provided the head of the repo is used. If a Git URL is specified, then a --podspec_name can be provided, if the podspec name is different than the git repo for some reason. |

### Specifations

| Command | Description |
| ----------- | ----------- |
| pod spec create [NAME|https://github.com/USER/REPO] | Creates a PodSpec, in the current working dir, called NAME.podspec. If a GitHub url is passed the spec is prepopulated. |
| pod spec lint [NAME.podspec|DIRECTORY|http://PATH/NAME.podspec ...] | Validates NAME.podspec. If a DIRECTORY is provided, it validates the podspec files found, including subfolders. In case the argument is omitted, it defaults to the current working dir. |
| pod spec cat [QUERY] | Prints the content of the podspec(s) whose name matches QUERY to standard output. |
| pod spec which [QUERY] | Prints the path of the .podspec file(s) whose name matches QUERY |
| pod spec edit [QUERY] | Opens the podspec matching QUERY to be edited. |


### Create a new Cocoapod

| Command | Description |
| ----------- | ----------- |
| pod lib create pod_name | creates a new pod project for you |
| pod trunk push pod_name.podspec | push podspec to the trunk |
| pod spec create pod_name | creates podspec template for you |
