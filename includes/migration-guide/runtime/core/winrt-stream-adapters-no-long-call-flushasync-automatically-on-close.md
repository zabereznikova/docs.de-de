---
ms.openlocfilehash: 60937459b6f18e9abae87ad2dc97c3942325eedc
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620273"
---
### <a name="winrt-stream-adapters-no-long-call-flushasync-automatically-on-close"></a><span data-ttu-id="989da-101">WinRT-Streamadapter rufen nicht mehr automatisch FlushAsync auf, wenn sie geschlossen werden</span><span class="sxs-lookup"><span data-stu-id="989da-101">WinRT stream adapters no long call FlushAsync automatically on close</span></span>

#### <a name="details"></a><span data-ttu-id="989da-102">Details</span><span class="sxs-lookup"><span data-stu-id="989da-102">Details</span></span>

<span data-ttu-id="989da-103">In Windows Store-Apps rufen Windows Runtime-Streamadapter nicht mehr über die Dispose-Methode die FlushAsync-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="989da-103">In Windows Store apps, Windows Runtime stream adapters no longer call the FlushAsync method from the Dispose method.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="989da-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="989da-104">Suggestion</span></span>

<span data-ttu-id="989da-105">Diese Änderung sollte transparent sein.</span><span class="sxs-lookup"><span data-stu-id="989da-105">This change should be transparent.</span></span> <span data-ttu-id="989da-106">Entwickler können das vorherige Verhalten wiederherstellen, indem sie Code wie den folgenden schreiben:</span><span class="sxs-lookup"><span data-stu-id="989da-106">Developers can restore the previous behavior by writing code like this:</span></span><pre><code class="lang-csharp">using (var stream = GetWindowsRuntimeStream() as Stream)&#13;&#10;{&#13;&#10;// do something&#13;&#10;await stream.FlushAsync();&#13;&#10;}&#13;&#10;</code></pre>

| <span data-ttu-id="989da-107">name</span><span class="sxs-lookup"><span data-stu-id="989da-107">Name</span></span>    | <span data-ttu-id="989da-108">Wert</span><span class="sxs-lookup"><span data-stu-id="989da-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="989da-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="989da-109">Scope</span></span>   |<span data-ttu-id="989da-110">Transparent</span><span class="sxs-lookup"><span data-stu-id="989da-110">Transparent</span></span>|
|<span data-ttu-id="989da-111">Version</span><span class="sxs-lookup"><span data-stu-id="989da-111">Version</span></span>|<span data-ttu-id="989da-112">4.5.1</span><span class="sxs-lookup"><span data-stu-id="989da-112">4.5.1</span></span>|
|<span data-ttu-id="989da-113">Typ</span><span class="sxs-lookup"><span data-stu-id="989da-113">Type</span></span>|<span data-ttu-id="989da-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="989da-114">Runtime</span></span>|
