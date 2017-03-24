---
title: "Generische Schnittstellen (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C#-Sprache, Generische Schnittstellen"
  - "Generika [C#], Schnittstellen"
ms.assetid: a8fa49a1-6e78-4a09-87e5-84a0b9f5ffbe
caps.latest.revision: 28
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 28
---
# Generische Schnittstellen (C#-Programmierhandbuch)
Es ist häufig sinnvoll, Schnittstellen entweder für generische Auflistungsklassen zu definieren oder für die generischen Klassen, die Elemente in der Auflistung darstellen.  Die Einstellung für generische Klassen ist, dass generische Schnittstellen verwendet werden sollen, z. B. <xref:System.IComparable%601> anstelle von <xref:System.IComparable>. Dadurch werden Boxing\- und Unboxingoperationen für Werttypen vermieden.  Durch die Klassenbibliothek von .NET Framework werden einige generische Schnittstellen definiert, die zusammen mit den Auflistungsklassen im <xref:System.Collections.Generic>\-Namespace verwendet werden können.  
  
 Wenn als Einschränkung für einen Typparameter eine Schnittstelle angegeben ist, können nur Typen verwendet werden, die diese Schnittstelle implementieren.  Das folgende Codebeispiel zeigt eine `SortedList<T>`\-Klasse, die von der `GenericList<T>`\-Klasse abgeleitet ist.  Weitere Informationen finden Sie unter [Einführung in Generika](../../../csharp/programming-guide/generics/introduction-to-generics.md).  `SortedList<T>` fügt die Einschränkung `where T : IComparable<T>` hinzu.  Dadurch kann die `BubbleSort`\-Methode in `SortedList<T>` die generische <xref:System.IComparable%601.CompareTo%2A>\-Methode für Listenelemente verwenden.  Im angegebenen Beispiel sind Listenelemente eine einfache Klasse \(`Person`\), die `IComparable<Person>` implementiert.  
  
 [!code-cs[csProgGuideGenerics#29](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_1.cs)]  
  
 Mehrere Schnittstellen können als Einschränkungen für einen einzelnen Typ wie folgt angegeben werden:  
  
 [!code-cs[csProgGuideGenerics#30](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_2.cs)]  
  
 Eine Schnittstelle kann mehr als einen Typparameter wie folgt definieren:  
  
 [!code-cs[csProgGuideGenerics#31](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_3.cs)]  
  
 Für Klassen gelten die gleichen Vererbungsregeln wie für Schnittstellen:  
  
 [!code-cs[csProgGuideGenerics#32](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_4.cs)]  
  
 Generische Schnittstellen können von nicht generischen Schnittstellen erben, sofern die generische Schnittstelle kontravariant ist, d. h., die generische Schnittstelle verwendet ausschließlich den eigenen Typparameter als Rückgabewert.  In der Klassenbibliothek von .NET Framework erbt <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Collections.IEnumerable>, da <xref:System.Collections.Generic.IEnumerable%601> nur `T` im Rückgabewert von <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> und in der Funktion zum Abrufen der <xref:System.Collections.Generic.IEnumerator%601.Current%2A>\-Eigenschaft verwendet.  
  
 Konkrete Klassen können geschlossene konstruierte Schnittstellen wie folgt implementieren:  
  
 [!code-cs[csProgGuideGenerics#33](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_5.cs)]  
  
 Generische Klassen können generische Schnittstellen oder geschlossene konstruierte Schnittstellen implementieren, sofern die Klassenparameterliste wie nachfolgend gezeigt sämtliche Argumente bereitstellt, die von der Schnittstelle benötigt werden:  
  
 [!code-cs[csProgGuideGenerics#34](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_6.cs)]  
  
 Die Regeln, die das Überladen von Methoden steuern, sind für die Methoden innerhalb von generischen Klassen, generischen Strukturen oder generischen Schnittstellen gleich.  Weitere Informationen finden Sie unter [Generische Methoden](../../../csharp/programming-guide/generics/generic-methods.md).  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Einführung in Generika](../../../csharp/programming-guide/generics/introduction-to-generics.md)   
 [Schnittstelle](../../../csharp/language-reference/keywords/interface.md)   
 [Generika](../Topic/Generics%20in%20the%20.NET%20Framework.md)