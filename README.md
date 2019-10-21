# cherryframework_php7
This is a fix for Cherry Framework so it works in PHP 7.x.
CherryFramework throws an error when you upgrade to PHP 7.x.
This repository fixes that by addressing the following errors:

Fatal error: 'continue' not in the 'loop' or 'switch' context in /wp-content/plugins/cherry-plugin/includes/widgets/widgets-manager.php on line 564
The problem is there's a 'continue' command in there, but it's not in a loop.

Fix: 
1. Replace file /wp-content/plugins/cherry-plugin/includes/widgets/widgets-manager.php
2. Change the code:
	// if widget doesn't exists - skip this iteration
	//if ( !isset($wp_registered_widgets[$id]) ) continue;
	if ( !isset($wp_registered_widgets[$id]) ) return false;

