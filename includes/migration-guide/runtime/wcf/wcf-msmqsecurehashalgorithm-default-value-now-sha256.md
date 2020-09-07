---
ms.openlocfilehash: 9baca45de1c8994f610815e84fdee8ba3930eb04
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497401"
---
### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a><span data-ttu-id="aa1aa-101">Der WCF-Standardwert MsmqSecureHashAlgorithm ist jetzt SHA256</span><span class="sxs-lookup"><span data-stu-id="aa1aa-101">WCF MsmqSecureHashAlgorithm default value is now SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="aa1aa-102">Details</span><span class="sxs-lookup"><span data-stu-id="aa1aa-102">Details</span></span>

<span data-ttu-id="aa1aa-103">Ab .NET Framework 4.7.1 ist SHA256 der Standardalgorithmus zum Signieren von Msmq-Nachrichten in WCF.</span><span class="sxs-lookup"><span data-stu-id="aa1aa-103">Starting with the .NET Framework 4.7.1, the default message signing algorithm in WCF for Msmq messages is SHA256.</span></span> <span data-ttu-id="aa1aa-104">In .NET Framework 4.7 und früheren Versionen ist SHA1 der Standardalgorithmus zum Signieren von Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="aa1aa-104">In the .NET Framework 4.7 and earlier versions, the default message signing algorithm is SHA1.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="aa1aa-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="aa1aa-105">Suggestion</span></span>

<span data-ttu-id="aa1aa-106">Wenn Kompatibilitätsprobleme durch diese Änderung an .NET Framework 4.7.1 oder höher auftreten, können Sie diese deaktivieren, indem Sie folgende Zeile zum Abschnitt <code>&lt;runtime&gt;</code> Ihrer App.config-Datei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="aa1aa-106">If you run into compatibility issues with this change on the .NET Framework 4.7.1 or later, you can opt-out the change by adding the following line to the <code>&lt;runtime&gt;</code>section of your app.config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="aa1aa-107">name</span><span class="sxs-lookup"><span data-stu-id="aa1aa-107">Name</span></span>    | <span data-ttu-id="aa1aa-108">Wert</span><span class="sxs-lookup"><span data-stu-id="aa1aa-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="aa1aa-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="aa1aa-109">Scope</span></span>   |<span data-ttu-id="aa1aa-110">Gering</span><span class="sxs-lookup"><span data-stu-id="aa1aa-110">Minor</span></span>|
|<span data-ttu-id="aa1aa-111">Version</span><span class="sxs-lookup"><span data-stu-id="aa1aa-111">Version</span></span>|<span data-ttu-id="aa1aa-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="aa1aa-112">4.7.1</span></span>|
|<span data-ttu-id="aa1aa-113">Typ</span><span class="sxs-lookup"><span data-stu-id="aa1aa-113">Type</span></span>|<span data-ttu-id="aa1aa-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="aa1aa-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="aa1aa-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="aa1aa-115">Affected APIs</span></span>

<span data-ttu-id="aa1aa-116">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="aa1aa-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
