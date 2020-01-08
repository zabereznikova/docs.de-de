---
title: Grundlegende Abfragevorgänge
ms.date: 07/20/2015
helpviewer_keywords:
- data sources [LINQ in Visual Basic]
- Join clause [LINQ in Visual Basic]
- ordering data [LINQ in Visual Basic]
- projections [LINQ in Visual Basic]
- LINQ [Visual Basic], query operations
- Order By clause [LINQ in Visual Basic]
- joining data [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], basic operations
- selecting data [LINQ in Visual Basic]
- Group By clause [LINQ in Visual Basic]
- grouping data [LINQ in Visual Basic]
- Select clause [LINQ in Visual Basic]
ms.assetid: 1146f6d0-fcb8-4f4d-8223-c9db52620d21
ms.openlocfilehash: b9216dba23f49e4d9fd99687e38f5c13addde8fb
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636873"
---
# <a name="basic-query-operations-visual-basic"></a>Grundlegende Abfrageoperationen (Visual Basic)
Dieses Thema bietet eine kurze Einführung in LINQ (Language-Integrated Query)-Ausdrücke in Visual Basic sowie einige typische Arten von Vorgängen, die Sie in einer Abfrage ausführen. Weitere Informationen finden Sie unter den folgenden Themen:  
  
 [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [Abfragen](../../../../visual-basic/language-reference/queries/index.md)  
  
 [Exemplarische Vorgehensweise: Schreiben von Abfragen in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a>Angeben der Datenquelle (von)  
 In einer LINQ-Abfrage besteht der erste Schritt darin, die Datenquelle anzugeben, die Sie Abfragen möchten. Daher wird die `From`-Klausel in einer Abfrage immer zuerst angezeigt. Abfrage Operatoren wählen und strukturieren das Ergebnis basierend auf dem Typ der Quelle.  
  
 [!code-vb[VbLINQBasicOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#1)]  
  
 Die `From`-Klausel gibt die Datenquelle, `customers`und eine *Bereichs Variable `cust`an*. Die Bereichs Variable ist wie eine Schleifen Iterations Variable, mit dem Unterschied, dass in einem Abfrage Ausdruck keine tatsächliche Iterationen auftritt. Wenn die Abfrage ausgeführt wird (häufig mithilfe einer `For Each`-Schleife), fungiert die Bereichs Variable als Verweis auf jedes aufeinander folgende Element in `customers`. Es ist nicht notwendig, diese explizit anzugeben, da der Compiler den Typ von `cust` ableitet. Beispiele für Abfragen, die mit und ohne explizite Typisierung geschrieben wurden, finden Sie unter [Typbeziehungen in Abfrage Vorgängen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).  
  
 Weitere Informationen zum Verwenden der `From`-Klausel in Visual Basic finden Sie unter [from-Klausel](../../../../visual-basic/language-reference/queries/from-clause.md).  
  
## <a name="filtering-data-where"></a>Filtern von Daten (wobei)  
 Der häufigste Abfrage Vorgang ist wahrscheinlich das Anwenden eines Filters in Form eines booleschen Ausdrucks. Die Abfrage gibt dann nur die Elemente zurück, für die der Ausdruck "true" ist. Eine `Where`-Klausel wird verwendet, um die Filterung durchzuführen. Der Filter gibt an, welche Elemente in der Datenquelle in die resultierende Sequenz eingeschlossen werden sollen. Im folgenden Beispiel sind nur die Kunden enthalten, die eine Adresse in London haben.  
  
 [!code-vb[VbLINQBasicOps#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#2)]  
  
 Sie können logische Operatoren wie `And` und `Or` verwenden, um Filter Ausdrücke in einer `Where`-Klausel zu kombinieren. Verwenden Sie z. b. den folgenden Code, um nur die Kunden zurückzugeben, die aus London stammen und deren Name "Devon" ist:  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"   
```  
  
 Um Kunden aus London oder Paris zurückzugeben, verwenden Sie den folgenden Code:  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"   
```  
  
 Weitere Informationen zum Verwenden der `Where`-Klausel in Visual Basic finden Sie unter [WHERE-Klausel](../../../../visual-basic/language-reference/queries/where-clause.md).  
  
## <a name="ordering-data-order-by"></a>Sortieren von Daten (Order by)  
 Häufig ist es praktisch, die zurückgegebenen Daten in eine bestimmte Reihenfolge zu sortieren. Die `Order By`-Klausel bewirkt, dass die Elemente in der zurückgegebenen Sequenz nach einem angegebenen Feld oder Feldern sortiert werden. Beispielsweise sortiert die folgende Abfrage die Ergebnisse auf der Grundlage der `Name`-Eigenschaft. Da `Name` eine Zeichenfolge ist, werden die zurückgegebenen Daten alphabetisch sortiert, von a bis Z.  
  
 [!code-vb[VbLINQBasicOps#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#3)]  
  
 Wenn Sie die Ergebnisse andersherum, von Z bis A, sortieren möchten, können Sie die `Order By...Descending`-Klausel verwenden. Der Standardwert ist `Ascending`, wenn weder `Ascending` noch `Descending` angegeben ist.  
  
 Weitere Informationen zum Verwenden der `Order By`-Klausel in Visual Basic finden Sie unter [Order By-Klausel](../../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
## <a name="selecting-data-select"></a>Auswählen von Daten (auswählen)  
 Die `Select`-Klausel gibt das Formular und den Inhalt der zurückgegebenen Elemente an. Sie können z. b. angeben, ob die Ergebnisse aus kompletten `Customer` Objekten, nur einer `Customer` Eigenschaft, einer Teilmenge von Eigenschaften, einer Kombination von Eigenschaften aus verschiedenen Datenquellen oder einem neuen Ergebnistyp basierend auf einer Berechnung bestehen sollen. Wenn die `Select`-Klausel etwas anderes als eine Kopie des Quellelements erzeugt, wird dieser Vorgang als *Projektion* bezeichnet.  
  
 Wählen Sie zum Abrufen einer Sammlung, die aus Complete `Customer` Objekten besteht, die Bereichs Variable selbst aus:  
  
 [!code-vb[VbLINQBasicOps#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#4)]  
  
 Wenn es sich bei einer `Customer` Instanz um ein großes Objekt mit vielen Feldern handelt und Sie lediglich den Namen abrufen möchten, können Sie `cust.Name`auswählen, wie im folgenden Beispiel gezeigt. Der lokale Typrückschluss erkennt, dass dadurch der Ergebnistyp aus einer Auflistung von `Customer` Objekten in eine Auflistung von Zeichen folgen geändert wird.  
  
 [!code-vb[VbLINQBasicOps#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#5)]  
  
 Wenn Sie mehrere Felder aus der Datenquelle auswählen möchten, haben Sie zwei Möglichkeiten:  
  
- Geben Sie in der `Select`-Klausel die Felder an, die Sie in das Ergebnis einschließen möchten. Der Compiler definiert einen anonymen Typ, der diese Felder als Eigenschaften hat. Weitere Informationen finden Sie unter [Anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
     Da die zurückgegebenen Elemente im folgenden Beispiel Instanzen eines anonymen Typs sind, können Sie nicht an anderer Stelle im Code auf den Typ verweisen. Der vom Compiler angegebene Name für den Typ enthält Zeichen, die in normalem Visual Basic Code nicht gültig sind. Im folgenden Beispiel sind die Elemente in der Auflistung, die von der Abfrage in `londonCusts4` zurückgegeben werden, Instanzen eines anonymen Typs.  
  
     [!code-vb[VbLINQBasicOps#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#6)]  
  
     \- oder -  
  
- Definieren Sie einen benannten Typ, der die Felder enthält, die Sie in das Ergebnis einschließen möchten, und erstellen und initialisieren Sie Instanzen des Typs in der `Select`-Klausel. Verwenden Sie diese Option nur, wenn Sie einzelne Ergebnisse außerhalb der Sammlung verwenden müssen, in der Sie zurückgegeben werden, oder wenn Sie Sie als Parameter in Methoden aufrufen übergeben müssen. Der `londonCusts5` im folgenden Beispiel ist IEnumerable (of NamePhone).  
  
     [!code-vb[VbLINQBasicOps#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#7)]  
  
     [!code-vb[VbLINQBasicOps#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#8)]  
  
 Weitere Informationen zum Verwenden der `Select`-Klausel in Visual Basic finden [Sie unter SELECT-Klausel](../../../../visual-basic/language-reference/queries/select-clause.md).  
  
## <a name="joining-data-join-and-group-join"></a>Verknüpfen von Daten (Join und Group Join)  
 Sie können mehr als eine Datenquelle in der `From`-Klausel auf verschiedene Weise kombinieren. Im folgenden Code werden z. b. zwei Datenquellen verwendet und implizit Eigenschaften beider Datenquellen im Ergebnis kombiniert. Die Abfrage wählt Studenten aus, deren Nachnamen mit einem vowel beginnen.  
  
 [!code-vb[VbLINQBasicOps#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#9)]  
  
> [!NOTE]
> Sie können diesen Code mit der Liste der Studenten ausführen, die unter Gewusst [wie: Erstellen einer Liste von Elementen](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)erstellt wurden.  
  
 Das `Join`-Schlüsselwort entspricht einem `INNER JOIN` in SQL. Es kombiniert zwei Auflistungen basierend auf übereinstimmenden Schlüsselwerten zwischen Elementen in den beiden Auflistungen. Die Abfrage gibt alle Elemente oder Teile der Auflistungs Elemente zurück, die übereinstimmende Schlüsselwerte aufweisen. Mit dem folgenden Code wird beispielsweise die Aktion des vorherigen impliziten Joins dupliziert.  
  
 [!code-vb[VbLINQBasicOps#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#10)]  
  
 `Group Join` kombiniert Auflistungen wie eine `LEFT JOIN` in SQL in einer einzelnen hierarchischen Auflistung. Weitere Informationen finden Sie unter [Join-Klausel](../../../../visual-basic/language-reference/queries/join-clause.md) und [Group Join-Klausel](../../../../visual-basic/language-reference/queries/group-join-clause.md).  
  
## <a name="grouping-data-group-by"></a>Gruppieren von Daten (Gruppieren nach)  
 Sie können eine `Group By`-Klausel hinzufügen, um die Elemente in einem Abfrageergebnis nach einem oder mehreren Feldern der Elemente zu gruppieren. Im folgenden Code werden z. b. Schüler und Studenten nach Class Year gruppiert.  
  
 [!code-vb[VbLINQBasicOps#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#11)]  
  
 Wenn Sie diesen Code mithilfe der Liste der in Gewusst [wie: Erstellen einer Liste von Elementen](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)erstellten Studenten ausführen, lautet die Ausgabe der `For Each`-Anweisung wie folgt:  
  
 Jahr: Junior  
  
 Tucker, Michael  
  
 Garcia, Hugo  
  
 Garcia, Debra  
  
 Tucker, Lance  
  
 Jahr: Senior  
  
 Omeltschenko, Svetlana  
  
 Osada, Michiko  
  
 Fakhuuri, Fadi  
  
 Feng, hanying  
  
 Adams, Terry  
  
 Jahr: Freshman  
  
 Mortensen, Sven  
  
 Garcia, Cesar  
  
 Die im folgenden Code gezeigte Variation ordnet die Klassen Jahre an und ordnet die Schüler/Studenten innerhalb der einzelnen Jahre nach Nachnamen an.  
  
 [!code-vb[VbLINQBasicOps#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#12)]  
  
 Weitere Informationen zu `Group By`finden Sie unter [Group By-Klausel](../../../../visual-basic/language-reference/queries/group-by-clause.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Collections.Generic.IEnumerable%601>
- [Getting Started with LINQ in Visual Basic (Erste Schritte mit LINQ in Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [Abfragen](../../../../visual-basic/language-reference/queries/index.md)
- [Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
