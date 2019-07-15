---
ms.openlocfilehash: a2d4b7592727ca20ee79867094d6972eb9c4baed
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67857265"
---
### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a><span data-ttu-id="435c7-101">Der WCF-Standardwert MsmqSecureHashAlgorithm ist jetzt SHA256</span><span class="sxs-lookup"><span data-stu-id="435c7-101">WCF MsmqSecureHashAlgorithm default value is now SHA256</span></span>

|   |   |
|---|---|
|<span data-ttu-id="435c7-102">Details</span><span class="sxs-lookup"><span data-stu-id="435c7-102">Details</span></span>|<span data-ttu-id="435c7-103">Ab .NET Framework 4.7.1 ist SHA256 der Standardalgorithmus zum Signieren von Msmq-Nachrichten in WCF.</span><span class="sxs-lookup"><span data-stu-id="435c7-103">Starting with the .NET Framework 4.7.1, the default message signing algorithm in WCF for Msmq messages is SHA256.</span></span> <span data-ttu-id="435c7-104">In .NET Framework 4.7 und früheren Versionen ist SHA1 der Standardalgorithmus zum Signieren von Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="435c7-104">In the .NET Framework 4.7 and earlier versions, the default message signing algorithm is SHA1.</span></span>|
|<span data-ttu-id="435c7-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="435c7-105">Suggestion</span></span>|<span data-ttu-id="435c7-106">Wenn Kompatibilitätsprobleme durch diese Änderung an .NET Framework 4.7.1 oder höher auftreten, können Sie diese deaktivieren, indem Sie folgende Zeile zum Abschnitt <code>&lt;runtime&gt;</code> Ihrer App.config-Datei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="435c7-106">If you run into compatibility issues with this change on the .NET Framework 4.7.1 or later, you can opt-out the change by adding the following line to the <code>&lt;runtime&gt;</code>section of your app.config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="435c7-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="435c7-107">Scope</span></span>|<span data-ttu-id="435c7-108">Gering</span><span class="sxs-lookup"><span data-stu-id="435c7-108">Minor</span></span>|
|<span data-ttu-id="435c7-109">Version</span><span class="sxs-lookup"><span data-stu-id="435c7-109">Version</span></span>|<span data-ttu-id="435c7-110">4.7.1</span><span class="sxs-lookup"><span data-stu-id="435c7-110">4.7.1</span></span>|
|<span data-ttu-id="435c7-111">Typ</span><span class="sxs-lookup"><span data-stu-id="435c7-111">Type</span></span>|<span data-ttu-id="435c7-112">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="435c7-112">Runtime</span></span>|

