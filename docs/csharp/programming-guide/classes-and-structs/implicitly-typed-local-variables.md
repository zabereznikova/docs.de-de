---
title: "Implizit typisierte lokale Variablen (C#-Programmierhandbuch) | Microsoft Docs"
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
  - "Implizit typisierte lokale Variablen [C#]"
  - "var [C#]"
ms.assetid: b9218fb2-ef5d-4814-8a8e-2bc29b0bbc9b
caps.latest.revision: 23
caps.handback.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Implizit typisierte lokale Variablen (C#-Programmierhandbuch)
Lokale Variablen können einen abgeleiteten "Typ" von `var` statt eines expliziten Typs erhalten.  Das `var`\-Schlüsselwort weist den Compiler an, den Typ der Variable aus dem Ausdruck an der rechten Seite der Initialisierungsanweisung abzuleiten.  Beim abgeleiteten Typ kann es sich um einen integrierten Typ, einen anonymen Typ, einen benutzerdefinierten Typ oder einen in der .NET Framework\-Klassenbibliothek definierten Typ handeln.  Weitere Informationen zum Initialisieren von Arrays mit `var` finden Sie unter [Implizit typisierte Arrays](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).  
  
 In den folgenden Beispielen werden verschiedene Methoden veranschaulicht, mit denen lokale Variablen mit `var` deklariert werden können:  
  
 [!code-cs[csProgGuideLINQ#43](../../../csharp/programming-guide/arrays/codesnippet/CSharp/csLINQProgRef/csRef30LangFeatures_2.cs#43)]  
  
 Beachten Sie, dass das `var`\-Schlüsselwort nicht für "variant" steht und damit nicht festgelegt wird, dass die Variable lose typisiert oder spät gebunden ist.  Es bedeutet nur, dass der Compiler den am besten geeigneten Typ bestimmt und zuweist.  
  
 Das `var`\-Schlüsselwort kann in den folgenden Kontexten verwendet werden:  
  
-   Für lokale Variablen \(bei Methodenbereich deklarierte Variablen\), wie im vorherigen Beispiel gezeigt.  
  
-   In einer [for](../../../csharp/language-reference/keywords/for.md)\-Initialisierungsanweisung.  
  
    ```  
    for(var x = 1; x < 10; x++)  
    ```  
  
-   In einer [foreach](../../../csharp/language-reference/keywords/foreach-in.md)\-Initialisierungsanweisung.  
  
    ```  
    foreach(var item in list){...}  
    ```  
  
-   In einer [using](../../../csharp/language-reference/keywords/using-statement.md)\-Anweisung.  
  
    ```  
    using (var file = new StreamReader("C:\\myfile.txt")) {...}  
    ```  
  
 Weitere Informationen finden Sie unter [Gewusst wie: Verwenden von implizit typisierten lokalen Variablen und Arrays in einem Abfrageausdruck](../../../csharp/programming-guide/classes-and-structs/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md).  
  
## var und anonyme Typen  
 In vielen Fällen ist die Verwendung von `var` optional und nur ein syntaktisches Hilfsmittel.  Bei der Initialisierung einer Variablen mit einem anonymen Typ muss diese Variable jedoch als `var` deklariert werden, wenn auf die Eigenschaften des Objekts später zugegriffen werden muss.  Dies ist ein allgemeines Szenario in [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)]\-Abfrageausdrücken.  Weitere Informationen finden Sie unter [Anonyme Typen](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).  
  
 Vom Quellcode aus betrachtet hat ein anonymer Typ keinen Namen.  Wenn eine Abfragevariable daher mit `var` initialisiert wurde, kann auf die Eigenschaften in der zurückgegebenen Folge von Objekten nur unter Verwendung von `var` als Typ der Iterationsvariable in der `foreach`\-Anweisung zugegriffen werden.  
  
 [!code-cs[csProgGuideLINQ#44](../../../csharp/programming-guide/arrays/codesnippet/CSharp/csLINQProgRef/csRef30LangFeatures_2.cs#44)]  
  
## Hinweise  
 Die folgenden Beschränkungen gelten für implizit typisierte Variablendeklarationen:  
  
-   `var` kann nur verwendet werden, wenn eine lokale Variable in der gleichen Anweisung deklariert und initialisiert wird. Die Variable kann nicht mit NULL oder einer Methodengruppe bzw. einer anonymen Funktion initialisiert werden.  
  
-   `var` kann nicht für Felder im Klassengültigkeitsbereich verwendet werden.  
  
-   Variablen, die mit `var` deklariert werden, können nicht im Initialisierungsausdruck verwendet werden.  Anders ausgedrückt, ist der Ausdruck `: int i = (i = 20);` gültig, während der Ausdruck `var i = (i = 20);` einen Kompilierungsfehler verursacht.  
  
-   Mehrere implizit typisierte Variablen können nicht in der gleichen Anweisung initialisiert werden.  
  
-   Wenn sich ein Typ mit der Bezeichnung `var` im Bereich befindet, wird das `var`\-Schlüsselwort zu diesem Typnamen aufgelöst und nicht als Teil einer implizit typisierten lokalen Variablendeklaration aufgefasst.  
  
 Möglicherweise stellen Sie fest, dass `var` auch bei Abfrageausdrücken nützlich sein kann, in denen der exakte konstruierte Typ der Abfragevariable nur schwer bestimmt werden kann.  Dies kann beim Gruppieren und Sortieren von Operationen auftreten.  
  
 Das `var`\-Schlüsselwort kann auch nützlich sein, wenn der spezifische Typ der Variable nur mühsam mit der Tastatur eingegeben werden kann, oder wenn er offensichtlich ist bzw. nicht zur Lesbarkeit des Codes beiträgt.  Ein Beispiel, in dem `var` auf diese Weise nützlich ist, sind geschachtelte Typen, z. B. solche, die mit Gruppenoperationen verwendet werden.  In der folgenden Abfrage ist der Typ dieser Variable `IEnumerable<IGrouping<string, Student>>`.  Solange Sie und andere, die Ihren Code verwalten müssen, sich dessen bewusst sind, steht dem Verwenden der impliziten Typisierung aus Gründen der Einfachheit und der Kürze nichts im Weg.  
  
 [!code-cs[cscsrefQueryKeywords#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/csquerykeywords/Group.cs#13)]  
  
 Der Einsatz von `var` kompliziert jedoch potenziell Ihren Code, sodass andere Entwickler ihn nur schwer nachvollziehen können.  Aus diesem Grund wird in der C\#\-Dokumentation `var` im Allgemeinen nur verwendet, wenn es erforderlich ist.  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [Implizit typisierte Arrays](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md)   
 [Gewusst wie: Verwenden von implizit typisierten lokalen Variablen und Arrays in einem Abfrageausdruck](../../../csharp/programming-guide/classes-and-structs/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md)   
 [Anonyme Typen](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [Objekt\- und Auflistungsinitialisierer](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)   
 [var](../../../csharp/language-reference/keywords/var.md)   
 [LINQ\-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [for](../../../csharp/language-reference/keywords/for.md)   
 [foreach, in](../../../csharp/language-reference/keywords/foreach-in.md)   
 [using\-Anweisung](../../../csharp/language-reference/keywords/using-statement.md)