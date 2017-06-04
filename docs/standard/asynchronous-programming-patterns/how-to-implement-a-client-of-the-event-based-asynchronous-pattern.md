---
title: "How to: Implement a Client of the Event-based Asynchronous Pattern | Microsoft Docs"
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
  - "Event-based Asynchronous Pattern"
  - "ProgressChangedEventArgs class"
  - "BackgroundWorker component"
  - "events [.NET Framework], asynchronous"
  - "Asynchronous Pattern"
  - "AsyncOperationManager class"
  - "threading [.NET Framework], asynchronous features"
  - "components [.NET Framework], asynchronous"
  - "AsyncOperation class"
  - "threading [Windows Forms], asynchronous features"
  - "AsyncCompletedEventArgs class"
ms.assetid: 21a858c1-3c99-4904-86ee-0d17b49804fa
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# How to: Implement a Client of the Event-based Asynchronous Pattern
Im folgenden Codebeispiel wird die Verwendung einer Komponente veranschaulicht, die der [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) folgt.  Das Formular für dieses Beispiel verwendet die unter [How to: Implement a Component That Supports the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md) beschriebene  `PrimeNumberCalculator` \-Komponente.  
  
 Sofern Sie ein Projekt mit diesem Beispiel ausführen, wird Ihnen das "Primzahlenrechner"\-Formular mit einem Datenblatt und den folgenden zwei Schaltflächen angezeigt: **Neuen Task starten** und **Abbrechen**.  Sie können auf die Schaltfläche **Neuen Task starten** mehrmals hintereinander klicken. Bei jedem Klick wird durch eine asynchrone Operation ein Rechenvorgang gestartet, um zu bestimmen, ob es sich bei einer zufällig generierten Testzahl um eine Primzahl handelt.  Das Formular zeigt in periodischen Abständen Fortschritt und inkrementelle Ergebnisse an.  Jeder Operation wird eine eindeutige Aufgaben\-ID zugewiesen.  Das Ergebnis der Berechnung wird in der **Ergebnis**\-Spalte angezeigt. Wenn die Testzahl keine Primzahl ist, wird sie als **Zusammengesetzt** bezeichnet und deren erster Primfaktor angezeigt.  
  
 Jede ausstehende Operation kann mit der Schaltfläche **Abbrechen** abgebrochen werden.  Es besteht die Möglichkeit der Mehrfachauswahl.  
  
> [!NOTE]
>  Bei den meisten Zahlen handelt es sich nicht um Primzahlen.  Wenn Sie nach mehreren abgeschlossenen Operationen keine Primzahl gefunden haben, starten Sie einfach zusätzliche Tasks, sodass schließlich einige Primzahlen ermittelt werden.  
  
## Beispiel  
 [!code-csharp[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#10)]
 [!code-vb[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#10)]  
  
## Siehe auch  
 <xref:System.ComponentModel.AsyncOperation>   
 <xref:System.ComponentModel.AsyncOperationManager>   
 <xref:System.Windows.Forms.WindowsFormsSynchronizationContext>