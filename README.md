foo_uie_playlists_dropdown
==========================

A component for [foobar2000](http://www.foobar2000.org/) audio player.

This component displays playlists in a dropdown list. Titles of the playlists are configurable and various informations about playlist are available (through formatting string).

The component supports Drag&Drop, easy playlists reordering and sorting, context menu, custom icons and styles, and much more!

Screenshot
----------

![foo_uie_playlists_dropdown](https://github.com/karolsarnacki/foo_uie_playlists_dropdown/raw/master/foo_uie_playlists_dropdown/screenshots/foo_uie_playlists_dropdown_0752.png)

Development Environment
-------------------------------------

Solution/Project files are for MSVC9 ("Visual Studio 2008").

Visual Studio 2008 *Express* users need to download and install [Windows Driver Kit](http://www.microsoft.com/whdc/DevTools/WDK/WDKpkg.mspx)
(for ATL) and [WTL](http://wtl.sourceforge.net/), and add ATL/WTL `include` directories to Visual Studio
Directories.

Columns UI SDK 6.3.1 + SDK 2010-10-02
-------------------------------------

You need to make a few changes to Columns UI SDK 6.3.1 in order to successfully compile the plugin against SDK 2010-10-02.

1. Replace all `infinite` occurrences with `pfc_infinite`.
2. In file `window.h`, replace the definition:
       window_factory() : service_factory_base(window::class_guid)
   with:  
       window_factory() : service_factory_base(window::class_guid, service_factory_traits<window>::factory_list())
