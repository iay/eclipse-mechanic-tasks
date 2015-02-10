# eclipse-mechanic

_Ian's Workspace Mechanic tasks for Eclipse_

**NOTE** that Workspace Mechanic has some issues under Eclipse Luna (V4.4, 2014) with repeatedly prompting for settings which are already correct. It's in maintenance mode and some months have gone by since this issue was reported, and it doesn't look like it will ever be fixed. I've therefore stopped using Workspace Mechanic in my own work.

This is an experiment in using the [Workspace Mechanic](http://code.google.com/a/eclipselabs.org/p/workspacemechanic/) plugin to automate the maintenance of my [Eclipse](http://eclipse.org) workspaces.  If you work with the [Shibboleth](http://shibboleth.net) source code, it may help to automate your workspace setup too.

I've recently stopped using a single monstrous Eclipse workspace with everything in it and moved towards using separate workspaces for each aspect of my work.  As a result I now have around a dozen workspaces on each of multiple machines, and getting consistent settings across all of them is a lot of work if done manually.  I'm too [lazy](http://c2.com/cgi/wiki?LazinessImpatienceHubris) for that, and Workspace Mechanic allows me to automate the setup of new workspaces as well as making it simpler to propagate settings changes across workspaces the next time I use each one.

When you install Workspace Mechanic, it starts out looking for tasks in a couple of well-known locations.  On the Mac, one of those is `~/.eclipse/mechanic/`.  This location has the advantage of being assumed for every workspace, but the disadvantage of being an all-or-nothing option.  You can tell Workspace Mechanic about any number of additional locations to consult for each workspace, so I've divided my tasks into directories:

* `/iay/` contains settings which are entirely personal; things like removing text from the perspectives bar and setting a non-US date format for Subversion history.  I soft-link this to `~/.eclipse/mechanic`.
* `/shib-required/` contains tasks for the "[Required Configuration](https://wiki.shibboleth.net/confluence/display/DEV/Configuring+Eclipse#ConfiguringEclipse-RequiredConfiguration)" settings for Shibboleth project work.  I use these for all of my workspaces, Shibboleth-related or not, as it turns out I quite like them.
* `/shib-recommended/` contains the corresponding "[Recommended Configuration](https://wiki.shibboleth.net/confluence/display/DEV/Configuring+Eclipse#ConfiguringEclipse-RecommendConfiguration)" settings.  Again, I use these for all my workspaces but you might want to be more selective.  I have left out the auto-update setting because it isn't workspace-specific; this means that it needs to know the precise location of your Eclipse install and obviously that varies.
* `/shib-repos/` contains a task for each of the Shibboleth subversion repositories.  I include this in all Shibboleth-related workspaces.  If your workspace already has the ones you need, you might want to avoid adding this directory, as it may duplicate some of the repository locations.  That doesn't seem to be harmful, though.
* `/other-repos/` contains a task for each of the other public repositories I have occasional need to use.

Setting up a new workspace therefore involves adding the `/shib-required/` and `/shib-recommended/` directories to the Workspace Mechanic preferences, and further adding `/shib-repos/` directory if the workspace is for Shibboleth work.

Everything here *seems* to work just as well in Eclipse Kepler (V4.3, 2013) as it did in Eclipse Juno (V4.2, 2012). Unfortunately Workspace Mechanic has some issues in Eclipse Luna (V4.4, 2014) on the Mac that mean that I no longer use it. However, the settings file themselves still seem to be valid.
