# Groupon Front-End Interview Assignment

Tech 

**CORS Proxy setup**
Proxy is possible to change in poackage.json "proxy": "https://aukro.cz" or in vite.js config file:
`vite.config.ts`
```
  proxy: {
    '/api': {
      target: 'https://aukro.cz',
      changeOrigin: true,
      rewrite: (path) => path.replace(/^\/api/, ''),
    },
  },
```

## How to run
 - `yarn dev` - for development
 - `yarn build` - production build
 - `yarn preview` - production version of application

 - `yarn lint` - run ESLint kode check
 - `yarn lint:fix` - run ESLint kode check with autofix

## Docker

**For development**
to build image: `docker build -t [name of the image] .`
to run image `docker run -it --rm -p 4001:4000 --name [name of the container] [name of the image]`

to run image with mounted local volume for Hot Module Reload
`docker run -it --rm -p 4001:4000 -v "$PWD"/src:/app/src [name of the container] [name of the image]`

**For production preview**
to build image: `docker build -t [name of image] -f dockerfile.preview .`
to run image `docker run -it --rm -p 4200:4200 --name [name of the container] [name of the image]`