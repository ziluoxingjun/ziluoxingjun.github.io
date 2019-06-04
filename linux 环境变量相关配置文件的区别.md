> /ect/profile

`/ect/profile` 登录操作系统时，为每个用户设置环境信息，当用户第一次登录时，该文件被执行。也就是说这个文件对每个 shell 都有效，用于获取系统的环境信息。

> /etc/bashrc

`/etc/bashrc` 每一个运行 bash shell 的用户执行此文件，当 bash shell 被打开时，该文件被读取。也就是说，当用户 shell 执行了 bash 时，运行这个文件。

> ~/.bash_profile

`~/.bash_profile` 每个用户都可使用该文件输入专用于自己使用的 shell 信息，当用户登录时，该文件仅仅执行一次！默认情况下，他设置一些环境变量，执行用户的 .bashrc 文件。

> ~/.profile

在 Debian 中使用该文件代替 .bash_profile 文件，例如：ubuntu 中。

> ~/.bashrc

`~/.bashrc` 每个用户的 bash shell 的信息，当用户登录时以及每次打开一个新的 shell 时，执行这个文件。在这个文件里可以自定义用户专属的个人信息。


> https://blog.jjonline.cn/shorthand/233.html
