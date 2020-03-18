---
title: 'Gewusst wie: Implementieren eines Anbieters'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- observer design pattern [.NET Framework], implementing providers
- providers [.NET Framework], in observer design pattern
- observables [.NET Framework], in observer design pattern
ms.assetid: 790b5d8b-d546-40a6-beeb-151b574e5ee5
ms.openlocfilehash: f5bb3cda0caa39ba3fd094b80e0b769a4bfc1f85
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73141552"
---
# <a name="how-to-implement-a-provider"></a>Gewusst wie: Implementieren eines Anbieters
Das Entwurfsmuster „Observer“ erfordert eine Trennung zwischen einem Anbieter, der Daten überwacht und Benachrichtigungen sendet, und mindestens einem Beobachter, der Benachrichtigungen (Rückrufe) vom Anbieter empfängt. In diesem Thema wird das Erstellen eines Anbieters behandelt. In dem verwandten Thema [Gewusst wie: Implementieren eines Observers](../../../docs/standard/events/how-to-implement-an-observer.md) wird erläutert, wie ein Observer erstellt wird.  
  
### <a name="to-create-a-provider"></a>So erstellen Sie einen Anbieter  
  
1. Definieren Sie die Daten, die vom Anbieter an Observer gesendet werden. Obwohl nur der Anbieter und die an Observer gesendeten Daten einen einzelnen Typ aufweisen können, werden sie in der Regel von unterschiedlichen Typen dargestellt. Beispiel: In einer Anwendung zur Temperaturüberwachung definiert die `Temperature`-Struktur die Daten, die der Anbieter (dargestellt durch die im nächsten Schritt definierte `TemperatureMonitor`-Klasse) überwacht, und die abonnierten Observer.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/data.cs#1)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/data.vb#1)]  
  
2. Definieren Sie den Datenanbieter, der einen Typ zur Implementierung der <xref:System.IObservable%601?displayProperty=nameWithType>-Schnittstelle aufweist. Das generische Typargument des Anbieters ist der Typ, den der Anbieter an Observer sendet. Das folgende Beispiel definiert eine `TemperatureMonitor`-Klasse, die eine erstellte <xref:System.IObservable%601?displayProperty=nameWithType>-Implementierung mit einem generischen Typargument von `Temperature` darstellt.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#2)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#2)]  
  
3. Stellen Sie fest, wie der Anbieter Verweise auf Observer speichert, damit jeder Observer ggf. benachrichtigt werden kann. In den meisten Fällen wird hierfür ein Auflistungsobjekt wie etwa ein generisches <xref:System.Collections.Generic.List%601>-Objekt verwendet. Das folgende Beispiel definiert ein privates <xref:System.Collections.Generic.List%601>-Objekt, das im Klassenkonstruktor `TemperatureMonitor` instanziiert wird.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#3)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#3)]  
  
4. Definieren Sie eine <xref:System.IDisposable>-Implementierung, die der Anbieter an Abonnenten zurückgeben kann, sodass diese jederzeit den Empfang von Benachrichtigungen beenden können. Im folgenden Beispiel wird eine geschachtelte `Unsubscriber`-Klasse definiert, der bei Instanziierung der Klasse ein Verweis auf die Auflistung der Abonnenten und auf den Abonnenten übergeben wird. Durch diesen Code kann der Abonnent die <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>-Implementierung des Objekts aufrufen, damit es selbst aus der Abonnentenauflistung entfernt wird.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#4)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#4)]  
  
5. Implementieren Sie die <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType>-Methode. Der Methode wird ein Verweis auf die <xref:System.IObserver%601?displayProperty=nameWithType>-Schnittstelle übergeben, und sie sollte im Objekt gespeichert werden, das hierfür in Schritt 3 entworfen wurde. Die Methode sollte dann die in Schritt 4 entwickelte <xref:System.IDisposable>-Implementierung zurückgeben. Im folgenden Beispiel wird die Implementierung der <xref:System.IObservable%601.Subscribe%2A>-Methode in der Klasse `TemperatureMonitor` veranschaulicht.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#5)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#5)]  
  
6. Benachrichtigen Sie ggf. Observer, indem Sie ihre <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>-, <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>- und <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>-Implementierungen aufrufen. In einigen Fällen kann ein Anbieter beim Auftreten eines Fehlers nicht die <xref:System.IObserver%601.OnError%2A>-Methode aufrufen. Beispielsweise simuliert die folgende `GetTemperature`-Methode einen Monitor, der alle fünf Sekunden Temperaturdaten liest und Observer benachrichtigt, wenn sich die Temperatur seit dem letzten Lesevorgang um mindestens 0,1 Grad geändert hat. Wenn das Gerät keine Temperatur meldet (d.h., wenn der Wert null ist), werden Observer durch den Anbieter darüber benachrichtigt, dass die Übertragung abgeschlossen ist. Beachten Sie, dass bei der <xref:System.IObserver%601.OnCompleted%2A>-Methode nicht nur die `GetTemperature`-Methode der einzelnen Observer aufgerufen wird, sondern auch die <xref:System.Collections.Generic.List%601>-Auflistung gelöscht wird. Dabei ruft der Anbieter nicht die <xref:System.IObserver%601.OnError%2A>-Methode der jeweiligen Observer auf.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#6)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#6)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel enthält den vollständigen Quellcode, um eine <xref:System.IObservable%601>-Implementierung für eine Anwendung zur Temperaturüberwachung zu definieren. Er enthält die `Temperature`-Struktur, die die an Observer gesendeten Daten umfasst, und die `TemperatureMonitor`-Klasse, die die <xref:System.IObservable%601>-Implementierung darstellt.  
  
 [!code-csharp[Conceptual.ObserverDesign.HowTo#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#7)]
 [!code-vb[Conceptual.ObserverDesign.HowTo#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#7)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.IObservable%601>
- [Beobachterentwurfsmuster](../../../docs/standard/events/observer-design-pattern.md)
- [Gewusst wie: Implementieren eines Observers](../../../docs/standard/events/how-to-implement-an-observer.md)
- [Empfohlene Vorgehensweisen für Beobachterentwurfsmuster](../../../docs/standard/events/observer-design-pattern-best-practices.md)
