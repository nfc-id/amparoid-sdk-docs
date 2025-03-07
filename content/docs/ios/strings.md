---
title: "Language Strings"
description: "This section describes the requirements to implement the Amparo ID Android SDK in your app."
summary: ""
date: 2023-09-07T16:04:48+02:00
lastmod: 2023-09-07T16:04:48+02:00
draft: false
weight: 831
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  robots: "" # custom robot tags (optional)
---

There are two requirements for the project's language file:
* AWS FaceLiveness : these strings are required for the functionality of AWS FaceLiveness. Please add the strings from the section to your `Localizable.xcstring` file.

* SDK Text Changes : Some text in the AmparoID identification process is open to change, you can check the list to see which ones you need to add.

## AWS Faceliveness

This text is **required** for the proper functioning of the SDK. Please add to your `Localizable.xcstring` file.

```json
{
  "strings" : {
    "amplify_ui_liveness_camera_permission_button_description" : {
      "extractionState" : "stale",
      "localizations" : {
        "en" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Ingresa a la configuración de tu celular para otorgar permisos de cámara, luego cierra la aplicación y vuelve a intentarlo."
          }
        },
        "es-419" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Ingresa a la configuración de tu celular para otorgar permisos de cámara, luego cierra la aplicación y vuelve a intentarlo."
          }
        }
      }
    },
    "amplify_ui_liveness_camera_permission_button_header" : {
      "extractionState" : "stale",
      "localizations" : {
        "en" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "No pudimos acceder a la cámara"
          }
        },
        "es-419" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "No pudimos acceder a la cámara"
          }
        }
      }
    },
    "amplify_ui_liveness_camera_permission_button_title" : {
      "extractionState" : "stale",
      "localizations" : {
        "en" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Cambia la configuración de la cámara"
          }
        },
        "es-419" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Cambia la configuración de la cámara"
          }
        }
      }
    },
    "amplify_ui_liveness_camera_permission_page_title" : {
      "extractionState" : "stale",
      "localizations" : {
        "en" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Prueba de vida"
          }
        },
        "es-419" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Prueba de vida"
          }
        }
      }
    },
    "amplify_ui_liveness_camera_setting_alert_message" : {
      "extractionState" : "stale",
      "localizations" : {
        "en" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Otorga el permiso de uso de la cámara en la configuración de tu celular."
          }
        },
        "es-419" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Otorga el permiso de uso de la cámara en la configuración de tu celular."
          }
        }
      }
    },
    "amplify_ui_liveness_camera_setting_alert_not_now_button_text" : {
      "extractionState" : "stale",
      "localizations" : {
        "en" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Ahora no"
          }
        },
        "es-419" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Ahora no"
          }
        }
      }
    },
    "amplify_ui_liveness_camera_setting_alert_title" : {
      "extractionState" : "stale",
      "localizations" : {
        "en" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Cambia las configuraciones de tu cámara"
          }
        },
        "es-419" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Cambia las configuraciones de tu cámara"
          }
        }
      }
    },
    "amplify_ui_liveness_camera_setting_alert_update_setting_button_text" : {
      "extractionState" : "stale",
      "localizations" : {
        "en" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Actualiza la configuración"
          }
        },
        "es-419" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Actualiza la configuración"
          }
        }
      }
    },
    "amplify_ui_liveness_center_your_face_text" : {
      "extractionState" : "stale",
      "localizations" : {
        "en" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Centra tu rostro"
          }
        },
        "es-419" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Centra tu rostro"
          }
        }
      }
    },
    "amplify_ui_liveness_challenge_cancel_a11y" : {
      "extractionState" : "stale",
      "localizations" : {
        "en" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Cancelar desafío"
          }
        },
        "es-419" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Cancelar desafío"
          }
        }
      }
    },
    "amplify_ui_liveness_challenge_connecting" : {
      "extractionState" : "stale",
      "localizations" : {
        "en" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Conectando..."
          }
        },
        "es-419" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Conectando..."
          }
        }
      }
    },
    "amplify_ui_liveness_challenge_instruction_hold_face_during_countdown" : {
      "extractionState" : "stale",
      "localizations" : {
        "en" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Mantenga la posición de su rostro durante la cuenta regresiva."
          }
        },
        "es-419" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Mantenga la posición de su rostro durante la cuenta regresiva."
          }
        }
      }
    },
    "amplify_ui_liveness_challenge_instruction_hold_face_during_freshness" : {
      "extractionState" : "stale",
      "localizations" : {
        "en" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Mantenga su rostro dentro del óvalo durante los destellos de colores."
          }
        },
        "es-419" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Mantenga su rostro dentro del óvalo durante los destellos de colores."
          }
        }
      }
    },
    "amplify_ui_liveness_challenge_instruction_hold_still" : {
      "extractionState" : "stale",
      "localizations" : {
        "en" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Quédate quieto"
          }
        },
        "es-419" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Quédate quieto"
          }
        }
      }
    },
    "amplify_ui_liveness_challenge_instruction_move_face_back" : {
      "extractionState" : "stale",
      "localizations" : {
        "en" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Aléjate"
          }
        },
        "es-419" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Aléjate"
          }
        }
      }
    },
    "amplify_ui_liveness_challenge_instruction_move_face_closer" : {
      "extractionState" : "stale",
      "localizations" : {
        "en" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Acércate"
          }
        },
        "es-419" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Acércate"
          }
        }
      }
    },
    "amplify_ui_liveness_challenge_instruction_move_face_in_front_of_camera" : {
      "extractionState" : "stale",
      "localizations" : {
        "en" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Mueve tu rostro en frente de la cámara"
          }
        },
        "es-419" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Mueve tu rostro en frente de la cámara"
          }
        }
      }
    },
    "amplify_ui_liveness_challenge_instruction_multiple_faces_detected" : {
      "extractionState" : "stale",
      "localizations" : {
        "en" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Muestra un sólo rostro por verificación"
          }
        },
        "es-419" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Muestra un sólo rostro por verificación"
          }
        }
      }
    },
    "amplify_ui_liveness_challenge_recording_indicator_label" : {
      "extractionState" : "stale",
      "localizations" : {
        "en" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Grabando"
          }
        },
        "es-419" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Grabando"
          }
        }
      }
    },
    "amplify_ui_liveness_challenge_verifying" : {
      "extractionState" : "stale",
      "localizations" : {
        "en" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Verificando"
          }
        },
        "es-419" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Verificando"
          }
        }
      }
    },
    "amplify_ui_liveness_close_button_a11y" : {
      "extractionState" : "stale",
      "localizations" : {
        "en" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Cerrar"
          }
        },
        "es-419" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Cerrar"
          }
        }
      }
    },
    "amplify_ui_liveness_face_not_prepared_reason_face_too_close" : {
      "extractionState" : "stale",
      "localizations" : {
        "en" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Aleja tu rostro"
          }
        },
        "es-419" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Aleja tu rostro"
          }
        }
      }
    },
    "amplify_ui_liveness_face_not_prepared_reason_move_face_closer" : {
      "extractionState" : "stale",
      "localizations" : {
        "en" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Acércate más"
          }
        },
        "es-419" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Acércate más"
          }
        }
      }
    },
    "amplify_ui_liveness_face_not_prepared_reason_move_face_left" : {
      "extractionState" : "stale",
      "localizations" : {
        "en" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Gira a la izquierda"
          }
        },
        "es-419" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Gira a la izquierda"
          }
        }
      }
    },
    "amplify_ui_liveness_face_not_prepared_reason_move_face_right" : {
      "extractionState" : "stale",
      "localizations" : {
        "en" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Gira a la derecha"
          }
        },
        "es-419" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Gira a la derecha"
          }
        }
      }
    },
    "amplify_ui_liveness_face_not_prepared_reason_move_to_brighter_area" : {
      "extractionState" : "stale",
      "localizations" : {
        "en" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Busca mayor iluminación"
          }
        },
        "es-419" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Busca mayor iluminación"
          }
        }
      }
    },
    "amplify_ui_liveness_face_not_prepared_reason_move_to_dimmer_area" : {
      "extractionState" : "stale",
      "localizations" : {
        "en" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Busca iluminación más tenue"
          }
        },
        "es-419" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Busca iluminación más tenue"
          }
        }
      }
    },
    "amplify_ui_liveness_face_not_prepared_reason_multiple_faces" : {
      "extractionState" : "stale",
      "localizations" : {
        "en" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Sólo un rostro por verificación"
          }
        },
        "es-419" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Sólo un rostro por verificación"
          }
        }
      }
    },
    "amplify_ui_liveness_face_not_prepared_reason_no_face" : {
      "extractionState" : "stale",
      "localizations" : {
        "en" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Pon tu rostro en frente de la cámara"
          }
        },
        "es-419" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Pon tu rostro en frente de la cámara"
          }
        }
      }
    },
    "amplify_ui_liveness_face_not_prepared_reason_not_in_oval" : {
      "extractionState" : "stale",
      "localizations" : {
        "en" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Posiciona tu rostro dentro del óvalo"
          }
        },
        "es-419" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Posiciona tu rostro dentro del óvalo"
          }
        }
      }
    },
    "amplify_ui_liveness_face_not_prepared_reason_pendingCheck" : {
      "extractionState" : "stale",
      "localizations" : {
        "en" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : " "
          }
        },
        "es-419" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : " "
          }
        }
      }
    },
    "amplify_ui_liveness_get_ready_begin_check" : {
      "extractionState" : "stale",
      "localizations" : {
        "en" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "COMENZAR"
          }
        },
        "es-419" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "COMENZAR"
          }
        }
      }
    },
    "amplify_ui_liveness_get_ready_page_title" : {
      "extractionState" : "stale",
      "localizations" : {
        "en" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Prueba de vida"
          }
        },
        "es-419" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Prueba de vida"
          }
        }
      }
    },
    "amplify_ui_liveness_get_ready_photosensitivity_description" : {
      "extractionState" : "stale",
      "localizations" : {
        "en" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "La próxima pantalla tiene luces parpadeantes y podrían afectar a personas fotosensibles."
          }
        },
        "es-419" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "La próxima pantalla tiene luces parpadeantes y podrían afectar a personas fotosensibles."
          }
        }
      }
    },
    "amplify_ui_liveness_get_ready_photosensitivity_dialog_description" : {
      "extractionState" : "stale",
      "localizations" : {
        "en" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Si tienes epilepsia, puede afectarte la exposición al tintineo de diferentes colores."
          }
        },
        "es-419" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Si tienes epilepsia, puede afectarte la exposición al tintineo de diferentes colores."
          }
        }
      }
    },
    "amplify_ui_liveness_get_ready_photosensitivity_dialog_title" : {
      "extractionState" : "stale",
      "localizations" : {
        "en" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Si eres fotosensible"
          }
        },
        "es-419" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Si eres fotosensible"
          }
        }
      }
    },
    "amplify_ui_liveness_get_ready_photosensitivity_icon_a11y" : {
      "extractionState" : "stale",
      "localizations" : {
        "en" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Información sobre fotosensibilidad"
          }
        },
        "es-419" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Información sobre fotosensibilidad"
          }
        }
      }
    },
    "amplify_ui_liveness_get_ready_photosensitivity_title" : {
      "extractionState" : "stale",
      "localizations" : {
        "en" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Advertencia para personas fotosensibles"
          }
        },
        "es-419" : {
          "stringUnit" : {
            "state" : "translated",
            "value" : "Advertencia para personas fotosensibles"
          }
        }
      }
    }
  },
  "version" : "1.0"
}

```

## SDK Text Changes

The text that can be changed using the `Localizable.xcstring` file is in the following table, you can add any of these to change the text.


| Name | String |
|---------------|-------|
| `amparo_id_sdk_SuccessCircleTitle` | ¡Listo! |
| `amparo_id_sdk_SuccessCircleSubTitle` | Lo hiciste muy bien. |
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
