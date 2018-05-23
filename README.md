# gocreate
One of the things I dislike about Golang (and using Glide) is the fact that you're bound to your `$GOPATH`.  
The solution? Creating a directory in your `$GOPATH/src` and symlink it to wherever you want the project to be.

## Installation
```bash
curl https://raw.githubusercontent.com/segersniels/gocreate/master/gocreate > /usr/local/bin/gocreate ; chmod +x /usr/local/bin/gocreate
```
