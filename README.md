setup.git
=========
Clone and run this on a Ubuntu 12.04.2 LTS to
configure both the machine and your individual development environment as
follows:

```sh
cd $HOME
sudo apt-get install -y git-core
git clone https://github.com/avidys/setup.git
./setup/setup.sh   
```

How to do a central repo
git --bare init
git remote add origin <url-of-bare-repo>
git push --all origin

how to duplicate

- Make a bare clone of the repository
```sh
git clone --bare https://github.com/exampleuser/old-repository.git
```

Mirror-push to the new repository
```sh
cd old-repository.git
git push --mirror https://github.com/exampleuser/new-repository.git
```

Remove our temporary local repository
```sh
cd ..
rm -rf old-repository.git
```

If you want to mirror a repository in another location, including getting updates from the original, you can clone a mirror and periodically push the changes.

Make a bare mirrored clone of the repository
```sh
git clone --mirror https://github.com/exampleuser/repository-to-mirror.git
```

Set the push location to your mirror
```sh
cd repository-to-mirror.git
git remote set-url --push origin https://github.com/exampleuser/mirrored
```

In order to siulateously push to 2 repo
```sh
git remote add all github:path/proj.git
git remote set-url --add --push all url = heroku:path/proj.git
git push all --all

git remote | xargs -L 1 git push
```
```
[remote "all"]
  url = github:path/proj.git
  url = heroku:path/proj.git
```

See also http://github.com/avidys/dotfiles.

From [Startup Engineering Video Lectures 4a/4b](https://class.coursera.org/startup-001/lecture/index).
