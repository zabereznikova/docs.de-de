---
title: Generische Schnittstellen – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generic interfaces
- generics [C#], interfaces
ms.assetid: a8fa49a1-6e78-4a09-87e5-84a0b9f5ffbe
ms.openlocfilehash: d0b9d35a7e814d8790ee57f1169f2b35f7c42536
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564210"
---
# <a name="generic-interfaces-c-programming-guide"></a>Generische Schnittstellen (C#-Programmierhandbuch)
Es ist häufig sinnvoll, Schnittstellen entweder für generische Auflistungsklassen zu definieren oder für die generischen Klassen, die Elemente in der Auflistung darstellen. Die Einstellung für generische Klassen ist, dass generische Schnittstellen verwendet werden sollen, z.B. <xref:System.IComparable%601> anstelle von <xref:System.IComparable>. Dadurch werden Boxing- und Unboxingoperationen für Werttypen vermieden. Durch die Klassenbibliothek von .NET Framework werden einige generische Schnittstellen definiert, die zusammen mit den Auflistungsklassen im Namespace <xref:System.Collections.Generic> verwendet werden können.  
  
 Wenn als Einschränkung für einen Typparameter eine Schnittstelle angegeben ist, können nur Typen verwendet werden, die diese Schnittstelle implementieren. Der folgende Code zeigt eine Klasse `SortedList<T>`, die von der Klasse `GenericList<T>` abgeleitet wird. Weitere Informationen finden Sie unter [Introduction to Generics (Einführung in Generika)](../../../csharp/programming-guide/generics/introduction-to-generics.md). `SortedList<T>` fügt die Einschränkung `where T : IComparable<T>` hinzu. Dadurch kann die Methode `BubbleSort` in `SortedList<T>` die generische Methode <xref:System.IComparable%601.CompareTo%2A> für Listenelemente verwenden. In diesem Beispiel sind Listenelemente eine einfache Klasse, `Person`, die `IComparable<Person>` implementiert.  
  
 [!code-csharp[csProgGuideGenerics#29](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_1.cs)]  
  
 Mehrere Schnittstellen können als Einschränkungen für einen einzelnen Typ wie folgt angegeben werden:  
  
 [!code-csharp[csProgGuideGenerics#30](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_2.cs)]  
  
 Eine Schnittstelle kann mehr als einen Typparameter wie folgt definieren:  
  
 [!code-csharp[csProgGuideGenerics#31](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_3.cs)]  
  
 Für Klassen gelten die gleichen Vererbungsregeln wie für Schnittstellen:  
  
 [!code-csharp[csProgGuideGenerics#32](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_4.cs)]  
  
 Generische Schnittstellen können von nicht generischen Schnittstellen erben, sofern die generische Schnittstelle kontravariant ist, also die generische Schnittstelle ausschließlich den eigenen Typparameter als Rückgabewert verwendet. In der Klassenbibliothek von .NET Framework erbt <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Collections.IEnumerable>, da <xref:System.Collections.Generic.IEnumerable%601> nur `T` im Rückgabewert von <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> und in der Funktion zum Abrufen der Eigenschaft <xref:System.Collections.Generic.IEnumerator%601.Current%2A> verwendet.  
  
 Konkrete Klassen können geschlossene konstruierte Schnittstellen wie folgt implementieren:  
  
 [!code-csharp[csProgGuideGenerics#33](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_5.cs)]  
  
 Generische Klassen können generische Schnittstellen oder geschlossene konstruierte Schnittstellen implementieren, sofern die Klassenparameterliste wie nachfolgend gezeigt sämtliche Argumente bereitstellt, die von der Schnittstelle benötigt werden:  
  
 [!code-csharp[csProgGuideGenerics#34](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_6.cs)]  
  
 Die Regeln, die das Überladen von Methoden steuern, sind für die Methoden innerhalb von generischen Klassen, generischen Strukturen oder generischen Schnittstellen gleich. Weitere Informationen finden Sie unter [Generic Methods (Generische Methoden)](../../../csharp/programming-guide/generics/generic-methods.md).  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
- [Einführung in Generika](../../../csharp/programming-guide/generics/introduction-to-generics.md)
- [interface](../../../csharp/language-reference/keywords/interface.md)
- [Generika](~/docs/standard/generics/index.md)
