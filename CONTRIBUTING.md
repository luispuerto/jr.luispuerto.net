# Contributing

When contributing to the code of this repository, please first discuss the changes you wish to make via [issue][issues], email, or any other method with the owner/s of this repository before making a change. 

However, if you want to to contribute with content, and you aren't a regular author of the blog, please contact the owners before contributing, preferable by email. Nevertheless, typos, orthography, grammar or style corrections in the content are much appreciated, since the two regular content contributors of the blog aren't English native speakers. Please make a pull request right away if you come across one of those and you want to correct. 

In any case, please, create a branch for your contribution, either on your fork or on this repository, if you have permission to do so. This way your contribution will go through **pull request process** and others will acknowledge your work. 


We are (trying to) follow [gitflow][] branching model, so if you are contributing to the code name your branch accordingly (fix, feature, etc). If you are contributing with content, either with a post or page we follow the convention `post/name-of-post` or `page/name-of-page` to name branches for the purpose of writing content and trying to mimic the gitflow method for code. The `name-of-post` has to be something descriptive and short. Doesn't have to be the tittle of the post. 

Even if you have pushing permission never ever push to master before you talk to the other regular contributors, so no one ends up with a mess in their local repo that ends in everyone repo's.  

## Pull Request Process

All the merges have to go through pull request process. There could be two kinds of pull request, for the code or for the content. 

### Code
 
1. Ensure that the page is building properly and nothing that was working before isn't working now. 
2. If you are doing some functionality change on the site, please update the [README.md][] and or any other proper documentation. 
3. If necessary increase the version numbers in any examples files and the README.md to the new version that this Pull Request would represent. The versioning scheme we use is [SemVer][].
4. Please be sure that the pull request passes the necessary tests. When test are passed we will proceed to merge it.  
5. Try to keep commits to the bare minimum that have sense for explaining the changes you are doing in a logical manner. Consider doing a `git rebase -i` to `develop` before you start the pull request. Squashing all commits into one could be a good idea, even more if we are talking of small changes. 

### Contend

1. Proofread the post to verify that there aren't any typo, o grammatical error. 
2. Please verify the there are no broken links on your post, either to another post or any other content. You can use the [`html-proofer` gem][html-proofer] to help in this process this process. 
3. Build the site locally so you can verify that is building as intended and nothing is out of place. 
4. `git rebase -i` to `master` is really advisable and squashing all the commits into one very recommended before start the pull request process. 

[issues]: https://github.com/luispuerto/jr.luispuerto.net/issues
[html-proofer]: https://github.com/gjtorikian/html-proofer
[code of conduct]: CODE_OF_CONDUCT.md
[SemVer]: http://semver.org/
[README.md]: README.md
[gitflow]: https://nvie.com/posts/a-successful-git-branching-model/
