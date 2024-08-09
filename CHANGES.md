
# 1.x.x

added snowagent_pkg variable because filename and pkgname are different
add rpm gpg key, https://community.snowsoftware.com/s/article/GPGPGPSigningofLinuxRPMpackages-SnowInventoryAgentClientforLinux-v2

rpm update not possible, so you have first to uninstall the old rpm
snowagent_current_version needed to check the installed rpm version

Config is included in the package, changed from template to lineinfile
The template itself gets obsolete
