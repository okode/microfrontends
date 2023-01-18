# Microfrontends

## Installing common dependencies

```
npm ci
```

## Build login microfrontend

```
npx nx build login
```

## Build dashboard host app

```
npx nx build dashboard
```

## Run login microfrontend in your desired custom port (LOGIN_PORT)

```
cd dist/apps/login
npx http-server -p [LOGIN_PORT] --cors
```

## Set your desired custom port in remotes configuration for dashboard app

Edit file `dist/apps/dashboard/assets/module-federation.manifest.json` and update port value:

```
{
    "login": "http://localhost:[LOGIN_PORT]"
}
```

## Run dashboard app

```
cd dist/apps/dashboard
npx http-server -p [DASHBOARD_PORT]
```

Open http://localhost:[DASHBOARD_PORT]