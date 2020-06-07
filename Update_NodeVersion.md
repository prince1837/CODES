to update node and npm

     npm cache clean -f
     npm install -g n
     n latest
     sudo n latest
     
If it will not work then run this command after root for root run 

    sudo su




Basic code to earase packeges or modles

removes the module from node_modules, but not package.json

    npm uninstall <name> 
also removes it from dependencies in package.json

    npm uninstall <name> --save 
also removes it from devDependencies in package.json

    npm uninstall <name> --save-dev
also removes it globally

    npm -g uninstall <name> --save 
