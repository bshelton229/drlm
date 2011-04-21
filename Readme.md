## DRLM (Drupal Link Manager): a perl script to manage a drupal symlink structure

DRLM is a simple perl script to help manage creating Drupal site folders which symlink back to cores and distributions managed centrally. The drupal_base folder should at least contain a folder name cores, and a folder named dists. The cores folder will contain various unaltered Drupal cores. The dists folder should contain versioned distributions. DRLM will generate new site folders that symlink core files to a certain core and link a dist to the sites/all folder.

### Install:

1. Place the script in your path and make it executable. No non-core perl modules are used.

2. Build a drupal base to link from, containins a cores, and dists folder
    
3. Set your the DRUPAL_BASE environment variable to contain the full path to where you checked out the cu_drupal repo. You may also set this on the command line each time using --base /path/to/cu_drupal.

### Drupal Base:

The Drupal base is a folder containing a cores and dists folders with the below naming convention.

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

### Usage:

 * drlm cores : Lists cores and can be run from anywhere, it reads cores from the base.
 * drlm dists : Lists dists and can be run from anywhere, it reads dists from the base.

#### The following commands must be run from the root directory of your drlm managed site folder

 * drlm site : Lists site information. It must be run from the root of a site folder. 
   It will show which core and dist the site is linked to.
 * drlm site new ./dest [core] [dist]: Will create a new site in ./dest. If core and dist are not entered
   on the command line you will be prompted with an interactive menu.
 * drlm site switch [core] [dist] : Will switch both dist and core. If core and dist are not entered
   on the command line you will be prompted with an interactive menu.
 * drlm site switch-core [core] : Will switch the core, if core isn't specified as an argument you will be prompted
   with an interactive menu.
