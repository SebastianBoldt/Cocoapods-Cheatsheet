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

### Create a new Cocoapod

| Command | Description |
| ----------- | ----------- |
| pod lib create pod_name | creates a new pod project for you |
| pod trunk push pod_name.podspec | push podspec to the trunk |
| pod spec create pod_name | creates podspec template for you |

### Browse

| Command | Description |
| ----------- | ----------- |
| pod search QUERY | Searches for pods, ignoring case, whose name, summary, description, or authors match QUERY. If the --simple option is specified, this will only search in the names of the pods. |
| pod list | Lists all available pods. |
| pod try NAME\|URL | Downloads the Pod with the given NAME (or Git URL), install its dependencies if needed and opens its demo project. If a Git URL is provided the head of the repo is used. If a Git URL is specified, then a --podspec_name can be provided, if the podspec name is different than the git repo for some reason. |

### Specifations

| Command | Description |
| ----------- | ----------- |
| pod spec create [NAME\|https://github.com/USER/REPO] | Creates a PodSpec, in the current working dir, called NAME.podspec. If a GitHub url is passed the spec is prepopulated. |
| pod spec lint [NAME.podspec|DIRECTORY|http://PATH/NAME.podspec ...] | Validates NAME.podspec. If a DIRECTORY is provided, it validates the podspec files found, including subfolders. In case the argument is omitted, it defaults to the current working dir. |
| pod spec cat [QUERY] | Prints the content of the podspec(s) whose name matches QUERY to standard output. |
| pod spec which [QUERY] | Prints the path of the .podspec file(s) whose name matches QUERY |
| pod spec edit [QUERY] | Opens the podspec matching QUERY to be edited. |

### Trunk

| Command | Description |
| ----------- | ----------- |
| pod trunk add-owner POD OWNER-EMAIL | Adds the registered user with specified OWNER-EMAIL as an owner of the given POD. An ‘owner’ is a registered user whom is allowed to make changes to a pod, such as pushing new versions and adding and removing other ‘owners’. |
| pod trunk info NAME | Returns information about a Pod. |
| pod trunk me | Includes information about your registration, followed by all your sessions.These are your current session, other valid sessions, unverified sessions, and expired sessions. |
| pod trunk push [PATH] | Publish the podspec at PATH to make it available to all users of the ‘master’ spec-repo. If PATH is not provided, defaults to the current directory.Before pushing the podspec to cocoapods.org, this will perform a local lint of the podspec, including a build of the library. However, it remains your responsibility to ensure that the published podspec will actually work for your users. Thus it is recommended that you first try to use the podspec to integrate the library into your demo and/or real application.If this is the first time you publish a spec for this pod, you will automatically be registered as the ‘owner’ of this pod. (Note that ‘owner’ in this case implies a person that is allowed to publish new versions and add other ‘owners’, not necessarily the library author.) |
| pod trunk register EMAIL [NAME] | Register a new account, or create a new session.If this is your first registration, both an EMAIL address and your NAME are required. If you’ve already registered with trunk, you may omit the NAME (unless you would like to change it).It is recommended that you provide a description of the session, so that it will be easier to identify later on. For instance, when you would like to clean-up your sessions. A common example is to specify the location where the machine, that you are using the session for, is physically located. |
| pod trunk remove-owner POD OWNER-EMAIL | Removes the user with specified OWNER-EMAIL from being an owner of the given POD. An ‘owner’ is a registered user whom is allowed to make changes to a pod, such as pushing new versions and adding and removing other ‘owners’. |
| pod trunk deprecate NAME | Deprecates a pod. |
| pod trunk delete NAME VERSION | *WARNING*: It is generally considered bad behavior to remove versions of a Pod that others are depending on! Please consider using the deprecate command instead. Deletes the specified pod version from trunk and the master specs repo. Once deleted, this version can never be pushed again. |

### Repos

| Command | Description |
| ----------- | ----------- |
| pod repo add NAME URL [BRANCH] | Clones URL in the local spec-repos directory at ~/.cocoapods/repos/. The remote can later be referred to by NAME. |
| pod repo update [NAME] | Updates the local clone of the spec-repo NAME. If NAME is omitted this will update all spec-repos in ~/.cocoapods/repos. |
| pod repo lint [NAME\|DIRECTORY] | Lints the spec-repo NAME. If a directory is provided it is assumed to be the root of a repo. Finally, if NAME is not provided this will lint all the spec-repos known to CocoaPods. |
| pod repo list  | List the repos from the local spec-repos directory at ~/.cocoapods/repos/. |
| pod repo remove NAME | Deletes the remote named NAME from the local spec-repos directory at ~/.cocoapods/repos/. |
| pod repo push REPO [NAME.podspec] | Validates NAME.podspec or \*.podspec in the current working dir, creates a directory and version folder for the pod in the local copy of REPO (~/.cocoapods/repos/[REPO]), copies the podspec file into the version directory, and finally it pushes REPO to its remote. |
| pod setup  | Creates a directory at ~/.cocoapods/repos which will hold your spec-repos. This is where it will create a clone of the public master spec-repo from: https://github.com/CocoaPods/Specs If the clone already exists, it will ensure that it is up-to-date. |


