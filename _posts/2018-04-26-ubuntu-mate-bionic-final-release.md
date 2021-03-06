---
layout: blog-post
class: blog
title: Ubuntu MATE 18.04 LTS Final Release
permalink: /blog/ubuntu-mate-bionic-final-release/
description: Ubuntu MATE 18.04 LTS (Bionic Beaver) Final Release
category: release
author: Martin Wimpress
lang: en
discourse_topic_id: 21335

gallery:
    - image: /images/blog/layouts/Familiar.png
      caption: Familiar - the default experience, a familiar two panel layout with a searchable menu
    - image: /images/blog/layouts/Mutiny.png
      caption: Mutiny - application dock, searchable launcher and global menus similar to Unity 7
    - image: /images/blog/layouts/Cupertino.png
      caption: Cupertino - a dock and top panel with searchable launcher and global menus similar to macOS
    - image: /images/blog/layouts/Redmond.png
      caption: Redmond - single bottom panel with a searchable menu, similar to the taskbar in Windows
    - image: /images/blog/layouts/Pantheon.png
      caption: Pantheon - a dock and top panel with a searchable menu
    - image: /images/blog/layouts/Contemporary.png
      caption: Contemporary - modernised two panel layout featuring a searchable menu with global menus
    - image: /images/blog/layouts/Netbook.png
      caption: Netbook - a compact, single top panel layout, ideal for small screens
    - image: /images/blog/layouts/Traditional.png
      caption: Traditional - two panel layout featuring the iconic 'Applications, Places, System' menu
---

**Charles Babbage wasn't lying when he said _"The only thing that would
make my Difference Engine any better would be a modern customisable
desktop environment that didn't deviate from traditional desktop
paradigms (unless I wanted it to.)"_ In a long lost diary entry Ada
Lovelace scribbled _"If only my code could be matched to an OS that had
a perfect blend of usability and style accompanied by a handpicked
selection of quality software packages."_
[ENIAC](https://en.wikipedia.org/wiki/ENIAC), moments before being
unplugged in 1956, spat out a final message: _"Give us a reboot when
Ubuntu MATE 18.04 LTS is out will ya?"_**

Dust off 20,000 vacuum tubes and check those 5,000,000 hand soldered
joints because Ubuntu MATE 18.04 LTS is here and it's time to power it
up.

MATE Desktop 1.20.1 inclusion alone is enough to make Babbage weep with
joy but there is still more. Caja is primed to encrypt your secrets
with GnuPG, and with bulk renaming built right in to the file manager
you can finally deal with those pesky family reunion photos.

Got a fancy new display and itty bitty pixels? HiDPI support bounds into
this LTS, it's so dynamic you won't know what to do with yourself. We
have tweaked desktop layouts, improved global menus, refined our
Head-Up Display (HUD) and updated Brisk Menu. It's dandy!

We could scream it all here in this blurb, instead we suggest you take
a scroll through the notes below and behold the majesty that is Ubuntu
MATE 18.04 LTS.

We will scream *"Thank You!"* however. A *"Thank You!"* to everyone who
contributed code, documentation, artwork, bug reports, translations or
artwork. A *"Thank You!"* to the members of our community forum who
offer advice and support to those who request it. A *"Thank You!"* to
everyone who has supported the Ubuntu MATE crowd funding that helps
reward and incentivise developers who work on MATE Desktop, Ubuntu MATE
and associated technologies in their spare time. You are the 20,000
vacuum tubes and the 5,000,000 hand soldered joints that make up Ubuntu
MATE. We couldn't be prouder.

{:.center}
![Ubuntu MATE 18.04 LTS](/images/blog/1804-final.png)

No one reads the release notes, isn't that right
[DasGeek](https://www.youtube.com/channel/UCIme1suHyN7cAGrTy8RBdhQ)? So
when our friend [Stuart Langridge](https://www.kryogenix.org/) was
reviewing our draft release notes and commented that they didn't speak
to him, we thought *"all right, we can fix that"*. Stuart, since you
are such a special snowflake and no one else will read these notes,
here they are, bespoke release notes just for you!

# What changed since the Ubuntu MATE 16.04 LTS release?

Just about everything! Ubuntu MATE 18.04 is rammed to the rafters with
new features and improvements compared to 16.04.

## MATE Desktop 1.20.1

The MATE Desktop has transitioned from the GTK 2.24 based MATE 1.12 to
the very latest MATE 1.20.1 based on GTK 3.22. This migration has been
several years in the making, and most of 2016 and 2017 was spent refining the
GTK3 implementation. The move to GTK3 has made it possible to introduce
many of the new features you'll read about below.

Support for `libinput` has been added and is now the default input
handler for mouse and touchpad, which has resulted in much improved
responsiveness and support for multi-finger touch gestures.

Thanks to our friends at
[Hypra.fr](http://hypra.fr/-Home-17-.html?lang=en) accessibility
support (particularly for visually impaired users) has seen continued
development and improvement. MATE Desktop is proud to provide visually
impaired users the most accessible open source desktop environment.

### HiDPI

High DPI displays have a high resolution relative to their physical size
that results in an increased pixel density compared to standard DPI
displays. They are mostly found in high-end laptops and monitors. Our
friends at elementary OS wrote a great blog post explaining
[What is HIDPI and why does it matter](https://medium.com/elementaryos/what-is-hidpi-and-why-does-it-matter-b024eabea20d).

MATE Desktop 1.20 supports HiDPI displays and if you have one then
Ubuntu MATE will automatically enable pixel scaling, presenting you
with a super crisp desktop and applications. HiDPI hints for Qt
applications are also pushed to the environment to improve cross
toolkit integration. Every aspect of the Ubuntu MATE, its themes, its
applications, its icons, its toolkit assets have been updated to take
advantage of HiDPI.

Should you have a HiDPI display and want to disable HiDPI scaling you
can do so via MATE Tweak (for the desktop) and Login Window (for the
greeter), both are available in the Control Centre.

### The File Manager (Caja)

We've added some new features to the file manager (Caja).

  * Added **[Advanced bulk rename](https://tari.in/www/software/cajarename/)** - A batch renaming extension.
  * Added **[Encryption](https://github.com/darkshram/seahorse-caja)** - An extension which allows encryption and decryption of files using GnuPG.
  * Added **[Hash checking](https://github.com/tristanheaven/gtkhash)** - An extension for computing and validating message digests or checksums.
  * Added **[Advanced ACL properties](https://github.com/darkshram/mate-eiciel)** - An extension to edit access control lists (ACLs) and extended attributes (xattr).
  * Updated **[Folder Color](http://foldercolor.tuxfamily.org/)** - An extension for applying custom colours and emblems to folders and files.
  * Replaced the deprecated `caja-gksu` with `caja-admin` which uses PolicyKit to elevate permissions in the file manager for administrative tasks.

`gksu` is deprecated and being removed from Debian. We are aligning
with that objective by replacing all use of `gksu` with PolicyKit.

{:.center}
![Caja Rename](/images/blog/layouts/caja-rename.png)

### Window Manager (Marco)

If your hardware/drivers support
[DRI3](https://en.wikipedia.org/wiki/Direct_Rendering_Infrastructure)
then the window manager (Marco) compositing is now hardware
accelerated. This dramatically improves 3D rendering performance,
particularly in games. If your hardware doesn't support DRI3 then Marco
will fall back to a software compositor.

Marco now supports drag to quadrant window tiling, cursor keys can be
used to navigate the <kbd>Alt</kbd>+<kbd>Tab</kbd>switcher and keyboard
shortcuts to move windows to another monitor were added.

{% include embed/youtube.html
    embed = "https://www.youtube.com/embed/V6kth-4M62o?html5=1&amp;rel=0&amp;showinfo=0"
%}

# Desktop layouts

Using MATE Tweak you can try out the various desktop layouts to find
one that suits you, and either stick with it or use it as a basis to
create your own custom desktop layout.

A new layout has been added to the collection for the Ubuntu 18.04
release Ubuntu MATE 18.04. It is called **Familiar** and is based on
the Traditional layout with the menu-bar (Applications, Places, System)
replaced by Brisk Menu. **Familiar is now the the default layout**.
Traditional will continue to be shipped, unchanged, and will be
available via MATE Tweak for those who prefer it.

Here are some screenshots of the desktop layouts included in Ubuntu MATE
to give you a feel for how you can configure your desktop experience.

{% include blog/gallery.html %}

  * **Familiar** - the default experience, a familiar two panel layout with a searchable menu
  * **Mutiny** - application dock, searchable launcher and global menus similar to Unity 7
  * **Cupertino** - a dock and top panel with searchable launcher and global menus similar to macOS
  * **Redmond** - single bottom panel with a searchable menu, similar to the taskbar in Windows
  * **Pantheon** - a dock and top panel with a searchable menu
  * **Contemporary** - modernised two panel layout featuring a searchable menu with global menus
  * **Netbook** - a compact, single top panel layout, ideal for small screens
  * **Traditional** Traditional - two panel layout featuring the iconic 'Applications, Places, System' menu

In order to create or improve the desktop layouts described above we've
spent the last two years working on a number of projects across the
MATE ecosystem that have enabled us to offer 8 different desktop
layouts, each providing a different desktop experience. Here's some
of the projects we worked on to make it all possible.

## Super key

<img class="right" src="/images/blog/layouts/superkey-small.png" alt="Super Key">

Super key (also known as the Windows key) support is available in the
majority of the desktop layouts. This means <kbd>Super</kbd> can be used
to activate the menus/launchers, and other key-bindings that include
the <kbd>Super</kbd> key also continue to function correctly.

MATE Dock Applet, used in the Mutiny layout, also includes launching or
switching to docked items based on their position using in the dock
using <kbd>Super</kbd> + <kbd>1</kbd>, <kbd>Super</kbd> + <kbd>2</kbd>
which will be familiar to Unity 7 users. <kbd>Super</kbd> +
<kbd>L</kbd> is also recognised as a screen lock key-binding along with
the usual <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>L</kbd> that MATE
Desktop users expect.

## Global Menu

The Global Menu implementation has switched from TopMenu to
[Vala Panel Appmenu](https://github.com/rilian-la-te/vala-panel-appmenu)
which is **compatible with GTK, Qt, LibreOffice, Firefox/Thunderbird, Google
Chrome, Electron and others.**

Global Menus are integrated in the Mutiny and Cupertino desktop layouts
but can be added to any panel, for those who just prefer to use global
menus or those who want to maximise screen space available to their
applications.

{:.center}
![Ubuntu MATE Global Menu](/images/blog/layouts/global-menu.gif)

## Indicators

<img class="right" src="/images/blog/layouts/indicators-small.png" alt="Indicators" />

**Ubuntu MATE 18.04 now uses Indicators by default in all layouts.** If
you've used Ubuntu, these will be familiar. Indicators offer better
accessibility support and ease of use over notification area applets.
The volume in Indicator Sound can now be overdriven, so it is
consistent with the MATE sound preferences. Notification area applets
are still supported as a fallback.

We've been improving Indicator support from release to release for some
time now. In Ubuntu MATE 17.10 many of the panel layouts offered a
complete line up of Indicators, all of which are fully compatible with
MATE. The default Indicators are:

  * Optimus (*only available if you have nvidia prime capable hardware and drivers*)
  * Bluetooth
  * Network
  * Power
  * Messages
  * Sound
  * Session

## MATE Dock Applet

[MATE Dock Applet](https://github.com/robint99/mate-dock-applet) is
used in the Mutiny and Netbook layouts, but anyone can add it to a
panel to create custom panel arrangements. MATE Dock Applet has seen
many improvements over the last 2 years, here are some of the
highlights:

### Icon scrolling

Icon scrolling is automatically enabled when the dock applet runs out
of space on the panel to expand into. Move the mouse over either the
first or last icon in the dock, if scrolling is possible in that
direction the icon will darken and an arrow will be displayed over it.
If you hover the mouse pointer over an icon in this state, the dock
will scroll in the indicated direction. Icon scrolling is automatically
configured and enabled when using the Mutiny desktop layout, when using
any other layout scrolling can be enabled via the MATE Dock Applet
preferences.

### Icon matching

MATE Dock Applet no longer uses its own method of matching icons to
applications and instead uses BAMF. This mean the applet is lot better
at matching applications and windows to their dock icons.

### Assorted improvements

  * Window lists and action lists now have rounded corners and point to their icon in the dock.
  * The delay before action lists appear when the mouse hovers over a dock icon can now be set in the preferences dialog.
  * Apps can now be pinned to specific workspaces, in other words their app icons only appear in the dock when a particular workspace is active. This allows users to customise the dock for each workspace they use.
  * When unpinning an application a notification is now displayed which allows the operation to be undone.
  * The appearance of progress bars on dock icons has been improved.
  * Popup windows (action lists and window lists) no longer steal focus from other windows.

## Brisk Menu

[Brisk Menu](https://github.com/solus-project/brisk-menu) is an
efficient, searchable, menu for the MATE Desktop. We've collaborated
with the [Solus Project](https://getsol.us), the maintainers
of Brisk Menu. A number of features have been added so that, like
Ubuntu MATE itself, Brisk Menu is chameleonic. You'll find Brisk Menu
is used in several of the Ubuntu MATE desktop layouts and is presented
slightly differently in each.

The Mutiny and Cupertino desktop layouts make use of a new dash-style
launcher, which enables a fullscreen searchable application launcher
while the other layouts present Brisk Menu as a more traditional menu.

{:.center}
!![Brisk Menu Dash Launcher](/images/blog/bionic/brisk-menu-dash.png)


## MATE Window Applets

[MATE Window Applets](https://github.com/ubuntu-mate/mate-window-applets) make it
possible to add window controls (mazimise, minimise and close) to a
panel. We used Window Applets to enhance the Mutiny and Netbook layouts
so that both will now remove window controls from maximised windows and
relocate the window controls in the panel.

{:.center}
![MATE Window Applets](/images/blog/bionic/maximus.gif)

## Head-Up Display

A favourite of Unity 7 users is the Head-Up Display (HUD) which
provides a way to search for and run menu-bar commands without your
fingers ever leaving the keyboard. The HUD can be enabled via MATE
Tweak. You activate the HUD by tapping <kbd>Alt</kbd>, you then enter a
search query to find menu items, highlight the one you want and press
enter to trigger it.

If you're trying to find that single filter in Gimp but can't remember
which filter category it fits into or if you can't recall if
preferences sits under File, Edit or Tools in your favourite browser,
you can just search for it rather than hunting through the menus.

The purpose of the HUD is to keep your fingers on the keyboard and
improve the efficiency in driving the menus for keyboard centric users.
We've locally integrated the HUD for similar reasons; if you're looking
at an application, why move the HUD to the top of screen away from where
your eyes are already focused? Keeping the HUD within the context of
the active application eliminates refocusing your attention to a
different part of the screen, particularly helpful for users with high
resolution or multi-display workstations.

{:.center}
![Heads-Up Display (HUD)](/images/blog/layouts/mate-hud-local.gif)

The HUD now has a 250ms (default) timeout, holding <kbd>Alt</kbd> any
longer won't trigger the HUD. This is consistent with how the HUD in
Unity 7 works. The HUD is also HiDPI aware now.

## MATE Tweak

MATE Tweak can now toggle HiDPI mode between auto detection, regular
scaling and forced scaling. HiDPI mode changes are dynamically applied
and we've added a button to launch the Font preferences so users with
HiDPI displays can fine tune their font DPI.

MATE Tweak has a deep understanding of Brisk Menu and Global Menu
capabilities and manages them transparently while switching layouts.
Switching layouts is far more reliable now too. We've removed the
*Interface* section from MATE Tweak. Sadly, all the features the
Interface section tweaked have been dropped from GTK3, making the whole section
redundant. When saving a panel layout the Dock status will be saved too.

{:.center}
![MATE Tweak](/images/blog/bionic/mate-tweak.png)

# Ubuntu MATE Welcome

Welcome and Boutique have been given some love. The software listings
in the Boutique have been refreshed, with some applications being
removed, many updated and some new additions Welcome now has snappier
animations and transitions. Applications selected for installation or
removal via the Software Boutique are now added to a queue so you can
select several installs and removals and process them all at once.

## Browser Selection

A new Browser Selection screen has been added so you can quickly
install your preferred browser.

{:.center}
![Browser Selection](/images/blog/bionic/browser-selection.png)

## System telemetry

Ubuntu MATE Welcome can submit anonymised system information, generated
during an install or upgrade, that will help the developers better
understand what devices Ubuntu MATE is being used on. This data will be
transmitted one time only and includes basic system components but
nothing that is uniquely identifiable. Here is [an example telemetry
report from the workstation of the Ubuntu MATE lead
developer](https://paste.ubuntu.com/p/xWxbbDGBfn/). **We kindly request
that if you install Ubuntu MATE you participate in sending us a
telemetry report.**

{:.center}
![Telemetry](/images/blog/bionic/telemetry.png)


# General improvements

## Minimal Installation

The Minimal Install is a new option presented in the installer that
will install just the MATE Desktop, its utilities, its themes and
Firefox. All the other applications such as office suite, email client,
video player, audio manager, etc. are not installed. If you're
interested, here is [the complete list of software that is removed from
a full Ubuntu MATE 18.04 installation to make the minimal install](https://bazaar.launchpad.net/~ubuntu-mate-dev/ubuntu-seeds/ubuntu-mate.bionic/view/head:/desktop.minimal-remove).

{:.center}
![Minimal Install](/images/blog/bionic/minimal-install.png)

So, who's this aimed at? There are users who like to uninstall the
software they do not need or want to build out their own desktop
experience. So for those users, a minimal install is a great platform
to build on. For those of you interested in creating "kiosk" style
devices, such as homebrew Steam machines or Kodi boxes, then a minimal
install is another useful starting point.

## Documentation

The Ubuntu MATE Guide is a comprehensive introduction to MATE Desktop and
Ubuntu MATE including **how to use everything we ship by default**, along with
detailed instruction on how to tailor, tweak and customise Ubuntu MATE to
suit your preferences.

{:.center}
![Ubuntu MATE Guide](/images/blog/bionic/ubuntu-mate-guide.png)

{% include blog/jumbotron.html
    title = "Buy the books"
    text = "Print and ebook versions of the books **Ubuntu MATE: Upgrading from Windows or OSX** and **Using Ubuntu MATE and Its Applications** are available from our shop."
    button_text = "Shop"
    button_url = "/shop/"
%}

## Slick Greeter

Ubuntu MATE switched to [Slick Greeter](https://github.com/linuxmint/slick-greeter) during the 17.10
development cycle, which still uses LightDM under the hood but is far
more attractive and HiDPI aware.

{:.center}
![Slick Greeter](/images/blog/layouts/slick-greeter.png)

### Slick Greeter Settings

We worked with our friends at [Lubuntu](https://lubuntu.me/) and
[Ubuntu Budgie](https://ubuntubudgie.org/) to land a configuration
utility for Slick Greeter just moments before the final freeze window
closed for 18.04.

{:.center}
![Slick Greeter Settings](/images/blog/bionic/lightdm-settings.png)

## Artwork

### Themes

The Ubuntu MATE themes have been uplifted from GTK2 to GTK3 including
the addition of a new dark variant of the Ambiant-MATE theme. We've
worked tirelessly on all the Ubuntu MATE themes making them fully
compatible with GTK 3.22 and ensuring every pixel is placed exactly
where it should be. [Michael Tunnel](http://michaeltunnell.com/) from
[TuxDigital](http://tuxdigital.com/) retouched countless art assets
for the Ubuntu MATE themes including scaled variants for use on HiDPI
displays. The Ubuntu MATE icon theme was given a facelift thanks to our
friends at [elementary OS](https://elementary.io/) and the default
mouse pointer cursors use the new upstream MATE theme which is also
HiDPI aware. Finally, blink and you'll miss it, the Ubuntu MATE
Plymouth theme (boot logo) is now HiDPI aware.

### Backgrounds

We are no longer shipping `mate-backgrounds` by default. They have
served us well, but are looking a little stale now. We have created a
new selection of high quality wallpapers comprised of some abstract
designs and high resolution photos from [unsplash.com](https://unsplash.com).

### Emoji

We've switched to Noto Sans for users of Japanese, Chinese and Korean
fonts and glyphs. MATE Desktop 1.20 supports emoji input, so we've
added a colour emoji font too.

You can enter emoji in one of two ways, type <kbd>Ctrl</kbd> +
<kbd>Shift</kbd> + <kbd>e</kbd> an **e** prompt will appear and you can
type usual emoji, such as `:-)`, and it will automatically change to a
glyph. Alternatively you can right click in the input area and select
*Insert Emoji* that will display the emoji picker below.

{:.center}
![Emoji Picker](/images/blog/bionic/emoji.png)

## Major Applications

Accompanying **MATE Desktop 1.20.1** and **Linux 4.15** are **Firefox
59.0.2**, **VLC 3.0.1**, **LibreOffice 6.0.3.2** and **Thunderbird 52.7.0**.

{:.center}
![Major Applications](/images/blog/bionic/versions.png)

See the [Ubuntu 18.04 Release
Notes](https://wiki.ubuntu.com/BionicBeaver/ReleaseNotes) for details of all
the changes and improvements that Ubuntu MATE benefits from.

{% include blog/jumbotron.html
    title = "Download Ubuntu MATE 18.04 LTS"
    text = "We've even redesigned the download page so it's even easier to get started."
    button_text = "Download"
    button_url = "/download/"
%}

## Upgrading from Ubuntu MATE 16.04 or 17.10

  * Open the "Software & Updates" from the Control Center.
  * Select the 3rd Tab called "Updates".
  * Set the "Notify me of a new Ubuntu version" dropdown menu to "Long-term support versions".
  * Press <kbd>Alt</kbd>+<kbd>F2</kbd> and type in `update-manager` into the command box.
  * Update Manager should open up and tell you: New distribution release '18.04' is available.
    * If not you can also use `/usr/lib/ubuntu-release-upgrader/check-new-release-gtk`
  * Click "Upgrade" and follow the on-screen instructions.

### Get the Ubuntu MATE snaps

When the upgrade is complete and you're logged in, open a terminal and execute:

    snap install ubuntu-mate-welcome --classic
    snap install software-boutique --classic
    snap install pulsemixer

The snap packages above are installed when performing a clean install of
Ubuntu MATE 18.04, but are not automatically installed when upgrading from an
earlier release.

## Raspberry Pi images

We're planning on releasing **Ubuntu MATE images for the Raspberry Pi after
that 18.10 release is out, in October 2018**. It takes usually takes about
a month to get the Raspberry Pi images built and tested, but we've encountered
some challenges with the 18.04 based images which has delayed their release.
Hopefully we'll have something in time for Christmas 2018 `:-)`
# Known Issues

Here are the known issues.

## Ubuntu MATE

  * Anyone upgrading from Ubuntu MATE 16.04 or 17.10 may need to **use MATE Tweak to reset the panel layout to one of the bundled layouts post upgrade**.
    * Migrating panel layouts, particularly those without Indicator support, is hit and miss. Mostly miss.
  * Choosing *Install Ubuntu MATE* from the boot menu on HiDPI displays will not display Indicators in the installer. However, installs will still complete successfully.
    * This issue only affects HiDPI display users and the workaround is to *Try Ubuntu MATE without installing* and run the installer from the live desktop session.

### Ubuntu family issues

This is our known list of bugs that affects all flavours.

  * [Ubiquity slide shows are missing for OEM installs of Ubuntu MATE and Ubuntu Budgie](https://pad.lv/1713720)
    * To work around this, run `apt install oem-config-slideshow-ubuntu-mate` in the OEM prepare session.
  * [Systems may fail to boot when connected over DisplayPort to an external screen, on nvidia graphics hardware such as the GTX970 chipset](https://pad.lv/1723619)
  * [The warning dialog when a user force a UEFI installation does not respond to input event and the installation is then blocked at this stage](https://pad.lv/1724482)
    * Avoid yourself some troubles and do not force a UEFI installation without a UEFI partition, `grub-installer` will fail anyway.
  * [Doing an *"Entire disk"* installation over an existing LVM installation will fail because the installer selects the wrong boot device](https://pad.lv/1724417)
    * Use custom partitioning instead and manually select the right boot device in the combo box.
  * [Setting a `ulimit` may cause segfaults in certain applications, especially those using webkit2gtk](https://salsa.debian.org/webkit-team/webkit/blob/wk2/unstable/debian/NEWS)
    * Disabling the `ulimit` should restore normal functionality.

You'll also want to check the Ubuntu MATE bug tracker to see what has
already been reported. These issues will be addressed in due course.

  * [Ubuntu MATE Bug Tracker](https://bugs.launchpad.net/ubuntu-mate)

## Feedback

Is there anything you can help with or want to be involved in? Maybe you just
want to discuss your experiences or ask the maintainers some questions. Please
[come and talk to us](https://ubuntu-mate.community/).
