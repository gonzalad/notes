# Virtual Box

sudo mount -t vboxsf /opt/git-projects ~/git-projects

# Configuration vi :

 * Installation vim : 
   sudo apt-get update
   sudo apt-get install vim
 * Installation gvim :
   sudo apt-get install vim-gnome 
 * Editer configuration VIM 
   `:e ~/_vimrc`

 
    " reglages VIM
    set nocompatible

    " afficher num?ro de ligne
    set number

    " Activation coloration syntaxique
    syntax on

    " Indentation toutes les quatre colonnes
    set tabstop=4

    " Set a nice theme
    color slate

    " VIM WINDOWS : everything goes to system clipboard
    set clipboard=unnamed

    " VIM WINDOWS : Visual selection copied automatically to clipboard
    set go+=a

    " Conversion des tabulations en espaces
    set expandtab

    " Indentation de quatre colonnes
    set shiftwidth=4
    set softtabstop=4

    " Indentation "intelligents"
    " set smartindent

    " Better command-line completion
    set wildmenu

    " Show partial commands in the last line of the screen
    set showcmd

    " Highlight searches (use <C-L> to temporarily turn off highlighting; see the
    " mapping of <C-L> below)
    set hlsearch

    " Attempt to determine the type of a file based on its name and possibly its
    " contents. Use this to allow intelligent auto-indenting for each filetype,
    " and for plugins that are filetype specific.
    filetype indent plugin on

    " Conserve l'indentation courante sur les nouvelles lignes
    set autoindent

    " retours arri?res intelligents
    set backspace=indent,eol,start

    " Indentation ? la marque de Tab la plus proche
    set shiftround

    " Display the cursor position on the last line of the screen or in the status
    " line of a window
    set ruler

    " Always display the status line, even if only one window is displayed
    set laststatus=2

    " Instead of failing a command because of unsaved changes, instead raise a
    " dialogue asking if you wish to save changed files.
    set confirm

    " Use visual bell instead of beeping when doing something wrong
    set visualbell

    " And reset the terminal code for the visual bell. If visualbell is set, and
    " this line is also included, vim will neither flash nor beep. If visualbell
    " is unset, this does nothing.
    set t_vb=

    " Enable use of the mouse for all modes
    set mouse=a

    " Use <F11> to toggle between 'paste' and 'nopaste'
    set pastetoggle=<F11>

    " Map <C-L> (redraw screen) to also turn off search highlighting until the
    " next search
    nnoremap <C-L> :nohl<CR><C-L>

    " Supprimer le menu windows
    if has("gui_running")
    " Set a nicer font.
    set guifont=Consolas:h11:cDEFAULT
    " Hide the toolbar.
    set guioptions-=T
    endif

# Installation sublime text

voir aussi [Sublime Text Repo](http://www.ubuntuupdates.org/ppa/sublime_text_3)

    sudo add-apt-repository ppa:webupd8team/sublime-text-3 
    sudo apt-get update
    sudo apt-get install sublime-text-installer

# Installation docker

c.f. https://docs.docker.com/engine/installation/linux/ubuntulinux/

 1. uname -r
   -> 4.4.0-21-generic
 1. Vérifier que les packages apt-transport-https, ca-certificates sont bien installés :
		dpkg -s apt-transport-https
		dpkg -s ca-certificates
	 Si KO, les installer via sudo apt-get install apt-transport-https ca-certificates
 1. Installer la clé PGP Docker
        sudo apt-key adv --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys 58118E89F3A912897C070ADBF76221572C52609D
 1. ouvrir (ou créer si il n'existe pas) le fichier /etc/apt/sources.list.d/docker.list, supprimer ce qui existe et ajouter :
   `deb https://apt.dockerproject.org/repo ubuntu-trusty main`
  (sur Xenial : `deb https://apt.dockerproject.org/repo ubuntu-xenial
main`).
 1. sudo apt-get update
   Purge the old repo if it exists.
 1. sudo apt-get purge lxc-docker
	Verify that APT is pulling from the right repository.
 1. apt-cache policy docker-engine
      From now on when you run apt-get upgrade, APT pulls from the new repository.
    * pre-requisites
      install linux-image-extra
      sudo apt-get update
      sudo apt-get install linux-image-extra-$(uname -r)
    * install Docker
      sudo apt-get update 
      sudo apt-get install docker-engine
    * Start the docker daemon
      sudo service docker start
    * Verify docker is installed correctly.
      sudo docker run hello-world
 1. S'ajouter dans le groupe docker :
   sudo usermod -aG docker <user>, puis se reloguer
   dans le cas contraire, docker ps génère une erreur (il faut dans ce cas faire sudo docker ps)

# Développement UI

sudo apt-get update
sudo apt-get install node npm 
ln -s /usr/bin/nodejs /usr/bin/node

suivre tutoriel https://angular.io/docs/js/latest/quickstart.html :
 * créer package.json, tsconfig.json, typings.json, systemjs.config.js
 * npm install



