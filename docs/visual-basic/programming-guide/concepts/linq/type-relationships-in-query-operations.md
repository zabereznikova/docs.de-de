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
ms.openlocfilehash: 4dc5497f2e9bacac3062fde6e7dc48270697f1df
ms.sourcegitcommit: 7156c0b9e4ce4ce5ecf48ce3d925403b638b680c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2019
ms.locfileid: "58465216"
---
# <a name="type-relationships-in-query-operations-visual-basic"></a>Typbeziehungen in Abfrageoperationen (Visual Basic)
Im verwendeten Variablen [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] Abfrage Vorgänge sind stark typisiert und miteinander kompatibel sein müssen. Starke Typisierung wird in der Datenquelle, in der Abfrage selbst und in die Ausführung der Abfrage verwendet werden. Die folgende Abbildung Begriffe, die zum Beschreiben einer [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Abfrage. Weitere Informationen zu den Teilen einer Abfrage finden Sie unter [Grundlegende Abfrageoperationen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md).  
  
 ![Screenshot der Pseudocode-Abfrage mit hervorgehobenen Elementen.](./media/type-relationships-in-query-operations/linq-query-description-terms.png)  
  
 Der Typ der Bereichsvariablen in der Abfrage muss mit dem Typ der Elemente in der Datenquelle kompatibel sein. Der Typ der Abfragevariable muss kompatibel mit der Sequence-Element definiert, der `Select` Klausel. Zum Schluss der Typ der Elemente der Sequenz auch muss kompatibel mit dem Typ, der die Loop-Steuerelementvariable, die verwendet wird die `For Each` -Anweisung, die die Abfrage ausgeführt wird. Diese starke Typisierung erleichtert die Identifizierung von Typfehler zur Kompilierzeit.  
  
 Visual Basic erleichtert eine starke Typisierung durch die Implementierung von lokaler Typrückschluss, auch bekannt als *implizite Typisierung*. Funktion wird im vorherigen Beispiel verwendet, und sehen Sie in allen verwendet die [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Beispiele und Dokumentation. Der lokale Typrückschluss erfolgt in Visual Basic einfach mithilfe einer `Dim` -Anweisung ohne eine `As` Klausel. Im folgenden Beispiel `city` ist stark typisiert, als Zeichenfolge.  
  
 [!code-vb[VbLINQTypeRels#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#1)]  
  
> [!NOTE]
>  Lokaler Typrückschluss funktioniert nur, wenn `Option Infer` nastaven NA hodnotu `On`. Weitere Informationen finden Sie unter [Option Infer-Anweisung](../../../../visual-basic/language-reference/statements/option-infer-statement.md).  
  
 Selbst bei Verwendung von lokalem Typrückschluss in einer Abfrage gibt jedoch die gleichen typbeziehungen zwischen den Variablen in der Datenquelle, die Abfragevariable und die Abfrage Ausführungsschleife vorhanden. Es ist hilfreich, um einen grundlegenden Überblick über diese typbeziehungen zu erhalten, wenn Sie schreiben [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Abfragen oder Arbeiten mit die Beispiele und Codebeispiele in der Dokumentation.  
  
 Sie müssen möglicherweise einen expliziten Typ für eine Bereichsvariable angeben, die nicht den Typ der Datenquelle übereinstimmen. Sie können den Typ der Bereichsvariablen angeben, mit einem `As` Klausel. Dies führt jedoch zu einem Fehler, wenn die Konvertierung ist ein [einschränkende Konvertierung](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) und `Option Strict` nastaven NA hodnotu `On`. Aus diesem Grund empfehlen wir, dass Sie auf die Daten aus der Datenquelle abgerufenen Werte die Konvertierung auszuführen. Sie können die Werte in den Typ der expliziten Bereich aus der Datenquelle konvertieren, mit der <xref:System.Linq.Enumerable.Cast%2A> Methode. Sie können auch die Werte, die im ausgewählten Umwandeln der `Select` -Klausel, um einen expliziten Typ, der sich von dem Typ der Bereichsvariablen. Diese Punkte sind in den folgenden Code dargestellt.  
  
 [!code-vb[VbLINQTypeRels#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#4)]  
  
## <a name="queries-that-return-entire-elements-of-the-source-data"></a>Abfragen, die gesamte Elemente der Quelldaten zurückgibt  
 Das folgende Beispiel zeigt eine [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Abfrageoperation, die eine Sequenz von Elementen, die aus dem quelldatenspeicher ausgewählt zurückgibt. Die Quelle `names`, enthält ein Array von Zeichenfolgen, und die Ausgabe der Abfrage ist eine Sequenz, die mit Zeichenfolgen, die mit dem Buchstaben M beginnen.  
  
 [!code-vb[VbLINQTypeRels#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#2)]  
  
 Dies entspricht dem folgenden Code, aber es ist viel kürzer und einfacher zu schreiben. Abhängigkeit von den lokalen Typrückschluss in Abfragen ist das bevorzugte Format in Visual Basic.  
  
 [!code-vb[VbLINQTypeRels#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#3)]  
  
 Die folgenden Beziehungen vorhanden sowohl von den vorherigen Codebeispielen, ob die Typen implizit oder explizit bestimmt werden.  
  
1.  Der Typ der Elemente in der Datenquelle `names`, ist der Typ der Bereichsvariablen, `name`, in der Abfrage.  
  
2.  Der Typ des Objekts, das ausgewählt ist, `name`, bestimmt den Typ der Abfragevariablen, `mNames`. Hier `name` ist eine Zeichenfolge, daher ist die Abfragevariable IEnumerable (Of String) in Visual Basic.  
  
3.  Die Abfrage, die in definierten `mNames` ausgeführt wird, der `For Each` Schleife. Die Schleife ist das Ergebnis der Ausführung der Abfrage durchläuft. Da `mNames`, wenn er ausgeführt wird, gibt eine Sequenz von Zeichenfolgen, die Schleifenvariable Iteration `nm`, ist auch eine Zeichenfolge.  
  
## <a name="queries-that-return-one-field-from-selected-elements"></a>Abfragen, die ein Feld aus der ausgewählten Elemente zurückgeben.  
 Das folgende Beispiel zeigt eine [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] Abfrageoperation, die eine Sequenz zurückgibt, enthält nur einen Teil der einzelnen Elemente aus der Datenquelle ausgewählt. Die Abfrage nimmt eine Auflistung von `Customer` Objekte, die als Datenquelle aus, und nur Projekte die `Name` im Ergebnis. Da es sich bei der Namen des Kunden auf eine Zeichenfolge ist, erzeugt die Abfrage eine Sequenz von Zeichenfolgen als Ausgabe.  
  
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
  
 Die Beziehungen zwischen den Variablen werden wie in der einfacheres Beispiel.  
  
1.  Der Typ der Elemente in der Datenquelle `customers`, ist der Typ der Bereichsvariablen, `cust`, in der Abfrage. In diesem Beispiel ist, der Typ ist `Customer`.  
  
2.  Die `Select` Anweisung gibt die `Name` Eigenschaft der einzelnen `Customer` Objekt anstelle des gesamten Objekts. Da `Name` ist eine Zeichenfolge, die Abfragevariable `custNames`, werden nicht erneut IEnumerable (Of String), der `Customer`.  
  
3.  Da `custNames` stellt eine Sequenz von Zeichenfolgen, die `For Each` Iterationsvariable-Schleife, `custName`, muss eine Zeichenfolge sein.  
  
 Ohne lokaler Typrückschluss wäre das vorherige Beispiel umständlicher zum Schreiben und zu verstehen, wie im folgenden Beispiel gezeigt.  
  
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
  
## <a name="queries-that-require-anonymous-types"></a>Abfragen, die anonyme Typen erfordern.  
 Das folgende Beispiel zeigt eine komplexere Situation. Im vorherigen Beispiel war es unpraktisch, Typen für alle Variablen explizit angeben. In diesem Beispiel ist es unmöglich. Anstelle des gesamten `Customer` Elemente aus der Datenquelle oder ein einzelnes Feld aus jedem Element, das `Select` -Klausel in diese Abfrage gibt zwei Eigenschaften des ursprünglichen `Customer` Objekt: `Name` und `City`. Als Reaktion auf die `Select` -Klausel, definiert der Compiler einen anonymen Typ, der diese beiden Eigenschaften enthält. Das Ergebnis der Ausführung `nameCityQuery` in die `For Each` Schleife ist eine Auflistung von Instanzen der neuen anonymen Typ. Da der anonyme Typ keinen verwendbaren Namen hat, nicht möglich, geben Sie den Typ der `nameCityQuery` oder `custInfo` explizit. D. h. mit einem anonymen Typ, haben kein Typname, anstelle von `String` in `IEnumerable(Of String)`. Weitere Informationen finden Sie unter [Anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
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
  
 Obwohl es nicht möglich, geben Sie die Typen für alle Variablen im vorherigen Beispiel ist, bleibt die Beziehungen.  
  
1.  Der Typ der Elemente in der Datenquelle ist es den Typ der Bereichsvariablen in der Abfrage. In diesem Beispiel `cust` ist eine Instanz der `Customer`.  
  
2.  Da die `Select` Anweisung erstellt einen anonymen Typ der Abfragevariable `nameCityQuery`, als anonymer Typ implizit typisiert sein muss. Ein anonymer Typ hat keinen verwendbaren Namen, und kann daher nicht explizit angegeben werden.  
  
3.  Der Typ der Iterationsvariablen in der `For Each` Schleife ist der anonyme Typ, der in Schritt 2 erstellt haben. Da der Typ keinen verwendbaren Namen aufweist, muss implizit der Typ der Schleifenvariablen Iteration bestimmt werden.  
  
## <a name="see-also"></a>Siehe auch
- [Getting Started with LINQ in Visual Basic (Erste Schritte mit LINQ in Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [Anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Abfragen](../../../../visual-basic/language-reference/queries/index.md)
