
### Port Forward default in VagrantFile


    config.vm.network :forwarded_port, guest: 3000, host: 3000
    config.vm.network :forwarded_port, guest: 5432, host: 5432

*5432 => default postgres*



### Install:

* Node.js stable version
* Postgresql 9.1



to make some chnages edit the file vagrant/puppet/manifests/main.pp

      class { 'postgresql::server':
          version => '9.1',
          port => 5432,
      }
      
      
more info [here](https://forge.puppetlabs.com/akumria/postgresql) about module usage