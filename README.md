## Instructure config using masterless puppet
 
Started from the RHEL base as Amazon Linux caused problems.  Facter < 1.7 does not recognise Amazon Linux as a compatible with RHEL so puppetlabs modules were not seeing a valid installation target.

### Make the instance ready for puppet
```
  sudo yum update
  sudo yum install puppet
  sudo yum install vim
  sudo yum install git
  gem install r10k
  gem install hiera
```

## R10k
Setup a  control repo as described in the  setup document
* R10k quickstart https://github.com/puppetlabs/r10k/blob/master/doc/dynamic-environments/quickstart.mkd

Modules defined in the Puppetfile can be installed using:
`r10k puppetfile install -v`

## Link to puppet locations
```
sudo ln -s $REPO/hieradata/ /var/lib/hiera/
```

### Apply puppet
`sudo puppet apply --modulepath="./modules:site" ./site.pp § --debug`


### References
* https://puppet.com/blog/git-workflow-and-puppet-environments
* https://docs.puppet.com/hiera/1/complete_example.html
* http://garylarizza.com/blog/2014/03/07/puppet-workflow-part-3b/
* https://docs.puppet.com/hiera/3.2/puppet.html
* https://docs.puppet.com/puppet/4.8/
* [Masterless puppet using a Puppetfile](https://gist.github.com/brasey/030b318a37b07acd21af)

