---
ms.openlocfilehash: ccdf232d743c9e270b6ed21f698998eb95a97399
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621221"
---
### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a><span data-ttu-id="3a5d0-101">Der WCF-Standardwert MsmqSecureHashAlgorithm ist jetzt SHA256</span><span class="sxs-lookup"><span data-stu-id="3a5d0-101">WCF MsmqSecureHashAlgorithm default value is now SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="3a5d0-102">Details</span><span class="sxs-lookup"><span data-stu-id="3a5d0-102">Details</span></span>

<span data-ttu-id="3a5d0-103">Ab .NET Framework 4.7.1 ist SHA256 der Standardalgorithmus zum Signieren von Msmq-Nachrichten in WCF.</span><span class="sxs-lookup"><span data-stu-id="3a5d0-103">Starting with the .NET Framework 4.7.1, the default message signing algorithm in WCF for Msmq messages is SHA256.</span></span> <span data-ttu-id="3a5d0-104">In .NET Framework 4.7 und früheren Versionen ist SHA1 der Standardalgorithmus zum Signieren von Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="3a5d0-104">In the .NET Framework 4.7 and earlier versions, the default message signing algorithm is SHA1.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3a5d0-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="3a5d0-105">Suggestion</span></span>

<span data-ttu-id="3a5d0-106">Wenn Kompatibilitätsprobleme durch diese Änderung an .NET Framework 4.7.1 oder höher auftreten, können Sie diese deaktivieren, indem Sie folgende Zeile zum Abschnitt <code>&lt;runtime&gt;</code> Ihrer App.config-Datei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="3a5d0-106">If you run into compatibility issues with this change on the .NET Framework 4.7.1 or later, you can opt-out the change by adding the following line to the <code>&lt;runtime&gt;</code>section of your app.config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="3a5d0-107">name</span><span class="sxs-lookup"><span data-stu-id="3a5d0-107">Name</span></span>    | <span data-ttu-id="3a5d0-108">Wert</span><span class="sxs-lookup"><span data-stu-id="3a5d0-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3a5d0-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="3a5d0-109">Scope</span></span>   |<span data-ttu-id="3a5d0-110">Gering</span><span class="sxs-lookup"><span data-stu-id="3a5d0-110">Minor</span></span>|
|<span data-ttu-id="3a5d0-111">Version</span><span class="sxs-lookup"><span data-stu-id="3a5d0-111">Version</span></span>|<span data-ttu-id="3a5d0-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="3a5d0-112">4.7.1</span></span>|
|<span data-ttu-id="3a5d0-113">Typ</span><span class="sxs-lookup"><span data-stu-id="3a5d0-113">Type</span></span>|<span data-ttu-id="3a5d0-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="3a5d0-114">Runtime</span></span>|
