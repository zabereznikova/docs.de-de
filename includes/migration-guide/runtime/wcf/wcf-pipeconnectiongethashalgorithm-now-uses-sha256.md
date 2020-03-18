---
ms.openlocfilehash: 318609c15d2e0b9a7ee59b38463735b33ef87974
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67857213"
---
### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a>Die PipeConnection.GetHashAlgorithm-Methode von WCF verwendet nun SHA256

|   |   |
|---|---|
|Details|Ab .NET Framework 4.7.1 verwendet Windows Communication Foundation einen SHA256-Hash, um zufällige Namen für Named Pipes zu generieren. In .NET Framework 4.7 und früheren Versionen wurde ein SHA1-Hash verwendet.|
|Vorschlag|Wenn Kompatibilitätsprobleme durch diese Änderung an .NET Framework 4.7.1 oder höher auftreten, können Sie diese deaktivieren, indem Sie folgende Zeile zum Abschnitt <code>&lt;runtime&gt;</code> Ihrer App.config-Datei hinzufügen:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|`Scope`|Nebenversion|
|Version|4.7.1|
|Geben Sie Folgendes ein:|Laufzeit|
