An NYU Classes File Exchange Uploader
=====================================

Interface
---------

In a script:

    .. code:: python

    import nyucdav

    uploader=nyucdav.FileExchangeUploader(username='mpl5',password='asdf')

    for (username,filename) in manifest:
        uploader.upload(filename,site_id,dest,user)

Another option would be with module functions:

    .. code:: python

    import nyucdav

    nyucdav.configure(username='mpl5',password='asdf')
    for (username,filename,destfilename) in manifest:
        nyucdav.upload(file_name,site_id,dest_file_name,user_name)

    nyucdav.upload(file,site_id,dest=None,user=None)
    """Upload `file` to NYU Classes site `site_id`.

    dest: name of destination file (default: same as original file)

    user: upload into this user's directory (if omitted, upload into the resources directory instead)
    """

    nyucdav.download(file,site_id,dest=None,user=None)
    """Download `file` from NYU Classes site `site_id`.

    dest: name of destination file (default: same as original file)

    user: download from this user's directory (if omitted, from the resources directory instead)
    """

    nyucdav.move(file,site,dest,user)
    """
    Move file within NYU Classes

    Would we ever want to move from resources to user?  Or from user to another?  Probably not.
    """

    nyucdav.list(file,site,user)
    """
    List files in an NYU Classes DAV directory

    Should return like an ordinary file glob
    """



I think I like the module version better.

On the command line:

    .. code:: shell

    $ nyucfxupload -u mpl5 -p asdf site-id username filename

The click package should make this pretty easy.

See also
--------

`Dropbox Uploader`__  by Andrea Fabrizi

    __ https://github.com/andreafabrizi/Dropbox-Uploader
