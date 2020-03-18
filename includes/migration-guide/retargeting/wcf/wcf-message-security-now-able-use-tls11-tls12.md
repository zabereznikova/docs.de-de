---
ms.openlocfilehash: 0a3dc43ebdc58d54675f2264a8ee56d9f4358cd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859085"
---
### <a name="wcf-message-security-now-is-able-to-use-tls11-and-tls12"></a>WCF-Nachrichtensicherheit kann jetzt TLS1.1 und TLS1.2 verwenden

|   |   |
|---|---|
|Details|Ab .NET Framework 4.7 können Kunden über die Anwendungskonfigurationseinstellungen neben SSL3.0 und TLS1.0 entweder TLS1.1 oder TLS1.2 in WCF-Nachrichtensicherheit konfigurieren.|
|Vorschlag|In .NET Framework 4.7 werden TLS1.1 und TLS1.2 in WCF-Nachrichtensicherheit standardmäßig nicht unterstützt. Sie können die Unterstützung aktivieren, indem Sie die folgende Zeile zum Abschnitt <code>&lt;runtime&gt;</code> der app.config- oder der web.config-Datei hinzufügen:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;Switch.System.Net.DontEnableSchUseStrongCrypto=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|`Scope`|Edge|
|Version|4.7|
|Geben Sie Folgendes ein:|Neuzuweisung|
