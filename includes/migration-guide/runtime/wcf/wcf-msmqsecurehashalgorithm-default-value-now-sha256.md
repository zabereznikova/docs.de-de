---
ms.openlocfilehash: ce8e162e11802de1b06bfbc63d5c55de67ef23df
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67857265"
---
### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a><span data-ttu-id="cce60-101">Der WCF-Standardwert MsmqSecureHashAlgorithm ist jetzt SHA256</span><span class="sxs-lookup"><span data-stu-id="cce60-101">WCF MsmqSecureHashAlgorithm default value is now SHA256</span></span>

|   |   |
|---|---|
|<span data-ttu-id="cce60-102">Details</span><span class="sxs-lookup"><span data-stu-id="cce60-102">Details</span></span>|<span data-ttu-id="cce60-103">Ab .NET Framework 4.7.1 ist SHA256 der Standardalgorithmus zum Signieren von Msmq-Nachrichten in WCF.</span><span class="sxs-lookup"><span data-stu-id="cce60-103">Starting with the .NET Framework 4.7.1, the default message signing algorithm in WCF for Msmq messages is SHA256.</span></span> <span data-ttu-id="cce60-104">In .NET Framework 4.7 und früheren Versionen ist SHA1 der Standardalgorithmus zum Signieren von Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="cce60-104">In the .NET Framework 4.7 and earlier versions, the default message signing algorithm is SHA1.</span></span>|
|<span data-ttu-id="cce60-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="cce60-105">Suggestion</span></span>|<span data-ttu-id="cce60-106">Wenn Kompatibilitätsprobleme durch diese Änderung an .NET Framework 4.7.1 oder höher auftreten, können Sie diese deaktivieren, indem Sie folgende Zeile zum Abschnitt <code>&lt;runtime&gt;</code> Ihrer App.config-Datei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="cce60-106">If you run into compatibility issues with this change on the .NET Framework 4.7.1 or later, you can opt-out the change by adding the following line to the <code>&lt;runtime&gt;</code>section of your app.config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="cce60-107">`Scope`</span><span class="sxs-lookup"><span data-stu-id="cce60-107">Scope</span></span>|<span data-ttu-id="cce60-108">Nebenversion</span><span class="sxs-lookup"><span data-stu-id="cce60-108">Minor</span></span>|
|<span data-ttu-id="cce60-109">Version</span><span class="sxs-lookup"><span data-stu-id="cce60-109">Version</span></span>|<span data-ttu-id="cce60-110">4.7.1</span><span class="sxs-lookup"><span data-stu-id="cce60-110">4.7.1</span></span>|
|<span data-ttu-id="cce60-111">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="cce60-111">Type</span></span>|<span data-ttu-id="cce60-112">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="cce60-112">Runtime</span></span>|
