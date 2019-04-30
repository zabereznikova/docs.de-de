---
title: Grundlegende Abfrageoperationen (Visual Basic)
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
ms.openlocfilehash: ed5ed56366911c3676c4413711207ac0a8f85765
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61925647"
---
# <a name="basic-query-operations-visual-basic"></a>Grundlegende Abfrageoperationen (Visual Basic)
Dieses Thema enthält eine kurze Einführung in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] Ausdrücke in Visual Basic, und klicken Sie auf einige der geläufigsten Vorgänge, die Sie in einer Abfrage ausführen. Weitere Informationen finden Sie unter den folgenden Themen:  
  
 [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [Abfragen](../../../../visual-basic/language-reference/queries/index.md)  
  
 [Exemplarische Vorgehensweise: Schreiben von Abfragen in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a>Angeben der Datenquelle (von)  
 In einem [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Abfrage wird der erste Schritt ist die Datenquelle an, die Sie abfragen möchten. Aus diesem Grund die `From` -Klausel in einer Abfrage immer zuerst eintritt. Abfrageoperatoren wählen und das Ergebnis basierend auf dem Typ der Quelle der Form.  
  
 [!code-vb[VbLINQBasicOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#1)]  
  
 Die `From` -Klausel gibt die Datenquelle `customers`, und ein *Bereichsvariable*, `cust`. Die Bereichsvariable ist wie eine Schleifeniterationsvariable, mit dem Unterschied, dass in einem Abfrageausdruck keine Iterationen auftritt. Wenn die Abfrage ausgeführt wird, häufig mit einem `For Each` Schleife, dient die Bereichsvariable als Verweis auf jedes darauffolgende Element in `customers`. Es ist nicht notwendig, diese explizit anzugeben, da der Compiler den Typ von `cust` ableitet. Beispiele für Abfragen mit und ohne die explizite Typisierung geschrieben wird, finden Sie unter [Typbeziehungen in Abfrageoperationen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).  
  
 Weitere Informationen zur Verwendung der `From` -Klausel in Visual Basic finden Sie unter [From-Klausel](../../../../visual-basic/language-reference/queries/from-clause.md).  
  
## <a name="filtering-data-where"></a>Filtern von Daten ()  
 Wahrscheinlich ist der üblichste Abfrageoperation einen Filter in Form eines booleschen Ausdrucks anwenden. Die Abfrage gibt dann nur die Elemente, die für die der Ausdruck wahr ist. Ein `Where` -Klausel wird verwendet, die gefiltert werden. Der Filter gibt die Elemente in der Datenquelle in der resultierenden Sequenz eingeschlossen werden sollen. Im folgenden Beispiel sind nur die Kunden, die eine Londoner Adresse haben, enthalten.  
  
 [!code-vb[VbLINQBasicOps#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#2)]  
  
 Sie können logische Operatoren wie z. B. `And` und `Or` zum Kombinieren von Filterausdrücken in einer `Where` Klausel. Um nur die Kunden zurückzugeben, angehören, die aus London und Namen Devon, verwenden Sie z. B. den folgenden Code:  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"   
```  
  
 Um Kunden aus London oder Paris zurückzugeben, verwenden Sie den folgenden Code:  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"   
```  
  
 Weitere Informationen zur Verwendung der `Where` -Klausel in Visual Basic finden Sie unter [Where-Klausel](../../../../visual-basic/language-reference/queries/where-clause.md).  
  
## <a name="ordering-data-order-by"></a>Sortieren von Daten (Order By)  
 Häufig ist es sinnvoll, um die zurückgegebenen Daten in einer bestimmten Reihenfolge zu sortieren. Die `Order By` -Klausel bewirkt, dass die Elemente in der zurückgegebenen Sequenz ein angegebenes Feld oder Felder sortiert werden. Beispielsweise sortiert die folgende Abfrage die Ergebnisse auf Grundlage der `Name` Eigenschaft. Da `Name` ist eine Zeichenfolge, die zurückgegebenen Daten werden alphabetisch von A bis Z sortiert werden.  
  
 [!code-vb[VbLINQBasicOps#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#3)]  
  
 Wenn Sie die Ergebnisse andersherum, von Z bis A, sortieren möchten, können Sie die `Order By...Descending`-Klausel verwenden. Der Standardwert ist `Ascending` Wenn weder `Ascending` noch `Descending` angegeben ist.  
  
 Weitere Informationen zur Verwendung der `Order By` -Klausel in Visual Basic finden Sie unter [Order By-Klausel](../../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
## <a name="selecting-data-select"></a>Auswählen von Daten (auswählen)  
 Die `Select` -Klausel gibt an, die Form und den Inhalt der zurückgegebenen Elemente. Beispielsweise können Sie angeben, ob Ihre Ergebnisse aus vollständigen bestehen `Customer` Objekten, die nur eine `Customer` -Eigenschaft, die eine Teilmenge der Eigenschaften, die eine Kombination von Eigenschaften aus verschiedenen Datenquellen oder eine neue Art von Ergebnis auf einer Berechnung basiert. Wenn die `Select`-Klausel etwas anderes als eine Kopie des Quellelements erzeugt, wird dieser Vorgang als *Projektion* bezeichnet.  
  
 Zum Abrufen einer Auflistung, der vollständige besteht `Customer` Objekte, wählen Sie die Bereichsvariable selbst:  
  
 [!code-vb[VbLINQBasicOps#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#4)]  
  
 Wenn eine `Customer` Instanz ist ein großes Objekt, das über viele Felder verfügt, und alles, was Sie abrufen möchten ist der Name, können Sie auswählen `cust.Name`, wie im folgenden Beispiel gezeigt. Lokaler Typrückschluss erkennt, dass sich dies ändert sich den Ergebnistyp aus einer Auflistung von `Customer` Objekte an eine Auflistung von Zeichenfolgen.  
  
 [!code-vb[VbLINQBasicOps#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#5)]  
  
 Um mehrere Felder aus der Datenquelle auswählen, haben Sie zwei Möglichkeiten:  
  
- In der `Select` -Klausel, geben Sie die Felder im Resultset enthalten sein sollen. Der Compiler definieren einen anonymen Typ, der diese Felder als Eigenschaften verfügt. Weitere Informationen finden Sie unter [Anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
     Da die zurückgegebenen Elemente im folgenden Beispiel Instanzen eines anonymen Typs sind, können nicht Sie in den Typ anhand des Namens an anderer Stelle in Ihrem Code verweisen. Der Compiler festgelegten Namen für den Typ enthält Zeichen, die in normalen Visual Basic-Code nicht gültig sind. Im folgenden Beispiel die Elemente in der Auflistung, die von der Abfrage in zurückgegeben wird `londonCusts4` sind Instanzen eines anonymen Typs  
  
     [!code-vb[VbLINQBasicOps#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#6)]  
  
     - oder -   
  
- Definieren Sie einen benannten Typ, der die Felder, die Sie verwenden möchten enthält, im Resultset einschließen, erstellen und initialisieren Sie die Instanzen des Typs in der `Select` Klausel. Verwenden Sie diese Option nur, wenn Sie keine einzelne Ergebnisse außerhalb der Auflistung verwenden, in dem sie zurückgegeben werden, oder wenn Sie sie in Methodenaufrufen als Parameter übergeben. Der Typ des `londonCusts5` im folgenden Beispiel wird die IEnumerable (Of NamePhone).  
  
     [!code-vb[VbLINQBasicOps#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#7)]  
  
     [!code-vb[VbLINQBasicOps#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#8)]  
  
 Weitere Informationen zur Verwendung der `Select` -Klausel in Visual Basic finden Sie unter [Select-Klausel](../../../../visual-basic/language-reference/queries/select-clause.md).  
  
## <a name="joining-data-join-and-group-join"></a>Verknüpfen von Daten ("Join" und "Group Join")  
 Sie können mehr als eine Datenquelle im Kombinieren der `From` Klausel auf verschiedene Weise. Beispielsweise wird der folgende Code verwendet zwei Datenquellen und implizit kombiniert Eigenschaften beide im Ergebnis. Die Abfrage wählt die Schüler/Studenten, deren Nachname mit einem Vokal beginnen.  
  
 [!code-vb[VbLINQBasicOps#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#9)]  
  
> [!NOTE]
>  Sie können diesen Code ausführen, mit der Liste der Schüler/Studenten, die im erstellten [Vorgehensweise: Erstellen Sie eine Liste von Elementen](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).  
  
 Die `Join` -Schlüsselwort ist äquivalent zu einer `INNER JOIN` in SQL. Es werden zwei Auflistungen, die basierend auf übereinstimmenden Schlüsselwerten zwischen Elementen in die beiden Auflistungen kombiniert. Die Abfrage gibt alle oder einen Teil der Elemente der Auflistung, die übereinstimmenden Schlüsselwerten. Der folgende Code wird z. B. die Aktion der vorherigen implizite Verknüpfung dupliziert.  
  
 [!code-vb[VbLINQBasicOps#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#10)]  
  
 `Group Join` Sammlungen in einer einzelnen hierarchischen Auflistung wie kombiniert eine `LEFT JOIN` in SQL. Weitere Informationen finden Sie unter [Join-Klausel](../../../../visual-basic/language-reference/queries/join-clause.md) und [Group Join-Klausel](../../../../visual-basic/language-reference/queries/group-join-clause.md).  
  
## <a name="grouping-data-group-by"></a>Gruppieren von Daten (Gruppieren nach)  
 Sie können Hinzufügen einer `Group By` -Klausel, um die Elemente in einem Abfrageergebnis nach einem oder mehreren Feldern der Elemente zu gruppieren. Im folgende Code werden z. B. Schüler/Studenten nach Klasse Jahr gruppiert.  
  
 [!code-vb[VbLINQBasicOps#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#11)]  
  
 Wenn Sie diesen Code mithilfe der Liste der Schüler/Studenten, die im erstellten ausführen [Vorgehensweise: Erstellen Sie eine Liste von Elementen](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), die aus der `For Each` -Anweisung ist:  
  
 Jahr: Junior  
  
 Tucker, Michael  
  
 Garcia, Hugo  
  
 Garcia, Debra  
  
 Tucker, Lance  
  
 Jahr: Senior  
  
 Omelchenko, Svetlana  
  
 Osada, Michiko  
  
 Fakhouri, Fadi  
  
 Feng "," Hanying  
  
 Adams, Terry  
  
 Jahr: Neunte Klasse  
  
 Mortensen, Sven  
  
 Garcia, Cesar  
  
 Die Variante, die in den folgenden Code gezeigt Bestellungen der Jahre Klasse, und klicken Sie dann die Schüler/Studenten innerhalb jedes Jahres nach dem Nachnamen sortiert.  
  
 [!code-vb[VbLINQBasicOps#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#12)]  
  
 Weitere Informationen zu `Group By`, finden Sie unter [Group By-Klausel](../../../../visual-basic/language-reference/queries/group-by-clause.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Collections.Generic.IEnumerable%601>
- [Getting Started with LINQ in Visual Basic (Erste Schritte mit LINQ in Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [Abfragen](../../../../visual-basic/language-reference/queries/index.md)
- [Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
