---
title: Erstellen von Threads und Übergeben von Daten zur Startzeit
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
ms.openlocfilehash: a628cbb4c9ec8e1c9ccd9fd73e72a82ecf2b2836
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138104"
---
# <a name="creating-threads-and-passing-data-at-start-time"></a><span data-ttu-id="1a998-102">Erstellen von Threads und Übergeben von Daten zur Startzeit</span><span class="sxs-lookup"><span data-stu-id="1a998-102">Creating threads and passing data at start time</span></span>

<span data-ttu-id="1a998-103">Wenn ein Betriebssystemprozess erstellt wird, führt das Betriebssystem einen Thread ein, um Code in diesem Prozess auszuführen, einschließlich einer etwaigen ursprünglichen Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="1a998-103">When an operating-system process is created, the operating system injects a thread to execute code in that process, including any original application domain.</span></span> <span data-ttu-id="1a998-104">Ab diesem Punkt können Anwendungsdomänen erstellt und gelöscht werden, ohne dass notwendigerweise Betriebssystemthreads erstellt oder zerstört werden.</span><span class="sxs-lookup"><span data-stu-id="1a998-104">From that point on, application domains can be created and destroyed without any operating system threads necessarily being created or destroyed.</span></span> <span data-ttu-id="1a998-105">Wenn der ausgeführte Code verwalteter Code ist, kann ein <xref:System.Threading.Thread> -Objekt für die Threadausführung in der aktuellen Anwendungsdomäne durch Abrufen der statischen <xref:System.Threading.Thread.CurrentThread%2A>-Eigenschaft des Typs <xref:System.Threading.Thread> abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1a998-105">If the code being executed is managed code, then a <xref:System.Threading.Thread> object for the thread executing in the current application domain can be obtained by retrieving the static <xref:System.Threading.Thread.CurrentThread%2A> property of type <xref:System.Threading.Thread>.</span></span> <span data-ttu-id="1a998-106">Dieses Thema beschreibt die Threaderstellung und erläutert Alternativen für die Übergabe von Daten an die Threadprozedur.</span><span class="sxs-lookup"><span data-stu-id="1a998-106">This topic describes thread creation and discusses alternatives for passing data to the thread procedure.</span></span>  
  
## <a name="creating-a-thread"></a><span data-ttu-id="1a998-107">Erstellen eines Threads</span><span class="sxs-lookup"><span data-stu-id="1a998-107">Creating a thread</span></span>

 <span data-ttu-id="1a998-108">Beim Erstellen eines neuen <xref:System.Threading.Thread>-Objekts wird ein neuer verwalteter Thread erstellt.</span><span class="sxs-lookup"><span data-stu-id="1a998-108">Creating a new <xref:System.Threading.Thread> object creates a new managed thread.</span></span> <span data-ttu-id="1a998-109">Die <xref:System.Threading.Thread>-Klasse verfügt über Konstruktoren, die einen <xref:System.Threading.ThreadStart>- oder <xref:System.Threading.ParameterizedThreadStart>-annehmen; der Delegat umschließt die Methode, die von dem neuen Thread aufgerufen wird, wenn Sie die <xref:System.Threading.Thread.Start%2A>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="1a998-109">The <xref:System.Threading.Thread> class has constructors that take a <xref:System.Threading.ThreadStart> delegate or a <xref:System.Threading.ParameterizedThreadStart> delegate; the delegate wraps the method that is invoked by the new thread when you call the <xref:System.Threading.Thread.Start%2A> method.</span></span> <span data-ttu-id="1a998-110">Bei mehrmaligem Aufrufen von <xref:System.Threading.Thread.Start%2A> wird eine <xref:System.Threading.ThreadStateException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="1a998-110">Calling <xref:System.Threading.Thread.Start%2A> more than once causes a <xref:System.Threading.ThreadStateException> to be thrown.</span></span>  
  
 <span data-ttu-id="1a998-111">Die Rückgabe der <xref:System.Threading.Thread.Start%2A>-Methode erfolgt sofort, oft bevor der neue Thread tatsächlich gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="1a998-111">The <xref:System.Threading.Thread.Start%2A> method returns immediately, often before the new thread has actually started.</span></span> <span data-ttu-id="1a998-112">Sie können mit den Eigenschaften <xref:System.Threading.Thread.ThreadState%2A> und <xref:System.Threading.Thread.IsAlive%2A> jederzeit den Status des Threads ermitteln, aber diese Eigenschaften sollten nie zum Synchronisieren der Aktivitäten von Threads verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1a998-112">You can use the <xref:System.Threading.Thread.ThreadState%2A> and <xref:System.Threading.Thread.IsAlive%2A> properties to determine the state of the thread at any one moment, but these properties should never be used for synchronizing the activities of threads.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1a998-113">Sobald ein Thread gestartet wird, ist es nicht notwendig, einen Verweis auf das <xref:System.Threading.Thread>-Objekt beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="1a998-113">Once a thread is started, it is not necessary to retain a reference to the <xref:System.Threading.Thread> object.</span></span> <span data-ttu-id="1a998-114">Der Thread wird weiterhin ausgeführt, bis die Threadprozedur endet.</span><span class="sxs-lookup"><span data-stu-id="1a998-114">The thread continues to execute until the thread procedure ends.</span></span>  
  
 <span data-ttu-id="1a998-115">Das folgende Codebeispiel erstellt zwei neue Threads, um Instanz- und statische Methode auf einem anderen Objekt aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="1a998-115">The following code example creates two new threads to call instance and static methods on another object.</span></span>  
  
 [!code-cpp[System.Threading.ThreadStart2#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.ThreadStart2#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source2.cs#2)]
 [!code-vb[System.Threading.ThreadStart2#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source2.vb#2)]  
  
## <a name="passing-data-to-threads"></a><span data-ttu-id="1a998-116">Übergeben von Daten an Threads</span><span class="sxs-lookup"><span data-stu-id="1a998-116">Passing data to threads</span></span>

 <span data-ttu-id="1a998-117">In .NET Framework Version 2.0 bietet der <xref:System.Threading.ParameterizedThreadStart>-Delegat eine einfache Möglichkeit, ein Objekt mit Daten an einen Thread zu übergeben, wenn Sie die <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>-Methodenüberladung aufrufen.</span><span class="sxs-lookup"><span data-stu-id="1a998-117">In the .NET Framework version 2.0, the <xref:System.Threading.ParameterizedThreadStart> delegate provides an easy way to pass an object containing data to a thread when you call the <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> method overload.</span></span> <span data-ttu-id="1a998-118">Ein Codebeispiel finden Sie unter <xref:System.Threading.ParameterizedThreadStart>.</span><span class="sxs-lookup"><span data-stu-id="1a998-118">See <xref:System.Threading.ParameterizedThreadStart> for a code example.</span></span>  
  
 <span data-ttu-id="1a998-119">Die Verwendung des <xref:System.Threading.ParameterizedThreadStart>-Delegaten ist keine typsichere Möglichkeit zur Übergabe von Daten, da die <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>-Methodenüberladung jedes Objekt akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="1a998-119">Using the <xref:System.Threading.ParameterizedThreadStart> delegate is not a type-safe way to pass data, because the <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> method overload accepts any object.</span></span> <span data-ttu-id="1a998-120">Eine Alternative ist, die Threadprozedur und die Daten in eine Hilfsklasse zu kapseln und die Threadprozedur mit dem <xref:System.Threading.ThreadStart>-Delegaten auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1a998-120">An alternative is to encapsulate the thread procedure and the data in a helper class and use the <xref:System.Threading.ThreadStart> delegate to execute the thread procedure.</span></span> <span data-ttu-id="1a998-121">Diese Prozedur wird im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="1a998-121">The following example demonstrates this technique:</span></span>

 [!code-cpp[System.Threading.ThreadStart2#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source3.cpp#3)]
 [!code-csharp[System.Threading.ThreadStart2#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source3.cs#3)]
 [!code-vb[System.Threading.ThreadStart2#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source3.vb#3)]  

<span data-ttu-id="1a998-122">Weder der Delegat <xref:System.Threading.ThreadStart> noch der Delegat <xref:System.Threading.ParameterizedThreadStart> haben einen Rückgabewert, da es keinen Ort gibt, an den die Daten aus einem asynchronen Aufruf zurückgegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="1a998-122">Neither <xref:System.Threading.ThreadStart> nor <xref:System.Threading.ParameterizedThreadStart> delegate has a return value, because there is no place to return the data from an asynchronous call.</span></span> <span data-ttu-id="1a998-123">Zum Abrufen der Ergebnisse einer Threadmethode können Sie wie im zweiten Codebeispiel gezeigt eine Rückrufmethode verwenden.</span><span class="sxs-lookup"><span data-stu-id="1a998-123">To retrieve the results of a thread method, you can use a callback method, as shown in the next section.</span></span>
  
## <a name="retrieving-data-from-threads-with-callback-methods"></a><span data-ttu-id="1a998-124">Abrufen von Daten aus Threads mit Rückrufmethoden</span><span class="sxs-lookup"><span data-stu-id="1a998-124">Retrieving data from threads with callback methods</span></span>

 <span data-ttu-id="1a998-125">Das folgende Beispiel veranschaulicht eine Rückrufmethode, die Daten von einem anderen Thread abruft.</span><span class="sxs-lookup"><span data-stu-id="1a998-125">The following example demonstrates a callback method that retrieves data from a thread.</span></span> <span data-ttu-id="1a998-126">Der Konstruktor für die Klasse, die die Daten enthält, und auch die Threadmethode akzeptieren einen Delegaten, der die Rückrufmethode darstellt; bevor die Threadmethode endet, ruft sie den Rückrufdelegaten auf.</span><span class="sxs-lookup"><span data-stu-id="1a998-126">The constructor for the class that contains the data and the thread method also accepts a delegate representing the callback method; before the thread method ends, it invokes the callback delegate.</span></span>  
  
 [!code-cpp[System.Threading.ThreadStart2#4](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source4.cpp#4)]
 [!code-csharp[System.Threading.ThreadStart2#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source4.cs#4)]
 [!code-vb[System.Threading.ThreadStart2#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source4.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="1a998-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1a998-127">See also</span></span>

- <xref:System.Threading.Thread>
- <xref:System.Threading.ThreadStart>
- <xref:System.Threading.ParameterizedThreadStart>
- <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>
- [<span data-ttu-id="1a998-128">Threading</span><span class="sxs-lookup"><span data-stu-id="1a998-128">Threading</span></span>](index.md)
- [<span data-ttu-id="1a998-129">Verwenden von Threads und Threading</span><span class="sxs-lookup"><span data-stu-id="1a998-129">Using Threads and Threading</span></span>](using-threads-and-threading.md)
