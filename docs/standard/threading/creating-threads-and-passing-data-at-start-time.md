---
title: "Erstellen von Threads und Übergeben von Daten zur Startzeit"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [.NET Framework], creating
- threading [.NET Framework], passing data to threads
- threading [.NET Framework], retrieving data from threads
ms.assetid: 52b32222-e185-4f42-91a7-eaca65c0ab6d
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 61808dc804cc627ab368a5250414dfcc5f54c87e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="creating-threads-and-passing-data-at-start-time"></a><span data-ttu-id="82c14-102">Erstellen von Threads und Übergeben von Daten zur Startzeit</span><span class="sxs-lookup"><span data-stu-id="82c14-102">Creating Threads and Passing Data at Start Time</span></span>
<span data-ttu-id="82c14-103">Wenn ein Betriebssystem-Prozess erstellt wird, wird das Betriebssystem einen Thread, um die Ausführung von Code in diesem Prozess, einschließlich der ursprünglichen Anwendungsdomäne eingefügt.</span><span class="sxs-lookup"><span data-stu-id="82c14-103">When an operating-system process is created, the operating system injects a thread to execute code in that process, including any original application domain.</span></span> <span data-ttu-id="82c14-104">Ab diesem Zeitpunkt können Anwendungsdomänen erstellt und gelöscht werden, ohne alle Betriebssystemthreads notwendigerweise erstellt oder zerstört werden.</span><span class="sxs-lookup"><span data-stu-id="82c14-104">From that point on, application domains can be created and destroyed without any operating system threads necessarily being created or destroyed.</span></span> <span data-ttu-id="82c14-105">Wenn der ausgeführte Code verwaltet wird Code, ein <xref:System.Threading.Thread> -Objekt für die vom Thread ausgeführten in die aktuelle Anwendungsdomäne abgerufen werden kann durch Abrufen der statischen <xref:System.Threading.Thread.CurrentThread%2A> Eigenschaft vom Typ <xref:System.Threading.Thread>.</span><span class="sxs-lookup"><span data-stu-id="82c14-105">If the code being executed is managed code, then a <xref:System.Threading.Thread> object for the thread executing in the current application domain can be obtained by retrieving the static <xref:System.Threading.Thread.CurrentThread%2A> property of type <xref:System.Threading.Thread>.</span></span> <span data-ttu-id="82c14-106">Dieses Thema beschreibt Threaderstellung und alternativen für die Übergabe von Daten an die Threadprozedur erläutert.</span><span class="sxs-lookup"><span data-stu-id="82c14-106">This topic describes thread creation and discusses alternatives for passing data to the thread procedure.</span></span>  
  
## <a name="creating-a-thread"></a><span data-ttu-id="82c14-107">Erstellen eines Threads</span><span class="sxs-lookup"><span data-stu-id="82c14-107">Creating a Thread</span></span>  
 <span data-ttu-id="82c14-108">Erstellen eines neuen <xref:System.Threading.Thread> Objekt einen neuen verwalteten Thread erstellt.</span><span class="sxs-lookup"><span data-stu-id="82c14-108">Creating a new <xref:System.Threading.Thread> object creates a new managed thread.</span></span> <span data-ttu-id="82c14-109">Die <xref:System.Threading.Thread> -Klasse verfügt über Konstruktoren, die eine <xref:System.Threading.ThreadStart> delegieren oder eine <xref:System.Threading.ParameterizedThreadStart> Delegieren; der Delegat umschließt die Methode, die von dem neuen Thread, beim Aufrufen aufgerufen wird der <xref:System.Threading.Thread.Start%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="82c14-109">The <xref:System.Threading.Thread> class has constructors that take a <xref:System.Threading.ThreadStart> delegate or a <xref:System.Threading.ParameterizedThreadStart> delegate; the delegate wraps the method that is invoked by the new thread when you call the <xref:System.Threading.Thread.Start%2A> method.</span></span> <span data-ttu-id="82c14-110">Aufrufen von <xref:System.Threading.Thread.Start%2A> mehr als einmal bewirkt, dass eine <xref:System.Threading.ThreadStateException> ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="82c14-110">Calling <xref:System.Threading.Thread.Start%2A> more than once causes a <xref:System.Threading.ThreadStateException> to be thrown.</span></span>  
  
 <span data-ttu-id="82c14-111">Die <xref:System.Threading.Thread.Start%2A> Methodenrückgabe sofort, bevor der neue Thread tatsächlich gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="82c14-111">The <xref:System.Threading.Thread.Start%2A> method returns immediately, often before the new thread has actually started.</span></span> <span data-ttu-id="82c14-112">Sie können die <xref:System.Threading.Thread.ThreadState%2A> und <xref:System.Threading.Thread.IsAlive%2A> Eigenschaften zum Ermitteln des Status des Threads jederzeit, aber diese Eigenschaften sollten nie zum Synchronisieren der Aktivitäten von Threads verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="82c14-112">You can use the <xref:System.Threading.Thread.ThreadState%2A> and <xref:System.Threading.Thread.IsAlive%2A> properties to determine the state of the thread at any one moment, but these properties should never be used for synchronizing the activities of threads.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82c14-113">Sobald ein Thread gestartet wird, ist es nicht notwendig, behalten einen Verweis auf die <xref:System.Threading.Thread> Objekt.</span><span class="sxs-lookup"><span data-stu-id="82c14-113">Once a thread is started, it is not necessary to retain a reference to the <xref:System.Threading.Thread> object.</span></span> <span data-ttu-id="82c14-114">Der Thread weiterhin ausgeführt, bis die Threadprozedur beendet.</span><span class="sxs-lookup"><span data-stu-id="82c14-114">The thread continues to execute until the thread procedure ends.</span></span>  
  
 <span data-ttu-id="82c14-115">Das folgende Codebeispiel erstellt zwei neue Threads, um Instanz- und statische Methoden für ein anderes Objekt aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="82c14-115">The following code example creates two new threads to call instance and static methods on another object.</span></span>  
  
 [!code-cpp[System.Threading.ThreadStart2#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.ThreadStart2#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source2.cs#2)]
 [!code-vb[System.Threading.ThreadStart2#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source2.vb#2)]  
  
## <a name="passing-data-to-threads-and-retrieving-data-from-threads"></a><span data-ttu-id="82c14-116">Übergeben von Daten an Threads und Abrufen von Daten aus Threads</span><span class="sxs-lookup"><span data-stu-id="82c14-116">Passing Data to Threads and Retrieving Data from Threads</span></span>  
 <span data-ttu-id="82c14-117">In .NET Framework, Version 2.0 die <xref:System.Threading.ParameterizedThreadStart> Delegaten bietet eine einfache Möglichkeit, übergeben Sie ein Objekt mit den Daten, die einem Thread beim Aufrufen der <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> -methodenüberladung.</span><span class="sxs-lookup"><span data-stu-id="82c14-117">In the .NET Framework version 2.0, the <xref:System.Threading.ParameterizedThreadStart> delegate provides an easy way to pass an object containing data to a thread when you call the <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> method overload.</span></span> <span data-ttu-id="82c14-118">Ein Codebeispiel finden Sie unter <xref:System.Threading.ParameterizedThreadStart>.</span><span class="sxs-lookup"><span data-stu-id="82c14-118">See <xref:System.Threading.ParameterizedThreadStart> for a code example.</span></span>  
  
 <span data-ttu-id="82c14-119">Mithilfe der <xref:System.Threading.ParameterizedThreadStart> Delegat ist eine typsichere Möglichkeit zur Übergabe von Daten nicht, da die <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> methodenüberladung akzeptiert jedes Objekt.</span><span class="sxs-lookup"><span data-stu-id="82c14-119">Using the <xref:System.Threading.ParameterizedThreadStart> delegate is not a type-safe way to pass data, because the <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> method overload accepts any object.</span></span> <span data-ttu-id="82c14-120">Eine Alternative besteht darin, die Threadprozedur und die Daten in eine Hilfsklasse zu kapseln und Verwenden der <xref:System.Threading.ThreadStart> Delegaten zum Ausführen der Threadprozedur.</span><span class="sxs-lookup"><span data-stu-id="82c14-120">An alternative is to encapsulate the thread procedure and the data in a helper class and use the <xref:System.Threading.ThreadStart> delegate to execute the thread procedure.</span></span> <span data-ttu-id="82c14-121">Diese Technik ist in den beiden Codebeispielen dargestellt, die folgen.</span><span class="sxs-lookup"><span data-stu-id="82c14-121">This technique is shown in the two code examples that follow.</span></span>  
  
 <span data-ttu-id="82c14-122">Beide Methoden Delegaten verfügt über einen Rückgabewert aus, da es keine Möglichkeit, die Daten aus einem asynchronen Aufruf zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="82c14-122">Neither of these delegates has a return value, because there is no place to return the data from an asynchronous call.</span></span> <span data-ttu-id="82c14-123">Um die Ergebnisse einer Methode Threads abzurufen, können Sie eine Rückrufmethode verwenden, wie im zweiten Codebeispiel wird veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="82c14-123">To retrieve the results of a thread method, you can use a callback method, as demonstrated in the second code example.</span></span>  
  
 [!code-cpp[System.Threading.ThreadStart2#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source3.cpp#3)]
 [!code-csharp[System.Threading.ThreadStart2#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source3.cs#3)]
 [!code-vb[System.Threading.ThreadStart2#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source3.vb#3)]  
  
### <a name="retrieving-data-with-callback-methods"></a><span data-ttu-id="82c14-124">Abrufen von Daten mit Rückrufmethoden</span><span class="sxs-lookup"><span data-stu-id="82c14-124">Retrieving Data with Callback Methods</span></span>  
 <span data-ttu-id="82c14-125">Das folgende Beispiel veranschaulicht eine Rückrufmethode, die Daten von einem anderen Thread abruft.</span><span class="sxs-lookup"><span data-stu-id="82c14-125">The following example demonstrates a callback method that retrieves data from a thread.</span></span> <span data-ttu-id="82c14-126">Der Konstruktor für die Klasse enthält die Daten und die Threadmethode nimmt auch einen Delegaten, der die Rückrufmethode darstellt; bevor die Threadmethode beendet wird, ruft er den Rückrufdelegaten auf.</span><span class="sxs-lookup"><span data-stu-id="82c14-126">The constructor for the class that contains the data and the thread method also accepts a delegate representing the callback method; before the thread method ends, it invokes the callback delegate.</span></span>  
  
 [!code-cpp[System.Threading.ThreadStart2#4](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source4.cpp#4)]
 [!code-csharp[System.Threading.ThreadStart2#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source4.cs#4)]
 [!code-vb[System.Threading.ThreadStart2#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source4.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="82c14-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82c14-127">See Also</span></span>  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadStart>  
 <xref:System.Threading.ParameterizedThreadStart>  
 <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="82c14-128">Threading</span><span class="sxs-lookup"><span data-stu-id="82c14-128">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="82c14-129">Verwenden von Threads und Threading</span><span class="sxs-lookup"><span data-stu-id="82c14-129">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)
