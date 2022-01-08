# Yorot Package Distribution (Yopad) Offical Repository
This repository is only for dstributing Yopad pakcages, if you want to see the source codes of Yopad, see [Official Yorot Repository](https://github.com/Haltroy/Yorot) or any flavor repository.

## Usage
`Yo`rot `Pa`ckage `D`istribution Service and Yorot Store will look for this repository for installing, searching and upgrading packages.

This repositroy includes all Yorot add-ons and a list of categories such as:
 - Themes
   - Uncategorized = `((leave empty))`
   - Black/White = `bw`
   - Multi-color = `mc`
   - Red = `red`
   - Pink = `pink`
   - Orange = `orange`
   - Brown = `brown`
   - Yellow = `yellow`
   - Green = `green`
   - Blue = `blue`
   - Purple = `purple`
 - Extensions
   - Uncategorized = `((leave empty))`
   - Accessibility = `access`
   - Blogging = `blog`
   - Developer Tools = `devtools`
   - Fun = `fun`
   - News & Weather = `nw`
   - Photos = `photos`
   - Productivity = `product`
   - Search Tools = `searchtools`
   - Shopping = `shop`
   - Social & Communication = `social`
   - Sports = `sports`
 - Web Engines
 - Apps
   - Uncategorized = `((leave empty))`
   - Accessibility = `access`
   - Blogging = `blog`
   - Developer Tools = `devtools`
   - Fun = `fun`
   - News & Weather = `nw`
   - Photos = `photos`
   - Productivity = `product`
   - Search Tools = `searchtools`
   - Shopping = `shop`
   - Social & Communication = `social`
   - Sports = `sports`
 - Languages
 - Experience Packs

These are all seperated to folders inside the main repository folder. Also, all package owners must create their own folders inside the main folders. An example folder scheme looks like this:

 - Themes
   - index.xml - Themes Main Repository file
   - Haltroy
     - Yorot Light
   - Someone else
     - Another Theme
   - ...
 - Extensions
   - index.xml - Extensions Main Repository File
   - Someone else
     - VPN Proxy 
   - Haltroy
     - Dark Mode  
   - ...
 - Apps 
   - ...


All add-ons must include 2 things:
 - A Foster file,
 - At least 1 Foster package file containing the add-on itself.
   - If the latest version is based out of another version, those packages are also have to be added. 
 - (Optional) Screnshots of your add-on in the same folder with Foster file in `[Screenshot Number].png` format.
**NOTE**: The numbers of screenshots are limited to 10, starting from 0 to end in 9.
 - (Optional) Older versions of the add-on itself for archiving.

Add-ons can include multiple versions and Foster Archs in the same folder. But the URL to folder for the add-on must be included in the index.xml files in each main add-on folder, not the main index.xml file locaten on root directory.

## Adding your own packages
Adding packages to this repository is allowed, but you have to create a pull request to submit packages.

 1. Fork this repository, start with editing the index.xml files inside the add-on type (ex. Themes, Apps etc.) folders:
     - Insert this text under `<root>`: `<PackageRef Url="[Your name]/[Add-on Name]/" />` 
     - You can add `Category` attribute with multiple categories. See the add-on list for category code names. Example: `<PackageRef Url="[Your name]/[Add-on Name]" Category="[Category]" />`
	 - You can mark your Add-on as inappropriate with `NSFW="true"` attribute. Example: `<PackageRef Url="[Your name]/[Add-on Name]" Category="[Category]" NSFW="true" />`
    - **Changing anything else makes your package rejected.**
 2. In your forked repository, create your own folder in add-on folder(s), create another folder inside your own folder for the add-on itself and put your add-on packages and Foster file there. You can also add screenshots. **You can only play with that folder, you cannot touch anyone else's folders without their consent or your package will be rejected.**
**NOTE**: You can use another URL for mirrors but we recommend putting your file inside that folder just in case. Also, the other mirror URLs must be allowed to use. See [SECURITY - Mirrors](https://github.com/Haltroy/Yopad/blob/main/SECURITY.md#mirrors) 
 3. In that same directory, create a `info.xml` file with following content (Note: The `<Desc>` node is optional.):
 
		<?xml version="1.0" encoding="utf-16"?>
		<root>
		  <Name>[Add-on Name]</Name>
		  <CodeName>[Add-on Code Name]</CodeName>
		  <Desc>[Add-on Description]</Desc>
		</root>


 4. Send a pull request to this repository with required information.
    - In title: `[NEW] [Add-on type] - [Your add-on name]`.
    - Description is optional.
 5. Moderating team will review your pull request. If your package passes tests, then it will be merged to main system. 
    - We check if your add-on complies with our [Security Policy](https://github.com/Haltroy/Yopad/blob/main/SECURITY.md).
    - We test and look the code of your add-on to test if this add-on contains malicious stuff or is malicious.
	- We check if your add-on is appropriate
 6. Your add-on appears on Yorot and any flavor.
 7. (Optional) Remove your forked repository from repository settings. **Only do this if your pull request is merged.**

## Updating your packages
Similar to adding a new package, except you don't need to create a new folder this time. 

 1. Fork this repository by adding your new version to your folder first.
 2. In your forked repository, change the Foster file of your package. You also can change the screenshots etc. too.
 3. Send a pull request sinmilar to before, but this time change "[NEW]" to "[UPDATE]" in the title.
 4. Follow step 4 in "Adding your package" section.

## Removing your packages
Similar to adding or updating packages, except you only have to delete the add-on folder and delete the `PackageRef` line of your addon from `index.xml` file and replace `[NEW]` or `[UPDATE]` with `[REMOVE]` in title. 

## Creating your own repositories
You can create a repository similar to this one, but you can't add that repository to here. You can move the packages independently.

Adding a custom repository to user's Yopad is simple an can be done in 2 ways:

 1. Console:
    - `yopad repos add [URL to raw text location fo your repository's root index.xml file]`
    - Example: `yopad repos add https://raw.githubusercontent.com/Haltroy/Yopad/main/index.xml`
 2.  Yopad:
    1. Open Yopad and click the hamburger icon on the left.
    2. Select "Manage repositories..." and then click "Add new..."
    3. Enter the URL to raw `index.xml` file located inside the root folder of your repository.
    4. Click "Add".
