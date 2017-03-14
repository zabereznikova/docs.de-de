---
title: "Objekt- und Auflistungsinitialisierer (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Auflistungsinitialisierer [C#]"
  - "Objektinitialisierer [C#]"
ms.assetid: c58f3db5-d7d4-4651-bd2d-5a3a97357f61
caps.latest.revision: 27
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 27
---
# Objekt- und Auflistungsinitialisierer (C#-Programmierhandbuch)
Mit Objektinitialisierern können Sie allen verfügbaren Feldern oder Eigenschaften eines Objekts zum Erstellungszeitpunkt Werte zuweisen, ohne einen Konstruktor gefolgt von Zeilen mit Zuweisungsanweisungen aufrufen zu müssen.  Mit der Objektinitialisierersyntax können Sie Argumente für einen Konstruktor angeben oder die Argumente \(und Klammersyntax\) weglassen.  Im folgenden Beispiel werden die Verwendung eines Objektinitialisierers mit einem benannten Typ, `Cat`, und das Aufrufen des Standardkonstruktors veranschaulicht.  Beachten Sie die Verwendung automatisch implementierter Eigenschaften in der `Cat`\-Klasse.  Weitere Informationen finden Sie unter [Automatisch implementierte Eigenschaften](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).  
  
 [!code-cs[csProgGuideLINQ#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_1.cs)]  
  
 [!code-cs[csProgGuideLINQ#45](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_2.cs)]  
  
## Objektinitialisierer mit anonymen Typen  
 Obwohl Objektinitialisierer in jedem Kontext verwendet werden können, sind sie vor allem in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]\-Abfrageausdrücken nützlich.  Abfrageausdrücke verwenden häufig [anonyme Typen](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md), die nur mit einem Objektinitialisierer initialisiert werden können, wie in der folgenden Deklaration veranschaulicht.  
  
```  
var pet = new { Age = 10, Name = "Fluffy" };  
```  
  
 Anonyme Typen ermöglichen der `select`\-Klausel in einem [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]\-Abfrageausdruck, Objekte der ursprünglichen Sequenz in Objekte zu transformieren, deren Wert und Form sich vom Original unterscheiden können.  Dies ist nützlich, wenn Sie nur einen Teil der Informationen aus jedem Objekt in einer Sequenz speichern möchten.  Im folgenden Beispiel wird angenommen, dass ein Produktobjekt \(`p`\) viele Felder und Methoden enthält und dass Sie nur eine Sequenz von Objekten erstellen möchten, die den Produktnamen und den Einzelpreis enthalten.  
  
 [!code-cs[csProgGuideLINQ#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_3.cs)]  
  
 Wenn diese Abfrage ausgeführt wird, enthält die `productInfos`\-Variable eine Sequenz von Objekten, auf die Sie über eine `foreach`\-Anweisung, wie im folgenden Beispiel gezeigt, zugreifen können:  
  
```  
foreach(var p in productInfos){...}  
```  
  
 Jedes Objekt im neuen anonymen Typ hat zwei öffentliche Eigenschaften, die die gleichen Namen wie die Eigenschaften oder Felder im ursprünglichen Objekt erhalten.  Sie können ein Feld auch umbenennen, wenn Sie einen anonymen Typ erstellen. Im folgenden Beispiel wird das `UnitPrice`\-Feld in `Price` umbenannt.  
  
```  
select new {p.ProductName, Price = p.UnitPrice};  
```  
  
## Objektinitialisierer mit dem Typ, der NULL\-Werte zulässt  
 Die Verwendung eines Objektinitialisierers mit einer Struktur, die NULL\-Werte zulässt, ist ein Fehler, der zum Zeitpunkt der Kompilierung auftritt.  
  
## Auflistungsinitialisierer  
 Mit Auflistungsinitialisierern können Sie einen oder mehrere Elementinitialisierer festlegen, wenn Sie eine Auflistungsklasse initialisieren, die <xref:System.Collections.IEnumerable> implementiert, oder eine Klasse mit einer `Add`\-Erweiterungsmethode.  Die Elementinitialisierer können ein einfacher Wert, ein Ausdruck oder ein Objektinitialisierer sein.  Durch den Einsatz eines Auflistungsinitialisierers müssen Sie nicht mehrere Aufrufe der `Add`\-Methode für die Klasse in Ihrem Quellcode angeben; der Compiler fügt die Aufrufe hinzu.  
  
 In den folgenden Beispielen werden zwei einfache Auflistungsinitialisierer dargestellt:  
  
```  
List<int> digits = new List<int> { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };  
List<int> digits2 = new List<int> { 0 + 1, 12 % 3, MakeInt() };  
```  
  
 Der folgende Auflistungsinitialisierer verwendet Objektinitialisierer, um Objekte der `Cat`\-Klasse, die in einem vorherigen Beispiel definiert wurden, zu initialisieren.  Beachten Sie, dass die einzelnen Objektinitialisierer in geschweifte Klammern eingeschlossen und durch Kommas voneinander getrennt werden.  
  
 [!code-cs[csProgGuideLINQ#41](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_4.cs)]  
  
 Sie können [Null](../../../csharp/language-reference/keywords/null.md) als ein Element in einem Auflistungsinitialisierer festlegen, wenn die `Add`\-Methode der Auflistung dies zulässt.  
  
 [!code-cs[csProgGuideLINQ#42](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_5.cs)]  
  
 Sie können indizierte Elemente angeben, falls die Auflistung  die Indizierung unterstützt.  
  
```  
var numbers = new Dictionary<int, string> {   
    [7] = "seven",   
    [9] = "nine",   
    [13] = "thirteen"   
};  
  
```  
  
## Beispiel  
 [!code-cs[csProgGuideLINQ#46](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_6.cs)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [LINQ\-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Anonyme Typen](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)