---
ms.openlocfilehash: 0e949cbdeda99dd7b94e919b903a21171a57f527
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614490"
---
### <a name="wcf-binding-with-the-transportwithmessagecredential-security-mode"></a>WCF-Bindung mit dem TransportWithMessageCredential-Sicherheitsmodus

#### <a name="details"></a>Details

Ab .NET Framework 4.6.1 kann die WCF-Bindung, die den TransportWithMessageCredential-Sicherheitsmodus verwendet, so eingerichtet werden, dass Nachrichten mit nicht signierten &quot;to&quot;-Headern für asymmetrische Sicherheitsschlüssel empfangen werden. Standardmäßig werden nicht signierte &quot;to&quot;-Header in .NET Framework 4.6.1 weiter abgelehnt. Sie werden nur akzeptiert, wenn eine Anwendung unter Verwendung des Switch.System.ServiceModel.AllowUnsignedToHeader-Konfigurationsschalters diesen neuen Vorgangsmodus aktiviert.

#### <a name="suggestion"></a>Vorschlag

Da diese Einstellung eine Opt-in-Funktion ist, sollte sie sich nicht auf das Verhalten vorhandener Apps auswirken.<br/>Verwenden Sie die folgende Konfigurationseinstellung, um zu steuern, ob das neue Verhalten verwendet werden soll:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.ServiceModel.AllowUnsignedToHeader=true" />
</runtime>
```

| name    | Wert       |
|:--------|:------------|
| Bereich   | Transparent |
| Version | 4.6.1       |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpsSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.WSFederationHttpSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType>
