#About
This repository contains the ebuild and source files for www-plugins/adobe-flash. The ebuild removes the Adobe January 12th 2021 EOL blocker by replacing the timestamp used to check for the blocking date with infinity.
#Installing
Just put the `www-plugins` directory into your local overlay repository and do `emerge www-plugins/adobe-flash`. You may have to regenerate the manifest in case I forgot to update it after modifying the files. Do this by executing `ebuild *.ebuild manifest` inside the `www-plugins/adobe-flash` directory.
#Removing the Blocker Manually
If you don't use Gentoo and want to remove the EOL blocker from a plugin shared object, you can use the following command: `sed -e 's/\x00\x00\x40\x46\x3E\x6F\x77\x42/\x00\x00\x00\x00\x00\x00\xFF\x7F/ < plugin.so > unblocked.so'
