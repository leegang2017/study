
when tsc --watch very slow, can try change volumes config
https://docs.docker.com/docker-for-mac/osxfs-caching/
```js
    volumes:
      - ${PWD}:/usr/src/app:cached
```