---
title: Ereignisse (C#-Programmierhandbuch)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- classes [C#], events
- C# language, events
- events [C#]
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
caps.latest.revision: 43
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c4ac62a38698f0e43c2868e86fa8776e913b715d
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="events-c-programming-guide"></a>Ereignisse (C#-Programmierhandbuch)
Ereignisse aktivieren eine [Klasse](../../../csharp/language-reference/keywords/class.md) oder ein Objekt, um Informationen über Aktionen von Interesse an andere Klassen oder Objekte zu übermitteln. Die Klasse, die das Ereignis sendet (oder *auslöst*), wird als *Herausgeber* bezeichnet, und die Klassen, die das Ereignis empfangen (oder *behandeln*), werden als *Abonnenten*bezeichnet.  
  
 In einer typischen C#-Windows Forms oder Web-Anwendung abonnieren Sie Ereignisse, die von Steuerelementen wie Schaltflächen und Listenfelder ausgelöst werden. Sie können die integrierte Entwicklungsumgebung (IDE) von Visual C# zum Durchsuchen der Ereignisse verwenden, die ein Steuerelement auslöst, und diejenigen wählen, die Sie behandeln möchten. Die IDE fügt automatisch eine leere Ereignishandlermethode und den Code zum Abonnieren des Ereignisses hinzu. Weitere Informationen finden Sie unter [Vorgehensweise: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).  
  
## <a name="events-overview"></a>Übersicht über Ereignisse  
 Ereignisse verfügen über folgende Eigenschaften:  
  
-   Der Herausgeber wird bestimmt, wenn ein Ereignis ausgelöst wird. Die Abonnenten bestimmen, welche Aktion als Reaktion auf das Ereignis ausgeführt wird.  
  
-   Ein Ereignis kann mehrere Abonnenten haben. Ein Abonnent kann mehrere Ereignisse von mehreren Herausgebern behandeln.  
  
-   Ereignisse, die keine Abonnenten haben, werden nie ausgelöst.  
  
-   Ereignisse werden in der Regel verwendet, um Benutzeraktionen wie Mausklicks oder Menüauswahlen in GUI-Schnittstellen zu signalisieren.  
  
-   Wenn ein Ereignis mehrere Abonnenten hat, werden die Ereignishandler synchron aufgerufen, wenn ein Ereignis ausgelöst wird. Informationen zum asynchronen Aufrufen von Ereignissen finden Sie unter [Calling Synchronous Methods Asynchronously](../../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).  
  
-   In der [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] -Klassenbibliothek basieren Ereignisse auf dem <xref:System.EventHandler> -Delegaten und der <xref:System.EventArgs> -Basisklasse.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 Weitere Informationen finden Sie unter:  
  
-   [Gewusst wie: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)  
  
-   [Gewusst wie: Veröffentlichen von Ereignissen, die den .NET Framework-Richtlinien entsprechen](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md)  
  
-   [Gewusst wie: Auslösen von Basisklassenereignissen in abgeleiteten Klassen](../../../csharp/programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md)  
  
-   [Gewusst wie: Implementieren von Schnittstellenereignissen](../../../csharp/programming-guide/events/how-to-implement-interface-events.md)  
  
-   [Threadsynchronisierung](../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)  
  
-   [Gewusst wie: Verwenden eines Wörterbuchs zum Speichern von Ereignisinstanzen](../../../csharp/programming-guide/events/how-to-use-a-dictionary-to-store-event-instances.md)  
  
-   [Gewusst wie: Implementieren benutzerdefinierter Ereigniszugriffsmethoden](../../../csharp/programming-guide/events/how-to-implement-custom-event-accessors.md)  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="featured-book-chapters"></a>Enthaltene Buchkapitel  
 [Delegaten, Ereignisse und Lambda-Ausdrücke](https://msdn.microsoft.com/library/orm-9780596516109-03-09.aspx) im [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://msdn.microsoft.com/library/orm-9780596516109-03.aspx)  
  
 [Delegaten und Ereignisse](https://msdn.microsoft.com/library/orm-9780596521066-01-17.aspx) in [Learning C# 3.0: Master the fundamentals of C# 3.0](https://msdn.microsoft.com/library/orm-9780596521066-01.aspx)  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.EventHandler>  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Delegaten](../../../csharp/programming-guide/delegates/index.md)  
 [Erstellen von Ereignishandlern in Windows Forms](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
 [Multithreadprogrammierung mit dem ereignisbasierten asynchronen Muster](../../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)
