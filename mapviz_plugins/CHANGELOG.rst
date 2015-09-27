^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Changelog for package mapviz_plugins
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Forthcoming
-----------
* Renames all marti_common packages that were renamed.
  (See http://github.com/swri-robotics/marti_common/issues/231)
* Fixes catkin_lint problems that could prevent installation.
* Exports the mapviz_plugins library
* Adds find_package(OpenCV REQUIRED) to cmake config
* adds icon to gps plug-in
* includes yaml_util header in mapviz plug-in base class
* adds gps_common dependency
* Sets the point orientation properly based on the GPSFix track.
* Converts incoming GPSFix points to the local XY frame as they arrive.
* Changes the GPS plugin to always transform from the local XY frame.
* Adds a plugin to display GPSFix data.
* Fixes a few instances where "multires" was typoed as "mutlires".
* updates cmake version to squash the CMP0003 warning
* removes dependencies on build_tools
* switches format 2 package definition
* Updates marker_plugin to correctly handle marker orientation.
* adds color selection for path visualization
* display preview icon next to plug-in names
* sets the z component of path points to 0 before transforming to avoid uninitialized values
* fixes missing organization in license text
* fixes for GLEW/GL include order
* catkinize mapviz
* changes license to BSD
* adds license and readme files
* Contributors: Edward Venator, Elliot Johnson, Marc Alban, P. J. Reed
