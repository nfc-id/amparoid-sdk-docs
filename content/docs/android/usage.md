---
title: "Usage"
description: "This section describes how to use the Amparo ID Android SDK."
summary: ""
date: 2023-09-07T16:04:48+02:00
lastmod: 2023-09-07T16:04:48+02:00
draft: false
weight: 40
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  robots: "" # custom robot tags (optional)
---
### Register Activity Request for Result

Before initializing the SDK, an activity must be defined to receive the result:
```
private val amparoLauncher = registerForActivityResult(ActivityResultContracts.StartActivityForResult()) { result ->
    if (result.resultCode == Activity.RESULT_OK) {
        val sdkResult = result.data?.getStringExtra("SDK_RESULT")
        Toast.makeText(this, "SDK Result: $sdkResult", Toast.LENGTH_LONG).show()
        // Manejar éxito
    } else {
        Toast.makeText(this, "SDK Cancelled or Failed", Toast.LENGTH_LONG).show()
        // Manejar error o cancelación
    }
}
```

### Creating SDK Configuration

The following parameters are required for SDK configuration:
- `API_KEY`: key for API endpoint consumption.
- `API_URL`: API base url.
- `CONTACT_CALLBACK_URL`: contact URL for the SDK help buttons.
- `E_CERT`: security certificate used by the SDK.
- `KSM_KEY`: SDK security key.
- `SKM_KEY`: SDK security key.

To use the Amparo ID SDK, create a configuration using the `AmparoIdSdkConfig` object as shown
below:

```
val amparoIdSdkConfig = AmparoIdSdkConfig.Builder()
    .setApiKey("API_KEY")
    .setBaseUrl("API_URL")
    .setContactCallbackUrl("CONTACT_CALLBACK_URL")
    .setECert("E_CERT")
    .setKsmKey("KSM_KEY")
    .setSkmKey("SKM_KEY")
    .build()
```

This instance will be used when invoking the SDK.

### Initializing the SDK

Obtain an instance of `AmparoIdApi`:
```
amparoIdSdk = AmparoIdApiFactory.create()
```
Call the SDK using the defined `launcher`:
```
amparoIdSdk!!.startActivityForResult(this@MainActivity, amparoIdSdkConfig, amparoLauncher)
```



### SDK Customization

#### Defining colors

To customize the SDK colors, define colors in the `themes.xml` file:
```
<style name="AppTheme" parent="AmparoIdSdkTheme">
    <item name="amparoIdPrimaryMain">@color/purple_200</item>
    <item name="amparoIdPrimaryLight">@color/purple_500</item>
</style>
```

With `AppTheme` as the application theme, the SDK will use the defined colors for
`amparoIdPrimaryMain` and `amparoIdPrimaryLight`.

#### Defining texts

To customize the SDK texts, define strings in the `strings.xml` file:

<!--
```xml
<string name="amparo_id_sdk_success_message_1">¡Listo!</string>
<string name="amparo_id_sdk_success_message_2">Lo hiciste muy bien.</string>
<string name="amparo_id_sdk_error_no_verifications">No tienes verificaciones pendientes</string>
<string name="amparo_id_sdk_error_disconnect">No es posible continuar con la verificación</string>
<string name="amparo_id_sdk_error_verification_failed">No pudimos verificar tu identidad</string>
<string name="amparo_id_sdk_error_incompatible">Lo sentimos, esta app no está disponible para este dispositivo.</string>
<string name="amparo_id_sdk_error_timer">¿Necesitas ayuda con este paso?</string>
<string name="amparo_id_sdk_error_deprecated">¡Tenemos lista una nueva actualización!</string>
<string name="amparo_id_sdk_error_nfc_disabled">Activa el lector de NFC de tu dispositivo móvil</string>
<string name="amparo_id_sdk_error_nfc_interrupted">¡Se interrumpió el proceso!</string>
<string name="amparo_id_sdk_error_no_verifications_description">No encontramos verificaciones asociadas a tu RUT. Si crees que esto es un error, por favor contáctanos.</string>
<string name="amparo_id_sdk_error_disconnect_description">En este momento nuestros servicios no están disponibles, estamos trabajando en resolverlo. Inténtalo más tarde.</string>
<string name="amparo_id_sdk_error_without_retry_description">Por favor contacta a un ejecutivo.</string>
<string name="amparo_id_sdk_error_with_retry_description">Por favor inténtalo de nuevo o contáctanos.</string>
<string name="amparo_id_sdk_error_incompatible_description">Contáctanos para que podamos ayudarte.</string>
<string name="amparo_id_sdk_error_deprecated_description">Para que tu App sea aún más segura y la puedas usar, necesitamos que esté actualizada.</string>
<string name="amparo_id_sdk_error_disabled_description">En **conexiones del dispositivo**, encuentra **NFC** y habilítalo.</string>
<string name="amparo_id_sdk_error_interrupted_description">Si luego de varios intentos el problema persiste, contacta a un ejecutivo.</string>
<string name="amparo_id_sdk_error_retry_main_button">Volver a intentar</string>
<string name="amparo_id_sdk_error_got_it_main_button">Entendido</string>
<string name="amparo_id_sdk_error_incompatible_main_button">Contactar a Servicio al Cliente</string>
<string name="amparo_id_sdk_error_timer_main_button">Contactar a Servicio al Cliente</string>
<string name="amparo_id_sdk_error_deprecated_main_button">Actualizar App</string>
<string name="amparo_id_sdk_error_nfc_disabled_main_button">Abrir conexiones</string>
<string name="amparo_id_sdk_error_nfc_interrupted_main_button">Volver a escanear</string>
<string name="amparo_id_sdk_error_contact_support_secondary_button">Contactar a Servicio al Cliente</string>
<string name="amparo_id_sdk_error_later_secondary_button">En otro momento</string>
<string name="amparo_id_sdk_error_dismiss_secondary_button">No, gracias</string>
<string name="amparo_id_sdk_error_nfc_bad_reading_1">La cédula de identidad fue **retirada durante el escaneo**.</string>
<string name="amparo_id_sdk_error_nfc_bad_reading_2">La carcasa de tu móvil bloquea el escaneo. **Retírala y vuelve a intentarlo.**</string>
<string name="amparo_id_sdk_error_nfc_bad_reading_error_description">Por favor, revisa las posibles causas y cuando estés listo, vuelve a intentarlo.</string>
```
-->

| Name | String |
|---------------|-------|
| `amparo_id_sdk_success_message_1` | ¡Listo! |
| `amparo_id_sdk_success_message_2` | Lo hiciste muy bien. |
| `amparo_id_sdk_error_no_verifications` | No tienes verificaciones pendientes |
| `amparo_id_sdk_error_disconnect` | No es posible continuar con la verificación |
| `amparo_id_sdk_error_verification_failed` | No pudimos verificar tu identidad |
| `amparo_id_sdk_error_incompatible` | Lo sentimos, esta app no está disponible para este dispositivo. |
| `amparo_id_sdk_error_timer` | ¿Necesitas ayuda con este paso? |
| `amparo_id_sdk_error_deprecated` | ¡Tenemos lista una nueva actualización! |
| `amparo_id_sdk_error_nfc_disabled` | Activa el lector de NFC de tu dispositivo móvil |
| `amparo_id_sdk_error_nfc_interrupted` | ¡Se interrumpió el proceso! |
| `amparo_id_sdk_error_no_verifications_description` | No encontramos verificaciones asociadas a tu RUT. Si crees que esto es un error, por favor contáctanos. |
| `amparo_id_sdk_error_disconnect_description` | En este momento nuestros servicios no están disponibles, estamos trabajando en resolverlo. Inténtalo más tarde. |
| `amparo_id_sdk_error_without_retry_description` | Por favor contacta a un ejecutivo. |
| `amparo_id_sdk_error_with_retry_description` | Por favor inténtalo de nuevo o contáctanos. |
| `amparo_id_sdk_error_incompatible_description` | Contáctanos para que podamos ayudarte. |
| `amparo_id_sdk_error_deprecated_description` | Para que tu App sea aún más segura y la puedas usar, necesitamos que esté actualizada. |
| `amparo_id_sdk_error_disabled_description` | En **conexiones del dispositivo**, encuentra **NFC** y habilítalo. |
| `amparo_id_sdk_error_interrupted_description` | Si luego de varios intentos el problema persiste, contacta a un ejecutivo. |
| `amparo_id_sdk_error_retry_main_button` | Volver a intentar |
| `amparo_id_sdk_error_got_it_main_button` | Entendido |
| `amparo_id_sdk_error_incompatible_main_button` | Contactar a Servicio al Cliente |
| `amparo_id_sdk_error_timer_main_button` | Contactar a Servicio al Cliente |
| `amparo_id_sdk_error_deprecated_main_button` | Actualizar App |
| `amparo_id_sdk_error_nfc_disabled_main_button` | Abrir conexiones |
| `amparo_id_sdk_error_nfc_interrupted_main_button` | Volver a escanear |
| `amparo_id_sdk_error_contact_support_secondary_button` | Contactar a Servicio al Cliente |
| `amparo_id_sdk_error_later_secondary_button` | En otro momento |
| `amparo_id_sdk_error_dismiss_secondary_button` | No, gracias |
| `amparo_id_sdk_error_nfc_bad_reading_1` | La cédula de identidad fue **retirada durante el escaneo**. |
| `amparo_id_sdk_error_nfc_bad_reading_2` | La carcasa de tu móvil bloquea el escaneo. **Retírala y vuelve a intentarlo.** |
| `amparo_id_sdk_error_nfc_bad_reading_error_description` | Por favor, revisa las posibles causas y cuando estés listo, vuelve a intentarlo. |
