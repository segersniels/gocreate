# gocreate
One of the things I dislike the most about Golang is the fact that you're bound to your `$GOPATH`.  
The solution? Create a directory in your `$GOPATH/src` and symlink it to wherever you keep all your other projects.

## Installation
```bash
curl https://raw.githubusercontent.com/segersniels/gocreate/master/gocreate > /usr/local/bin/gocreate ; chmod +x /usr/local/bin/gocreate
```

I suggest creating the following alias, so whenever you cd into your symlinked folder you follow the symlink.

```bash
alias cd='cd -P'
```

## Code

```bash
#!/usr/bin/env bash
PROJECT="$1"
DIR="${HOME}/go/src/${PROJECT}"

mkdir -p $DIR
ln -s $DIR ./$PROJECT

cat > ./${PROJECT}/${PROJECT}.go <<- EOM
package main

import (
)

func main() {
}
EOM

cd ./$PROJECT ; echo "N" |glide init
```
