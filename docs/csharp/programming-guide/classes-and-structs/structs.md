---
title: "Strukturen (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C#-Sprache, Strukturen"
  - "Strukturen [C#]"
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
caps.latest.revision: 31
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 31
---
# Strukturen (C#-Programmierhandbuch)
Strukturen werden mithilfe des [struct](../../../csharp/language-reference/keywords/struct.md)\-Schlüsselworts definiert. Beispiel:  
  
 [!code-cs[csProgGuideObjects#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/structs_1.cs)]  
  
 Strukturen haben fast die gleiche Syntax wie Klassen, unterliegen jedoch mehr Beschränkungen als Klassen:  
  
-   Innerhalb einer Strukturdeklaration können Felder nur dann initialisiert werden, wenn sie als konstant oder statisch deklariert werden.  
  
-   Eine Struktur kann keinen Standardkonstruktor \(ein Konstruktor ohne Parameter\) und keinen Destruktor deklarieren.  
  
-   Strukturen werden durch Zuweisung kopiert.  Wenn eine Struktur einer neuen Variablen zugewiesen wird, werden alle Daten kopiert. Änderungen an der neuen Kopie wirken sich nicht auf die Daten in der ursprünglichen Kopie aus.  Dies sollte beim Arbeiten mit Auflistungen von Werttypen wie Dictionary\<string, myStruct\> nicht vergessen werden.  
  
-   Strukturen sind Werttypen, und Klassen sind Referenztypen.  
  
-   Strukturen können im Gegensatz zu Klassen ohne den Operator `new` instanziiert werden.  
  
-   Strukturen können Konstruktoren deklarieren, die über Parameter verfügen.  
  
-   Eine Struktur ist nicht in der Lage, von einer anderen Struktur oder Klasse zu erben, und sie kann auch nicht die Basis einer Klasse sein.  Alle Strukturen erben direkt von `System.ValueType`, welcher von `System.Object` erbt.  
  
-   Eine Struktur kann Schnittstellen implementieren.  
  
-   Eine Struktur kann als Typ verwendet werden, der NULL\-Werte zulässt, und einer Struktur kann ein NULL\-Wert zugewiesen werden.  
  
## Verwandte Abschnitte  
 Weitere Informationen:  
  
-   [Verwenden von Strukturen](../../../csharp/programming-guide/classes-and-structs/using-structs.md)  
  
-   [Konstruktoren](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
  
-   [Typen, die NULL\-Werte zulassen](../../../csharp/programming-guide/nullable-types/index.md)  
  
-   [Gewusst wie: Unterschiede zwischen dem Übergeben einer Struktur und dem Übergeben eines Klassenverweises an eine Methode](../../../csharp/programming-guide/classes-and-structs/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)  
  
-   [Gewusst wie: Implementieren von benutzerdefinierten Konvertierungen zwischen Strukturen](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [More About Variables](http://go.microsoft.com/fwlink/?LinkId=221230) in [Beginning Visual C\# 2010](http://go.microsoft.com/fwlink/?LinkId=221214)  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Klassen](../../../csharp/programming-guide/classes-and-structs/classes.md)