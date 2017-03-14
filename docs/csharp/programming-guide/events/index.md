---
title: "Ereignisse (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Klassen [C#], Ereignisse"
  - "C#-Sprache, Ereignisse"
  - "Ereignisse [C#]"
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
caps.latest.revision: 43
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 43
---
# Ereignisse (C#-Programmierhandbuch)
Ereignisse aktivieren eine [Klasse](../../../csharp/language-reference/keywords/class.md) oder ein Objekt, um Informationen über Aktionen von Interesse an andere Klassen oder Objekte zu übermitteln. Die Klasse, die das Ereignis sendet \(oder *auslöst*\), wird als *Herausgeber* bezeichnet, und die Klassen, die das Ereignis empfangen \(oder *behandeln*\), werden als *Abonnenten* bezeichnet.  
  
 In einer typischen C\#\-Windows Forms oder Web\-Anwendung abonnieren Sie Ereignisse, die von Steuerelementen wie Schaltflächen und Listenfelder ausgelöst werden. Sie können die [!INCLUDE[csprcs](~/includes/csprcs-md.md)]\-integrierte Entwicklungsumgebung \(IDE\) zum Durchsuchen der Ereignisse verwenden, die ein Steuerelement auslöst, und diejenigen wählen, die Sie behandeln möchten. Die IDE fügt automatisch eine leere Ereignishandlermethode und den Code zum Abonnieren des Ereignisses hinzu. Weitere Informationen finden Sie unter [Gewusst wie: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).  
  
## Übersicht über Ereignisse  
 Ereignisse verfügen über folgende Eigenschaften:  
  
-   Der Herausgeber wird bestimmt, wenn ein Ereignis ausgelöst wird. Die Abonnenten bestimmen, welche Aktion als Reaktion auf das Ereignis ausgeführt wird.  
  
-   Ein Ereignis kann mehrere Abonnenten haben. Ein Abonnent kann mehrere Ereignisse von mehreren Herausgebern behandeln.  
  
-   Ereignisse, die keine Abonnenten haben, werden nie ausgelöst.  
  
-   Ereignisse werden in der Regel verwendet, um Benutzeraktionen wie Mausklicks oder Menüauswahlen in GUI\-Schnittstellen zu signalisieren.  
  
-   Wenn ein Ereignis mehrere Abonnenten hat, werden die Ereignishandler synchron aufgerufen, wenn ein Ereignis ausgelöst wird. Informationen zum asynchronen Aufrufen von Ereignissen finden Sie unter [Calling Synchronous Methods Asynchronously](../Topic/Calling%20Synchronous%20Methods%20Asynchronously.md).  
  
-   In der [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]\-Klassenbibliothek basieren Ereignisse auf dem <xref:System.EventHandler>\-Delegaten und der <xref:System.EventArgs>\-Basisklasse.  
  
## Verwandte Abschnitte  
 Weitere Informationen finden Sie unter:  
  
-   [Gewusst wie: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)  
  
-   [Gewusst wie: Veröffentlichen von Ereignissen, die den .NET Framework\-Richtlinien entsprechen](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md)  
  
-   [Gewusst wie: Auslösen von Basisklassenereignissen in abgeleiteten Klassen](../../../csharp/programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md)  
  
-   [Gewusst wie: Implementieren von Schnittstellenereignissen](../../../csharp/programming-guide/events/how-to-implement-interface-events.md)  
  
-   [Threadsynchronisierung](../Topic/Thread%20Synchronization%20\(C%23%20and%20Visual%20Basic\).md)  
  
-   [Gewusst wie: Verwenden eines Wörterbuchs zum Speichern von Ereignisinstanzen](../../../csharp/programming-guide/events/how-to-use-a-dictionary-to-store-event-instances.md)  
  
-   [Gewusst wie: Implementieren benutzerdefinierter Ereignisaccessoren](../../../csharp/programming-guide/events/how-to-implement-custom-event-accessors.md)  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## Enthaltene Buchkapitel  
 [Delegaten, Ereignisse und Lambda\-Ausdrücke](http://go.microsoft.com/fwlink/?LinkId=195395) im [C\# 3.0 Cookbook, Third Edition: More than 250 solutions for C\# 3.0 programmers](http://go.microsoft.com/fwlink/?LinkId=195369)  
  
 [Delegaten und Ereignisse](http://go.microsoft.com/fwlink/?LinkId=195418) in [Learning C\# 3.0: Master the fundamentals of C\# 3.0](http://go.microsoft.com/fwlink/?LinkId=195412)  
  
## Siehe auch  
 <xref:System.EventHandler>   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Delegaten](../../../csharp/programming-guide/delegates/index.md)   
 [Erstellen von Ereignishandlern in Windows Forms](../Topic/Creating%20Event%20Handlers%20in%20Windows%20Forms.md)   
 [Multithreaded Programming with the Event\-based Asynchronous Pattern](../Topic/Multithreaded%20Programming%20with%20the%20Event-based%20Asynchronous%20Pattern.md)