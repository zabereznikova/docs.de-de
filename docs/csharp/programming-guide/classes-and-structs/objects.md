---
title: "Objekte (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Objekte [C#], Informationen über Objekte"
  - "Variablen [C#]"
ms.assetid: af4a5230-fbf3-4eea-95e1-8b883c2f845c
caps.latest.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 26
---
# Objekte (C#-Programmierhandbuch)
Eine Klassen\- oder Strukturdefinition ist mit einer Blaupause vergleichbar, die die Möglichkeiten des Typs angibt.  Ein Objekt stellt im Wesentlichen einen Speicherblock dar, der auf Grundlage der Blaupause belegt und konfiguriert wurde.  Von einem Programm können viele Objekte derselben Klasse erstellt werden.  Objekte werden auch Instanzen genannt. Sie können in einer benannten Variablen, in einem Array oder in einer Auflistung gespeichert werden.  Clientcode ist der Code, der diese Variablen verwendet, um die Methoden aufzurufen und auf die öffentlichen Eigenschaften des Objekts zuzugreifen.  In einer objektorientierten Sprache, wie z. B. C\#, besteht ein typisches Programm aus mehreren, dynamisch interagierenden Objekten.  
  
> [!NOTE]
>  Statische Typen weisen ein anderes als das hier beschriebene Verhalten auf.  Weitere Informationen finden Sie unter [Statische Klassen und statische Klassenmember](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
## Struktur\-Instanzen VS.\-Klasseninstanzen  
 Da es sich bei Klassen um Referenztypen handelt, enthalten Variablen eines Klassenobjekts einen Verweis auf die Adresse des Objekts auf dem verwalteten Heap.  Wenn dem ersten Objekt ein zweites Objekt desselben Typs zugewiesen wird, verweisen beide Variablen auf das Objekt an dieser Adresse.  Dieser Punkt wird weiter unten in diesem Thema ausführlich erläutert.  
  
 Instanzen von Klassen werden mit dem [Operator "new"](../../../csharp/language-reference/keywords/new-operator.md) erstellt.  Im folgenden Beispiel stellt `Person` den Typ dar, und `person1` und `person 2` sind Instanzen bzw. Objekte dieses Typs.  
  
 [!code-cs[csProgGuideStatements#30](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/objects_1.cs)]  
  
 Da es sich bei Strukturen um Werttypen handelt, enthält die Variable eines Strukturobjekts eine Kopie des gesamten Objekts.  Strukturinstanzen können daher mithilfe des Operators `new` erstellt werden. Dies ist jedoch, wie im folgenden Beispiel dargestellt, nicht erforderlich:  
  
 [!code-cs[csProgGuideStatements#31](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/objects_2.cs)]  
  
 Der Arbeitsspeicher wird sowohl für `p1` als auch für `p2` auf dem Threadstapel belegt.  Dieser Arbeitsspeicher wird zusammen mit dem Typ oder der Methode wieder freigegeben, in dem bzw. der er deklariert ist.  Dies ist ein Grund, weshalb Strukturen bei Zuweisung kopiert werden.  Im Gegensatz dazu wird der für eine Klasseninstanz belegte Speicher automatisch von der Common Language Runtime freigegeben \(mithilfe der Garbage Collection\), wenn alle Verweise auf das Objekt ungültig geworden sind.  Klassenobjekte können nicht deterministisch zerstört werden wie in C\+\+.  Weitere Informationen über Garbage Collection in [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] finden Sie unter [Garbage Collection](../Topic/Garbage%20Collection.md).  
  
> [!NOTE]
>  Das Belegen und das Freigeben von Speicher auf dem verwalteten Heap wurden in der Common Language Runtime stark optimiert.  Meist besteht kein wesentlicher Unterschied zwischen den Leistungseinbußen bei der Reservierung einer Klasseninstanz auf dem Heap und dem Reservieren einer Strukturinstanz auf dem Stapel.  
  
## Objektidentität VS.\-Wertgleichheit  
 Wenn Sie zwei Objekte auf Gleichheit prüfen möchten, müssen Sie zunächst entscheiden, ob Sie prüfen möchten, ob die beiden Variablen dasselbe Objekt im Speicher darstellen oder ob die Werte für eines oder mehrere ihrer Felder übereinstimmen.  Beim Vergleich von Werten muss beachtet werden, ob es sich bei den Objekten um Instanzen von Werttypen \(Strukturen\) oder Referenztypen \(Klassen, Delegate oder Arrays\) handelt.  
  
-   Um zu ermitteln, ob zwei Klasseninstanzen auf denselben Speicherplatz verweisen \(d. h., sie haben dieselbe *Identität*\), können Sie die statische <xref:System.Object.Equals%2A>\-Methode verwenden.  \(<xref:System.Object?displayProperty=fullName> stellt die implizite Basisklasse für alle Wert\- und Referenztypen, einschließlich benutzerdefinierter Strukturen und Klassen, dar.\)  
  
-   Mit der <xref:System.ValueType.Equals%2A?displayProperty=fullName>\-Methode können Sie bestimmen, ob die Instanzfelder zweier Strukturinstanzen über dieselben Werte verfügen.  Da alle Strukturen implizit von <xref:System.ValueType?displayProperty=fullName> erben, wird die Methode für das Objekt direkt aufgerufen, wie im folgenden Beispiel gezeigt:  
  
 [!code-cs[csProgGuideStatements#32](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/objects_3.cs)]  
  
 Die <xref:System.ValueType?displayProperty=fullName>\-Implementierung von `Equals` verwendet Reflektion, da sie die Typen der Felder jeder Struktur ermitteln muss.  Wenn Sie eigene Strukturen erstellen, überschreiben Sie die `Equals`\-Methode, um einen effizienten, auf den von Ihnen verwendeten Typ zugeschnittenen Algorithmus zur Prüfung auf Gleichheit bereitzustellen.  
  
-   Um zu bestimmen, ob die Werte der Felder in zwei Klasseninstanzen gleich sind, können Sie die <xref:System.Object.Equals%2A>\-Methode oder den [Operator \=\=](../../../csharp/language-reference/operators/equality-comparison-operator.md) verwenden.  Nutzen Sie sie jedoch nur dann, wenn die Klasse sie überschrieben oder überladen hat, um eine benutzerdefinierte Definition dafür bereitzustellen, was "Gleichheit" für Objekte dieses Typs bedeutet.  Die Klasse kann auch die <xref:System.IEquatable%601>\-Schnittstelle oder die <xref:System.Collections.Generic.IEqualityComparer%601>\-Schnittstelle implementieren.  Beide Schnittstellen stellen Methoden bereit, mit denen die Wertgleichheit getestet werden kann.  Wenn Sie eigene Klassen entwerfen, die `Equals` überschreiben, stellen Sie sicher, dass Sie die Richtlinien befolgen, die in [Gewusst wie: Definieren von Wertgleichheit für einen Typ](../../../csharp/programming-guide/statements-expressions-operators/how-to-define-value-equality-for-a-type.md) und <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName> angegeben sind.  
  
## Verwandte Abschnitte  
 Weitere Informationen:  
  
-   [Klassen](../../../csharp/programming-guide/classes-and-structs/classes.md)  
  
-   [Strukturen](../../../csharp/programming-guide/classes-and-structs/structs.md)  
  
-   [Konstruktoren](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
  
-   [Destruktoren](../../../csharp/programming-guide/classes-and-structs/destructors.md)  
  
-   [Ereignisse](../../../csharp/programming-guide/events/index.md)  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [object](../../../csharp/language-reference/keywords/object.md)   
 [Vererbung](../../../csharp/programming-guide/classes-and-structs/inheritance.md)   
 [Klasse](../../../csharp/language-reference/keywords/class.md)   
 [struct](../../../csharp/language-reference/keywords/struct.md)   
 [new\-Operator](../../../csharp/language-reference/keywords/new-operator.md)   
 [Allgemeines Typsystem](../../../standard/base-types/common-type-system.md)