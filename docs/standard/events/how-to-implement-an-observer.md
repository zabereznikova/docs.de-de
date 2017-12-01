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
# <a name="how-to-implement-an-observer"></a>Gewusst wie: Implementieren eines Observers
Das Entwurfsmuster "Beobachter" ist eine Trennung zwischen ein Beobachter, der für Benachrichtigungen registriert, und einen Anbieter, den Daten überwacht, und sendet an einen oder mehrere Beobachter Benachrichtigungen erforderlich. In diesem Thema wird erläutert, wie einen Beobachter erstellt wird. Ein verwandtes Thema [Vorgehensweise: Implementieren eines Anbieters](../../../docs/standard/events/how-to-implement-a-provider.md), beschreibt, wie Sie einen Anbieter zu erstellen.  
  
### <a name="to-create-an-observer"></a>So erstellen eine "Beobachter"  
  
1.  Definieren Sie den Beobachter, der ein Typ implementiert die <xref:System.IObserver%601?displayProperty=nameWithType> Schnittstelle. Der folgende Code definiert z. B. einen Typ mit dem Namen `TemperatureReporter` d. h. konstruierte <xref:System.IObserver%601?displayProperty=nameWithType> -Implementierung mit der ein generisches Typargument `Temperature`.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#8)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#8)]  
  
2.  Wenn der Beobachter beenden kann, Empfangen von Benachrichtigungen, bevor der Anbieter ruft seine <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> Implementierung, definieren Sie eine private Variable, die enthalten soll die <xref:System.IDisposable> Implementierung, die der Anbieter zurückgegeben hat <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType> Methode. Sie sollten auch eine Abonnementmethode, die des Anbieters ruft definieren <xref:System.IObservable%601.Subscribe%2A> -Methode und speichert das zurückgegebene <xref:System.IDisposable> Objekt. Der folgende Code definiert z. B. eine private Variable, die mit dem Namen `unsubscriber` und definiert eine `Subscribe` -Methode, die des Anbieters ruft <xref:System.IObservable%601.Subscribe%2A> Methode und weist das zurückgegebene Objekt in der `unsubscriber` Variable.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#9)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#9)]  
  
3.  Definieren Sie eine Methode, die es ermöglicht die Beobachter den Empfang von Benachrichtigungen, bevor der Anbieter Ruft die <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> Implementierung, wenn diese Funktion erforderlich ist. Das folgende Beispiel definiert eine `Unsubscribe` Methode.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#10)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#10)]  
  
4.  Implementierungen der drei Methoden definiert, durch Bereitstellen der <xref:System.IObserver%601> Schnittstelle: <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>, und <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>. Abhängig von dem Anbieter und den Anforderungen der Anwendung die <xref:System.IObserver%601.OnError%2A> und <xref:System.IObserver%601.OnCompleted%2A> Methoden Stub-Implementierungen werden können. Beachten Sie, dass die <xref:System.IObserver%601.OnError%2A> Methode sollte nicht die übergebene verarbeiten <xref:System.Exception> Objekt als eine Ausnahme aus, und die <xref:System.IObserver%601.OnCompleted%2A> Methode ist frei, um den Anbieter Aufrufen <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> Implementierung. Das folgende Beispiel zeigt die <xref:System.IObserver%601> Implementierung der `TemperatureReporter` Klasse.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#11)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#11)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel enthält den vollständigen Quellcode für die `TemperatureReporter` -Klasse, die bietet die <xref:System.IObserver%601> Implementierung für eine Anwendung zur temperaturüberwachung.  
  
 [!code-csharp[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#12)]
 [!code-vb[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#12)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IObserver%601>  
 [Beobachterentwurfsmuster](../../../docs/standard/events/observer-design-pattern.md)  
 [Gewusst wie: Implementieren eines Anbieters](../../../docs/standard/events/how-to-implement-a-provider.md)  
 [Empfohlene Vorgehensweisen für Beobachterentwurfsmuster](../../../docs/standard/events/observer-design-pattern-best-practices.md)
