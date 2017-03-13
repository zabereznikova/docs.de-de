---
title: "Gewusst wie: Ausl&#246;sen von Basisklassenereignissen in abgeleiteten Klassen (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Ereignisse [C#], In abgeleiteten Klassen"
ms.assetid: 2d20556a-0aad-46fc-845e-f85d86ea617a
caps.latest.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 24
---
# Gewusst wie: Ausl&#246;sen von Basisklassenereignissen in abgeleiteten Klassen (C#-Programmierhandbuch)
Das folgende einfache Beispiel veranschaulicht die herkömmliche Methode zum Deklarieren von Ereignissen in einer Basisklasse, damit sie über abgeleitete Klassen ausgelöst werden können.  Dieses Beispiel wird für zahlreiche Windows Forms\-Klassen in der [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]\-Klassenbibliothek verwendet.  
  
 Wenn Sie eine Klasse erstellen, die als Basisklasse für andere Klassen verwendet werden kann, dürfen Sie nicht vergessen, dass Ereignisse ein spezieller Delegattyp sind und nur innerhalb der Klasse aufgerufen werden können, in der sie deklariert wurden.  Abgeleitete Klassen können Ereignisse, die innerhalb der Basisklasse deklariert wurden, nicht direkt aufrufen.  Mitunter kann es zwar erwünscht sein, dass ein Ereignis nur von der Basisklasse ausgelöst werden kann, in den meisten Fällen sollten Sie jedoch die abgeleitete Klasse zum Aufrufen von Basisklassenereignissen aktivieren.  Hierzu können Sie eine geschützte aufrufende Methode in der Basisklasse erstellen, die das Ereignis umschließt.  Abgeleitete Klassen können das Ereignis durch Aufrufen oder Überschreiben dieser aufrufenden Methode indirekt aufrufen.  
  
> [!NOTE]
>  Deklarieren Sie keine virtuellen Ereignisse in einer Basisklasse, und überschreiben Sie sie in einer abgeleiteten Klasse.  Der C\#\-Compiler verarbeitet diese nicht ordnungsgemäß, und er ist unvorhersehbar, ob ein Abonnent in den abgeleiteten Ereignisses tatsächlich in den Basisklassen Ereignis abonniert wird.  
  
## Beispiel  
 [!code-cs[csProgGuideEvents#1](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-raise-base-class-events-in-derived-classes_1.cs)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Ereignisse](../../../csharp/programming-guide/events/index.md)   
 [Delegaten](../../../csharp/programming-guide/delegates/index.md)   
 [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [Erstellen von Ereignishandlern in Windows Forms](../Topic/Creating%20Event%20Handlers%20in%20Windows%20Forms.md)