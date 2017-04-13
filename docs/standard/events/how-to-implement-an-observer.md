---
title: "Gewusst wie: Implementieren eines Observers | Microsoft Docs"
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
  - "Observer [.NET Framework], Observerentwurfsmuster"
  - "Observerentwurfsmuster [.NET Framework], Implementieren von Observern"
ms.assetid: 8ecfa9f5-b500-473d-bcf0-5652ffb1e53d
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Implementieren eines Observers
Das Entwurfsmuster Beobachter erfordert eine Unterteilung in einen Beobachter, der sich für Benachrichtigungen registriert, und einen Anbieter, der Daten überwacht und Benachrichtigungen an einen oder mehrere Beobachter sendet.  In diesem Thema wird erläutert, wie ein Beobachter erstellt wird.  Im zugehörigen Thema [Gewusst wie: Implementieren eines Anbieters](../../../docs/standard/events/how-to-implement-a-provider.md) wird das Erstellen eines Anbieters beschrieben.  
  
### So erstellen Sie einen Beobachter  
  
1.  Definieren Sie den Beobachter. Dies ist ein Typ, der die <xref:System.IObserver%601?displayProperty=fullName>\-Schnittstelle implementiert.  Der folgende Code definiert beispielsweise einen Typ mit dem Namen `TemperatureReporter`, bei dem es sich um eine erstellte <xref:System.IObserver%601?displayProperty=fullName>\-Implementierung mit dem generischem Typargument `Temperature` handelt.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#8)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#8)]  
  
2.  Wenn der Beobachter den Empfang von Benachrichtigungen einstellen kann, bevor der Anbieter die zugehörige <xref:System.IObserver%601.OnCompleted%2A?displayProperty=fullName>\-Implementierung aufruft, definieren Sie eine private Variable, die die <xref:System.IDisposable>\-Implementierung enthält, die von der <xref:System.IObservable%601.Subscribe%2A?displayProperty=fullName>\-Methode des Anbieters zurückgegeben wird.  Definieren Sie zusätzlich eine Abonnementmethode, die die <xref:System.IObservable%601.Subscribe%2A>\-Methode des Anbieters aufruft und das zurückgegebene <xref:System.IDisposable>\-Objekt speichert.  Der folgende Code definiert z. B. eine private Variable mit dem Namen `unsubscriber` und definiert eine `Subscribe`\-Methode, die die <xref:System.IObservable%601.Subscribe%2A>\-Methode des Anbieters aufruft und das zurückgegebene Objekt der `unsubscriber`\-Variablen zuweist.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#9)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#9)]  
  
3.  Definieren Sie eine Methode, durch die der Beobachter den Empfang von Benachrichtigungen beenden kann, bevor der Anbieter die zugehörige <xref:System.IObserver%601.OnCompleted%2A?displayProperty=fullName>\-Implementierung aufgerufen hat, falls diese Funktion benötigt wird.  Im folgenden Beispiel wird eine `Unsubscribe`\-Methode definiert.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#10)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#10)]  
  
4.  Stellen Sie Implementierungen der folgenden drei Methoden bereit, die durch die <xref:System.IObserver%601>\-Schnittstelle definiert werden: <xref:System.IObserver%601.OnNext%2A?displayProperty=fullName>, <xref:System.IObserver%601.OnError%2A?displayProperty=fullName> und <xref:System.IObserver%601.OnCompleted%2A?displayProperty=fullName>.  Je nach Anforderungen der Anwendung und des Anbieters können die <xref:System.IObserver%601.OnError%2A>\-Methode und die <xref:System.IObserver%601.OnCompleted%2A>\-Methode können Stubimplementierungen sein.  Beachten Sie, dass die <xref:System.IObserver%601.OnError%2A>\-Methode das übergebene <xref:System.Exception>\-Objekt nicht als Ausnahme behandeln sollte. Ein Aufruf der <xref:System.IDisposable.Dispose%2A?displayProperty=fullName>\-Implementierung des Anbieters ist in der <xref:System.IObserver%601.OnCompleted%2A>\-Methode jederzeit möglich.  Im folgenden Beispiel wird die <xref:System.IObserver%601>\-Implementierung der `TemperatureReporter`\-Klasse veranschaulicht.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#11)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#11)]  
  
## Beispiel  
 Das folgende Beispiel enthält den vollständigen Quellcode für die `TemperatureReporter`\-Klasse, die die <xref:System.IObserver%601>\-Implementierung für eine Anwendung zur Temperaturüberwachung bereitstellt.  
  
 [!code-csharp[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#12)]
 [!code-vb[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#12)]  
  
## Siehe auch  
 <xref:System.IObserver%601>   
 [Beobachterentwurfsmuster](../../../docs/standard/events/observer-design-pattern.md)   
 [Gewusst wie: Implementieren eines Anbieters](../../../docs/standard/events/how-to-implement-a-provider.md)   
 [Empfohlene Vorgehensweisen für Beobachterentwurfsmuster](../../../docs/standard/events/observer-design-pattern-best-practices.md)