---
ms.openlocfilehash: 87dc93ece10eaedbfbabddb5f857d0bcd12e05c4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615693"
---
### <a name="only-tls-10-11-and-12-protocols-supported-in-systemnetservicepointmanager-and-systemnetsecuritysslstream"></a>Nur die Protokolle TLS 1.0, 1.1 und 1.2 werden in System.Net.ServicePointManager und System.Net.Security.SslStream unterstützt

#### <a name="details"></a>Details

Ab .NET Framework 4.6 dürfen die Klassen <xref:System.Net.ServicePointManager> und <xref:System.Net.Security.SslStream> nur eines der folgenden drei Protokolle verwenden: TLS 1.0, TLS 1.1 oder TLS 1.2. Weder das SSL3.0-Protokoll noch das RC4-Verschlüsselungsverfahren werden unterstützt.

#### <a name="suggestion"></a>Vorschlag

Die empfohlene Risikominderung besteht darin, für die serverseitige App ein Upgrade auf TLS 1.0, TLS 1.1 oder TLS 1.2 vorzunehmen. Wenn dies nicht möglich ist oder die Client-Apps fehlerhaft sind, kann die Klasse <xref:System.AppContext?displayProperty=fullName> verwendet werden, um das Feature auf zwei verschiedene Art und Weisen abzuwählen:

- durch programmgesteuertes Festlegen von Kompatibilitätsoptionen für <xref:System.AppContext?displayProperty=fullName>, wie [hier](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46) beschrieben wird.
- Durch Hinzufügen der folgenden Zeile zum Abschnitt `<runtime>` der app.config-Datei:

```xml
<AppContextSwitchOverrides value="Switch.System.Net.DontEnableSchUseStrongCrypto=true"/>
```

| name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.6         |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Net.SecurityProtocolType.Ssl3?displayProperty=nameWithType>
- <xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType>
- <xref:System.Security.Authentication.SslProtocols.Ssl2?displayProperty=nameWithType>
- <xref:System.Security.Authentication.SslProtocols.Ssl3?displayProperty=nameWithType>
