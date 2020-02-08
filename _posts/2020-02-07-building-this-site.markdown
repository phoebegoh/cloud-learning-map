---
layout: posts
title:  "how to create this site from github"
date:   2020-02-07 15:58:04 -0400
categories: updates docker
---

* using the jekyll/jekyll container
  * set the variable JEKYLL_VERSION if you want to specify it anywhere. sometimes i've made it static and i should probably fix that.
  * to SERVE the files in the directory: `docker run --rm --volume="$PWD:/srv/jekyll" --volume="$PWD/vendor/bundle:/usr/local/bundle" -it -p 4000:4000 jekyll/jekyll:$JEKYLL_VERSION jekyll serve --watch --drafts --trace`
  * to BUILD the files in the directory: `docker run --rm --volume="$PWD:/srv/jekyll" --volume="$PWD/vendor/bundle:/usr/local/bundle" -it jekyll/jekyll:$JEKYLL_VERSION jekyll build --watch`
* using docker-compose
  * build the docker-compose file and run `docker-compose up` (run `docker-compose down` to end)