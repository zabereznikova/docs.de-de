---
ms.openlocfilehash: ce8e162e11802de1b06bfbc63d5c55de67ef23df
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67857265"
---
### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a>Der WCF-Standardwert MsmqSecureHashAlgorithm ist jetzt SHA256

|   |   |
|---|---|
|Details|Ab .NET Framework 4.7.1 ist SHA256 der Standardalgorithmus zum Signieren von Msmq-Nachrichten in WCF. In .NET Framework 4.7 und früheren Versionen ist SHA1 der Standardalgorithmus zum Signieren von Nachrichten.|
|Vorschlag|Wenn Kompatibilitätsprobleme durch diese Änderung an .NET Framework 4.7.1 oder höher auftreten, können Sie diese deaktivieren, indem Sie folgende Zeile zum Abschnitt <code>&lt;runtime&gt;</code> Ihrer App.config-Datei hinzufügen:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|`Scope`|Nebenversion|
|Version|4.7.1|
|Geben Sie Folgendes ein:|Laufzeit|
