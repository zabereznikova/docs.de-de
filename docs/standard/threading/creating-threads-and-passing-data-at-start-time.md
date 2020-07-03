---
title: Erstellen von Threads und Übergeben von Daten zur Startzeit
description: Erfahren Sie, wie Sie in .NET Threads erstellen und Daten zur Startzeit eines Betriebssystemprozesses übergeben.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [.NET Framework], creating
- threading [.NET Framework], passing data to threads
- threading [.NET Framework], retrieving data from threads
ms.assetid: 52b32222-e185-4f42-91a7-eaca65c0ab6d
ms.openlocfilehash: 811028d3c853441ff3a61d3628a44e5c65ba7059
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2020
ms.locfileid: "84661913"
---
# <a name="creating-threads-and-passing-data-at-start-time"></a><span data-ttu-id="df04c-103">Erstellen von Threads und Übergeben von Daten zur Startzeit</span><span class="sxs-lookup"><span data-stu-id="df04c-103">Creating threads and passing data at start time</span></span>

<span data-ttu-id="df04c-104">Wenn ein Betriebssystemprozess erstellt wird, führt das Betriebssystem einen Thread ein, um Code in diesem Prozess auszuführen, einschließlich einer etwaigen ursprünglichen Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="df04c-104">When an operating-system process is created, the operating system injects a thread to execute code in that process, including any original application domain.</span></span> <span data-ttu-id="df04c-105">Ab diesem Punkt können Anwendungsdomänen erstellt und gelöscht werden, ohne dass notwendigerweise Betriebssystemthreads erstellt oder zerstört werden.</span><span class="sxs-lookup"><span data-stu-id="df04c-105">From that point on, application domains can be created and destroyed without any operating system threads necessarily being created or destroyed.</span></span> <span data-ttu-id="df04c-106">Wenn der ausgeführte Code verwalteter Code ist, kann ein <xref:System.Threading.Thread> -Objekt für die Threadausführung in der aktuellen Anwendungsdomäne durch Abrufen der statischen <xref:System.Threading.Thread.CurrentThread%2A>-Eigenschaft des Typs <xref:System.Threading.Thread> abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="df04c-106">If the code being executed is managed code, then a <xref:System.Threading.Thread> object for the thread executing in the current application domain can be obtained by retrieving the static <xref:System.Threading.Thread.CurrentThread%2A> property of type <xref:System.Threading.Thread>.</span></span> <span data-ttu-id="df04c-107">Dieses Thema beschreibt die Threaderstellung und erläutert Alternativen für die Übergabe von Daten an die Threadprozedur.</span><span class="sxs-lookup"><span data-stu-id="df04c-107">This topic describes thread creation and discusses alternatives for passing data to the thread procedure.</span></span>  
  
## <a name="creating-a-thread"></a><span data-ttu-id="df04c-108">Erstellen eines Threads</span><span class="sxs-lookup"><span data-stu-id="df04c-108">Creating a thread</span></span>

 <span data-ttu-id="df04c-109">Beim Erstellen eines neuen <xref:System.Threading.Thread>-Objekts wird ein neuer verwalteter Thread erstellt.</span><span class="sxs-lookup"><span data-stu-id="df04c-109">Creating a new <xref:System.Threading.Thread> object creates a new managed thread.</span></span> <span data-ttu-id="df04c-110">Die <xref:System.Threading.Thread>-Klasse verfügt über Konstruktoren, die einen <xref:System.Threading.ThreadStart>- oder <xref:System.Threading.ParameterizedThreadStart>-annehmen; der Delegat umschließt die Methode, die von dem neuen Thread aufgerufen wird, wenn Sie die <xref:System.Threading.Thread.Start%2A>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="df04c-110">The <xref:System.Threading.Thread> class has constructors that take a <xref:System.Threading.ThreadStart> delegate or a <xref:System.Threading.ParameterizedThreadStart> delegate; the delegate wraps the method that is invoked by the new thread when you call the <xref:System.Threading.Thread.Start%2A> method.</span></span> <span data-ttu-id="df04c-111">Bei mehrmaligem Aufrufen von <xref:System.Threading.Thread.Start%2A> wird eine <xref:System.Threading.ThreadStateException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="df04c-111">Calling <xref:System.Threading.Thread.Start%2A> more than once causes a <xref:System.Threading.ThreadStateException> to be thrown.</span></span>  
  
 <span data-ttu-id="df04c-112">Die Rückgabe der <xref:System.Threading.Thread.Start%2A>-Methode erfolgt sofort, oft bevor der neue Thread tatsächlich gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="df04c-112">The <xref:System.Threading.Thread.Start%2A> method returns immediately, often before the new thread has actually started.</span></span> <span data-ttu-id="df04c-113">Sie können mit den Eigenschaften <xref:System.Threading.Thread.ThreadState%2A> und <xref:System.Threading.Thread.IsAlive%2A> jederzeit den Status des Threads ermitteln, aber diese Eigenschaften sollten nie zum Synchronisieren der Aktivitäten von Threads verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="df04c-113">You can use the <xref:System.Threading.Thread.ThreadState%2A> and <xref:System.Threading.Thread.IsAlive%2A> properties to determine the state of the thread at any one moment, but these properties should never be used for synchronizing the activities of threads.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="df04c-114">Sobald ein Thread gestartet wird, ist es nicht notwendig, einen Verweis auf das <xref:System.Threading.Thread>-Objekt beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="df04c-114">Once a thread is started, it is not necessary to retain a reference to the <xref:System.Threading.Thread> object.</span></span> <span data-ttu-id="df04c-115">Der Thread wird weiterhin ausgeführt, bis die Threadprozedur endet.</span><span class="sxs-lookup"><span data-stu-id="df04c-115">The thread continues to execute until the thread procedure ends.</span></span>  
  
 <span data-ttu-id="df04c-116">Das folgende Codebeispiel erstellt zwei neue Threads, um Instanz- und statische Methode auf einem anderen Objekt aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="df04c-116">The following code example creates two new threads to call instance and static methods on another object.</span></span>  
  
 [!code-cpp[System.Threading.ThreadStart2#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.ThreadStart2#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source2.cs#2)]
 [!code-vb[System.Threading.ThreadStart2#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source2.vb#2)]  
  
## <a name="passing-data-to-threads"></a><span data-ttu-id="df04c-117">Übergeben von Daten an Threads</span><span class="sxs-lookup"><span data-stu-id="df04c-117">Passing data to threads</span></span>

 <span data-ttu-id="df04c-118">In .NET Framework Version 2.0 bietet der <xref:System.Threading.ParameterizedThreadStart>-Delegat eine einfache Möglichkeit, ein Objekt mit Daten an einen Thread zu übergeben, wenn Sie die <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>-Methodenüberladung aufrufen.</span><span class="sxs-lookup"><span data-stu-id="df04c-118">In the .NET Framework version 2.0, the <xref:System.Threading.ParameterizedThreadStart> delegate provides an easy way to pass an object containing data to a thread when you call the <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> method overload.</span></span> <span data-ttu-id="df04c-119">Ein Codebeispiel finden Sie unter <xref:System.Threading.ParameterizedThreadStart>.</span><span class="sxs-lookup"><span data-stu-id="df04c-119">See <xref:System.Threading.ParameterizedThreadStart> for a code example.</span></span>  
  
 <span data-ttu-id="df04c-120">Die Verwendung des <xref:System.Threading.ParameterizedThreadStart>-Delegaten ist keine typsichere Möglichkeit zur Übergabe von Daten, da die <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>-Methodenüberladung jedes Objekt akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="df04c-120">Using the <xref:System.Threading.ParameterizedThreadStart> delegate is not a type-safe way to pass data, because the <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> method overload accepts any object.</span></span> <span data-ttu-id="df04c-121">Eine Alternative ist, die Threadprozedur und die Daten in eine Hilfsklasse zu kapseln und die Threadprozedur mit dem <xref:System.Threading.ThreadStart>-Delegaten auszuführen.</span><span class="sxs-lookup"><span data-stu-id="df04c-121">An alternative is to encapsulate the thread procedure and the data in a helper class and use the <xref:System.Threading.ThreadStart> delegate to execute the thread procedure.</span></span> <span data-ttu-id="df04c-122">Diese Prozedur wird im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="df04c-122">The following example demonstrates this technique:</span></span>

 [!code-cpp[System.Threading.ThreadStart2#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source3.cpp#3)]
 [!code-csharp[System.Threading.ThreadStart2#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source3.cs#3)]
 [!code-vb[System.Threading.ThreadStart2#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source3.vb#3)]  

<span data-ttu-id="df04c-123">Weder der Delegat <xref:System.Threading.ThreadStart> noch der Delegat <xref:System.Threading.ParameterizedThreadStart> haben einen Rückgabewert, da es keinen Ort gibt, an den die Daten aus einem asynchronen Aufruf zurückgegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="df04c-123">Neither <xref:System.Threading.ThreadStart> nor <xref:System.Threading.ParameterizedThreadStart> delegate has a return value, because there is no place to return the data from an asynchronous call.</span></span> <span data-ttu-id="df04c-124">Zum Abrufen der Ergebnisse einer Threadmethode können Sie wie im zweiten Codebeispiel gezeigt eine Rückrufmethode verwenden.</span><span class="sxs-lookup"><span data-stu-id="df04c-124">To retrieve the results of a thread method, you can use a callback method, as shown in the next section.</span></span>
  
## <a name="retrieving-data-from-threads-with-callback-methods"></a><span data-ttu-id="df04c-125">Abrufen von Daten aus Threads mit Rückrufmethoden</span><span class="sxs-lookup"><span data-stu-id="df04c-125">Retrieving data from threads with callback methods</span></span>

 <span data-ttu-id="df04c-126">Das folgende Beispiel veranschaulicht eine Rückrufmethode, die Daten von einem anderen Thread abruft.</span><span class="sxs-lookup"><span data-stu-id="df04c-126">The following example demonstrates a callback method that retrieves data from a thread.</span></span> <span data-ttu-id="df04c-127">Der Konstruktor für die Klasse, die die Daten enthält, und auch die Threadmethode akzeptieren einen Delegaten, der die Rückrufmethode darstellt; bevor die Threadmethode endet, ruft sie den Rückrufdelegaten auf.</span><span class="sxs-lookup"><span data-stu-id="df04c-127">The constructor for the class that contains the data and the thread method also accepts a delegate representing the callback method; before the thread method ends, it invokes the callback delegate.</span></span>  
  
 [!code-cpp[System.Threading.ThreadStart2#4](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source4.cpp#4)]
 [!code-csharp[System.Threading.ThreadStart2#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source4.cs#4)]
 [!code-vb[System.Threading.ThreadStart2#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source4.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="df04c-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df04c-128">See also</span></span>

- <xref:System.Threading.Thread>
- <xref:System.Threading.ThreadStart>
- <xref:System.Threading.ParameterizedThreadStart>
- <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>
- [<span data-ttu-id="df04c-129">Threading</span><span class="sxs-lookup"><span data-stu-id="df04c-129">Threading</span></span>](index.md)
- [<span data-ttu-id="df04c-130">Verwenden von Threads und Threading</span><span class="sxs-lookup"><span data-stu-id="df04c-130">Using Threads and Threading</span></span>](using-threads-and-threading.md)
