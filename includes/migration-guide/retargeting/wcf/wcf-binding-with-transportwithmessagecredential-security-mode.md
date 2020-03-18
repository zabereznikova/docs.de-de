---
ms.openlocfilehash: 2359dafb9042c13ae75e644d4ea655f53c14e95e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804342"
---
### <a name="wcf-binding-with-the-transportwithmessagecredential-security-mode"></a>WCF-Bindung mit dem TransportWithMessageCredential-Sicherheitsmodus

|   |   |
|---|---|
|Details|Ab .NET Framework 4.6.1 kann die WCF-Bindung, die den TransportWithMessageCredential-Sicherheitsmodus verwendet, so eingerichtet werden, dass Nachrichten mit nicht signierten &quot;to&quot;-Headern für asymmetrische Sicherheitsschlüssel empfangen werden. Standardmäßig werden nicht signierte &quot;to&quot;-Header in .NET Framework 4.6.1 weiter abgelehnt. Sie werden nur akzeptiert, wenn eine Anwendung unter Verwendung des Switch.System.ServiceModel.AllowUnsignedToHeader-Konfigurationsschalters diesen neuen Vorgangsmodus aktiviert.|
|Vorschlag|Da diese Einstellung eine Opt-in-Funktion ist, sollte sie sich nicht auf das Verhalten vorhandener Apps auswirken.<br/>Verwenden Sie die folgende Konfigurationseinstellung, um zu steuern, ob das neue Verhalten verwendet werden soll:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.AllowUnsignedToHeader=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|`Scope`|Transparent|
|Version|4.6.1|
|Geben Sie Folgendes ein:|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType></li><li><xref:System.ServiceModel.BasicHttpsSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType></li><li><xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential?displayProperty=nameWithType></li><li><xref:System.ServiceModel.WSFederationHttpSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType></li></ul>|
