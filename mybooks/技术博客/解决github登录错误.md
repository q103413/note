# How to fix: fatal: Authentication failed for https://github.com/



![thumb](http://img.rmb520.com/test/error.png)

After enabling a two-factor authentication in my GitHub account, when I run the Git `git push` command it throws the following error message:

```
$ git push
Username for 'https://github.com': Username
Password for 'https://Username@github.com':
remote: Invalid username or password.
fatal: Authentication failed for 'https://github.com/username/repository.git/'
```

## What causes this error

This error message is self explanatory. It means that we are trying to use the invalid username or password. But I’m sure I’m using the correct username and password. In my case, this happened with me after I turned on a two-factor authentication (2FA) in my GitHub account. So I know what caused this error message.

## How to solve it

Once we know what is causing the `git` run to fail, we can use it to solve the problem. It is a really easy process. To solve this problem all we need to do is create a GitHub personal access token and use it instead of our GitHub password and a two-factor authentication code. Now, step by step guide.

------

Creating a GitHub personal access token.

- In the upper-right corner of any page, click your profile photo, then click `Settings`.
- In the left sidebar, click `Developer settings`.
- In the left sidebar, click `Personal access tokens`.
- Click `Generate new token`.
- Give your token a descriptive name.
- Select the scopes, or permissions, you’d like to grant this token. To use your token to access repositories from the command line, select `repo`.
- Click `Generate token`.
- Copy the token to your clipboard. For security reasons, after you navigate off the page, you will not be able to see the token again.

![How to fix: fatal: Authentication failed for https://github.com/](http://img.rmb520.com/test/1.png)

> **Note!** Treat your tokens like passwords and keep them secret (if you don’t want other people to use the API on your behalf). When working with the API, use tokens as environment variables instead of hardcoding them into your programs.

------

Using a token on the command line.

Once we have a token, we can enter it instead of our password when performing Git operations over HTTPS. Just inter your token after prompted a password and then watch the magic happen…

```
git push
Username: your_username
Password: your_token
```

> **Note!** Personal access tokens can only be used for HTTPS Git operations. If your repository uses an SSH remote URL, you will need to [switch the remote from SSH to HTTPS](https://help.github.com/articles/changing-a-remote-s-url/#switching-remote-urls-from-ssh-to-https).

> **Note!** If you are not prompted for your username and password, your credentials may be cached on your computer. You can [update your credentials in the Keychain](https://help.github.com/articles/updating-credentials-from-the-osx-keychain) to replace your old password with the token.

## Conclusion

That’s it, you’re done. Now the problem that arose after enabling two-factor authentication in the GitHub account has been solved. So simple isn’t it?

If you are having trouble solving this problem with the instructions above, but are being able to solve this problem with any another method please describe it in the comment section below. Thanks!

I hope this article has helped you learn how to solve the problem that arose after enabling two-factor authentication in the GitHub account. If this article has helped you then please [leave a comment](https://www.mycyberuniverse.com/how-fix-fatal-authentication-failed-for-https-github-com.html#comments) ![:smiley:](http://img.rmb520.com/test/1f603.png)

Thanks for reading!