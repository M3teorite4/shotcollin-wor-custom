THIS MODIFIED VERSION OF THE SCRIPT MAKES CHANGES TO CAMSVC SERVICE RELATED COMMANDS SO THE SCRIPT DOESN'T MESS WITH YOUR CONFIGURATION OF THE SERVICE ( DOESN'T CAUSE INABILITY TO OPEN THE SETTINGS APP ETC.)
THE ORIGINAL SCRIPT WAS CREATED BY shotcollin : https://github.com/shotcollin


l - stands for line (:) {line in question}
camsvc - Capability Access Manager Service 


the reason why the camsvc is disabled when the $beMicrophoneSafe is set to 1 or true by default and causes the settings problem is so the privacy of your microphone cannot be compromised by software via the "access to microphone by apps" setting, the settings app doesn't run when the camsvc is disabled, control panel is not a full substitue for the Settings app so we need it, but it also does it's job and apps can no longer access your microphone and more importantly cannot change the setting.


comment:  if you find yourself in a situation where your camsvc is already messed up and you are unable to open your settings app, navigate to the services app which is still accessible, find the Capability Access Manager Service in the list and change the startup type to manual or automatic ( in case of manual an app or an event has to first ask for the service to startup, in case of automatic the service starts with the bootup but it's your preference) - not disabled


l:30 - beMicrophoneSafe is set to false
in addition{
	l:1411-1419 - even if $beMicrophoneSafe is true, it won't touch your camsvc configuration either way
}

l:1284 - removed the change in startup of camsvc to automatic; the removed command no longer makes your settings app inaccessible



