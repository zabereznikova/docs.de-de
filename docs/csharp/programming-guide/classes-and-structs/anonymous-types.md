---
title: "Anonyme Typen (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Anonyme Typen [C#]"
  - "Die Programmiersprache C#, Anonyme Typen"
ms.assetid: 59c9d7a4-3b0e-475e-b620-0ab86c088e9b
caps.latest.revision: 28
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 28
---
# Anonyme Typen (C#-Programmierhandbuch)
Anonyme Typen stellen eine praktische Möglichkeit dar, einen Satz schreibgeschützter Eigenschaften in einem Objekt zu kapseln, ohne zuerst explizit einen Typ definieren zu müssen. Der Typname wird vom Compiler generiert und ist auf Quellcodeebene nicht verfügbar. Der Typ der einzelnen Eigenschaften wird vom Compiler abgeleitet.  
  
 Sie erstellen anonyme Typen mit dem [new](../../../csharp/language-reference/keywords/new.md)\-Operator zusammen mit einem Objektinitialisierer. Weitere Informationen zu Objektinitialisierern finden Sie unter [Objekt\- und Auflistungsinitialisierer](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).  
  
 Das folgende Beispiel veranschaulicht einen anonymen Typ, der mit den beiden Eigenschaften `Amount` und `Message` initialisiert wird.  
  
```c#  
  
var v = new { Amount = 108, Message = "Hello" };  
  
// Rest the mouse pointer over v.Amount and v.Message in the following  
// statement to verify that their inferred types are int and string.  
Console.WriteLine(v.Amount + v.Message);  
  
```  
  
 Anonyme Typen werden normalerweise in der [select](../../../csharp/language-reference/keywords/select-clause.md)\-Klausel eines Abfrageausdrucks verwendet, um von jedem Objekt in der Quellsequenz eine Teilmenge der Eigenschaften zurückzugeben. Weitere Informationen zu Abfragen finden Sie unter [LINQ\-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md).  
  
 Anonyme Typen enthalten mindestens eine schreibgeschützte Eigenschaft. Andere Arten von Klassenmembern wie Methoden oder Ereignisse sind ungültig. Der Ausdruck, der zum Initialisieren einer Eigenschaft verwendet wird, kann weder `null` noch eine anonyme Funktion oder ein Zeigertyp sein.  
  
 Das gängigste Szenario ist die Initialisierung eines anonymen Typs mit den Eigenschaften eines anderen Typs. Nehmen Sie im folgenden Beispiel an, dass eine Klasse mit dem Namen `Product` vorhanden ist. Die `Product`\-Klasse enthält die Eigenschaften `Color` und `Price` sowie weitere Eigenschaften, die für Sie nicht relevant sind. Die Variable `products` ist eine Auflistung von `Product`\-Objekten. Die Deklaration eines anonymen Typs beginnt mit dem Schlüsselwort `new`. Die Deklaration initialisiert einen neuen Typ, der nur zwei Eigenschaften von `Product` verwendet. Dadurch wird eine geringere Datenmenge in der Abfrage zurückgegeben.  
  
 Wenn Sie im anonymen Typ keine Membernamen angeben, gibt der Compiler den Membern des anonymen Typs den Namen der Eigenschaft, mit der sie initialisiert werden. Sie müssen einen Namen für eine Eigenschaft angeben, die mit einem Ausdruck initialisiert wird, wie im vorherigen Beispiel dargestellt. Im folgenden Beispiel lauten die Namen der Eigenschaften des anonymen Typs `Color` und `Price`.  
  
 [!code-cs[csRef30Features#81](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/anonymous-types_1.cs)]  
  
 Wenn Sie einen anonymen Typ zum Initialisieren einer Variablen verwenden, deklarieren Sie die Variable normalerweise mithilfe von [var](../../../csharp/language-reference/keywords/var.md) als implizit typisierte lokale Variable. Der Typname kann in der Variablendeklaration nicht angegeben werden, da nur der Compiler über Zugriff auf den zugrunde liegenden Namen des anonymen Typs verfügt. Weitere Informationen zu `var` finden Sie unter [Implizit typisierte lokale Variablen](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).  
  
 Sie können ein Array anonym typisierter Elemente erstellen, indem Sie eine implizit typisierte lokale Variable und ein implizit typisiertes Array kombinieren, wie im folgenden Beispiel veranschaulicht.  
  
```c#  
var anonArray = new[] { new { name = "apple", diam = 4 }, new { name = "grape", diam = 1 }};  
```  
  
## Hinweise  
 Anonyme Typen sind [Klassentypen](../../../csharp/language-reference/keywords/class.md), die direkt vom [Objekt](../../../csharp/language-reference/keywords/object.md) abgleitet werden und in keinen anderen Typ als ein [Objekt](../../../csharp/language-reference/keywords/object.md) umgewandelt werden können. Der Compiler gibt für jeden anonymen Typ einen Namen an, Ihre Anwendung kann jedoch nicht darauf zugreifen. Aus der Perspektive der Common Language Runtime unterscheidet sich ein anonymer Typ nicht von anderen Verweistypen.  
  
 Wenn zwei oder mehr anonyme Objektinitialisierer in einer Assembly eine Sequenz von Eigenschaften angeben, die die gleiche Reihenfolge und die gleichen Namen und Typen aufweisen, behandelt der Compiler die Objekte als Instanzen desselben Typs. Sie erhalten die gleichen vom Compiler generierten Typinformationen.  
  
 Sie können ein Feld, eine Eigenschaft, ein Ereignis oder den Rückgabetyp einer Methode nicht mit einem anonymen Typ deklarieren. Auch können Sie einen formalen Parameter einer Methode, einer Eigenschaft, eines Konstruktors oder eines Indexers nicht als anonymen Typ deklarieren. Um einen anonymen Typ oder eine Auflistung mit anonymen Typen als Argument einer Methode zu übergeben, können Sie den Parameter als Typobjekt deklarieren. Dadurch wird jedoch der Zweck der starken Typisierung vereitelt. Wenn Sie Abfrageergebnisse speichern oder außerhalb der Methodengrenze übergeben müssen, könnten Sie statt eines anonymen Typs eine Struktur oder Klasse mit einem gewöhnlichen Namen verwenden.  
  
 Da die Methoden <xref:System.Object.Equals%2A> und <xref:System.Object.GetHashCode%2A> von anonymen Typen anhand der Methoden `Equals` und `GetHashCode` der Eigenschaften definiert werden, sind zwei Instanzen eines anonymen Typs nur gleich, wenn alle Eigenschaften gleich sind.  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Objekt\- und Auflistungsinitialisierer](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)   
 [Getting Started with LINQ in C\#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [LINQ\-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)