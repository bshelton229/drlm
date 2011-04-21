DRLM: a perl script to manage a drupal symlink structure
--------------------------------------------------------

Install
-------
1. Place the script in your path and make it executable.
2. Build a drupal base to link from, containins a cores, and dists folder
3. Set your the DRUPAL_BASE environment variable to contain the full path to where you checked out the cu_drupal repo. You may also set this on the command line each time using --base /path/to/cu_drupal.

Usage:
 * drlm cores : Lists cores and can be run from anywhere, it reads cores from the base.
 * drlm dists : Lists dists and can be run from anywhere, it reads dists from the base.
 * -- The following commands must be run from the root directory of your drlm managed site folder --
 * drlm site : Lists site information. It must be run from the root of a site folder. 
   It will show which core and dist the site is linked to.
 * drlm site new ./dest [core] [dist]: Will create a new site in ./dest. If core and dist are not entered
   on the command line you will be prompted with an interactive menu.
 * drlm site switch [core] [dist] : Will switch both dist and core. If core and dist are not entered
   on the command line you will be prompted with an interactive menu.
 * drlm site switch-core [core] : Will switch the core, if core isn't specified as an argument you will be prompted
   with an interactive menu.
