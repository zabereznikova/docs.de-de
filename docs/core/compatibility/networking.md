---
title: Breaking Changes für Netzwerke
description: Listet die Breaking Changes für Netzwerke in .NET Core auf.
ms.date: 05/05/2020
ms.openlocfilehash: fdbd3f3bdcae5048b4f01e4d827f8a0e876c5c15
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050516"
---
# <a name="networking-breaking-changes"></a>Breaking Changes für Netzwerke

Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:

| Unterbrechende Änderung | Eingeführt in Version |
| - | - |
| [NegotiateStream und SslStream lassen aufeinanderfolgende Begin-Vorgänge zu](#negotiatestream-and-sslstream-allow-successive-begin-operations) | 5.0 |
| [Socket.LocalEndPoint wird nach dem Aufruf von SendToAsync aktualisiert](#socketlocalendpoint-is-updated-after-calling-sendtoasync) | 5.0 |
| [Entfernung von WinHttpHandler aus der .NET-Runtime](#winhttphandler-removed-from-net-runtime) | 5.0 |
| [MulticastOption.Group akzeptiert keine null-Werte](#multicastoptiongroup-doesnt-accept-a-null-value) | 5.0 |
| [Verarbeitung von Cookiepfaden jetzt mit RFC 6265 konform](#cookie-path-handling-now-conforms-to-rfc-6265) | 5.0 |
| [Standardwert von HttpRequestMessage.Version wurde in 1.1 geändert](#default-value-of-httprequestmessageversion-changed-to-11) | 3.0 |
| [WebClient.CancelAsync wird nicht immer sofort abgebrochen](#webclientcancelasync-doesnt-always-cancel-immediately) | 2.0 |

## <a name="net-50"></a>.NET 5.0

[!INCLUDE [negotiatestream-sslstream-dont-fail-on-successive-begin-calls](../../../includes/core-changes/networking/5.0/negotiatestream-sslstream-dont-fail-on-successive-begin-calls.md)]

***

[!INCLUDE [localendpoint-updated-on-sendtoasync](../../../includes/core-changes/networking/5.0/localendpoint-updated-on-sendtoasync.md)]

***

[!INCLUDE [winhttphandler-removed-from-runtime](../../../includes/core-changes/networking/5.0/winhttphandler-removed-from-runtime.md)]

***

[!INCLUDE [multicastoption-group-doesnt-accept-null](../../../includes/core-changes/networking/5.0/multicastoption-group-doesnt-accept-null.md)]

***

[!INCLUDE [cookie-path-conforms-to-rfc6265](../../../includes/core-changes/networking/5.0/cookie-path-conforms-to-rfc6265.md)]

***

## <a name="net-core-30"></a>.NET Core 3.0

[!INCLUDE[Default value of HttpRequestMessage.Version changed to 1.1](~/includes/core-changes/networking/3.0/httprequestmessage-version-change.md)]

***

## <a name="net-core-20"></a>.NET Core 2.0

[!INCLUDE [behavior-change-webclient-cancelasync](../../../includes/core-changes/networking/2.0/behavior-change-webclient-cancelasync.md)]

***
