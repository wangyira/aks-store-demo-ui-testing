# AKS Store Demo UI Testing

## Get started

```sh
npx playwright install --with-deps
```

## Run tests on Microsoft Playwright service

If you want to run tests on Microsoft Playwright service, you need to set the `PLAYWRIGHT_SERVICE_URL` environment variable.

Browse to https://playwright.microsoft.com and sign in with your Azure account and create a new workspace.

```sh
export PLAYWRIGHT_SERVICE_URL=wss://<LOCATION>.api.playwright.microsoft.com/accounts/<ACCOUNT_ID>/browsers
```

## Run tests

```sh
export STORE_FRONT_URL=http://<STORE_FRONT_PUBLIC_IP>/
export STORE_ADMIN_URL=http://<STORE_ADMIN_PUBLIC_IP>/
npx playwright test
```

## Run tests with GitHub Actions

To run tests with GitHub Actions, you should fork the repository then create repository secrets.

```sh
gh repo fork pauldotyu/aks-store-demo-ui-testing --clone
cd aks-store-demo-ui-testing
gh repo set-default
```

Create repository secrets:

```sh
gh secret set STORE_FRONT_URL --body http://<STORE_FRONT_PUBLIC_IP>/ --repo <YOUR_USERNAME>/aks-store-demo-ui-testing
gh secret set STORE_ADMIN_URL --body http://<STORE_ADMIN_PUBLIC_IP>/ --repo <YOUR_USERNAME>/aks-store-demo-ui-testing

# optional if you want to run tests on Microsoft Playwright service
gh secret set PLAYWRIGHT_SERVICE_URL --body wss://<LOCATION>.api.playwright.microsoft.com/accounts/<ACCOUNT_ID>/browsers
```
