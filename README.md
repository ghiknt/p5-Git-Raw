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

## License

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

