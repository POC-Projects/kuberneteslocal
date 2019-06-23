<H3>Pre-Requisites:</H3>
1) Install vagrant
2) Install Virtual Box

cd into this location and run the command vagrant up

<H3>How to stop vm's spun up with vagrant ?</H3>
1) vagrant suspend
2) vagrant halt
3) vagrant destroy

<H3><B>Suspend</B></H3>
Command: vagrant suspend [name|id]

This suspends the guest machine Vagrant is managing, rather than fully shutting it down or destroying it.

A suspend effectively saves the exact point-in-time state of the machine, so that when you resume it later, it begins running immediately from that point, rather than doing a full boot.

This generally requires extra disk space to store all the contents of the RAM within your guest machine, but the machine no longer consumes the RAM of your host machine or CPU cycles while it is suspended.

<H3>Halt</H3>
Command: vagrant halt [name|id]

This command shuts down the running machine Vagrant is managing.

Vagrant will first attempt to gracefully shut down the machine by running the guest OS shutdown mechanism. If this fails, or if the --force flag is specified, Vagrant will effectively just shut off power to the machine.

For linux-based guests, Vagrant uses the shutdown command to gracefully terminate the machine. Due to the varying nature of operating systems, the shutdown command may exist at many different locations in the guest's $PATH. It is the guest machine's responsibility to properly populate the $PATH with directory containing the shutdown command.

» Options

-f or --force - Do not attempt to gracefully shut down the machine. This effectively pulls the power on the guest machine.

<H3>Destroy</H3>
Command: vagrant destroy [name|id]

This command stops the running machine Vagrant is managing and destroys all resources that were created during the machine creation process. After running this command, your computer should be left at a clean state, as if you never created the guest machine in the first place.

For linux-based guests, Vagrant uses the shutdown command to gracefully terminate the machine. Due to the varying nature of operating systems, the shutdown command may exist at many different locations in the guest's $PATH. It is the guest machine's responsibility to properly populate the $PATH with directory containing the shutdown command.

» Options

-f or --force - Do not ask for confirmation before destroying.
--[no-]parallel - Destroys multiple machines in parallel if the provider supports it. Please consult the provider documentation to see if this feature is supported.
The destroy command does not remove a box that may have been installed on your computer during vagrant up. Thus, even if you run vagrant destroy, the box installed in the system will still be present on the hard drive. To return your computer to the state as it was before vagrant up command, you need to use vagrant box remove.
