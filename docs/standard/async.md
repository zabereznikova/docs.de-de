---
title: "Async (Übersicht)"
description: "Erfahren Sie mehr über die asynchrone Programmierung als eine wichtige Technik, mit der E/A-Blockierung und gleichzeitige Vorgänge auf mehreren Kernen direkt behandelt werden können."
keywords: .NET, .NET Core
author: cartermp
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 1e38e9d9-8284-46ee-a15f-199adc4f26f4
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: f2dddc21dfb124fe97c397a156743981a67e4037
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="async-overview"></a><span data-ttu-id="f11fd-104">Async (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="f11fd-104">Async Overview</span></span>

<span data-ttu-id="f11fd-105">Es ist noch nicht lange her, da wurden Apps einfach durch die Ausführung auf einem aktuelleren PC oder Server schneller, und dann endete dieser Trend.</span><span class="sxs-lookup"><span data-stu-id="f11fd-105">Not so long ago, apps got faster simply by buying a newer PC or server and then that trend stopped.</span></span> <span data-ttu-id="f11fd-106">In der Tat hat er sich umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="f11fd-106">In fact, it reversed.</span></span> <span data-ttu-id="f11fd-107">Mobiltelefone mit 1-GHz-Single Core-ARM-Chips erschienen auf dem Markt, und Serverarbeitsauslastungen wurden VMs übertragen.</span><span class="sxs-lookup"><span data-stu-id="f11fd-107">Mobile phones appeared with 1ghz single core ARM chips and server workloads transitioned to VMs.</span></span> <span data-ttu-id="f11fd-108">Benutzer wünschen immer noch reaktionsfähige Benutzeroberflächen, und Geschäftsinhaber wünschen sich Server, die sich ihren Unternehmen anpassen können.</span><span class="sxs-lookup"><span data-stu-id="f11fd-108">Users still want responsive UI and business owners want servers that scale with their business.</span></span> <span data-ttu-id="f11fd-109">Aus dem Übergang zu Mobilgeräten und zur Cloud und mehr als 3 Mrd. Internetbenutzern resultiert eine neue Gruppe von Softwaremustern.</span><span class="sxs-lookup"><span data-stu-id="f11fd-109">The transition to mobile and cloud and an internet-connected population of >3B users has resulted in a new set of software patterns.</span></span> 

* <span data-ttu-id="f11fd-110">Clientanwendungen sollen Always On/Always Connected sein und ständig auf Benutzerinteraktionen reagieren (z.B. Berühren) – mit hohen App Store-Bewertungen!</span><span class="sxs-lookup"><span data-stu-id="f11fd-110">Client applications are expected to be always-on, always-connected and constantly responsive to user interaction (for example, touch) with high app store ratings!</span></span>
* <span data-ttu-id="f11fd-111">Dienste sollen Verkehrsspitzen durch ordnungsgemäßes zentrales Hoch- und Herunterskalieren behandeln.</span><span class="sxs-lookup"><span data-stu-id="f11fd-111">Services are expected to handle spikes in traffic by gracefully scaling up and down.</span></span> 

<span data-ttu-id="f11fd-112">Asynchrone Programmierung ist eine wichtige Technik, mit der E/A-Blockierung und gleichzeitige Vorgänge auf mehreren Kernen direkt behandelt werden können.</span><span class="sxs-lookup"><span data-stu-id="f11fd-112">Async programming is a key technique that makes it straightforward to handle blocking I/O and concurrent operations on multiple cores.</span></span> <span data-ttu-id="f11fd-113">.NET bietet mit benutzerfreundlichen asynchronen Programmiermodellen auf Sprachebene in C#, VB und F# die Möglichkeit, Apps und Dienste reaktionsfähig und flexibel zu machen.</span><span class="sxs-lookup"><span data-stu-id="f11fd-113">.NET provides the capability for apps and services to be responsive and elastic with easy-to-use, language-level asynchronous programming models in C#, VB, and F#.</span></span>

## <a name="why-write-async-code"></a><span data-ttu-id="f11fd-114">Warum sollten Sie Async-Code schreiben?</span><span class="sxs-lookup"><span data-stu-id="f11fd-114">Why Write Async Code?</span></span>

<span data-ttu-id="f11fd-115">Moderne Apps machen umfassenden Gebrauch von Datei- und Netzwerk-E/A.</span><span class="sxs-lookup"><span data-stu-id="f11fd-115">Modern apps make extensive use of file and networking I/O.</span></span> <span data-ttu-id="f11fd-116">E/A-APIs sind üblicherweise Blockaden, was Benutzerfreundlichkeit und Hardwarenutzung beeinträchtigt, solange Sie keine herausfordernden Muster erlernen und verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="f11fd-116">I/O APIs traditionally block by default, resulting in poor user experiences and hardware utilization unless you want to learn and use challenging patterns.</span></span> <span data-ttu-id="f11fd-117">Taskbasierte, asynchrone APIs und das asynchrone Programmiermodell auf Sprachebene kehren dieses Modell um, sodass die asynchrone Ausführung zum Standard wird, wobei einige neue Konzepte zu erlernen sind.</span><span class="sxs-lookup"><span data-stu-id="f11fd-117">Task-based async APIs and the language-level asynchronous programming model invert this model, making async execution the default with few new concepts to learn.</span></span>

<span data-ttu-id="f11fd-118">Asynchroner Code weist folgende Merkmale auf:</span><span class="sxs-lookup"><span data-stu-id="f11fd-118">Async code has the following characteristics:</span></span>

* <span data-ttu-id="f11fd-119">Behandeln einer höheren Zahl von Serveranforderungen durch Erzeugen von Threads zum Behandeln einer höheren Zahl von Anforderungen während des Wartens auf die Rückmeldung von E/A-Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="f11fd-119">Handles more server requests by yielding threads to handle more requests while waiting for I/O requests to return.</span></span>
* <span data-ttu-id="f11fd-120">Reaktionsfähigere Benutzeroberflächen durch Erzeugen von Threads für die Benutzeroberflächeninteraktion während des Wartens auf E/A-Anforderungen und durch Übertragen zeitintensiver Abläufe auf andere CPU-Kerne.</span><span class="sxs-lookup"><span data-stu-id="f11fd-120">Enables UIs to be more responsive by yielding threads to UI interaction while waiting for I/O requests and by transitioning long-running work to other CPU cores.</span></span>
* <span data-ttu-id="f11fd-121">Viele der neueren .NET-APIs sind asynchron.</span><span class="sxs-lookup"><span data-stu-id="f11fd-121">Many of the newer .NET APIs are asynchronous.</span></span>
* <span data-ttu-id="f11fd-122">In .NET schreiben Sie im Handumdrehen asynchronen Code!</span><span class="sxs-lookup"><span data-stu-id="f11fd-122">It's easy to write async code in .NET!</span></span>

## <a name="whats-next"></a><span data-ttu-id="f11fd-123">Ausblick</span><span class="sxs-lookup"><span data-stu-id="f11fd-123">What's next?</span></span>

<span data-ttu-id="f11fd-124">Tiefe Einblicke in asynchrone Konzepte und Programmierung finden Sie unter [Async ausführlich](async-in-depth.md) und [Task-based asynchronous programming (Taskbasiertes, asynchrones Programmieren)](~/docs/standard/parallel-programming/task-based-asynchronous-programming.md).</span><span class="sxs-lookup"><span data-stu-id="f11fd-124">For a deep dive into async concepts and programming, see [Async in depth](async-in-depth.md) and [Task-based asynchronous programming](~/docs/standard/parallel-programming/task-based-asynchronous-programming.md).</span></span>
