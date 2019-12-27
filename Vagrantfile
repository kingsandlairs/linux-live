Vagrant.configure(2) do |config|
  config.vm.box = "debian/buster64"
  config.vm.provision "shell", inline: <<-SHELL
		sudo locale-gen UTF-8
		sudo apt-get update
		sudo apt-get -y install gcc-8
		sudo apt-get -y install nasm python36 python3-pip nodejs npm
		sudo apt-get -y install qemu squashfs-tools
		sudo apt-get -y install xorriso zip apache2 git bazaar subversion mercurial
		sudo apt-get install -y genisoimage cmake qt5
		sudo apt-get install -y qtcreator
		wget ftp://ftp.gnu.org/gnu/mtools/mtools-4.0.23.tar.gz
		tar xvzf mtools-4.0.23.tar.gz
		cd mtools-4.0.23
		./configure
		make
		sudo make install
		sudo ln -s /usr/bin/gcc-8 /usr/bin/x86_64-elf-gcc
		sudo ln -s /usr/bin/ld /usr/bin/x86_64-elf-ld
		sudo ln -s /usr/bin/as /usr/bin/x86_64-elf-as
		sudo ln -s /usr/bin/nm /usr/bin/x86_64-elf-nm
		sudo ln -s /usr/bin/objdump /usr/bin/x86_64-elf-objdump
  SHELL
end
