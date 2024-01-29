HUGO_ADDR="https://github.com/gohugoio/hugo/releases/download/v0.120.4/hugo_0.120.4_Linux-64bit.tar.gz" 
newsite:
	hugo new site quickstart
	cd quickstart && git init && git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke && echo "theme = 'ananke'" >> hugo.toml
	cd quickstart && rm -rfv .git/ .gitmodules
newcontent:
	cd quickstart && hugo new content post/my-first-post.md

theme-loveit:
	cd quickstart && git init && git submodule add https://github.com/dillonzq/LoveIt.git themes/LoveIt && rm -rfv .git/ .gitmodules
	
server:
	cd quickstart && hugo server 
dev:
	cd quickstart && hugo server -D

publish:
	# 运行 hugo 命令 并不会 删除之前生成的文件。所以必须在运行 hugo 命令之前删除你的 public/ 目录
	cd quickstart && rm -rfv public/ && hugo

deploy: publish
	cd quickstart && rsync -av ./public/    rsync://xiaozhi@sing2.tool333.com:8873/volume

install_hugo:
	wget -O - "$(HUGO_ADDR)" | tar -xzf - -C /usr/local/bin/ hugo && chmod +x /usr/local/bin/hugo

clean:
	rm -rfv ./quickstart


