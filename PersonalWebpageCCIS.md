# How to Start a Personal Webpage, hosted by CCIS

This was featured at the end of our Linux workshop.


## Connect to a CCIS server

For this workshop, we will be connecting to the CCIS machines, so it is necessary that you have your CCIS username and password. 
- Forgot your password? Go [here](https://my.ccs.neu.edu/forgot/password)

### Windows Users:
- Download [PuTTY](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html), an SSH client compatible with Windows
- Open PuTTY > Host Name: "login.ccs.neu.edu" > Open
- Enter your username and password

### Mac/Linux Users:
- In the terminal, `ssh <username>@login.ccs.neu.edu`
- Enter your password


## Create a `.www` directory within your home directory

First, check to see if you have a `.www` directory already.

```$ ls -a | grep ".www"```

If nothing is returned, you have to create the directory: 

`mkdir .www`

Once the directory has been created, you must give it read and search permissions (so that other people can view your website!)

```
$ chmod 711 ~/.www
$ chmod a+x ~
```

## Make an index.html file

The HTML code that you put in your `index.html` will determine what is displayed when someone views your website!

Here is some starter HTML code:

```
<! DOCTYPE HTML>
<html>
<body>
<h1> My Personal Website! </h1>
<p> This is the personal website of ______ </p>
</body>
</html>
```

Just create a new index.html file, and add in your own HTML!

```
$ touch index.html
$ nano index.html
```

## Check out your fresh site!

Once you've completed those steps, go to `www.ccs.neu.edu/home/<username>/` to see your webpage!

Research some more advanced HTML to customize your site, and feel free to share any cool designs with us!
