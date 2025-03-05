---
title: "Overview"
description: "This section introduces the Amparo ID Android SDK."
summary: ""
date: 2023-09-07T16:04:48+02:00
lastmod: 2023-09-07T16:04:48+02:00
draft: false
weight: 10
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  robots: "" # custom robot tags (optional)
---

This documentation aims to guide the implementation of the Amparo ID SDK in Android mobile
applications. Designed to provide an intuitive experience for both developers and end users,
this SDK encapsulates a reliable identification process with multiple layers of security and
validation.

Some key features of the Amparo ID SDK include:
- A pre-built UI flow that abstracts the identification process, extensively designed and tested by
the Amparo ID team.
- Secure user authentication through multiple security layers: MRZ scanning, NFC chip reading from
the identity card, liveness detection, and facial comparison between the NFC chip photo and the
image captured during the liveness test.
- Additional security layers: security question set and front-side identity card scanning.
- Secure communication with our services via mTLS and API Key.
- Customization of primary colors and error modal texts.

<!--
## Further reading

- Read [about how-to guides](https://diataxis.fr/how-to-guides/) in the Diátaxis framework
-->
