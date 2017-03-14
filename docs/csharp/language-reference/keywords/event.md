---
title: "event (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "event"
  - "remove"
  - "event_CSharpKeyword"
  - "add"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "event-Schlüsselwort [C#]"
ms.assetid: 7858fd85-153b-4259-85d0-6aa13c35f174
caps.latest.revision: 28
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 28
---
# event (C#-Referenz)
Das `event`\-Schlüsselwort wird verwendet, um in einer Herausgeberklasse ein Ereignis zu deklarieren.  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie ein Ereignis, das <xref:System.EventHandler> als zugrunde liegenden Delegattyp verwendet, deklariert und ausgelöst wird.  Das vollständige Codebeispiel, das zudem die Verwendung des generischen <xref:System.EventHandler%601>\-Delegattyps, das Abonnieren eines Ereignisses und das Erstellen einer Ereignishandlermethode veranschaulicht, finden Sie unter [Gewusst wie: Veröffentlichen von Ereignissen, die den .NET Framework\-Richtlinien entsprechen](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md).  
  
 [!code-cs[csrefKeywordsModifiers#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/event_1.cs)]  
  
 Ereignisse sind ein spezieller Typ von Multicastdelegaten, die nur innerhalb der Klasse oder Struktur aufgerufen werden können, in der sie deklariert wurden \(die Herausgeberklasse\).  Wenn andere Klassen oder Strukturen das Ereignis abonnieren, werden ihre Ereignishandlermethoden aufgerufen, wenn die Herausgeberklasse das Ereignis auslöst.  Weitere Informationen und Codebeispiele finden Sie unter [Ereignisse](../../../csharp/programming-guide/events/index.md) und [Delegaten](../../../csharp/programming-guide/delegates/index.md).  
  
 Ereignisse können als [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) oder `protected``internal` gekennzeichnet werden.  Diese Zugriffsmodifizierer definieren, wie Benutzer der Klasse auf das Ereignis zugreifen können.  Weitere Informationen finden Sie unter [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
## Schlüsselwörter und Ereignisse  
 Die folgenden Schlüsselwörter gelten für Ereignisse.  
  
|Schlüsselwort|Beschreibung|Weitere Informationen|  
|-------------------|------------------|---------------------------|  
|[static](../../../csharp/language-reference/keywords/static.md)|Macht das Ereignis jederzeit für Aufrufer verfügbar, selbst wenn keine Instanz der Klasse vorhanden ist.|[Statische Klassen und statische Klassenmember](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)|  
|[virtual](../../../csharp/language-reference/keywords/virtual.md)|Ermöglicht es abgeleiteten Klassen, das Verhalten von Ereignissen mit dem [override](../../../csharp/language-reference/keywords/override.md)\-Schlüsselwort zu überschreiben.|[Vererbung](../../../csharp/programming-guide/classes-and-structs/inheritance.md)|  
|[sealed](../../../csharp/language-reference/keywords/sealed.md)|Gibt an, dass es für abgeleitete Klassen nicht mehr virtuell ist.||  
|[abstract](../../../csharp/language-reference/keywords/abstract.md)|Der Compiler generiert keinen `add`\-Ereignisaccessorblock und `remove`\-Ereignisaccessorblock, sodass abgeleitete Klassen ihre eigene Implementierung bereitstellen müssen.||  
  
 Ein Ereignis kann mit dem [static](../../../csharp/language-reference/keywords/static.md)\-Schlüsselwort als statisches Ereignis deklariert werden.  Dadurch wird das Ereignis jederzeit für Aufrufer verfügbar, selbst wenn keine Instanz der Klasse vorhanden ist.  Weitere Informationen finden Sie unter [Statische Klassen und statische Klassenmember](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
 Ein Ereignis kann mit dem [virtual](../../../csharp/language-reference/keywords/virtual.md)\-Schlüsselwort als virtuelles Ereignis gekennzeichnet werden.  Dies ermöglicht abgeleiteten Klassen, das Verhalten von Ereignissen mit dem [override](../../../csharp/language-reference/keywords/override.md)\-Schlüsselwort zu überschreiben.  Weitere Informationen finden Sie unter [Vererbung](../../../csharp/programming-guide/classes-and-structs/inheritance.md).  Ein Ereignis, das ein virtuelles Ereignis überschreibt, kann auch [versiegelt](../../../csharp/language-reference/keywords/sealed.md) sein. Damit wird angegeben, dass es für abgeleitete Klassen nicht mehr virtuell ist.  Schließlich kann ein Ereignis als [abstrakt](../../../csharp/language-reference/keywords/abstract.md) deklariert werden, d. h., der Compiler generiert keinen `add`\-Ereignisaccessorblock und keinen `remove`\-Ereignisaccessorblock.  Somit müssen abgeleitete Klassen ihre eigene Implementierung bereitstellen.  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Hinzufügen](../../../csharp/language-reference/keywords/add.md)   
 [Entfernen](../../../csharp/language-reference/keywords/remove.md)   
 [Modifizierer](../../../csharp/language-reference/keywords/modifiers.md)   
 [Gewusst wie: Kombinieren von Delegaten \(Multicastdelegaten\)](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)