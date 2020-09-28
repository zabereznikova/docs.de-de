---
ms.openlocfilehash: 7c0227980aa5d90f3788783088bcd7cd9509ed66
ms.sourcegitcommit: 261e0c98a111357692b3b63c596edf0cacf72991
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2020
ms.locfileid: "90770782"
---
### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a>Der WCF-Standardwert MsmqSecureHashAlgorithm ist jetzt SHA256

#### <a name="details"></a>Details

Ab .NET Framework 4.7.1 ist SHA256 der Standardalgorithmus zum Signieren von Msmq-Nachrichten in WCF. In .NET Framework 4.7 und früheren Versionen ist SHA1 der Standardalgorithmus zum Signieren von Nachrichten.

#### <a name="suggestion"></a>Vorschlag

Wenn Kompatibilitätsprobleme durch diese Änderung an .NET Framework 4.7.1 oder höher auftreten, können Sie diese beseitigen, indem Sie folgende Zeile zum Abschnitt `<runtime>` Ihrer app.config-Datei hinzufügen:

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; />
  </runtime>
</configuration>
```

| name    | Wert   |
|:--------|:--------|
| Bereich   | Gering   |
| Version | 4.7.1   |
| Typ    | Laufzeit |

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
