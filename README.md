# microbin-cli
Nice little CLI client for uploading, managing files, and posting to a microbin instance.
Be sure to put the public URL to your Microbin instance into the mb-cli file (extension .py)

Also note, the file upload password (`uploader_password`) is unique to my fork.

```
usage: mb-cli [-h] [-e] [-x WHEN]
              [-p {public,unlisted,private,secret,readonly}]
              [-b {0,1,10,100,1000,10000}] [-S SYNTAX]
              [--upload-password UPLOAD_PASSWORD]
              [--file-password FILE_PASSWORD] [--upload-timeout SECONDS]
              [--no-progress] [-u URL] [-f FILE] [-a] [-U USER]
              [--delete-path DELETE_PATH] [-s] [-d KEY] [-i] [-y] [-j JOBS]
              [-t TIMEOUT] [--sort {created,expires,size,key,hits}]
              [--columns COLUMNS] [--no-color]
              [files ...]

List, upload and delete MicroBin entries

positional arguments:
  files                 files to upload; listing is printed when none are
                        given

options:
  -h, --help            show this help message and exit
  -e, --edit            compose a text entry in $EDITOR and upload it on save
  -x, --expire WHEN     expiration: 1min, 10min, 1hour, 24hour, 3days, 1week,
                        1month, 6months, 1year, 2years, 4years, 8years,
                        16years, never
  -p, --privacy {public,unlisted,private,secret,readonly}
                        entry visibility
  -b, --burn {0,1,10,100,1000,10000}
                        delete after this many reads
  -S, --syntax SYNTAX   syntax highlighting hint for text entries
  --upload-password UPLOAD_PASSWORD
                        value for the uploader_password field, checked against
                        MICROBIN_UPLOADER_PASSWORD; applies to text entries
                        and, in readonly mode, to every upload
  --file-password FILE_PASSWORD
                        value for the uploader_password field when a file is
                        attached, checked against
                        MICROBIN_FILE_UPLOAD_PASSWORD; defaults to --upload-
                        password
  --upload-timeout SECONDS
                        socket timeout for uploads; 0 disables it, which is
                        the default because the timeout applies per send
                        operation and aborts large transfers
  --no-progress
  -u, --url URL         instance base URL (default https://p.dgsd.ph, or
                        $PDROP_BASE)
  -f, --file FILE       parse a saved listing instead of fetching
  -a, --admin           authenticate and use the admin listing; enables
                        deletion of entries that expose no Remove link
  -U, --user USER       admin username; cached in ~/.config/pls/admin_user
                        after a successful login, so only the password is
                        prompted for
  --delete-path DELETE_PATH
                        admin deletion path used when a row carries no action
                        link (default /delete)
  -s, --size            resolve size, MIME type and filename (list mode only;
                        admin listings already report size)
  -d, --delete KEY      delete an entry by key; repeatable
  -i, --interactive     print a numbered list and prompt for entries to delete
  -y, --yes             skip confirmation prompts
  -j, --jobs JOBS
  -t, --timeout TIMEOUT
  --sort {created,expires,size,key,hits}
  --columns COLUMNS     comma-separated subset of: key,name,kind,size,mime,cre
                        ated,expires,url,edit,remove,delete,enc,priv,editable,
                        hits
  --no-color
```
