---
title: Async (Übersicht)
description: Erfahren Sie mehr über die asynchrone Programmierung als eine wichtige Technik, mit der E/A-Blockierung und gleichzeitige Vorgänge auf mehreren Kernen direkt behandelt werden können.
author: cartermp
ms.author: wiwagn
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: 1e38e9d9-8284-46ee-a15f-199adc4f26f4
ms.openlocfilehash: d649bc3a92d3bb834b3bc4f7d3c1bcb0f9417375
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159727"
---
# <a name="async-overview"></a><span data-ttu-id="65bb0-103">Async (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="65bb0-103">Async Overview</span></span>

<span data-ttu-id="65bb0-104">Es ist noch nicht lange her, da wurden Apps einfach durch die Ausführung auf einem aktuelleren PC oder Server schneller, und dann endete dieser Trend.</span><span class="sxs-lookup"><span data-stu-id="65bb0-104">Not so long ago, apps got faster simply by buying a newer PC or server and then that trend stopped.</span></span> <span data-ttu-id="65bb0-105">In der Tat hat er sich umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="65bb0-105">In fact, it reversed.</span></span> <span data-ttu-id="65bb0-106">Mobiltelefone mit 1-GHz-Single Core-ARM-Chips erschienen auf dem Markt, und Serverarbeitsauslastungen wurden VMs übertragen.</span><span class="sxs-lookup"><span data-stu-id="65bb0-106">Mobile phones appeared with 1ghz single core ARM chips and server workloads transitioned to VMs.</span></span> <span data-ttu-id="65bb0-107">Benutzer wünschen immer noch reaktionsfähige Benutzeroberflächen, und Geschäftsinhaber wünschen sich Server, die sich ihren Unternehmen anpassen können.</span><span class="sxs-lookup"><span data-stu-id="65bb0-107">Users still want responsive UI and business owners want servers that scale with their business.</span></span> <span data-ttu-id="65bb0-108">Aus dem Übergang zu Mobilgeräten und zur Cloud und mehr als 3 Mrd. Internetbenutzern resultiert eine neue Gruppe von Softwaremustern.</span><span class="sxs-lookup"><span data-stu-id="65bb0-108">The transition to mobile and cloud and an internet-connected population of >3B users has resulted in a new set of software patterns.</span></span>

- <span data-ttu-id="65bb0-109">Clientanwendungen sollen Always On/Always Connected sein und ständig auf Benutzerinteraktionen reagieren (z.B. Berühren) – mit hohen App Store-Bewertungen!</span><span class="sxs-lookup"><span data-stu-id="65bb0-109">Client applications are expected to be always-on, always-connected and constantly responsive to user interaction (for example, touch) with high app store ratings!</span></span>
- <span data-ttu-id="65bb0-110">Dienste sollen Verkehrsspitzen durch ordnungsgemäßes zentrales Hoch- und Herunterskalieren behandeln.</span><span class="sxs-lookup"><span data-stu-id="65bb0-110">Services are expected to handle spikes in traffic by gracefully scaling up and down.</span></span>

<span data-ttu-id="65bb0-111">Asynchrone Programmierung ist eine wichtige Technik, mit der E/A-Blockierung und gleichzeitige Vorgänge auf mehreren Kernen direkt behandelt werden können.</span><span class="sxs-lookup"><span data-stu-id="65bb0-111">Async programming is a key technique that makes it straightforward to handle blocking I/O and concurrent operations on multiple cores.</span></span> <span data-ttu-id="65bb0-112">.NET bietet mit benutzerfreundlichen asynchronen Programmiermodellen auf Sprachebene in C#, Visual Basic und F# die Möglichkeit, Apps und Dienste reaktionsfähig und flexibel zu machen.</span><span class="sxs-lookup"><span data-stu-id="65bb0-112">.NET provides the capability for apps and services to be responsive and elastic with easy-to-use, language-level asynchronous programming models in C#, Visual Basic, and F#.</span></span>

## <a name="why-write-async-code"></a><span data-ttu-id="65bb0-113">Warum sollten Sie Async-Code schreiben?</span><span class="sxs-lookup"><span data-stu-id="65bb0-113">Why Write Async Code?</span></span>

<span data-ttu-id="65bb0-114">Moderne Apps machen umfassenden Gebrauch von Datei- und Netzwerk-E/A.</span><span class="sxs-lookup"><span data-stu-id="65bb0-114">Modern apps make extensive use of file and networking I/O.</span></span> <span data-ttu-id="65bb0-115">E/A-APIs sind üblicherweise Blockaden, was Benutzerfreundlichkeit und Hardwarenutzung beeinträchtigt, solange Sie keine herausfordernden Muster erlernen und verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="65bb0-115">I/O APIs traditionally block by default, resulting in poor user experiences and hardware utilization unless you want to learn and use challenging patterns.</span></span> <span data-ttu-id="65bb0-116">Taskbasierte, asynchrone APIs und das asynchrone Programmiermodell auf Sprachebene kehren dieses Modell um, sodass die asynchrone Ausführung zum Standard wird, wobei einige neue Konzepte zu erlernen sind.</span><span class="sxs-lookup"><span data-stu-id="65bb0-116">Task-based async APIs and the language-level asynchronous programming model invert this model, making async execution the default with few new concepts to learn.</span></span>

<span data-ttu-id="65bb0-117">Asynchroner Code weist folgende Merkmale auf:</span><span class="sxs-lookup"><span data-stu-id="65bb0-117">Async code has the following characteristics:</span></span>

- <span data-ttu-id="65bb0-118">Behandeln einer höheren Zahl von Serveranforderungen durch Erzeugen von Threads zum Behandeln einer höheren Zahl von Anforderungen während des Wartens auf die Rückmeldung von E/A-Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="65bb0-118">Handles more server requests by yielding threads to handle more requests while waiting for I/O requests to return.</span></span>
- <span data-ttu-id="65bb0-119">Reaktionsfähigere Benutzeroberflächen durch Erzeugen von Threads für die Benutzeroberflächeninteraktion während des Wartens auf E/A-Anforderungen und durch Übertragen zeitintensiver Abläufe auf andere CPU-Kerne.</span><span class="sxs-lookup"><span data-stu-id="65bb0-119">Enables UIs to be more responsive by yielding threads to UI interaction while waiting for I/O requests and by transitioning long-running work to other CPU cores.</span></span>
- <span data-ttu-id="65bb0-120">Viele der neueren .NET-APIs sind asynchron.</span><span class="sxs-lookup"><span data-stu-id="65bb0-120">Many of the newer .NET APIs are asynchronous.</span></span>
- <span data-ttu-id="65bb0-121">In .NET schreiben Sie im Handumdrehen asynchronen Code!</span><span class="sxs-lookup"><span data-stu-id="65bb0-121">It's easy to write async code in .NET!</span></span>

## <a name="whats-next"></a><span data-ttu-id="65bb0-122">Ausblick</span><span class="sxs-lookup"><span data-stu-id="65bb0-122">What's next?</span></span>

<span data-ttu-id="65bb0-123">Weitere Informationen finden Sie im Artikel zu [Async](async-in-depth.md).</span><span class="sxs-lookup"><span data-stu-id="65bb0-123">For more information, see the [Async in depth](async-in-depth.md) topic.</span></span>

<span data-ttu-id="65bb0-124">Das Thema [Muster für die asynchrone Programmierung](asynchronous-programming-patterns/index.md) bietet eine Übersicht über diese drei in .NET unterstützten asynchronen Programmierungsmuster:</span><span class="sxs-lookup"><span data-stu-id="65bb0-124">The [Asynchronous Programming Patterns](asynchronous-programming-patterns/index.md) topic provides an overview of the three asynchronous programming patterns supported in .NET:</span></span>  
  
- <span data-ttu-id="65bb0-125">[Asynchronous Programming Model (APM) (Asynchrones Programmiermodell (APM))](asynchronous-programming-patterns/asynchronous-programming-model-apm.md) (Legacy)</span><span class="sxs-lookup"><span data-stu-id="65bb0-125">[Asynchronous Programming Model (APM)](asynchronous-programming-patterns/asynchronous-programming-model-apm.md) (legacy)</span></span>  
  
- <span data-ttu-id="65bb0-126">[Event-based Asynchronous Pattern (EAP) (Ereignisbasiertes asynchrones Muster (EAP))](asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (Legacy)</span><span class="sxs-lookup"><span data-stu-id="65bb0-126">[Event-based Asynchronous Pattern (EAP)](asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (legacy)</span></span>  
  
- <span data-ttu-id="65bb0-127">[Task-based Asynchronous Pattern (TAP) (Taskbasierte asynchrone Muster (TAP))](asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) (für neue Entwicklung empfohlen)</span><span class="sxs-lookup"><span data-stu-id="65bb0-127">[Task-based Asynchronous Pattern (TAP)](asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) (recommended for new development)</span></span>  

<span data-ttu-id="65bb0-128">Weitere Informationen zum empfohlenen aufgabenbasierten Programmierungsmodell finden Sie im Artikel [Aufgabenbasierte asynchrone Programmierung](parallel-programming/task-based-asynchronous-programming.md).</span><span class="sxs-lookup"><span data-stu-id="65bb0-128">For more information about recommended task-based programming model, see the [Task-based asynchronous programming](parallel-programming/task-based-asynchronous-programming.md) topic.</span></span>
