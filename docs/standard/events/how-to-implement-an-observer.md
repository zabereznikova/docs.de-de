---
title: 'Gewusst wie: Implementieren eines Observers'
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
helpviewer_keywords:
- observers [.NET Framework], observer design pattern
- observer design pattern [.NET Framework], implementing observers
ms.assetid: 8ecfa9f5-b500-473d-bcf0-5652ffb1e53d
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a964bd031f6f8a7fc029b2b209b9693b72e688af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-an-observer"></a><span data-ttu-id="28871-102">Gewusst wie: Implementieren eines Observers</span><span class="sxs-lookup"><span data-stu-id="28871-102">How to: Implement an Observer</span></span>
<span data-ttu-id="28871-103">Das Entwurfsmuster "Beobachter" ist eine Trennung zwischen ein Beobachter, der für Benachrichtigungen registriert, und einen Anbieter, den Daten überwacht, und sendet an einen oder mehrere Beobachter Benachrichtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="28871-103">The observer design pattern requires a division between an observer, which registers for notifications, and a provider, which monitors data and sends notifications to one or more observers.</span></span> <span data-ttu-id="28871-104">In diesem Thema wird erläutert, wie einen Beobachter erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="28871-104">This topic discusses how to create an observer.</span></span> <span data-ttu-id="28871-105">Ein verwandtes Thema [Vorgehensweise: Implementieren eines Anbieters](../../../docs/standard/events/how-to-implement-a-provider.md), beschreibt, wie Sie einen Anbieter zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="28871-105">A related topic, [How to: Implement a Provider](../../../docs/standard/events/how-to-implement-a-provider.md), discusses how to create an provider.</span></span>  
  
### <a name="to-create-an-observer"></a><span data-ttu-id="28871-106">So erstellen eine "Beobachter"</span><span class="sxs-lookup"><span data-stu-id="28871-106">To create an observer</span></span>  
  
1.  <span data-ttu-id="28871-107">Definieren Sie den Beobachter, der ein Typ implementiert die <xref:System.IObserver%601?displayProperty=nameWithType> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="28871-107">Define the observer, which is a type that implements the <xref:System.IObserver%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="28871-108">Der folgende Code definiert z. B. einen Typ mit dem Namen `TemperatureReporter` d. h. konstruierte <xref:System.IObserver%601?displayProperty=nameWithType> -Implementierung mit der ein generisches Typargument `Temperature`.</span><span class="sxs-lookup"><span data-stu-id="28871-108">For example, the following code defines a type named `TemperatureReporter` that is a constructed <xref:System.IObserver%601?displayProperty=nameWithType> implementation with a generic type argument of `Temperature`.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#8)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#8)]  
  
2.  <span data-ttu-id="28871-109">Wenn der Beobachter beenden kann, Empfangen von Benachrichtigungen, bevor der Anbieter ruft seine <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> Implementierung, definieren Sie eine private Variable, die enthalten soll die <xref:System.IDisposable> Implementierung, die der Anbieter zurückgegeben hat <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="28871-109">If the observer can stop receiving notifications before the provider calls its <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> implementation, define a private variable that will hold the <xref:System.IDisposable> implementation returned by the provider's <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="28871-110">Sie sollten auch eine Abonnementmethode, die des Anbieters ruft definieren <xref:System.IObservable%601.Subscribe%2A> -Methode und speichert das zurückgegebene <xref:System.IDisposable> Objekt.</span><span class="sxs-lookup"><span data-stu-id="28871-110">You should also define a subscription method that calls the provider's <xref:System.IObservable%601.Subscribe%2A> method and stores the returned <xref:System.IDisposable> object.</span></span> <span data-ttu-id="28871-111">Der folgende Code definiert z. B. eine private Variable, die mit dem Namen `unsubscriber` und definiert eine `Subscribe` -Methode, die des Anbieters ruft <xref:System.IObservable%601.Subscribe%2A> Methode und weist das zurückgegebene Objekt in der `unsubscriber` Variable.</span><span class="sxs-lookup"><span data-stu-id="28871-111">For example, the following code defines a private variable named `unsubscriber` and defines a `Subscribe` method that calls the provider's <xref:System.IObservable%601.Subscribe%2A> method and assigns the returned object to the `unsubscriber` variable.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#9)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#9)]  
  
3.  <span data-ttu-id="28871-112">Definieren Sie eine Methode, die es ermöglicht die Beobachter den Empfang von Benachrichtigungen, bevor der Anbieter Ruft die <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> Implementierung, wenn diese Funktion erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="28871-112">Define a method that enables the observer to stop receiving notifications before the provider calls its <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> implementation, if this feature is required.</span></span> <span data-ttu-id="28871-113">Das folgende Beispiel definiert eine `Unsubscribe` Methode.</span><span class="sxs-lookup"><span data-stu-id="28871-113">The following example defines an `Unsubscribe` method.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#10)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#10)]  
  
4.  <span data-ttu-id="28871-114">Implementierungen der drei Methoden definiert, durch Bereitstellen der <xref:System.IObserver%601> Schnittstelle: <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>, und <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="28871-114">Provide implementations of the three methods defined by the <xref:System.IObserver%601> interface: <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>, and <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="28871-115">Abhängig von dem Anbieter und den Anforderungen der Anwendung die <xref:System.IObserver%601.OnError%2A> und <xref:System.IObserver%601.OnCompleted%2A> Methoden Stub-Implementierungen werden können.</span><span class="sxs-lookup"><span data-stu-id="28871-115">Depending on the provider and the needs of the application, the <xref:System.IObserver%601.OnError%2A> and <xref:System.IObserver%601.OnCompleted%2A> methods can be stub implementations.</span></span> <span data-ttu-id="28871-116">Beachten Sie, dass die <xref:System.IObserver%601.OnError%2A> Methode sollte nicht die übergebene verarbeiten <xref:System.Exception> Objekt als eine Ausnahme aus, und die <xref:System.IObserver%601.OnCompleted%2A> Methode ist frei, um den Anbieter Aufrufen <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> Implementierung.</span><span class="sxs-lookup"><span data-stu-id="28871-116">Note that the <xref:System.IObserver%601.OnError%2A> method should not handle the passed <xref:System.Exception> object as an exception, and the <xref:System.IObserver%601.OnCompleted%2A> method is free to call the provider's <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="28871-117">Das folgende Beispiel zeigt die <xref:System.IObserver%601> Implementierung der `TemperatureReporter` Klasse.</span><span class="sxs-lookup"><span data-stu-id="28871-117">The following example shows the <xref:System.IObserver%601> implementation of the `TemperatureReporter` class.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#11)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#11)]  
  
## <a name="example"></a><span data-ttu-id="28871-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="28871-118">Example</span></span>  
 <span data-ttu-id="28871-119">Das folgende Beispiel enthält den vollständigen Quellcode für die `TemperatureReporter` -Klasse, die bietet die <xref:System.IObserver%601> Implementierung für eine Anwendung zur temperaturüberwachung.</span><span class="sxs-lookup"><span data-stu-id="28871-119">The following example contains the complete source code for the `TemperatureReporter` class, which provides the <xref:System.IObserver%601> implementation for a temperature monitoring application.</span></span>  
  
 [!code-csharp[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#12)]
 [!code-vb[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="28871-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="28871-120">See Also</span></span>  
 <xref:System.IObserver%601>  
 [<span data-ttu-id="28871-121">Beobachterentwurfsmuster</span><span class="sxs-lookup"><span data-stu-id="28871-121">Observer Design Pattern</span></span>](../../../docs/standard/events/observer-design-pattern.md)  
 [<span data-ttu-id="28871-122">Gewusst wie: Implementieren eines Anbieters</span><span class="sxs-lookup"><span data-stu-id="28871-122">How to: Implement a Provider</span></span>](../../../docs/standard/events/how-to-implement-a-provider.md)  
 [<span data-ttu-id="28871-123">Empfohlene Vorgehensweisen für Beobachterentwurfsmuster</span><span class="sxs-lookup"><span data-stu-id="28871-123">Observer Design Pattern Best Practices</span></span>](../../../docs/standard/events/observer-design-pattern-best-practices.md)
