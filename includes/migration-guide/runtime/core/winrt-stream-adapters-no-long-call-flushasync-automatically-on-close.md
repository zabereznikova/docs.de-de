---
ms.openlocfilehash: 2b4f35fe15f806897e5e4d85ee774b2e4572d974
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496291"
---
### <a name="winrt-stream-adapters-no-long-call-flushasync-automatically-on-close"></a><span data-ttu-id="937d2-101">WinRT-Streamadapter rufen nicht mehr automatisch FlushAsync auf, wenn sie geschlossen werden</span><span class="sxs-lookup"><span data-stu-id="937d2-101">WinRT stream adapters no long call FlushAsync automatically on close</span></span>

#### <a name="details"></a><span data-ttu-id="937d2-102">Details</span><span class="sxs-lookup"><span data-stu-id="937d2-102">Details</span></span>

<span data-ttu-id="937d2-103">In Windows Store-Apps rufen Windows Runtime-Streamadapter nicht mehr über die Dispose-Methode die FlushAsync-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="937d2-103">In Windows Store apps, Windows Runtime stream adapters no longer call the FlushAsync method from the Dispose method.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="937d2-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="937d2-104">Suggestion</span></span>

<span data-ttu-id="937d2-105">Diese Änderung sollte transparent sein.</span><span class="sxs-lookup"><span data-stu-id="937d2-105">This change should be transparent.</span></span> <span data-ttu-id="937d2-106">Entwickler können das vorherige Verhalten wiederherstellen, indem sie Code wie den folgenden schreiben:</span><span class="sxs-lookup"><span data-stu-id="937d2-106">Developers can restore the previous behavior by writing code like this:</span></span><pre><code class="lang-csharp">using (var stream = GetWindowsRuntimeStream() as Stream)&#13;&#10;{&#13;&#10;// do something&#13;&#10;await stream.FlushAsync();&#13;&#10;}&#13;&#10;</code></pre>

| <span data-ttu-id="937d2-107">name</span><span class="sxs-lookup"><span data-stu-id="937d2-107">Name</span></span>    | <span data-ttu-id="937d2-108">Wert</span><span class="sxs-lookup"><span data-stu-id="937d2-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="937d2-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="937d2-109">Scope</span></span>   |<span data-ttu-id="937d2-110">Transparent</span><span class="sxs-lookup"><span data-stu-id="937d2-110">Transparent</span></span>|
|<span data-ttu-id="937d2-111">Version</span><span class="sxs-lookup"><span data-stu-id="937d2-111">Version</span></span>|<span data-ttu-id="937d2-112">4.5.1</span><span class="sxs-lookup"><span data-stu-id="937d2-112">4.5.1</span></span>|
|<span data-ttu-id="937d2-113">Typ</span><span class="sxs-lookup"><span data-stu-id="937d2-113">Type</span></span>|<span data-ttu-id="937d2-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="937d2-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="937d2-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="937d2-115">Affected APIs</span></span>

<span data-ttu-id="937d2-116">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="937d2-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
