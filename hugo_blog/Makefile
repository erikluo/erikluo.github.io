newsite:
        hugo new site quickstart
        cd quickstart && git init && git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke && echo "theme = 'ananke'" >> hugo.toml
        cd quickstart && rm -rfv .git/ .gitmodules
newcontent:
        cd quickstart && hugo new content posts/my-first-post.md
server:
        cd quickstart && hugo server 
dev:
        cd quickstart && hugo server -D
download:
        wget https://github.com/gohugoio/hugo/releases/download/v0.120.4/hugo_0.120.4_Linux-64bit.tar.gz && tar -xvf hugo_0.120.4_Linux-64bit.tar.gz hugo && sudo mv -v ./hugo /usr/local/bin/hugo

clean:
        rm -rfv ./quickstart
