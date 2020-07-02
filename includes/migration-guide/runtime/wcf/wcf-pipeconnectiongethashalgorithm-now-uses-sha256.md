---
ms.openlocfilehash: 0f87f9e9b87860da97ce96e18104b44ec4327c91
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621233"
---
### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a><span data-ttu-id="2b294-101">Die PipeConnection.GetHashAlgorithm-Methode von WCF verwendet nun SHA256</span><span class="sxs-lookup"><span data-stu-id="2b294-101">WCF PipeConnection.GetHashAlgorithm now uses SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="2b294-102">Details</span><span class="sxs-lookup"><span data-stu-id="2b294-102">Details</span></span>

<span data-ttu-id="2b294-103">Ab .NET Framework 4.7.1 verwendet Windows Communication Foundation einen SHA256-Hash, um zufällige Namen für Named Pipes zu generieren.</span><span class="sxs-lookup"><span data-stu-id="2b294-103">Starting with the .NET Framework 4.7.1, Windows Communication Foundation uses a SHA256 hash to generate random names for named pipes.</span></span> <span data-ttu-id="2b294-104">In .NET Framework 4.7 und früheren Versionen wurde ein SHA1-Hash verwendet.</span><span class="sxs-lookup"><span data-stu-id="2b294-104">In the .NET Framework 4.7 and earlier versions, it used a SHA1 hash.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2b294-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="2b294-105">Suggestion</span></span>

<span data-ttu-id="2b294-106">Wenn Kompatibilitätsprobleme durch diese Änderung an .NET Framework 4.7.1 oder höher auftreten, können Sie diese deaktivieren, indem Sie folgende Zeile zum Abschnitt <code>&lt;runtime&gt;</code> Ihrer App.config-Datei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="2b294-106">If you run into compatibility issue with this change on the .NET Framework 4.7.1 or later, you can opt-out it by adding the following line to the <code>&lt;runtime&gt;</code> section of your app.config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="2b294-107">name</span><span class="sxs-lookup"><span data-stu-id="2b294-107">Name</span></span>    | <span data-ttu-id="2b294-108">Wert</span><span class="sxs-lookup"><span data-stu-id="2b294-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2b294-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="2b294-109">Scope</span></span>   |<span data-ttu-id="2b294-110">Gering</span><span class="sxs-lookup"><span data-stu-id="2b294-110">Minor</span></span>|
|<span data-ttu-id="2b294-111">Version</span><span class="sxs-lookup"><span data-stu-id="2b294-111">Version</span></span>|<span data-ttu-id="2b294-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="2b294-112">4.7.1</span></span>|
|<span data-ttu-id="2b294-113">Typ</span><span class="sxs-lookup"><span data-stu-id="2b294-113">Type</span></span>|<span data-ttu-id="2b294-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="2b294-114">Runtime</span></span>|
