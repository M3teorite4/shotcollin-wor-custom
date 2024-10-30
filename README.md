THIS MODIFIED VERSION OF THE SCRIPT MAKES CHANGES TO CAMSVC SERVICE RELATED COMMANDS SO THE SCRIPT DOESN'T MESS WITH YOUR CONFIGURATION OF THE SERVICE
THE ORIGINAL SCRIPT WAS CREATED BY shotcollin : https://github.com/shotcollin


l - stands for line (:) {line in question}
camsvc - Capability Access Manager Service 


l:30 - beMicrophoneSafe is set to false
in addition{
	l:1411-1419 - even if $beMicrophoneSafe is true, it won't touch your camsvc configuration either way
}

l:1284 - removed the change in startup of camsvc to automatic; the removed command no longer makes your settings app inaccessible



