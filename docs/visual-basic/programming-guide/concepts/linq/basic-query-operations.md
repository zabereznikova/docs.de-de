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
ms.openlocfilehash: efae72c65ad67b4a1b157b67dcc4d4d65f31f77b
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266377"
---
# <a name="basic-query-operations-visual-basic"></a>Grundlegende Abfrageoperationen (Visual Basic)
Dieses Thema enthält eine kurze Einführung in LINQ-Ausdrücke (Language-Integrated Query) in Visual Basic und zu einigen der typischen Arten von Vorgängen, die Sie in einer Abfrage ausführen. Weitere Informationen finden Sie in den folgenden Themen:  
  
 [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [Abfragen](../../../../visual-basic/language-reference/queries/index.md)  
  
 [Exemplarische Vorgehensweise: Schreiben von Abfragen in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a>Angeben der Datenquelle (Von)  
 In einer LINQ-Abfrage besteht der erste Schritt darin, die Datenquelle anzugeben, die Sie abfragen möchten. Daher steht `From` die Klausel in einer Abfrage immer an erster Stelle. Abfrageoperatoren wählen das Ergebnis basierend auf dem Typ der Quelle aus und formen es.  
  
 [!code-vb[VbLINQBasicOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#1)]  
  
 Die `From` Klausel gibt die `customers`Datenquelle , und `cust`eine *Bereichsvariable*an , . Die Bereichsvariable ist wie eine Schleifeniterationsvariable, mit der Ausnahme, dass in einem Abfrageausdruck keine tatsächliche Iteration stattfindet. Wenn die Abfrage ausgeführt wird, `For Each` oft mithilfe einer Schleife, dient die Bereichsvariable als Verweis auf jedes aufeinander folgende Element in `customers`. Es ist nicht notwendig, diese explizit anzugeben, da der Compiler den Typ von `cust` ableitet. Beispiele für Abfragen, die mit und ohne explizite Eingabe geschrieben wurden, finden Sie unter [Typbeziehungen in Abfragevorgängen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).  
  
 Weitere Informationen zur Verwendung `From` der Klausel in Visual Basic finden Sie unter [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md).  
  
## <a name="filtering-data-where"></a>Filtern von Daten (Wo)  
 Der wahrscheinlich häufigste Abfragevorgang ist das Anwenden eines Filters in Form eines booleschen Ausdrucks. Die Abfrage gibt dann nur die Elemente zurück, für die der Ausdruck wahr ist. Eine `Where` Klausel wird verwendet, um die Filterung durchzuführen. Der Filter gibt an, welche Elemente in der Datenquelle in die resultierende Sequenz eingeschlossen werden sollen. Im folgenden Beispiel sind nur Kunden enthalten, die eine Adresse in London haben.  
  
 [!code-vb[VbLINQBasicOps#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#2)]  
  
 Sie können logische Operatoren verwenden, z. `And` B. und `Or` zum Kombinieren von Filterausdrücken in einer `Where` Klausel. Verwenden Sie beispielsweise den folgenden Code, um nur Kunden zurückzugeben, die aus London stammen und devon nennen:  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"
```  
  
 Um Kunden aus London oder Paris zurückzugeben, verwenden Sie den folgenden Code:  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"
```  
  
 Weitere Informationen zur Verwendung `Where` der Klausel in Visual Basic finden Sie unter [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).  
  
## <a name="ordering-data-order-by"></a>Bestelldaten (Bestellung nach)  
 Es ist oft bequem, zurückgegebene Daten in einer bestimmten Reihenfolge zu sortieren. Die `Order By` Klausel bewirkt, dass die Elemente in der zurückgegebenen Sequenz nach einem oder nach bestimmten Feldern sortiert werden. Die folgende Abfrage sortiert z. B. die Ergebnisse basierend auf der `Name` Eigenschaft. Da `Name` es sich um eine Zeichenfolge handelt, werden die zurückgegebenen Daten alphabetisch sortiert, von A bis Z.  
  
 [!code-vb[VbLINQBasicOps#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#3)]  
  
 Wenn Sie die Ergebnisse andersherum, von Z bis A, sortieren möchten, können Sie die `Order By...Descending`-Klausel verwenden. Der Standardwert `Ascending` `Ascending` ist, wenn weder noch angegeben `Descending` ist.  
  
 Weitere Informationen zur Verwendung `Order By` der Klausel in Visual Basic finden Sie unter [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
## <a name="selecting-data-select"></a>Auswählen von Daten (Auswahl)  
 Die `Select` Klausel gibt die Form und den Inhalt zurückgegebener Elemente an. Sie können z. B. angeben, `Customer` ob die `Customer` Ergebnisse aus vollständigen Objekten, nur einer Eigenschaft, einer Teilmenge von Eigenschaften, einer Kombination von Eigenschaften aus verschiedenen Datenquellen oder einem neuen Ergebnistyp auf der Grundlage einer Berechnung bestehen. Wenn die `Select`-Klausel etwas anderes als eine Kopie des Quellelements erzeugt, wird dieser Vorgang als *Projektion* bezeichnet.  
  
 Um eine Auflistung abzurufen, die aus vollständigen `Customer` Objekten besteht, wählen Sie die Bereichsvariable selbst aus:  
  
 [!code-vb[VbLINQBasicOps#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#4)]  
  
 Wenn `Customer` es sich bei einer Instanz um ein großes Objekt mit vielen Feldern `cust.Name`handelt und Sie nur den Namen abrufen möchten, können Sie auswählen, wie im folgenden Beispiel gezeigt. Der lokale Typrückschluss erkennt, dass dadurch der `Customer` Ergebnistyp von einer Auflistung von Objekten in eine Auflistung von Zeichenfolgen geändert wird.  
  
 [!code-vb[VbLINQBasicOps#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#5)]  
  
 Um mehrere Felder aus der Datenquelle auszuwählen, haben Sie zwei Möglichkeiten:  
  
- Geben `Select` Sie in der Klausel die Felder an, die Sie in das Ergebnis einbeziehen möchten. Der Compiler definiert einen anonymen Typ, der diese Felder als Eigenschaften enthält. Weitere Informationen finden Sie unter [Anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
     Da es sich bei den zurückgegebenen Elementen im folgenden Beispiel um Instanzen eines anonymen Typs handelt, können Sie nicht auf den Typ anhand des Namens an anderer Stelle im Code verweisen. Der vom Compiler festgelegte Name für den Typ enthält Zeichen, die im normalen Visual Basic-Code ungültig sind. Im folgenden Beispiel handelt es sich bei den Elementen `londonCusts4` in der Auflistung, die von der Abfrage zurückgegeben wird, um Instanzen eines anonymen Typs.  
  
     [!code-vb[VbLINQBasicOps#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#6)]  
  
     Oder  
  
- Definieren Sie einen benannten Typ, der die bestimmten Felder enthält, die Sie in `Select` das Ergebnis einbeziehen möchten, und erstellen und initialisieren Sie Instanzen des Typs in der Klausel. Verwenden Sie diese Option nur, wenn Sie einzelne Ergebnisse außerhalb der Auflistung verwenden müssen, in der sie zurückgegeben werden, oder wenn Sie sie als Parameter in Methodenaufrufen übergeben müssen. Der Typ `londonCusts5` im folgenden Beispiel ist IEnumerable(Of NamePhone).  
  
     [!code-vb[VbLINQBasicOps#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#7)]  
  
     [!code-vb[VbLINQBasicOps#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#8)]  
  
 Weitere Informationen zur Verwendung `Select` der Klausel in Visual Basic finden Sie unter [Auswahlklausel](../../../../visual-basic/language-reference/queries/select-clause.md).  
  
## <a name="joining-data-join-and-group-join"></a>Verknüpfen von Daten (Join und Group Join)  
 Sie können mehr als eine `From` Datenquelle in der Klausel auf verschiedene Weise kombinieren. Der folgende Code verwendet z. B. zwei Datenquellen und kombiniert implizit Eigenschaften aus beiden im Ergebnis. Die Abfrage wählt Schüler aus, deren Nachnamen mit einem Vokal beginnen.  
  
 [!code-vb[VbLINQBasicOps#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#9)]  
  
> [!NOTE]
> Sie können diesen Code mit der Liste der Kursteilnehmer ausführen, die unter [Gewusst wie: Erstellen einer Liste von Elementen](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)erstellt wurden.  
  
 Das `Join` Schlüsselwort entspricht `INNER JOIN` einem in SQL. Es kombiniert zwei Auflistungen basierend auf übereinstimmenden Schlüsselwerten zwischen Elementen in den beiden Auflistungen. Die Abfrage gibt alle oder einen Teil der Auflistungselemente zurück, die übereinstimmende Schlüsselwerte aufweisen. Der folgende Code dupliziert z. B. die Aktion der vorherigen impliziten Verknüpfung.  
  
 [!code-vb[VbLINQBasicOps#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#10)]  
  
 `Group Join`kombiniert Auflistungen in einer einzigen hierarchischen Auflistung, genau wie in `LEFT JOIN` SQL. Weitere Informationen finden Sie unter [Join Clause](../../../../visual-basic/language-reference/queries/join-clause.md) and Group [Join Clause](../../../../visual-basic/language-reference/queries/group-join-clause.md).  
  
## <a name="grouping-data-group-by"></a>Gruppieren von Daten (Gruppe nach)  
 Sie können `Group By` eine Klausel hinzufügen, um die Elemente in einem Abfrageergebnis nach einem oder mehreren Feldern der Elemente zu gruppieren. Der folgende Code gruppiert die Schüler z. B. nach Klassenjahr.  
  
 [!code-vb[VbLINQBasicOps#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#11)]  
  
 Wenn Sie diesen Code mit der Liste der Kursteilnehmer ausführen, die unter [Gewusst wie: Erstellen einer Liste von Elementen](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)erstellt wurden, lautet die Ausgabe aus der `For Each` Anweisung:  
  
 Jahr: Junior  
  
 Tucker, Michael  
  
 Garcia, Hugo  
  
 Garcia  
  
 Tucker  
  
 Jahr: Senior  
  
 Omelchenko  
  
 Osada  
  
 Fakhouri  
  
 Feng  
  
 Adams  
  
 Jahr: Freshman  
  
 Mortensen, Sven  
  
 Garcia  
  
 Die im folgenden Code dargestellte Variante ordnet die Klassenjahre an und ordnet die Schüler dann innerhalb eines jeden Jahres nach Nachnamen an.  
  
 [!code-vb[VbLINQBasicOps#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#12)]  
  
 Weitere Informationen `Group By`zu finden Sie unter [Gruppennach-Klausel](../../../../visual-basic/language-reference/queries/group-by-clause.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Collections.Generic.IEnumerable%601>
- [Erste Schritte mit LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [Abfragen](../../../../visual-basic/language-reference/queries/index.md)
- [Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
