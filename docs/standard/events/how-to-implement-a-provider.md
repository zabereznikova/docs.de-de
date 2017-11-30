---
title: 'Gewusst wie: Implementieren eines Anbieters'
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
- observer design pattern [.NET Framework], implementing providers
- providers [.NET Framework], in observer design pattern
- observables [.NET Framework], in observer design pattern
ms.assetid: 790b5d8b-d546-40a6-beeb-151b574e5ee5
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b9d8f96de8cb3d13568e755f1d5e885e0474d891
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-a-provider"></a>Gewusst wie: Implementieren eines Anbieters
Das Entwurfsmuster "Beobachter" erfordert eine Trennung zwischen einem Anbieter, der Daten überwacht, und sendet Benachrichtigungen, und mindestens ein Beobachter, die Benachrichtigungen (Rückrufe) vom Anbieter empfängt. In diesem Thema wird erläutert, wie einen Anbieter erstellt wird. Ein verwandtes Thema [Vorgehensweise: Implementieren eines observers](../../../docs/standard/events/how-to-implement-an-observer.md), erläutert, wie ein "Beobachter" zu erstellen.  
  
### <a name="to-create-a-provider"></a>Zum Erstellen eines Anbieters  
  
1.  Definieren Sie die Daten, die der Anbieter an Beobachter gesendet werden. Obwohl nur ein Anbieter und die Daten, die an die Beobachter gesendet werden können, werden sie in der Regel von anderen Typen dargestellt. Z. B. in einer Anwendung zur temperaturüberwachung der `Temperature` Struktur definiert die Daten, die den Anbieter (durch dargestellt die `TemperatureMonitor` Klasse, die im nächsten Schritt definiert) überwacht und welche Observer-Objekte abonnieren.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/data.cs#1)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/data.vb#1)]  
  
2.  Definieren Sie den Datenanbieter, der einen Typ implementiert die <xref:System.IObservable%601?displayProperty=nameWithType> Schnittstelle. Der Anbieter generisches Typargument ist der Typ, den der Anbieter an die Beobachter sendet. Das folgende Beispiel definiert eine `TemperatureMonitor` Klasse, die einer erstellten <xref:System.IObservable%601?displayProperty=nameWithType> -Implementierung mit der ein generisches Typargument `Temperature`.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#2)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#2)]  
  
3.  Bestimmen Sie, wie der Anbieter Verweise auf Observer-Objekte gespeichert werden, damit jede "Beobachter" bei Bedarf benachrichtigt werden kann. In den meisten Fällen ein Auflistungsobjekt, z. B. eine generische <xref:System.Collections.Generic.List%601> Objekt für diesen Zweck verwendet wird. Das folgende Beispiel definiert einen privaten <xref:System.Collections.Generic.List%601> -Objekt, das in instanziiert wird die `TemperatureMonitor` Klassenkonstruktor.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#3)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#3)]  
  
4.  Definieren einer <xref:System.IDisposable> Implementierung, die der Anbieter an Abonnenten zurückgeben kann, sodass sie mit dem Empfang von Benachrichtigungen jederzeit anhalten können. Das folgende Beispiel definiert einen geschachtelten `Unsubscriber` -Klasse, die einen Verweis auf die Auflistung der Abonnenten und auf den Abonnenten übergeben wird, wenn die Klasse instanziiert wird. Dieser Code kann der Abonnent zum Aufrufen des Objekts <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> Implementierung, die selbst von der abonnentenauflistung entfernt.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#4)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#4)]  
  
5.  Implementieren Sie die <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType>-Methode. Die Methode ist ein Verweis auf übergeben der <xref:System.IObserver%601?displayProperty=nameWithType> Schnittstelle, und in dem Objekt, das zu diesem Zweck in Schritt 3 gespeichert werden sollen. Die Methode sollte dann zurückgeben der <xref:System.IDisposable> Implementierung, die in Schritt 4 entwickelt wurden. Das folgende Beispiel zeigt die Implementierung der <xref:System.IObservable%601.Subscribe%2A> Methode in der `TemperatureMonitor` Klasse.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#5)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#5)]  
  
6.  Benachrichtigen Sie Observer-Objekte nach Bedarf durch den Aufruf ihrer <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>, und <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> Implementierungen. In einigen Fällen ein Anbieter kann nicht aufgerufen werden die <xref:System.IObserver%601.OnError%2A> Methode, wenn ein Fehler auftritt. Beispielsweise die folgenden `GetTemperature` -Methode simuliert einen Monitor, der alle fünf Sekunden für Temperaturdaten liest und Beobachter benachrichtigt, wenn die Temperatur seit dem letzten Lesevorgang mindestens.1 allmählich geändert hat. Wenn das Gerät meldet keine Temperatur (d. h., wenn der Wert null ist), benachrichtigt der Anbieter Beobachter, dass die Übertragung abgeschlossen ist. Beachten Sie, dass zusätzlich zum Aufrufen aller Beobachter <xref:System.IObserver%601.OnCompleted%2A> -Methode, die `GetTemperature` -Methode löscht die <xref:System.Collections.Generic.List%601> Auflistung. In diesem Fall wird der Anbieter keine Aufrufe der <xref:System.IObserver%601.OnError%2A> Methode der Beobachter.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#6)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#6)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel enthält den vollständigen Quellcode für die Definition einer <xref:System.IObservable%601> Implementierung für eine Anwendung zur temperaturüberwachung. Es enthält die `Temperature` -Struktur, die die Daten an die Beobachter gesendet werden, und die `TemperatureMonitor` Klasse, die die <xref:System.IObservable%601> Implementierung.  
  
 [!code-csharp[Conceptual.ObserverDesign.HowTo#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#7)]
 [!code-vb[Conceptual.ObserverDesign.HowTo#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#7)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IObservable%601>  
 [Beobachterentwurfsmuster](../../../docs/standard/events/observer-design-pattern.md)  
 [Gewusst wie: Implementieren eines Observers](../../../docs/standard/events/how-to-implement-an-observer.md)  
 [Empfohlene Vorgehensweisen für Beobachterentwurfsmuster](../../../docs/standard/events/observer-design-pattern-best-practices.md)
