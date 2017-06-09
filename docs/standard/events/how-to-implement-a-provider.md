---
title: "Gewusst wie: Implementieren eines Anbieters | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Beobachterentwurfsmuster [.NET Framework], Implementieren von Anbietern"
  - "Anbieter [.NET Framework], in Beobachterentwurfsmuster"
  - "Wahrnehmbare Elemente [.NET Framework], in Beobachterentwurfsmuster"
ms.assetid: 790b5d8b-d546-40a6-beeb-151b574e5ee5
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Implementieren eines Anbieters
Das Entwurfsmuster Beobachter erfordert eine Unterteilung in einen Anbieter, der Daten überwacht und Benachrichtigungen sendet, und in einen oder mehrere Beobachter, die Benachrichtigungen \(Rückrufe\) vom Anbieter empfangen.  In diesem Thema wird erläutert, wie ein Anbieter erstellt wird.  Im zugehörigen Thema [Gewusst wie: Implementieren eines Observers](../../../docs/standard/events/how-to-implement-an-observer.md) wird das Erstellen eines Beobachters beschrieben.  
  
### So erstellen Sie einen Anbieter  
  
1.  Definieren Sie die Daten, die der Anbieter an Beobachter senden soll.  Obwohl der Anbieter und die Daten, die an Beobachter gesendet werden, ein einzelner Typ sein können, werden sie im Allgemeinen durch verschiedene Typen dargestellt.  In einer Anwendung zur Temperaturüberwachung definiert die `Temperature`\-Struktur z. B. die Daten, die der Anbieter \(der durch die im nächsten Schritt definierte `TemperatureMonitor`\-Klasse dargestellt wird\) überwacht und für die sich Beobachter registrieren können.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/data.cs#1)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/data.vb#1)]  
  
2.  Definieren Sie den Datenanbieter. Dies ist ein Typ, der die <xref:System.IObservable%601?displayProperty=fullName>\-Schnittstelle implementiert.  Das generische Typargument des Anbieters ist der Typ, den der Anbieter an Beobachter sendet.  Im folgenden Beispiel wird eine Klasse `TemperatureMonitor`\-Klasse erstellt, die eine erzeugte <xref:System.IObservable%601?displayProperty=fullName>\-Implementierung mit dem generischen Typargument `Temperature` ist.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#2)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#2)]  
  
3.  Legen Sie fest, wie der Anbieter Verweise auf Beobachter speichert, sodass jeder Beobachter bei Bedarf benachrichtigt werden kann.  Am häufigsten wird ein Auflistungsobjekt, z. B. ein generisches <xref:System.Collections.Generic.List%601>\-Objekt, für diesen Zweck verwendet.  Im folgenden Beispiel wird ein privates <xref:System.Collections.Generic.List%601>\-Objekt definiert, das im `TemperatureMonitor`\-Klassenkonstruktor instanziiert wird.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#3)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#3)]  
  
4.  Definieren Sie eine <xref:System.IDisposable>\-Implementierung, die der Anbieter an Abonnenten zurückgeben kann, damit diese den Empfang von Benachrichtigungen jederzeit beenden können.  Im folgenden Beispiel wird eine geschachtelte `Unsubscriber`\-Klasse definiert, an die ein Verweis auf die Auflistung der Abonnenten und auf den Abonnenten übergeben wird, sobald die Klasse instanziiert wird.  Dieser Code ermöglicht es dem Abonnenten, die <xref:System.IDisposable.Dispose%2A?displayProperty=fullName>\-Implementierung des Objekts aufzurufen, um sich selbst aus der Auflistung der Abonnenten zu entfernen.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#4)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#4)]  
  
5.  Implementieren Sie die <xref:System.IObservable%601.Subscribe%2A?displayProperty=fullName>\-Methode.  An die Methode wird ein Verweis auf die <xref:System.IObserver%601?displayProperty=fullName>\-Schnittstelle übergeben. Sie sollte in dem Objekt gespeichert werden, das in Schritt 3 für diesen Zweck entworfen wurde.  Anschließend muss die Methode die <xref:System.IDisposable>\-Implementierung aus Schritt 4 zurückgeben.  Im folgenden Beispiel wird die Implementierung der <xref:System.IObservable%601.Subscribe%2A>\-Methode in der `TemperatureMonitor`\-Klasse veranschaulicht.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#5)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#5)]  
  
6.  Benachrichtigen Sie Beobachter entsprechend, indem Sie ihre Implementierungen von <xref:System.IObserver%601.OnNext%2A?displayProperty=fullName>, <xref:System.IObserver%601.OnError%2A?displayProperty=fullName> und <xref:System.IObserver%601.OnCompleted%2A?displayProperty=fullName> aufrufen.  In einigen Fällen bleibt im Anbieter nach einem Fehler der Aufruf der <xref:System.IObserver%601.OnError%2A>\-Methode aus.  Zum Beispiel simuliert die folgende `GetTemperature`\-Methode eine Überwachung, die alle 5 Sekunden Temperaturdaten liest und Beobachter benachrichtigt, wenn sich die Temperatur seit dem letzten Lesevorgang um mindestens 0,1 Grad geändert hat.  Wenn das Gerät keine Temperatur meldet \(das heißt, wenn der Wert NULL ist\), benachrichtigt der Anbieter die Beobachter, dass die Übertragung abgeschlossen ist.  Beachten Sie, dass zusätzlich zum Aufruf der <xref:System.IObserver%601.OnCompleted%2A>\-Methode jedes Beobachters mit der `GetTemperature`\-Methode die <xref:System.Collections.Generic.List%601>\-Auflistung gelöscht wird.  In diesem Fall führt der Anbieter keine Aufrufe der <xref:System.IObserver%601.OnError%2A>\-Methode der Beobachter aus.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#6)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#6)]  
  
## Beispiel  
 Das folgende Beispiel enthält den vollständigen Quellcode zum Definieren einer <xref:System.IObservable%601>\-Implementierung für eine Anwendung zur Temperaturüberwachung.  Es umfasst die `Temperature`\-Struktur, die die Daten darstellt, die an die Beobachter gesendet werden, und die `TemperatureMonitor`\-Klasse, die die <xref:System.IObservable%601>\-Implementierung darstellt.  
  
 [!code-csharp[Conceptual.ObserverDesign.HowTo#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#7)]
 [!code-vb[Conceptual.ObserverDesign.HowTo#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#7)]  
  
## Siehe auch  
 <xref:System.IObservable%601>   
 [Beobachterentwurfsmuster](../../../docs/standard/events/observer-design-pattern.md)   
 [Gewusst wie: Implementieren eines Observers](../../../docs/standard/events/how-to-implement-an-observer.md)   
 [Empfohlene Vorgehensweisen für Beobachterentwurfsmuster](../../../docs/standard/events/observer-design-pattern-best-practices.md)