# HelloWorldRepo

A tutorial to setup a basic github (with markdown)

## Prerequisite:
  * I hope you understand directory trees.
  * And the meaning of $HOME $PWD (if not,try `echo $HOME` or `echo $PWD`)
  * Remember `.` is synonymous to `$PWD`

## Making your first commmit

1. Clone the past index of this repository to your local directory, say $HOME
    ```
    git clone https://github.com/shouldsee/HelloWorldRepo $HOME/HelloWorldRepo  
    #### The traget directory can be omiited to just $HOME (or empty which means $PWD)
    #### Or try to be humourous:
    git clone https://github.com/shouldsee/HelloWorldRepo mySecretion  
    ```
1. Download your favourite meme in the format of `.jpg` or `.png` or `.svg`
    * And save it as '$HOME/mySecretion/someMeme.jpg' 
    * if you are feeling lazy, do `wget https://i.imgflip.com/12zidp.jpg -O $HOME/mySecretion/someMeme.jpg`

1. Create a markdown file `$HOME/myMeme.md`
    * Paste the following text into `$HOME/myMeme.md` 
    ```
    ### This is some lovely meme
    
    ![ In plain markdown, you only see me when the link to image is broken ](./someMeme.jpg)
    
    Unless you downloaded you image from [Imgur](https://imgur.com/), you probably should not find the image above on Imgur.
    
    But you can calculate its probability easily with:
    
    $$
    P(\text{imgur}) =\sum_{\text{images}}{ P(\text{imgur},\text{images})  }
    $$
    ```
1. If you are good at markdown, play some tricks with `README.md`

1. Now add/stage your changes using `git add`
    * You can specify files explicitly `git add myMeme.md someMeme.jpg`
    * Or to be lazy just do `git add $PWD` or `git add .` to add all modifications to next commit
    * Make sure files are added by doing `git status`
1. Once you are sure all modifications are added, record these by making a COMMIT!
    * `git commit -m i_dont_know_what_im_doing`
    * or just do `git commit` and enter your message in the new text editor window. You have to save a non-empty COMMIT_MSG in order to proceed
1. If you commit is successful, git should have recorded your changes and you can continue to make next commit
    * Optional:
        * You can jump back one commit temporarily with `git checkout HEAD~1`
        * You can jump to the newest commit with `git checkout HEAD`

## Update your changes to a remote server:

So far you have made a local commit, that is not visible to others unless you email the directory to them or somehow exchanged the index in `.git/` . Luckily, there are many public servers that host remote copy of a repository.

1. To check what remotes are visible to your current git repo, do `git remote -v`
    * You should see that `origin https://github.com/shouldsee/HelloWorldRepo` is listed. Hence it's known as `origin`
1. To check what branches are visible, do `git branch -v`
    * You should see `* master ` is your current branch
1. Now try `git push origin master`, which would push the `master` branch to `origin` remote.
    * And you would enter username and password to attempt this push.
    * And you would find yourself failed, since you are not authorised write permission of this repository.
    * In real life, you would record the error message and search Google or StackOverflow for an answer.
1. Okay, but we can always find another way.
    * Open the remote (https://github.com/shouldsee/HelloWorldRepo) as a webpage.
    * Click `Fork` on the top-right corner
    * Login if required
1. You will now obtain a remote fork of this repository, associated with a url (which you can read off in the URL bar, often in the form `https://github.com/{YOUR_GITHUB_USERNAME}/HelloWorldRepo`)
    * now we are gonna do some magic to redirect the upstream to your new remote repository
    * `git remote set-url origin https://github.com/{YOUR_GITHUB_USERNAME}/HelloWorldRepo`   (you will need to fill in this command before execution!!!)
1. After redirect the `origin` to your newly forked repository, you can try to push the commit again
    * `git push origin master`
    * Enter github credential accordingly
    * Works like a charm hopefully


**Feel free to PR this repository should you find any typo/bug.**

    
