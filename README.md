About
-----

This is a Windows 7 (32bit) Box that is derived from a box provided by
microsoft on [Modern.IE](https://developer.microsoft.com/en-us/microsoft-edge/tools/vms/windows) with a 10 day evaluation licence or use this
["IE11 on Win7" Vagrant Box with build number 20150916](https://az792536.vo.msecnd.net/vms/VMBuild_20150916/Vagrant/IE11/IE11.Win7.Vagrant.zip) adapted to match vagrant's requirements:

 * User is 'vagrant' (password 'vagrant')
 * WinRM is activated (for ``vagrant powershell``)
 * RDP is activated (for ``vagrant rdp``)
 * SSH is activated (for ``vagrant ssh``)
 * chocolately is installed for easy unattended software installations
 * Windows Defender is disabled to avoid unnecessary load


Easy install  on an vagrant
--------------------------------
* Download from [here](https://az792536.vo.msecnd.net/vms/VMBuild_20150916/Vagrant/IE11/IE11.Win7.Vagrant.zip)
* Unpack "IE11 - Win7.box" in ZIP-file to project directory
* run ``vagrant box add "IE11 - Win7.box" --name IE11Win7`` or
* rename box to "IE11-Win7.box" and run ``vagrant box add  file:///C:/path/to/file.box/IE11-Win7.box  --name IE11Win7 ``
* run ``vagrant up`` (wait for timeout message!)


To create this box run the following steps
---------------------------------------------------------------------------------

* Download most up to date image from "https://dev.windows.com/en-us/microsoft-edge/tools/vms/windows/"
* Unpack "IE11 - Win7.box" in ZIP-file to project directory
* run ``vagrant box add "IE11 - Win7.box" --name IE11Win7``
* run ``vagrant up`` (wait for timeout message!)
* Start VirtualBox, and do the following operations in the vanillas-win-... guest:
  * open IE click "Network"
  * activate "Network discovery and filesharing" for private networks
  * run ``\\VBOXSRV\vagrant\step1_run_on_guest_as_IEUser_as_admin.cmd`` as admin
  * run ``\\VBOXSRV\vagrant\step2_run_on_guest_as_vagrant_as_admin.cmd`` as admin
  * activate "Private Network" for private networks
  * optionally update Virtualbox guest additions (Virtualbox Menu "Device / Guest additions")
* run ``\\VBOXSRV\vagrant\step3_run_on_host.cmd`` (from host)
* (optionally upload new created ``vanilla-win7-32bit.box`` to http://atlas.hashicorp.com)
