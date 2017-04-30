# φ | php helper installer
Shell script installer, updater, dependency manager.

Originally made to fast deploy and update shell scripts from a remote index.

This is alpha quality software for aware peoples.

Currently, it suit perfectly my needs, but feel free to participate or give a star if you see usefulness.

It is tested in debian base, ubuntu, mint, raspbian.

Should work in mac os with a little patch (using .bash_profiles instead of .bashrc, please report).

<pre>
<b>Usage: phi [list[install|local|update] [url|path]
---------------------------------------------------
Install remote shell scripts (sh,bash,php,csh,python,perl..) as linux applications</b>

Parse remote directories or file to find shell script and install them.

Will configure the shell and save big time to create launchers and aliases. 

<b>[list]</b>     Parse script to display infos
            Parse remote index defined in script, or the url given as 2nd argument
            
<b>[install]</b>  Get all remote scripts from index or url given as 2nd argument.
            Create launcher.desktop for each scripts
            Create aliases in .bashrc
            Create shortcuts in the gnome programming submenu
            
<b>[update]</b>   Update/replace local scripts by all scripts from remote index 
            or url given as 2nd arument
            
<b>[local]</b>    Install local script given as 2nd argument (local path)

</pre>
### Any script can after install be started by:
 - <b>Clicking his icon in the gnome programming menu</b>
 - <b>Typing his name in terminal</b>
 - <b>Call his name from other shell scripts</b>
 
When done, icons can be changed as regular, scripts can be uninstalled by right click from the menu.

Keyboards shortcuts commands will directly works with no paths headaches.

We can then create scripts without caring of paths, they will work on other machines when deployed with phi.

### How are parsed scripts:
<pre>
I use scripts without extensions, i recommend you to do so, and this is how this program is written.
Scripts are valids only if they are extensionless.
Anything without extensions won't download at all.

<b>#!</b> Script: are valids only when a shebang <b>#!</b> match the document two first chars

<b>#</b>  Comments: lines begining with a <b>#</b> will be displayed as informations

<b>#></b> Dependencies: lines with <b>#></b> will be silently installed via apt.
    Specify program names separated by spaces
    Example, this line anywhere on a script
    <b><i>#> lolcat</i></b>
    Will install lolcat with <b>apt</b>, 
    just like: <b><i>sudo apt install lolcat</i></b>
 </pre>
 
The directory path is a hidden folder <b>.phi</b> in home. 

Files in this folder will be erased while updating.

Editing is best done from remote.

Then do a <b>phi update</b>

### Installation:

You need php installed on the system: 

<pre><b>sudo apt install php</b></pre>

Online installation from github:
<pre><b>php <(curl https://webdev23.github.io/phi/phi) install</b></pre>    
    
You can as well <a href="https://github.com/webdev23/phi/archive/master.zip">download the archive</a> and run <b>./phi</b>

### Examples of uses:

<b> Launch phi without installing </b>

    php <(curl https://webdev23.github.io/phi/phi) 
    
<b> Check infos from a remote script from url:</b>

    phi list https://webdev23.github.io/gif/gif

<b>List scripts in the defined main remote index:</b>

    phi list
    
I<b>nstall all scripts from the main defined index:</b>

    phi install
    
<b>Parse and install all scripts including those in subfolders (be careful..)</b>

    phi install URL
    
<b>Update all scripts from the main remote index whithout checking local installs</b>

    phi update
   
<b>Install local script:</b>

    phi local LOCALPATH
    
<b>(Advanced:) Pipe install phi and all scripts from remote index</b>

    php <(curl https://webdev23.github.io/phi/phi) install 

<b>(Advanced:) pipe install from another remote script (!)

There is <b>no needs of sudo</b> when piping, but for apt scripts depedencies, if required.

This is golden if you got it.. <i>enjoy</i></b>
 
    php <(curl https://webdev23.github.io/phi/phi) install https://webdev23.github.io/gif/gif
   
<b>(Advanced:) Check a website to find shell scripts, including those in subfolders.</b>

     phi list URL
     
     
 


     


