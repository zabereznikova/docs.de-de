---
title: Timer
description: Erfahren Sie, welche .NET-Timer in einer Multithreadumgebung verwendet werden können.
ms.date: 07/03/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [.NET Framework], timers
- timers, about timers
ms.assetid: 7091500d-be18-499b-a942-95366ce185e5
author: pkulikov
ms.openlocfilehash: d7d1fa13b02fe7425fa9b4cb81ba20297a23fe4b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128949"
---
# <a name="timers"></a><span data-ttu-id="93cbd-103">Timer</span><span class="sxs-lookup"><span data-stu-id="93cbd-103">Timers</span></span>

<span data-ttu-id="93cbd-104">.NET stellt zwei Timer zur Verfügung, die in einer Multithreadumgebung verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="93cbd-104">.NET provides two timers to use in a multithreaded environment:</span></span>

- <span data-ttu-id="93cbd-105"><xref:System.Threading.Timer?displayProperty=nameWithType>, der eine einmalige Callbackmethode in regelmäßigen Intervallen für einen <xref:System.Threading.ThreadPool>-Thread ausführt.</span><span class="sxs-lookup"><span data-stu-id="93cbd-105"><xref:System.Threading.Timer?displayProperty=nameWithType>, which executes a single callback method on a <xref:System.Threading.ThreadPool> thread at regular intervals.</span></span>
- <span data-ttu-id="93cbd-106"><xref:System.Timers.Timer?displayProperty=nameWithType>, der standardmäßig in regelmäßigen Intervallen ein Ereignis in einem <xref:System.Threading.ThreadPool>-Thread auslöst.</span><span class="sxs-lookup"><span data-stu-id="93cbd-106"><xref:System.Timers.Timer?displayProperty=nameWithType>, which by default raises an event on a <xref:System.Threading.ThreadPool> thread at regular intervals.</span></span>

> [!NOTE]
> <span data-ttu-id="93cbd-107">Einige .NET-Implementierungen können zusätzliche Timer enthalten:</span><span class="sxs-lookup"><span data-stu-id="93cbd-107">Some .NET implementations may include additional timers:</span></span>
>
> - <span data-ttu-id="93cbd-108"><xref:System.Windows.Forms.Timer?displayProperty=nameWithType>: eine Windows Forms-Komponente, die in regelmäßigen Abständen ein Ereignis auslöst.</span><span class="sxs-lookup"><span data-stu-id="93cbd-108"><xref:System.Windows.Forms.Timer?displayProperty=nameWithType>: a Windows Forms component that fires an event at regular intervals.</span></span> <span data-ttu-id="93cbd-109">Die Komponente besitzt keine Benutzeroberfläche und wurde für die Verwendung in einer Singlethreadumgebung entwickelt.</span><span class="sxs-lookup"><span data-stu-id="93cbd-109">The component has no user interface and is designed for use in a single-threaded environment.</span></span>  
> - <span data-ttu-id="93cbd-110"><xref:System.Web.UI.Timer?displayProperty=nameWithType>: eine ASP.NET-Komponente, die asynchrone oder synchrone Webseitenpostbacks in regelmäßigen Intervallen ausführt.</span><span class="sxs-lookup"><span data-stu-id="93cbd-110"><xref:System.Web.UI.Timer?displayProperty=nameWithType>: an ASP.NET component that performs asynchronous or synchronous web page postbacks at a regular interval.</span></span>
> - <span data-ttu-id="93cbd-111"><xref:System.Windows.Threading.DispatcherTimer?displayProperty=nameWithType>: ein Timer, der in die <xref:System.Windows.Threading.Dispatcher>-Warteschlange integriert ist. Diese wird in einem festgelegten Zeitintervall und mit einer festgelegten Priorität verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="93cbd-111"><xref:System.Windows.Threading.DispatcherTimer?displayProperty=nameWithType>: a timer that is integrated into the <xref:System.Windows.Threading.Dispatcher> queue which is processed at a specified interval of time and at a specified priority.</span></span>

## <a name="the-systemthreadingtimer-class"></a><span data-ttu-id="93cbd-112">Die System.Threading.Timer-Klasse</span><span class="sxs-lookup"><span data-stu-id="93cbd-112">The System.Threading.Timer class</span></span>

<span data-ttu-id="93cbd-113">Mithilfe der <xref:System.Threading.Timer?displayProperty=nameWithType>-Klasse können Sie einen Delegaten kontinuierlich in bestimmten Zeitintervallen aufrufen.</span><span class="sxs-lookup"><span data-stu-id="93cbd-113">The <xref:System.Threading.Timer?displayProperty=nameWithType> class enables you to continuously call a delegate at specified time intervals.</span></span> <span data-ttu-id="93cbd-114">Sie können diese Klasse ebenfalls verwenden, um einen einzelnen Aufruf eines Delegaten in einem bestimmten Zeitintervall zu planen.</span><span class="sxs-lookup"><span data-stu-id="93cbd-114">You also can use this class to schedule a single call to a delegate in a specified time interval.</span></span> <span data-ttu-id="93cbd-115">Der Delegat wird in einem <xref:System.Threading.ThreadPool>-Thread ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="93cbd-115">The delegate is executed on a <xref:System.Threading.ThreadPool> thread.</span></span>

<span data-ttu-id="93cbd-116">Wenn Sie ein <xref:System.Threading.Timer?displayProperty=nameWithType>-Objekt erstellen, geben Sie einen <xref:System.Threading.TimerCallback>-Delegaten an, der die Callbackmethode definiert, ein optionales Zustandsobjekt, das an die Callbackmethode übergeben wird, die Verzögerung vor dem ersten Aufruf der Callbackmethode und das Zeitintervall zwischen den Aufrufen der Callbackmethode.</span><span class="sxs-lookup"><span data-stu-id="93cbd-116">When you create a <xref:System.Threading.Timer?displayProperty=nameWithType> object, you specify a <xref:System.Threading.TimerCallback> delegate that defines the callback method, an optional state object that is passed to the callback, the amount of time to delay before the first invocation of the callback, and the time interval between callback invocations.</span></span> <span data-ttu-id="93cbd-117">Wenn Sie einen anstehenden Timer löschen möchten, rufen Sie die <xref:System.Threading.Timer.Dispose%2A?displayProperty=nameWithType>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="93cbd-117">To cancel a pending timer, call the <xref:System.Threading.Timer.Dispose%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="93cbd-118">Im folgenden Beispiel wird ein Timer erstellt, der den bereitgestellten Delegaten zum ersten Mal nach einer Sekunde (1000 Millisekunden) und dann alle zwei Sekunden aufruft.</span><span class="sxs-lookup"><span data-stu-id="93cbd-118">The following example creates a timer that calls the provided delegate for the first time after one second (1000 milliseconds) and then calls it every two seconds.</span></span> <span data-ttu-id="93cbd-119">Das Zustandsobjekt im Beispiel wird verwendet, um die Häufigkeit der Aufrufe des Delegaten zu zählen.</span><span class="sxs-lookup"><span data-stu-id="93cbd-119">The state object in the example is used to count how many times the delegate is called.</span></span> <span data-ttu-id="93cbd-120">Der Timer wird beendet, wenn der Delegat mindestens zehnmal aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="93cbd-120">The timer is stopped when the delegate has been called at least 10 times.</span></span>

[!code-cpp[System.Threading.Timer#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.Timer/CPP/source2.cpp#2)]
[!code-csharp[System.Threading.Timer#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.Timer/CS/source2.cs#2)]
[!code-vb[System.Threading.Timer#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.Timer/VB/source2.vb#2)]

<span data-ttu-id="93cbd-121">Weitere Informationen und Beispiele finden Sie unter <xref:System.Threading.Timer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="93cbd-121">For more information and examples, see <xref:System.Threading.Timer?displayProperty=nameWithType>.</span></span>

## <a name="the-systemtimerstimer-class"></a><span data-ttu-id="93cbd-122">Die System.Timers.Timer-Klasse</span><span class="sxs-lookup"><span data-stu-id="93cbd-122">The System.Timers.Timer class</span></span>

<span data-ttu-id="93cbd-123">Ein weiterer Timer, der in einer Multithreadumgebung verwendet werden kann, ist <xref:System.Timers.Timer?displayProperty=nameWithType>. Dieser löst standardmäßig ein Ereignis in einem <xref:System.Threading.ThreadPool>-Thread aus.</span><span class="sxs-lookup"><span data-stu-id="93cbd-123">Another timer that can be used in a multithreaded environment is <xref:System.Timers.Timer?displayProperty=nameWithType> that by default raises an event on a <xref:System.Threading.ThreadPool> thread.</span></span>

<span data-ttu-id="93cbd-124">Wenn Sie ein <xref:System.Timers.Timer?displayProperty=nameWithType>-Objekt erstellen, können Sie das Zeitintervall angeben, in dem ein <xref:System.Timers.Timer.Elapsed>-Ereignis ausgelöst werden soll.</span><span class="sxs-lookup"><span data-stu-id="93cbd-124">When you create a <xref:System.Timers.Timer?displayProperty=nameWithType> object, you may specify the time interval in which to raise an <xref:System.Timers.Timer.Elapsed> event.</span></span> <span data-ttu-id="93cbd-125">Verwenden Sie die <xref:System.Timers.Timer.Enabled%2A>-Eigenschaft, um anzugeben, ob ein Timer ein <xref:System.Timers.Timer.Elapsed>-Ereignis auslösen soll.</span><span class="sxs-lookup"><span data-stu-id="93cbd-125">Use the <xref:System.Timers.Timer.Enabled%2A> property to indicate if a timer should raise an <xref:System.Timers.Timer.Elapsed> event.</span></span> <span data-ttu-id="93cbd-126">Wenn ein <xref:System.Timers.Timer.Elapsed>-Event nur ausgelöst werden soll, nachdem das angegebene Intervall verstrichen ist, legen Sie <xref:System.Timers.Timer.AutoReset%2A> auf `false` fest.</span><span class="sxs-lookup"><span data-stu-id="93cbd-126">If you need an <xref:System.Timers.Timer.Elapsed> event to be raised only once after the specified interval has elapsed, set the <xref:System.Timers.Timer.AutoReset%2A> to `false`.</span></span> <span data-ttu-id="93cbd-127">Der Standardwert der <xref:System.Timers.Timer.AutoReset%2A>-Eigenschaft ist `true`. Das bedeutet, dass ein <xref:System.Timers.Timer.Elapsed>-Ereignis regelmäßig in dem von der <xref:System.Timers.Timer.Interval%2A>-Eigenschaft angegebenen Intervall ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="93cbd-127">The default value of the <xref:System.Timers.Timer.AutoReset%2A> property is `true`, which means that an <xref:System.Timers.Timer.Elapsed> event is raised regularly at the interval defined by the <xref:System.Timers.Timer.Interval%2A> property.</span></span>

<span data-ttu-id="93cbd-128">Weitere Informationen und Beispiele finden Sie unter <xref:System.Timers.Timer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="93cbd-128">For more information and examples, see <xref:System.Timers.Timer?displayProperty=nameWithType>.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="93cbd-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93cbd-129">See also</span></span>

- <xref:System.Threading.Timer?displayProperty=nameWithType>
- <xref:System.Timers.Timer?displayProperty=nameWithType>
- [<span data-ttu-id="93cbd-130">Threading Objects and Features (Threadingobjekte und -funktionen)</span><span class="sxs-lookup"><span data-stu-id="93cbd-130">Threading Objects and Features</span></span>](threading-objects-and-features.md)
