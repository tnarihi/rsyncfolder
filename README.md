# Sync folder over ssh using rsync

## How to use

1. Copy `.sync_*` files into the root of your local folder in which contents
  are going to synchronized with remote folder. You can do this by the
  following one-liner at your local folder.

    git clone git@github.com:tnarihi/rsyncfolder.git .tmp.rsyncfolder && ln -s .tmp.rsyncfolder/.sync_* .
  
  I recommend you add executable permission to `.sync_{up,down}`,
  otherwise you will call these by use bash command followed by them.

2. Edit `.sync_settings` and set your remote host and specify a folder

3. Set include/exclude pattern in `.sync_{include,exclude}`.
  If you empty `.sync_include`, no files/folders are synchronized.

4. If the remote folder and the contents exist, first you can run `.sync_down`
  so that you will get the remote contents in your local folder.
  After editing you local folder, you can synchronize your local folder
  to remote folder in up direction using `.sync_up` command.
  The `.sync_{up,down}` commands will list files/folders to be changed and ask 
  you to make sure if you want to sync them before actual sync.

I use this scripts only on my Ubuntu 14.04 LTS desktop, not test on any other environments.
