---
title: 'Breaking Change: TLS-Standardverschlüsselungssuites für .NET unter Linux'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, durch den .NET unter Linux jetzt bei der Verwendung von TLS/SSL die OpenSSL-Konfiguration für Standard-Cipher-Suites berücksichtigt.
ms.date: 10/16/2020
ms.openlocfilehash: f1c23517161ac213a9cd7cf6e7da8eebeb91583b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759188"
---
# <a name="default-tls-cipher-suites-for-net-on-linux"></a>TLS-Standardverschlüsselungssuites für .NET unter Linux

.NET unter Linux akzeptiert jetzt die OpenSSL-Konfiguration für Standardverschlüsselungssuites bei der Verwendung von TLS/SSL über die Klasse <xref:System.Net.Security.SslStream> oder Vorgänge auf höherer Ebene, z. B. HTTP über die Klasse <xref:System.Net.Http.HttpClient>. Wenn keine Standardverschlüsselungssuites explizit konfiguriert werden, verwendet .NET unter Linux eine stark eingeschränkte Liste mit zulässigen Verschlüsselungssuites.

## <a name="change-description"></a>Änderungsbeschreibung

In früheren .NET-Versionen akzeptiert .NET die Systemkonfiguration für Standardverschlüsselungssuites nicht. Die Liste der Standardverschlüsselungssuites für .NET unter Linux umfasst wenige Einschränkungen.

Ab .NET 5.0 akzeptiert .NET unter Linux die OpenSSL-Konfiguration für Standardverschlüsselungssuites, wenn diese in *openssl.cnf* angegeben ist. Wenn keine Verschlüsselungssuites explizit konfiguriert sind, lauten die einzigen zulässigen Verschlüsselungssuites wie folgt:

- TLS 1.3-Verschlüsselungssuites
- TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384
- TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256
- TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384
- TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256
- TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384
- TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256
- TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384
- TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256

Da dieser Fallbackstandard keine Verschlüsselungssuites enthält, die mit TLS 1.0 oder TLS 1.1 kompatibel sind, werden diese älteren Protokollversionen standardmäßig deaktiviert.

Das Bereitstellen eines CipherSuitePolicy-Werts für SslStream für eine bestimmte Sitzung ersetzt weiterhin den Inhalt der Konfigurationsdatei und/oder den .NET-Fallbackstandard.

## <a name="reason-for-change"></a>Grund für die Änderung

Benutzer, die .NET unter Linux ausführen, haben darum gebeten, dass die Standardkonfiguration für <xref:System.Net.Security.SslStream> so geändert werden muss, dass sie eine zuverlässige Bewertung der Sicherheit von Bewertungstools von Drittanbietern bereitstellt.

## <a name="version-introduced"></a>Eingeführt in Version

5.0

## <a name="recommended-action"></a>Empfohlene Maßnahme

Die neuen Standardeinstellungen funktionieren sehr wahrscheinlich bei der Kommunikation mit modernen Clients oder Servern. Wenn Sie die Liste der Standardverschlüsselungssuites erweitern müssen, damit Legacyclients akzeptiert (oder Legacyserver kontaktiert) werden, geben Sie entweder einen `CipherSuitePolicy`-Wert an, oder ändern Sie die OpenSSL-Konfigurationsdatei. Bei vielen Linux-Distributionen befindet sich die OpenSSL-Konfigurationsdatei unter */etc/ssl/openssl.cnf*.

Diese *openssl.cnf*-Beispieldatei stellt eine Basisdatei dar, die der Richtlinie für Standardverschlüsselungssuites für .NET 5.0 und höher unter Linux entspricht. Anstatt die Systemdatei zu ersetzen, sollten Sie diese Konzepte mit der Datei zusammenführen, die auf Ihrem System vorhanden ist.

```ini
openssl_conf = default_conf

[default_conf]
ssl_conf = ssl_sect

[ssl_sect]
system_default = system_default_sect

[system_default_sect]
CipherString = ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-SHA384:ECDHE-ECDSA-AES128-SHA256:ECDHE-RSA-AES256-SHA384:ECDHE-RSA-AES128-SHA256
```

In den Red Hat Enterprise Linux-, CentOS- und Fedora-Distributionen werden .NET-Anwendungen standardmäßig auf die Verschlüsselungssuites beschränkt, die von den systemweiten Kryptografierichtlinien zugelassen werden. Verwenden Sie für diese Distributionen die Kryptografierichtlinienkonfiguration anstelle von *openssl.cnf*.

## <a name="affected-apis"></a>Betroffene APIs

Nicht über eine API-Analyse erkennbar

<!--

### Affected APIs

- Not detectible via API analysis.

### Category

- Cryptography
- Security

-->
