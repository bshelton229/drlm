## DRLM (Drupal Link Manager): a perl script to manage a drupal symlink structure

DRLM is a simple perl script to help manage creating Drupal site folders that symlink back to centrally managed cores and distributions. The centrally managed cores and distributions are stored in a base folder. DRLM will create relative symbolic links back to the base.

### Install:

1. Place the script in your path and make it executable. No non-core perl modules are used. Chang the shebang to point to your system's perl if it's not /usr/bin/perl.

2. Build a drupal base folder (See Drupal Base below.)
    
3. Set your the DRUPAL_BASE environment variable to contain the full path to the drupal base folder you created. You may also set this on the command line using --base /path/to/drupal_base. Your Drupal base folder will most likely be checked into revision control.

### Drupal Base Folder:

The Drupal base folder must contain both a cores and dists sub-folder. The cores and dists folders contain Drupal cores and sites/all distributions compatible with the cores. Like this:

    -- drupal_base
        -- cores
            -- drupal-6.18
            -- drupal-6.20
            -- drupal-7.0
        -- dists
            -- 6.x-1.0
            -- 6.x-1.1
            -- 7.x-1.0
            -- 7.x-1

Cores are standard Drupal distributions from drupal.org. Dists are linked to the sites/all folder when you create/modify a site. Both need to adhere to the above naming conventions. Dists contain what your sites/all folder contains. When prompted interactively dist versions are checked against the core major versions. For example, 7.x dists are compatible with all drupal-7.x cores.

### Commands:

 * #### drlm cores
    
    Lists available cores
    
 * #### drlm dists 

    Lists available dists
    
 * #### drlm site

    Lists site information. It must be run from the root of a site folder. 
    It will show which core and dist the site is linked to. Must be run from
    the root of a linked site folder.

 * #### drlm site new ./dest [core] [dist] 
 
    Will create a new site in ./dest. If core and dist are not entered on the command 
    line you will be prompted with an interactive menu.

 * #### drlm site switch [core] [dist]
 
    Will switch both dist and core. If core and dist are not entered on the command line 
    you will be prompted with an interactive menu. Must be run from the root of a linked
    site folder.

 * #### drlm site switch-core [core]
 
    Will switch the core, if core isn't specified as an argument you will 
    be prompted with an interactive menu. Must be run from the root of a
    linked site folder.
    
 * #### drlm site switch-dist [dist]

    Will switch the dist, if dist isn't specified as an argument you will 
    be prompted with an interactive menu. Must be run from the root of a
    linked site folder.
