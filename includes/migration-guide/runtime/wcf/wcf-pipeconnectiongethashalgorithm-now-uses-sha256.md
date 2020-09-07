---
ms.openlocfilehash: d32725b0d3063d3320b73e02039ff567090da932
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496609"
---
### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a><span data-ttu-id="a1fc2-101">Die PipeConnection.GetHashAlgorithm-Methode von WCF verwendet nun SHA256</span><span class="sxs-lookup"><span data-stu-id="a1fc2-101">WCF PipeConnection.GetHashAlgorithm now uses SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="a1fc2-102">Details</span><span class="sxs-lookup"><span data-stu-id="a1fc2-102">Details</span></span>

<span data-ttu-id="a1fc2-103">Ab .NET Framework 4.7.1 verwendet Windows Communication Foundation einen SHA256-Hash, um zufällige Namen für Named Pipes zu generieren.</span><span class="sxs-lookup"><span data-stu-id="a1fc2-103">Starting with the .NET Framework 4.7.1, Windows Communication Foundation uses a SHA256 hash to generate random names for named pipes.</span></span> <span data-ttu-id="a1fc2-104">In .NET Framework 4.7 und früheren Versionen wurde ein SHA1-Hash verwendet.</span><span class="sxs-lookup"><span data-stu-id="a1fc2-104">In the .NET Framework 4.7 and earlier versions, it used a SHA1 hash.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a1fc2-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="a1fc2-105">Suggestion</span></span>

<span data-ttu-id="a1fc2-106">Wenn Kompatibilitätsprobleme durch diese Änderung an .NET Framework 4.7.1 oder höher auftreten, können Sie diese deaktivieren, indem Sie folgende Zeile zum Abschnitt <code>&lt;runtime&gt;</code> Ihrer App.config-Datei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="a1fc2-106">If you run into compatibility issue with this change on the .NET Framework 4.7.1 or later, you can opt-out it by adding the following line to the <code>&lt;runtime&gt;</code> section of your app.config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="a1fc2-107">name</span><span class="sxs-lookup"><span data-stu-id="a1fc2-107">Name</span></span>    | <span data-ttu-id="a1fc2-108">Wert</span><span class="sxs-lookup"><span data-stu-id="a1fc2-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a1fc2-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="a1fc2-109">Scope</span></span>   |<span data-ttu-id="a1fc2-110">Gering</span><span class="sxs-lookup"><span data-stu-id="a1fc2-110">Minor</span></span>|
|<span data-ttu-id="a1fc2-111">Version</span><span class="sxs-lookup"><span data-stu-id="a1fc2-111">Version</span></span>|<span data-ttu-id="a1fc2-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="a1fc2-112">4.7.1</span></span>|
|<span data-ttu-id="a1fc2-113">Typ</span><span class="sxs-lookup"><span data-stu-id="a1fc2-113">Type</span></span>|<span data-ttu-id="a1fc2-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="a1fc2-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="a1fc2-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="a1fc2-115">Affected APIs</span></span>

<span data-ttu-id="a1fc2-116">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="a1fc2-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
