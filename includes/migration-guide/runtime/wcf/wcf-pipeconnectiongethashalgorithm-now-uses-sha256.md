---
ms.openlocfilehash: 9f5f238e3d4222af1da3a1713e1b3e65de6e6f49
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "91024985"
---
### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a>Die PipeConnection.GetHashAlgorithm-Methode von WCF verwendet nun SHA256

#### <a name="details"></a>Details

Ab .NET Framework 4.7.1 verwendet Windows Communication Foundation einen SHA256-Hash, um zufällige Namen für Named Pipes zu generieren. In .NET Framework 4.7 und früheren Versionen wurde ein SHA1-Hash verwendet.

#### <a name="suggestion"></a>Vorschlag

Wenn Kompatibilitätsprobleme durch diese Änderung an .NET Framework 4.7.1 oder höher auftreten, können Sie diese deaktivieren, indem Sie folgende Zeile zum Abschnitt `<runtime>` Ihrer App.config-Datei hinzufügen:

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true" />
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
