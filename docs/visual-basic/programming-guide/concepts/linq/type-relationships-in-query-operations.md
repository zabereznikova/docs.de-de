---
title: Typbeziehungen in Abfrageoperationen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variable relationships [LINQ in Visual Basic]
- type information inferred [LINQ in Visual Basic]
- type relationships [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], type relationships
- data sources [LINQ in Visual Basic], type relationships
- LINQ [Visual Basic], type relationships
- inferring type information [LINQ in Visual Basic]
- relationships [LINQ in Visual Basic]
ms.assetid: b5ff4da5-f3fd-4a8e-aaac-1cbf52fa16f6
ms.openlocfilehash: ed0072eeb44a17201ddab2af6f6a44fd14461029
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="type-relationships-in-query-operations-visual-basic"></a>Typbeziehungen in Abfrageoperationen (Visual Basic)
Im verwendeten Variablen [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] Abfrage Vorgänge sind stark typisiert und müssen miteinander kompatibel sein. Starke Typisierung wird in der Datenquelle, in der Abfrage selbst und in die Ausführung der Abfrage verwendet werden. Die folgende Abbildung Begriffe, die zum Beschreiben einer [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Abfrage. Weitere Informationen über die Teile einer Abfrage finden Sie unter [Grundlegende Abfrageoperationen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md).  
  
 ![Pseudocode-Abfrage mit hervorgehobenen Elementen. ] (../../../../visual-basic/programming-guide/concepts/linq/media/sjltyperels.png "SJLtypeRels")  
Teile einer LINQ-Abfrage  
  
 Der Typ der Bereichsvariablen in der Abfrage muss mit dem Typ der Elemente in der Datenquelle kompatibel sein. Der Typ der Abfragevariablen muss kompatibel mit dem Sequenzelement definiert, der `Select` Klausel. Schließlich der Typ der Elemente der Sequenz auch muss kompatibel mit dem Typ des Loop-Steuerelementvariable, die verwendet wird die `For Each` -Anweisung, die die Abfrage ausgeführt wird. Diese starke Typisierung erleichtert die Identifizierung der Typfehler zur Kompilierzeit.  
  
 Visual Basic erleichtert eine starke Typisierung durch Implementieren von lokaler Typrückschluss, auch bekannt als *implizite Typisierung*. Funktion wird im vorherigen Beispiel verwendet, und sehen Sie in der gesamten verwendet die [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Beispiele und Dokumentation. Lokaler Typrückschluss erfolgt in Visual Basic einfach mithilfe einer `Dim` -Anweisung ohne eine `As` Klausel. Im folgenden Beispiel `city` stark typisiert ist, als Zeichenfolge.  
  
 [!code-vb[VbLINQTypeRels#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_1.vb)]  
  
> [!NOTE]
>  Lokaler Typrückschluss funktioniert nur, wenn `Option Infer` festgelegt ist, um `On`. Weitere Informationen finden Sie unter [Option Infer-Anweisung](../../../../visual-basic/language-reference/statements/option-infer-statement.md).  
  
 Selbst bei Verwendung von lokalem Typrückschluss in einer Abfrage gibt jedoch die gleichen typbeziehungen zwischen den Variablen in der Datenquelle, die Abfragevariable und der Ausführungsschleife Abfrage vorhanden. Es ist sinnvoll, einen grundlegenden Überblick über diese typbeziehungen zu verwenden, wenn Sie schreiben [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Abfragen oder Arbeiten mit den Beispielen und Codebeispielen in der Dokumentation.  
  
 Sie müssen möglicherweise einen expliziten Typ für eine Bereichsvariable angeben, die nicht aus der Datenquelle zurückgegebenen Typ übereinstimmt. Sie können den Typ der Bereichsvariablen angeben, mit einem `As` Klausel. Dies führt jedoch zu einem Fehler, wenn die Konvertierung ist ein [einschränkende Konvertierung](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) und `Option Strict` festgelegt ist, um `On`. Aus diesem Grund wird empfohlen, dass Sie die Konvertierung, auf den Werten aus der Datenquelle abgerufen durchführen. Sie können die Werte in den Variablentyp expliziten Bereich aus der Datenquelle konvertieren, mithilfe der <xref:System.Linq.Enumerable.Cast%2A> Methode. Sie können auch die Werte, die im ausgewählten Umwandeln der `Select` -Klausel, um einen expliziten Typ, der den Typ der Bereichsvariablen unterscheidet. Diese Punkte werden in den folgenden Code veranschaulicht.  
  
 [!code-vb[VbLINQTypeRels#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_2.vb)]  
  
## <a name="queries-that-return-entire-elements-of-the-source-data"></a>Abfragen, die ganze Elemente der Quelldaten zurückgeben  
 Das folgende Beispiel zeigt eine [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Abfrageoperation, die eine Sequenz von Elementen, die aus den Quelldaten ausgewählt zurückgibt. Die Quelle `names`, enthält ein Array von Zeichenfolgen, und die Abfrageausgabe ist eine Sequenz mit Zeichenfolgen, die mit dem Buchstaben M beginnen.  
  
 [!code-vb[VbLINQTypeRels#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_3.vb)]  
  
 Dies entspricht dem folgenden Code, aber es ist sehr viel kürzer und einfacher zu schreiben. Abhängigkeit von lokalem Typrückschluss in Abfragen ist das bevorzugte Format in Visual Basic.  
  
 [!code-vb[VbLINQTypeRels#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_4.vb)]  
  
 Die folgenden Beziehungen vorhanden sind in den beiden vorherigen Codebeispielen, ob die Datentypen implizit oder explizit bestimmt werden.  
  
1.  Der Typ der Elemente in der Datenquelle `names`, ist der Typ der Bereichsvariablen, `name`, in der Abfrage.  
  
2.  Der Typ des Objekts, das ausgewählt ist, `name`, bestimmt den Typ der Abfragevariablen, `mNames`. Hier `name` ist eine Zeichenfolge, daher ist die Abfragevariable IEnumerable (Of String) in Visual Basic.  
  
3.  Die Abfrage, die in definierten `mNames` ausgeführt wird, der `For Each` Schleife. Die Schleife durchläuft das Ergebnis der Ausführung der Abfrage. Da `mNames`, wenn er ausgeführt wird, wird eine Sequenz von Zeichenfolgen, die Schleifeniterationsvariable zurückgegeben `nm`, ist auch eine Zeichenfolge.  
  
## <a name="queries-that-return-one-field-from-selected-elements"></a>Abfragen, die ein Feld aus ausgewählten Elementen zurückgeben  
 Das folgende Beispiel zeigt eine [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] Abfrageoperation, die eine Sequenz zurückgibt, enthält nur ein Teil jedes Element aus der Datenquelle ausgewählt. Die Abfrage nimmt eine Auflistung von `Customer` Objekte als Datenquelle und projiziert nur die `Name` im Ergebnis. Da der Kundenname eine Zeichenfolge ist, erzeugt die Abfrage eine Sequenz von Zeichenfolgen als Ausgabe.  
  
```vb  
' Method GetTable returns a table of Customer objects.  
Dim customers = db.GetTable(Of Customer)()  
Dim custNames = From cust In customers   
                Where cust.City = "London"   
                Select cust.Name  
  
For Each custName In custNames  
    Console.WriteLine(custName)  
Next  
```  
  
 Die Beziehungen zwischen den Variablen werden wie im Beispiel einfacher.  
  
1.  Der Typ der Elemente in der Datenquelle `customers`, ist der Typ der Bereichsvariablen, `cust`, in der Abfrage. In diesem Beispiel wird der Typ `Customer`.  
  
2.  Die `Select` Anweisung gibt die `Name` -Eigenschaft jedes `Customer` Objekt anstatt als ganzes Objekt. Da `Name` ist eine Zeichenfolge, die Abfragevariable `custNames`, werden nicht erneut IEnumerable (Of String), der `Customer`.  
  
3.  Da `custNames` stellt eine Sequenz von Zeichenfolgen, die `For Each` -Schleife Iterationsvariable, `custName`, muss eine Zeichenfolge sein.  
  
 Ohne lokaler Typrückschluss wäre das vorherige Beispiel umständlicher zum Schreiben von und zu verstehen, wie im folgenden Beispiel gezeigt.  
  
```vb  
' Method GetTable returns a table of Customer objects.  
 Dim customers As Table(Of Customer) = db.GetTable(Of Customer)()  
 Dim custNames As IEnumerable(Of String) =  
     From cust As Customer In customers   
     Where cust.City = "London"   
     Select cust.Name  
  
 For Each custName As String In custNames  
     Console.WriteLine(custName)  
 Next  
```  
  
## <a name="queries-that-require-anonymous-types"></a>Abfragen, die anonyme Typen erfordern  
 Das folgende Beispiel zeigt eine komplexere Situation. Im vorherigen Beispiel war es unpraktisch, Typen für alle Variablen explizit anzugeben. In diesem Beispiel ist es unmöglich. Anstelle des gesamten `Customer` Elemente aus der Datenquelle oder ein einzelnes Feld aus jedem Element der `Select` -Klausel in der diese Abfrage gibt zwei Eigenschaften des ursprünglichen `Customer` Objekt: `Name` und `City`. Als Antwort auf die `Select` -Klausel, definiert der Compiler einen anonymen Typ, der diese beiden Eigenschaften enthält. Das Ergebnis der Ausführung `nameCityQuery` in die `For Each` Schleife ist eine Auflistung von Instanzen des neuen anonymen Typs. Da der anonyme Typ keinen verwendbaren Namen aufweist, kann nicht, geben Sie den Typ des `nameCityQuery` oder `custInfo` explizit. D. h. mit einen anonymen Typ haben Sie keine Namen an, verwenden Sie anstelle von `String` in `IEnumerable(Of String)`. Weitere Informationen finden Sie unter [Anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
```vb  
' Method GetTable returns a table of Customer objects.  
Dim customers = db.GetTable(Of Customer)()  
Dim nameCityQuery = From cust In customers   
                    Where cust.City = "London"   
                    Select cust.Name, cust.City  
  
For Each custInfo In nameCityQuery  
    Console.WriteLine(custInfo.Name)  
Next  
```  
  
 Obwohl es nicht möglich, Typen für alle Variablen im vorherigen Beispiel anzugeben, bleiben die Beziehungen gleich.  
  
1.  Der Typ der Elemente in der Datenquelle ist erneut den Typ der Bereichsvariablen in der Abfrage. In diesem Beispiel `cust` ist eine Instanz der `Customer`.  
  
2.  Da die `Select` Anweisung erzeugt einen anonymen Typ, der die Abfragevariable `nameCityQuery`, implizit als anonymer Typ typisiert sein. Ein anonymer Typ hat keinen verwendbaren Namen und kann daher nicht explizit angegeben werden.  
  
3.  Der Typ der Iterationsvariablen in der `For Each` Schleife ist der anonyme Typ, der in Schritt 2 erstellt haben. Da der Typ keinen verwendbaren Namen aufweist, muss der Typ der Schleifenvariablen Iteration implizit bestimmt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Getting Started with LINQ in Visual Basic (Erste Schritte mit LINQ in Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [Anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [Abfragen](../../../../visual-basic/language-reference/queries/queries.md)
