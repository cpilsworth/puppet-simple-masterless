## Things to install on instance
 
```
  sudo yum update
  sudo yum install puppet
  sudo yum install vim
  sudo yum install git
  gem install r10k
  gem install hiera
```

## setup 
* R10k quickstart https://github.com/puppetlabs/r10k/blob/master/doc/dynamic-environments/quickstart.mkd



Apply puppet : 
`sudo puppet apply --modulepath="./modules:site" ./site.pp § --debug`
