twitter-tagger
==============
http://twitter-tagger.nodejitsu.com/

Using the Twitter firehose, NLTK, the Yhat streaming API to tag tweets in real-time.

## Go baby go
```bash
# set twitter API
$ export consumer_key="abcd1234"
$ export consumer_secret="efgh5678"
$ export access_token_key="ijkl91011"
$ export access_token_secret="mnop12131415"

# install/run the app
$ npm install .
# will default to putin, obama, ukraine
$ node app.js
# can specify your own
$ node app.js baseball yankees "new york"
```


# Pushing to yhat dokku server
This is very much like how you push to heroku.

### Adding the remote

```bash
$ git remote add live dokku@54.83.27.88:twitter-tagger
```

### Pushing

```bash
$ git push live master
```

### SSH-ing onto the server

```bash
$ ssh -i ~/Dropbox/yhathq/dev/yhat-dev.pem ubuntu@54.83.27.88
```

### Adding your public key

```bash
$ cat ~/.ssh/id_rsa.pub | ssh -i ~/Dropbox/yhathq/dev/yhat-dev.pem ubuntu@54.83.27.88 "sudo sshcommand acl-add dokku live"
```