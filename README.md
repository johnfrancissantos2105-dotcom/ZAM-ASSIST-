# ZAM Power Assist

A responsive .NET 10 Blazor WebAssembly progressive web app prototype for electricity consumers. It follows the supplied ZAM Power Assist login reference and adapts to phone, tablet, and desktop screens.

## Temporary demo deployment

The current demo preview is available at [zam-power-assist-demo.rough-cockatoo-158.workers.dev](https://zam-power-assist-demo.rough-cockatoo-158.workers.dev/). It was deployed to a temporary Cloudflare preview account. Cloudflare requires the owner to claim that preview from the browser claim page and complete the email verification before the claim deadline; otherwise, the temporary deployment may expire. Claim the preview before treating this address as a permanent app URL.

## Run locally

```powershell
dotnet run
```

Open the local URL printed by `dotnet run`. The app starts at the login screen. Demo login and account creation are simulated; no credentials are checked.

## Build and deploy the PWA

```powershell
dotnet publish -c Release
```

Publish the contents of `bin/Release/net10.0/publish/wwwroot` to a static web host with HTTPS and a fallback to `index.html` for the app route. On Android, open the deployed site in Chrome and choose **Install app** or **Add to Home screen**. The PWA manifest and service worker provide an app-like install and offline shell.

## Google Play Store

This project is a web PWA, not a signed Android package. To list it on Google Play, first deploy it to a permanent HTTPS domain, then package that domain as a Trusted Web Activity (for example with PWABuilder or Bubblewrap), publish the domain association file, sign an Android App Bundle, and submit it through a Google Play developer account. Store listing, signing credentials, and the domain association must be supplied by the publisher; this repository cannot publish to Play Store on its own.

## Prototype limitations before production

The login, registration, reports, payment, reminders, feedback, announcements, and service requests are demo interactions stored only in the current browser session. They are not connected to ZAMSURECO systems or a backend. Usage, bills, announcements, and contact details are sample data; verify the hotline numbers with the cooperative and local authorities. Production deployment needs secure server-side authentication, APIs and persistence, payment-provider integration, authoritative consumer data, and verified contact details. Do not use the prototype's simulated sign-in or payment for real accounts or transactions.
