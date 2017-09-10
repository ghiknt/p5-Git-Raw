# p5-Git-Raw locacl repository


## Structure
This is my local clone of Jacques Germishuys p5-Git-Raw project <https://github.com/jacquesg/p5-Git-Raw> to allow local changes.

* Branches:
    * master - My development branch.
        *  Includes a local Bugs Everywhere repository
    * upstream - Clone of current upstream project <https://github.com/jacquesg/p5-Git-Raw>
    * upstream-merge - Includes cherry picked updates from master for submission to upstream.


## Creation/updates

```bash
git clone git@github.com:jacquesg/p5-Git-Raw.git
cd p5-Git-Raw
git remote rename origin github-jacquesg
git branch -m master upstream
git branch --set-upstream-to=github-jacquesg/master upstream
git remote add github-ghiknt git@github.com:ghiknt/p5-Git-Raw.git
git checkout -b upstream-merge github-ghiknt/master
git branch master
git checkout master
git branch -v -a
```

## Building

```bash
# Based on commands in .travis.yml
#Prerequisites
sudo apt-get install libtinfo-dev
sudo apt-get install libreadline-dev 

cpan
install cpanminus

cpanm --sudo  Term::ReadLine::Gnu 
cpanm --sudo MooseX::Getopt
cpanm --sudo PPI::XS
cpanm --sudo Dist::Zilla~">= 5.0000, < 6.0000"
cpanm --sudo --notest Dist::Zilla~">= 5.0000, < 6.0000"
cpanm --sudo --notest  Dist::Zilla::PluginBundle::Author::ALEXBIO
cpanm --sudo  Pod::Coverage::TrustPod
cpanm --sudo  Devel::Cover::Report::Coveralls
cpanm --sudo  Dist::Zilla::App::Command::cover
dzil authordeps --missing
   cpanm --sudo Dist::Zilla::Plugin::MetaProvides::Package
   cpanm --sudo Dist::Zilla::Plugin::MinimumPerl
dzil listdeps --missing


cpanm --local-lib=~/perl5 local::lib && eval $(perl -I ~/perl5/lib/perl5/ -Mlocal::lib)
dzil build

# Test
NETWORK_TESTING=1 dzil test -ignore_re ^deps -ignore_re CORE -ignore_re ^const -ignore_re curl -test

# Coverage
dzil cover -ignore_re ^deps -ignore_re CORE -ignore_re ^const -ignore_re curl -test 

# Install
dzil install --install-command "cpanm --sudo ."
```


##   License

* Upstream Authors:
    * Alessandro Ghedini <alexbio@cpan.org>
    * Jacques Germishuys <jacquesg@striata.com>

* Upstream Copyright Statement

    2012 Alessandro Ghedini

    This program is free software; you can redistribute it and/or modify it under the terms of either: the GNU General Public License as published by the Free Software Foundation; or the Artistic License.

    See http://dev.perl.org/licenses/ for more information.

* Local Modifications

    Copyright 2017 whk <https://whk.name/about/me/>

    This program is free software; you can redistribute it and/or modify it under the terms of either: the GNU General Public License as published by the Free Software Foundation; or the Artistic License.

    See http://dev.perl.org/licenses/ for more information.

