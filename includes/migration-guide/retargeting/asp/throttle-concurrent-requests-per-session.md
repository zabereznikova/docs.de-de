---
ms.openlocfilehash: b521f4163bf5bf4a369d0eec12dae503703a976e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614434"
---
### <a name="throttle-concurrent-requests-per-session"></a><span data-ttu-id="7b1a8-101">Einschränken von gleichzeitigen Anforderungen pro Sitzung</span><span class="sxs-lookup"><span data-stu-id="7b1a8-101">Throttle concurrent requests per session</span></span>

#### <a name="details"></a><span data-ttu-id="7b1a8-102">Details</span><span class="sxs-lookup"><span data-stu-id="7b1a8-102">Details</span></span>

<span data-ttu-id="7b1a8-103">In .NET Framework 4.6.2 und früheren Versionen führt ASP.NET Anforderungen mit der gleichen SessionID sequentiell durch, und ASP.NET stellt die SessionID standardmäßig über Cookies aus.</span><span class="sxs-lookup"><span data-stu-id="7b1a8-103">In the .NET Framework 4.6.2 and earlier, ASP.NET executes requests with the same Sessionid sequentially, and ASP.NET always issues the Sessionid through cookies by default.</span></span> <span data-ttu-id="7b1a8-104">Wenn eine Seite zum Reagieren viel Zeit in Anspruch nimmt, wird die Serverleistung allein durch Drücken von <kbd>F5</kbd> im Browser erheblich eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="7b1a8-104">If a page takes a long time to respond, it will significantly degrade server performance just by pressing <kbd>F5</kbd> on the browser.</span></span> <span data-ttu-id="7b1a8-105">Mit der Fehlerbehebung verfolgt ein Zähler die in die Warteschlange eingestellten Anforderungen nach und beendet die Anforderungen, wenn sie einen angegebenen Grenzwert überschreiten.</span><span class="sxs-lookup"><span data-stu-id="7b1a8-105">In the fix, we added a counter to track the queued requests and terminate the requests when they exceed a specified limit.</span></span> <span data-ttu-id="7b1a8-106">Der Standardwert ist 50.</span><span class="sxs-lookup"><span data-stu-id="7b1a8-106">The default value is 50.</span></span> <span data-ttu-id="7b1a8-107">Wenn der Grenzwert erreicht wird, wird eine Warnung in das Ereignisprotokoll geschrieben, und möglicherweise wird eine HTTP 500-Antwort im IIS-Protokoll aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="7b1a8-107">If the limit is reached, a warning will be logged in the event log, and an HTTP 500 response may be recorded in the IIS log.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7b1a8-108">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="7b1a8-108">Suggestion</span></span>

<span data-ttu-id="7b1a8-109">Um das alte Verhalten wiederherzustellen, können Sie Ihrer web.config-Datei die folgende Einstellung hinzufügen, um sich gegen das neue Verhalten zu entscheiden.</span><span class="sxs-lookup"><span data-stu-id="7b1a8-109">To restore the old behavior, you can add the following setting to your web.config file to opt out of the new behavior.</span></span>

```xml
<appSettings>
    <add key="aspnet:RequestQueueLimitPerSession" value="2147483647"/>
</appSettings>
```

| <span data-ttu-id="7b1a8-110">name</span><span class="sxs-lookup"><span data-stu-id="7b1a8-110">Name</span></span>    | <span data-ttu-id="7b1a8-111">Wert</span><span class="sxs-lookup"><span data-stu-id="7b1a8-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7b1a8-112">Bereich</span><span class="sxs-lookup"><span data-stu-id="7b1a8-112">Scope</span></span>   | <span data-ttu-id="7b1a8-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="7b1a8-113">Edge</span></span>        |
| <span data-ttu-id="7b1a8-114">Version</span><span class="sxs-lookup"><span data-stu-id="7b1a8-114">Version</span></span> | <span data-ttu-id="7b1a8-115">4.7</span><span class="sxs-lookup"><span data-stu-id="7b1a8-115">4.7</span></span>         |
| <span data-ttu-id="7b1a8-116">Typ</span><span class="sxs-lookup"><span data-stu-id="7b1a8-116">Type</span></span>    | <span data-ttu-id="7b1a8-117">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="7b1a8-117">Retargeting</span></span> |
