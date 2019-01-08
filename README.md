# ADFS-Onload-JS

## ADFS 3.0+ onload.js JavaScript Commands
When adding another Claims Provider to ADFS, end users are by default provided multiple Claims Provider options.

The following code is for automation of Claim Provider selection during Home Realm Discovery (HRD) for Microsoft Active Directory Federation Services 3.0+. Please refer to official Microsoft documentation on how to deploy the code: [Micrsoft Docs] (https://docs.microsoft.com/en-us/windows-server/identity/ad-fs/operations/advanced-customization-of-ad-fs-sign-in-pages)

## Instructions
Add the code to your onload.js including the description slashes to assist with identifying your code in future

### Automatically select Active Directory for Desktop Devices but still display Claims Provider selection for Mobile Devices
```
// Automatically select Active Directory for Desktop Devices

if (navigator.userAgent.match(/Windows NT|Macintosh|Linux/i) != null) { HRD.selection('AD Authority')};
```

### Automatically select Additional Claims Provider for Mobile Devices but still display Claims Provider selection for Desktop Devices

```
// Automatically select Additional Claims Provider for Mobile Devices

if (navigator.userAgent.match(/iPad|iPhone|Android|Windows Phone/i) != null) { HRD.selection('https://claimsprovider.com/replacethisurl.xml')};
```

### Automatically select 3rd Party Claims Provider for Mobile Devices and Active Directory for Desktop Devices

```
// Automatically select Additional Claims Provider for Mobile Devices and Active Directory for Desktop Devices

if (navigator.userAgent.match(/iPad|iPhone|Android|Windows Phone/i) != null) { HRD.selection('https://claimsprovider.com/replacethisurl.xml')}; else {HRD.selection('AD AUTHORITY')};
```
