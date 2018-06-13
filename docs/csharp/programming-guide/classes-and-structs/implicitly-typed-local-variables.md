---
title: Implizit typisierte lokale Variablen (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- implicitly-typed local variables [C#]
- var [C#]
ms.assetid: b9218fb2-ef5d-4814-8a8e-2bc29b0bbc9b
ms.openlocfilehash: c6c2bae39764e78fad2510bbc8937b0ac790bef5
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2018
ms.locfileid: "34172005"
---
# <a name="implicitly-typed-local-variables-c-programming-guide"></a>Implizit typisierte lokale Variablen (C#-Programmierhandbuch)
Lokale Variablen können deklariert werden, ohne einen expliziten Typ anzugeben. Das `var`-Schlüsselwort weist den Compiler an, den Typ der Variablen vom Ausdruck auf der rechten Seite der Initialisierungsanweisung abzuleiten. Der hergeleitete Typ ist möglicherweise ein integrierter Typ, ein anonymer Typ, ein benutzerdefinierter Typ oder ein Typ, der in der .NET Framework-Klassenbibliothek definiert wurde. Weitere Informationen zur Initialisierung von Arrays mithilfe von `var` finden Sie unter [Implizit typisierte Arrays](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).  
  
 Die folgenden Beispiele veranschaulichen verschiedene Arten, wie Sie lokale Variablen mit `var` deklarieren können:  
  
 [!code-csharp[csProgGuideLINQ#43](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-local-variables_1.cs)]  
  
 Es ist von großer Bedeutung zu verstehen, dass das `var`-Schlüsselwort nicht „variant“ bedeutet, und das es nicht darauf hinweist, dass die Variable schwach typisiert oder spät gebunden ist. Es bedeutet nur, dass der Compiler den angemessensten Typen bestimmt und zuweist.  
  
 Das `var`-Schlüsselwort kann in folgendem Kontext verwendet werden:  
  
-   Für lokale Variablen (Variablen, die im Geltungsbereich der Methode deklariert wurden), wie in vorherigem Beispiel gezeigt.  
  
-   In einer [for](../../../csharp/language-reference/keywords/for.md)-Initialisierungsanweisung.  
  
    ```csharp  
    for(var x = 1; x < 10; x++)  
    ```  
  
-   In einer [foreach](../../../csharp/language-reference/keywords/foreach-in.md)-Initialisierungsanweisung.  
  
    ```csharp  
    foreach(var item in list){...}  
    ```  
  
-   In einer [using](../../../csharp/language-reference/keywords/using-statement.md)-Anweisung.  
  
    ```csharp  
    using (var file = new StreamReader("C:\\myfile.txt")) {...}  
    ```  
  
 Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden von implizit typisierten lokalen Variablen und Arrays in einem Abfrageausdruck](../../../csharp/programming-guide/classes-and-structs/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md).  
  
## <a name="var-and-anonymous-types"></a>var und anonyme Typen  
 In vielen Fällen ist der Einsatz von `var` optional und nur eine praktische Syntax. Wenn eine Variable allerdings mit einem anonymen Typ initialisiert wird, müssen Sie die Variable als `var` deklarieren, wenn Sie zu einem späteren Zeitpunkt auf die Eigenschaften des Objekts zugreifen möchten. Das ist ein häufiges Szenario in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfrageausdrücken. Weitere Informationen finden Sie unter [Anonyme Typen](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).  
  
 Aus der Perspektive Ihres Quellcodes hat ein anonymer Typ keinen Namen. Wenn eine Abfragevariable mit `var` initialisiert wurde, ist es deshalb nur möglich, auf die Eigenschaften in der zurückgegebenen Objektsequenz zuzugreifen, wenn Sie `var` in der `foreach`-Anweisung als Typen der Iterationvariablen verwenden.  
  
 [!code-csharp[csProgGuideLINQ#44](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-local-variables_2.cs)]  
  
## <a name="remarks"></a>Hinweise  
 Die folgenden Einschränkungen gelten für implizit typisierte Variablendeklarationen:  
  
-   `var` kann nur verwendet werden, wenn eine lokale Variable deklariert und in derselben Anweisung initialisiert wird; die Variable kann weder mit NULL noch mit einer Methodengruppe oder einer anonymen Funktion initialisiert werden.  
  
-   `var` kann nicht für Felder im Klassenbereich verwendet werden.  
  
-   Variablen, die mit `var` deklariert wurden, können nicht im Initialisierungsausdruck verwendet werden. Sprich, dieser Ausdruck ist gültig`: int i = (i = 20);`, aber dieser Ausdruck führt zu einem Kompilierzeitfehler: `var i = (i = 20);`  
  
-   Es können nicht mehrere implizit typisierte Variablen in derselben Anweisung initialisiert werden.  
  
-   Wenn sich ein Typ mit dem Namen `var` im Geltungsbereich befindet, löst sich das `var`-Schlüsselwort zu diesem Typnamen auf und wird nicht als Teil der Deklaration einer implizit typisierten lokalen Variablen behandelt.  
  
 `var` erweist sich auch bei Abfrageausdrücken als nützlich, deren genauer konstruierter Typ der Abfragevariable schwer ermittelbar ist. Dies kann bei Gruppierungs- und Sortierungsvorgängen auftreten.  
  
 Das `var`-Schlüsselwort erweist sich auch als nützlich, wenn es umständlich ist, den Variablentypen mit der Tastatur einzugeben – oder wenn der Typ offensichtlich ist, oder nicht zur Lesbarkeit des Codes beiträgt. `var` ist z.B. bei geschachtelten generischen Typen wie die, die in Gruppenvorgängen verwendet werden, auf diese Weise nützlich. In der folgenden Abfrage ist der Typ der Abfragevariablen `IEnumerable<IGrouping<string, Student>>`. Solange dies Ihnen und denen, die Ihren Code verwalten müssen, klar ist, spricht nichts dagegen, implizite Typisierung aus Gründen der Zweckmäßigkeit und der Kürze zu verwenden.  
  
 [!code-csharp[cscsrefQueryKeywords#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/implicitly-typed-local-variables_3.cs)]  
  
 Durch den Gebrauch von `var` besteht aber zumindest die Möglichkeit, dass Ihr Code für andere Entwickler schwerer zu verstehen ist. Aus diesem Grund wird `var` in der C#-Dokumentation nur dann verwendet, wenn es tatsächlich erforderlich ist.  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [Implizit typisierte Arrays](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md)  
 [Gewusst wie: Verwenden von implizit typisierten lokalen Variablen und Arrays in einem Abfrageausdruck](../../../csharp/programming-guide/classes-and-structs/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md)  
 [Anonyme Typen](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)  
 [Objekt- und Auflistungsinitialisierer](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)  
 [var](../../../csharp/language-reference/keywords/var.md)  
 [LINQ-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [LINQ (Language Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)  
 [for](../../../csharp/language-reference/keywords/for.md)  
 [foreach, in](../../../csharp/language-reference/keywords/foreach-in.md)  
 [Using-Anweisung](../../../csharp/language-reference/keywords/using-statement.md)
