---
ms.openlocfilehash: 60759e3d03137bb5983703cbf04719ba4946cb6e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235629"
---
### <a name="winrt-stream-adapters-no-long-call-flushasync-automatically-on-close"></a><span data-ttu-id="cfcea-101">WinRT-Streamadapter rufen nicht mehr automatisch FlushAsync auf, wenn sie geschlossen werden</span><span class="sxs-lookup"><span data-stu-id="cfcea-101">WinRT stream adapters no long call FlushAsync automatically on close</span></span>

|   |   |
|---|---|
|<span data-ttu-id="cfcea-102">Details</span><span class="sxs-lookup"><span data-stu-id="cfcea-102">Details</span></span>|<span data-ttu-id="cfcea-103">In Windows Store-Apps rufen Windows Runtime-Streamadapter nicht mehr über die Dispose-Methode die FlushAsync-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="cfcea-103">In Windows Store apps, Windows Runtime stream adapters no longer call the FlushAsync method from the Dispose method.</span></span>|
|<span data-ttu-id="cfcea-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="cfcea-104">Suggestion</span></span>|<span data-ttu-id="cfcea-105">Diese Änderung sollte transparent sein.</span><span class="sxs-lookup"><span data-stu-id="cfcea-105">This change should be transparent.</span></span> <span data-ttu-id="cfcea-106">Entwickler können das vorherige Verhalten wiederherstellen, indem sie Code wie den folgenden schreiben:</span><span class="sxs-lookup"><span data-stu-id="cfcea-106">Developers can restore the previous behavior by writing code like this:</span></span><pre><code class="lang-csharp">using (var stream = GetWindowsRuntimeStream() as Stream)&#13;&#10;{&#13;&#10;// do something&#13;&#10;await stream.FlushAsync();&#13;&#10;}&#13;&#10;</code></pre>|
|<span data-ttu-id="cfcea-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="cfcea-107">Scope</span></span>|<span data-ttu-id="cfcea-108">Transparent</span><span class="sxs-lookup"><span data-stu-id="cfcea-108">Transparent</span></span>|
|<span data-ttu-id="cfcea-109">Version</span><span class="sxs-lookup"><span data-stu-id="cfcea-109">Version</span></span>|<span data-ttu-id="cfcea-110">4.5.1</span><span class="sxs-lookup"><span data-stu-id="cfcea-110">4.5.1</span></span>|
|<span data-ttu-id="cfcea-111">Typ</span><span class="sxs-lookup"><span data-stu-id="cfcea-111">Type</span></span>|<span data-ttu-id="cfcea-112">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="cfcea-112">Runtime</span></span>|
