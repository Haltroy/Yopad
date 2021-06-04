# Yorot Package Distribution (Yopad) Offical Repository
This repository is only for dstributing Yopad pakcages, if you want to see the source codes of Yopad, see [Official Yorot Repository](https://github.com/Haltroy/Yorot) or any flavor repository.

## Usage
**Yo**rot **Pa**ckage **D**istribution Service and Yorot Store will look for this repository for installing, searching and upgrading packages.

This repositroy includes all Yorot add-ons such as:
 - Themes
 - Extensions
 - Web Engines
 - Apps
 - Languages
 - Experience Packs

These are all seperated to folders inside the main repository folder. Also, all package owners must create their own folders inside the main folders. An example folder scheme looks like this:

 - Themes
   - index.yrf - Themes Main Repository file
   - Haltroy
     - Yorot Light
   - Someone else
     - Another Theme
   - ...
 - Extensions
   - index.yrf - Extensions Main Repository File
   - Someone else
     - VPN Proxy 
   - Haltroy
     - Dark Mode  
   - ...
 - Apps 
   - ...


All add-ons must include 2 things:
 - HTUPDATE file,
 - at least 1 HTUPDATE package file containing the add-on itself.

Add-ons can include multiple versions and HTUPDATE archs in the same folder. But the URL to raw HTUPDATE file for the add-on must be included in the index.yrf files in each main add-on folder, not the main index.yrf file locaten on root directory.

## Adding your own packages
Adding packages to this repository is allowed, but you have to create a pull request to submit packages.

 1. Fork this repository online, star with editing the index.yrf files:
     - Insert this text under `<root>`: `<PackageRef Url="https://raw.githubusercontent.com/Haltroy/Yopad/main/[Add-on type]/[Your name]/[Add-on Name]/[HTUPDATE File Name].htupdate" />`
    - **Changing anything else makes your package rejected.**
 2. In your forked repository, create your own folder in add-on folder(s) and put your add-on packages and HTUPDATE there. You can also add screenshots. **You can only play with that folder, you cannot touch anyone else's folders or your package will be rejected.**
 3. Send a pull request to this repository with required information.
    - In title: `[NEW] [Add-on type] - [Your add-on name]`.
    - Description is optional.
 4. Moderating team will review your pull request. IF your package passes tests, then it will be merged to main system. 
    - We check if your add-on complies with our [Terms of Service](https://haltroy.com/blog/yopad-terms-of-service/).
    - We test and look the code of your add-on to test if this add-on contains or is malicious.
 5. Your add-on appears on Yorot and any flavor.
 6. (Optional) Remove your forked repository from rpository settings. **Only do this if your add-on is merged.**

## Updating your packages
Similar to adding a new package, except you don't need to create a new folder this time. 

 1. For this repository online by adding your new version to your folder first.
 2. In your forked repository, change the HTUPDATE of your package. You also can change the screenshots etc. too.
 3. Send a pull request sinmilar to before, but this time change "[NEW]" to "[UPDATE]" in the title.
 4. Similar to step 4 in "Adding your package" section.

## Removing your packages
You can't remove packages but mark them as unsupproted by just simply editing HTUPDATE file of your add-on.

## Creating own repositories
You can create a repository similar to this one, but you can't add that repository to here. You can move the packages independently.

Adding a custom repository to user's Yopad is simple an can be done in 2 ways:

 1. Console:
    - `yopad repos add [URL to raw text location fo your repository's root index.yrf file]`
    - Example: `yopad repos add https://raw.githubusercontent.com/Haltroy/Yopad/main/index.yrf`
 2.  Yopad:
    1. Open Yopad and click the hamburger icon on the left.
    2. Select "Manage repositories..." and then click "Add new..."
    3. Enter the URL to raw index.yrf file located inside the root folder of your repository.
    4. Click "Add".
