# app-multi-window

This is an example of how to implement multiple windows for OakOS using a single display

## Running locally

Make sure that you are running the right version of Node locally. You will find the required version in the `.nvmrc` file
If you are not running the same version (`node -v`) then you will need to run

``` bash
nvm install $(cat .nvmrc)
npm run rebuild
```

### Now you can run electron locally

``` bash
npm run dev
```

### Running in a docker container

``` bash
xhost +
docker-compose up --build
```

### Shutting down the  docker container

``` bash
docker-compose down
```

## Example Installation

If there is no environmental variable send for `WINDOW_X` then the window is positioned according to its `WINDOW_PERCENT`.

``` json
{
  "services": [
    {
      "image": "index.docker.io/oaklabs/app-multi-window:latest",
      "environment": {
        "TZ": "America/Phoenix",
        "REMOTE_URL":"https://www.fast.com",
        "WINDOW_PERCENT":".5",
        "WINDOW_X": "100",
        "BACKGROUND_COLOR":"#000000",
        "WINDOW_ONTOP":"false",
        "SSL_EXCEPTIONS":"localhost;*.google.com",
        "WINDOW_INSECURE":"false",
        "DISPLAY_ID":"0",
        "ELECTRON_DISABLE_SECURITY_WARNINGS":"true",
        "WAIT_ON":"https://www.fast.com;https://www.google.com"
      }
    }
  ]
}

```