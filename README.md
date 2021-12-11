## Welcome 👋
Hello world, if you want to use my powershell configuration you will have to do the following configurations: 

1. install from the microsoft store, windows terminal and powershell separately.
2. install scoop as a package manager, this can be done by entering the following commands
3. install oh-my-posh, posh-git, terminal-icons 
4. globally configure the initialization of the custom toolbar and any aliases you wish to extend from those already used in the configuration.
5. Install by means of scoop fzf in order to have autocompletion in the command line.

You must install any font inside nerdfonts this, it allows you to have icons in all your commands that involve it inside the console, and of course it gives you a unique style, you can do it through its official page, the link is the following one:
https://www.nerdfonts.com/font-downloads


## Scoop installation

to install scoop run the following command
    iwr -useb get.scoop.sh | iex

if you run into policy problems you should enter the following command

    Set-ExecutionPolicy RemoteSigned -scope CurrentUser

finally to install packages you should enter the following command 

    scoop install curl

Each of the offered commands can be verified within the official page which is:  https://scoop.sh/

## Config 
Before continuing I remind you that you will need to have git installed on your computer to perform most of the configurations. You should also have a code editor of your choice for the following sessions.

> you need to navigate to the users folder, this in windows is found by
> accessing the local disk c, then enter users, then the current user
> that is updating on the machine. the hypothetical commands would be as
> follows

assuming we are on the local disk c

    cd users/${you_current_user}

inside this we will find a folder called .config/ exactly we must include the point, we will accede to it this way:

    cd .config

then create a new configuration folder and navigate to it:

    mkdir powershell
    
    cd powershell

inside this folder we will clone the configuration files, these will suffer some small modifications, you must change the name gerar.omp.json, to the name of your user, that is to say: 

    ${you_current}_user.omp.json

after changing this name, enter the file user_profile.ps1, and change the following line: 

    $omp_config = Join-Path $PSScriptRoot ".\gerar.omp.json"

where the path will be changed to the name of your user, i.e. something like this:

    $omp_config = Join-Path $PSScriptRoot ".\{you_current_user}.omp.json"
    
## Config alias, theme, profile change

Everything should be ready to work correctly, now we will add inside our environment paths the configuration file, we will enter the following file

    $PROFILE.currentUserCurrentHost

there inside we will write the following command:

    . $env:USERPROFILE\.config\powershell\user_profile.ps1


## Install required packages
Ready, now everything should work correctly, however, we have not yet installed the necessary packages to see our changes reflected, for this we will run the following commands

    Install-Module oh-my-posh -scope currentUser -Force
    Install-Module posh-git -scope currentUser -Force
    Install-Module Terminal-Icons -scope currentUser -Force
    Install-Module PSFzf -scope currentUser -Force
    Install-Module PSReadLine -scope currentUser -Force


## Finished and features
now you can enjoy your terminal, stylish and functional that will streamline your workflow, finally I would like to remind you that the configuration is fully extendable to your liking, remember that you only have to check the official site of oh-my-posh to understand what to do:

https://ohmyposh.dev/docs/

Secondly, I would like to mention that the current features are:
1. Color assimilation according to the background.
2. responsive to any window
3. nodeJS version
4. git status (insertions, deletions, additions)
5. current git branch where user is currently editing
6. The time (for those of us who lose hours programming)

Happy hacking 👋
