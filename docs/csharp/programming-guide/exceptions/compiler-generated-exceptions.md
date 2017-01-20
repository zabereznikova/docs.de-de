---
title: "Vom Compiler generierte Ausnahmen (C#-Programmierhandbuch) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Ausnahmen [C#], vom Compiler generierte"
ms.assetid: 53b52f97-b366-4ed7-b05b-9eb78096b7f9
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Vom Compiler generierte Ausnahmen (C#-Programmierhandbuch)
Einige Ausnahmen werden automatisch von der .NET Framework Common Language Runtime \(CLR\) ausgelöst, wenn grundlegende Operationen fehlschlagen.  Diese Ausnahmen und ihre Fehlerbedingungen werden in der folgenden Tabelle aufgelistet.  
  
|Ausnahme|Beschreibung|  
|--------------|------------------|  
|<xref:System.ArithmeticException>|Eine Basisklasse für Ausnahmen, die während arithmetischer Operationen ausgelöst werden, z. B. <xref:System.DivideByZeroException> und <xref:System.OverflowException>.|  
|<xref:System.ArrayTypeMismatchException>|Wird ausgelöst, wenn ein Element nicht in einem Array gespeichert werden kann, weil der tatsächliche Typ des Elements nicht mit dem tatsächlichen Typ des Arrays kompatibel ist.|  
|<xref:System.DivideByZeroException>|Wird ausgelöst, wenn versucht wird, einen ganzzahligen Wert durch 0 zu teilen.|  
|<xref:System.IndexOutOfRangeException>|Wird ausgelöst, wenn versucht wird, ein Array mit einem Index zu indizieren, der kleiner als 0 ist oder außerhalb der Grenzen des Arrays liegt.|  
|<xref:System.InvalidCastException>|Wird ausgelöst, wenn eine explizite Konvertierung von einem Basistyp in einen Schnittstellentyp oder in einen abgeleiteten Typ zur Laufzeit fehlschlägt.|  
|<xref:System.NullReferenceException>|Wird ausgelöst, wenn Sie versuchen, auf ein Objekt zu verweisen, dessen Wert [NULL](../../../csharp/language-reference/keywords/null.md) ist.|  
|<xref:System.OutOfMemoryException>|Wird ausgelöst, wenn ein Versuch, Speicherplatz mit dem Operator [new](../../../csharp/language-reference/keywords/new-operator.md) zu belegen, fehlschlägt.  Dies weist darauf hin, dass der für die Common Language Runtime verfügbare Speicher erschöpft ist.|  
|<xref:System.OverflowException>|Wird ausgelöst, wenn ein Überlauf einer arithmetischen Operation in einem `checked`\-Kontext auftritt.|  
|<xref:System.StackOverflowException>|Wird ausgelöst, wenn der Ausführungsstapel durch zu viele anstehende Methodenaufrufe ausgelastet ist. Im Normalfall deutet dies auf eine zu tiefe Rekursion oder eine Endlosschleife hin.|  
|<xref:System.TypeInitializationException>|Wird ausgelöst, wenn ein statischer Konstruktor eine Ausnahme auslöst und keine `catch`\-Klausel existiert, um sie abzufangen.|  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Ausnahmen und Ausnahmebehandlung](../../../csharp/programming-guide/exceptions/exceptions-and-exception-handling.md)   
 [Ausnahmebehandlung](../../../csharp/programming-guide/exceptions/exception-handling.md)   
 [try\-catch](../../../csharp/language-reference/keywords/try-catch.md)   
 [try\-finally](../../../csharp/language-reference/keywords/try-finally.md)   
 [try\-catch\-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)