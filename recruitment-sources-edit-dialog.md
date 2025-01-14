## Edit recruitment source

Enter the name and cost per conversion.

### Enabling and disabling recruitment sources
By default all recruitment sources are enabled. If you wish to turn one off then use the **Source ENABLED** / **Source DISABLED** select to do so.

> When recruitment source is disabled any traffic sent from the URL will be terminated immediately.

In order for the recruitment source tracking to work you must supply the **source** parameter on the URL. Example:

```
https://domain.sampleninja.io/registration/1/ENG-CA?source=10
```
### AdBloom conversion reporting

In order to use **AdBloom** conversion reporting you must first enable it in the **Panel Settings** under **Integrations**. You must have an account with **AdBloom** and know your **Reporting URL** before you can enable the service. This information is available via **AdBloom** admin interface or from your **AdBloom** representative

Next create a **recruitment source** and enabled **ADBLOOM** integration.

When enabled the recruitment source ID or **source** and AdBloom click ID or **cid** URL query parameters must be provided. For example if your standard **Registration Survey** URL looks like this:

```
https://domain.sampleninja.io/registration/1/ENG-CA
```

You need apped the required parameters and the final URL will look like this:

```
https://domain.sampleninja.io/registration/1/ENG-CA?source=10&cid=a93b5fc7d44234dab8f8
```

> **AdBloom** must use this URL format for all the redirects they do.

### TUNE Conversion reporting

In order to use **TUNE** conversion reporting you must first enable it in the **Panel Settings** under **Integrations**. You must have an account with **TUNE** and know your **Reporting URL** before you can enable the service. This information is available via **TUNE** admin interface or from your **TUNE** representative.

Use the **Integration Partner** pulldown and select **TUNE**

When enabled the recruitment source ID or **source** and TUNE transaction id or **transaction_id** URL query parameters must be provided. For example if your standard **Registration Survey** URL looks like this:
```
https://domain.sampleninja.io/registration/1/ENG-CA
```

You need apped the required parameters and the final URL will look like this:

```
https://domain.sampleninja.io/registration/1/ENG-CA?source=10&transaction_id=935f78f8
```

> **TUNE** must use this URL format for all the redirects they do.

Or for test mode:

```
https://domain.sampleninja.io/registration/1/ENG-CA?source=10&transaction_id=935f78f8&test=true
```
As long as the **registration survey** URL is configured in **TUNE's admin interface** these URL parameters are automatically and appended when new recruits land into your registration survey.

> The **source** parameter must be a valid **Recruitment Source ID** and the **Recruitment Source** must have **TUNE** enabled.

> For more information visit https://www.tune.com

### MVF Conversion reporting

In order to use **MVF** integration you must first enable it in the **Panel Settings** under **Integrations** -tab. You must have an account **MVF** and know you reporting pixel URL.

Use the **Integration Partner** pulldown to and select **MVF**.

> For more information visit https://www.mvfglobal.com

When **MVF** is turned on for a **Recruitment Source** Sample Ninja expects 6 URL query parameters to be passed in:

1) **sid** MVF internal user identifier (assigned by MVF)
2) **pix** MVF internal pixel identifier (assigned by MVF)
3) **first** First name collected by MVF -> auto saved as **FIRST_NAME** -data variable.
4) **last**  Last name collected by MVF -> auto saved as **LAST_NAME** -data variable.
5) **gender** Gender collected by MVF -> auto saved as **GENDER** -data variable.
6) **email** Email address collected by MVF -> auto saved as **EMAIL** -data variable.

Let's say you have **Recruitment Source** with **ID 4** with **MVF reporting** enabled. Your base **Registration Survey** URL would look like this:

```
https://client.sampleninja.io/registration/1/ENG-US
```

Next you append the required query parameters to the URL:

```
?source=4&sid=12345&pix=123456&first=John&last=Doe&email=john.doe@sampleninja.io&gender=1
```
> **MVF** must use this URL format for all the redirects they do.

Questions **FIRST_NAME**, **LAST_NAME**, **GENDER** and **EMAIL** are automatically answered and user will only see **EMAIL** which is prefilled but needs user's confirmation. You can add any number of additional questions to your registration survey. **EMAIL** address is pre-filled but must be confirmed the registerting user the rest of the questions are auto populated.

As long as you have configured your **MVF** account correctly these parameters are automatically passed in from **MVF** when new recruits land into your registration survey.

> Variable data that does not pass the validation by Sample Ninja will be silently ignored and users are automatically asked to fill in these questions again.

> **IMPORTANT!** You must have **GENDER** variable in your **Registration Survey** or **GENDER** will fail to automatically collect.
