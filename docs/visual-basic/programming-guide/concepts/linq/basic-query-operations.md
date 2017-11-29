---
title: Grundlegende Abfrageoperationen (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "37"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 794d77a18b50cc1667fddbad17c46735ae91be26
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="basic-query-operations-visual-basic"></a>Grundlegende Abfrageoperationen (Visual Basic)
Dieses Thema enthält eine kurze Einführung in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] Ausdrücke in Visual Basic und einige typischen Arten von Vorgängen, die Sie in einer Abfrage ausführen. Weitere Informationen finden Sie unter den folgenden Themen:  
  
 [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [Abfragen](../../../../visual-basic/language-reference/queries/queries.md)  
  
 [Exemplarische Vorgehensweise: Schreiben von Abfragen in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a>Angeben der Datenquelle (von)  
 In einem [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Abfrage ist der erste Schritt ist die Datenquelle an, die Sie abfragen möchten. Aus diesem Grund die `From` -Klausel in einer Abfrage immer zuerst eintritt. Abfrageoperatoren auswählen und das Ergebnis basierend auf dem Typ der Quelle Form.  
  
 [!code-vb[VbLINQBasicOps#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_1.vb)]  
  
 Die `From` -Klausel gibt die Datenquelle `customers`, und ein *Bereichsvariable*, `cust`. Die Bereichsvariable ist wie eine Schleifeniterationsvariable mit dem Unterschied, dass in einem Abfrageausdruck keine wirkliche Iteration stattfindet. Wenn die Abfrage ausgeführt wird, häufig mit einem `For Each` Schleife, die Bereichsvariable dient als Verweis auf jedes darauffolgende Element in `customers`. Es ist nicht notwendig, diese explizit anzugeben, da der Compiler den Typ von `cust` ableitet. Beispiele für Abfragen mit und ohne die explizite Typisierung geschrieben, finden Sie unter [Typbeziehungen in Abfrageoperationen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).  
  
 Weitere Informationen zur Verwendung der `From` -Klausel in Visual Basic finden Sie unter [From-Klausel](../../../../visual-basic/language-reference/queries/from-clause.md).  
  
## <a name="filtering-data-where"></a>Filtern von Daten (Where)  
 Wahrscheinlich wendet üblichste Abfrageoperation einen Filter in Form eines booleschen Ausdrucks. Die Abfrage gibt dann nur die Elemente, die für die der Ausdruck "true" aufweist. Ein `Where` -Klausel wird verwendet, um die Filterung auszuführen. Der Filter gibt die Elemente in der Datenquelle in der resultierenden Sequenz eingeschlossen werden sollen. Im folgenden Beispiel sind nur Kunden, die über eine Adresse in London enthalten.  
  
 [!code-vb[VbLINQBasicOps#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_2.vb)]  
  
 Sie können logische Operatoren wie z. B. `And` und `Or` zum Kombinieren von Filterausdrücken in eine `Where` Klausel. Damit nur die Kunden zurückgegeben werden, die von London stammen und Namen Devon, verwenden Sie beispielsweise den folgenden Code:  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"   
```  
  
 Um Kunden aus London oder Paris zurückzugeben, verwenden Sie den folgenden Code ein:  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"   
```  
  
 Weitere Informationen zur Verwendung der `Where` -Klausel in Visual Basic finden Sie unter [Where-Klausel](../../../../visual-basic/language-reference/queries/where-clause.md).  
  
## <a name="ordering-data-order-by"></a>Sortieren von Daten (Order By)  
 Es ist häufig sinnvoll, um die zurückgegebene Daten in einer bestimmten Reihenfolge zu sortieren. Die `Order By` -Klausel bewirkt, dass die Elemente in der zurückgegebenen Sequenz ein angegebenes Feld oder Felder sortiert werden. Beispielsweise sortiert die folgende Abfrage die Ergebnisse auf Grundlage der `Name` Eigenschaft. Da `Name` ist eine Zeichenfolge, die zurückgegebenen Daten alphabetisch sortiert, von A bis Z.  
  
 [!code-vb[VbLINQBasicOps#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_3.vb)]  
  
 Wenn Sie die Ergebnisse andersherum, von Z bis A, sortieren möchten, können Sie die `Order By...Descending`-Klausel verwenden. Die Standardeinstellung ist `Ascending` Wenn weder `Ascending` noch `Descending` angegeben ist.  
  
 Weitere Informationen zur Verwendung der `Order By` -Klausel in Visual Basic finden Sie unter [Order By-Klausel](../../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
## <a name="selecting-data-select"></a>Auswählen von Daten (auswählen)  
 Die `Select` -Klausel gibt die Form und die Inhalte der zurückgegebenen Elemente an. Sie können beispielsweise angeben, ob die Ergebnisse der vollständigen bestehen `Customer` Objekte aufweist, nur einen `Customer` Eigenschaft, die eine Teilmenge der Eigenschaften, die eine Kombination von Eigenschaften aus verschiedenen Datenquellen oder einem neuen Ergebnistyp auf einer Berechnung basiert. Wenn die `Select`-Klausel etwas anderes als eine Kopie des Quellelements erzeugt, wird dieser Vorgang als *Projektion* bezeichnet.  
  
 Abrufen eine Auflistung, aus denen vollständige besteht `Customer` Objekte, wählen Sie die Bereichsvariable selbst:  
  
 [!code-vb[VbLINQBasicOps#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_4.vb)]  
  
 Wenn eine `Customer` Instanz ist ein großes Objekt, das viele Felder verfügt und Sie abrufen möchten lediglich den Namen, können Sie auswählen `cust.Name`, wie im folgenden Beispiel gezeigt. Lokaler Typrückschluss erkennt, dass dies ändert sich den Ergebnistyp aus einer Auflistung von `Customer` -Objekten, die eine Auflistung von Zeichenfolgen.  
  
 [!code-vb[VbLINQBasicOps#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_5.vb)]  
  
 Um mehrere Felder aus der Datenquelle auswählen, haben Sie zwei Optionen:  
  
-   In der `Select` -Klausel, geben Sie die Felder im Resultset enthalten sein sollen. Der Compiler definieren einen anonymen Typ, der diese Felder als Eigenschaften verfügt. Weitere Informationen finden Sie unter [Anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
     Da die zurückgegebenen Elemente im folgenden Beispiel Instanzen eines anonymen Typs sind, können nicht Sie in den Typ an anderer Stelle im Code verweisen. Der vom Compiler festgelegte Name für den Typ enthält Zeichen, die in normaler Visual Basic-Code nicht gültig sind. Im folgenden Beispiel werden die Elemente in der Auflistung, die von der Abfrage zurückgegeben wird `londonCusts4` sind Instanzen eines anonymen Typs  
  
     [!code-vb[VbLINQBasicOps#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_6.vb)]  
  
     - oder -   
  
-   Definieren eines benannten Typs, die bestimmte Felder, die Sie verwenden möchten enthält, im Resultset einschließen, erstellen und initialisieren Sie die Instanzen des Typs in, der `Select` Klausel. Verwenden Sie diese Option nur, wenn Sie keine einzelne Ergebnisse außerhalb der Auflistung verwenden, in dem sie zurückgegeben werden, oder wenn Sie sie als Parameter in Methodenaufrufen übergeben. Der Typ des `londonCusts5` im folgenden Beispiel wird IEnumerable (Of NamePhone).  
  
     [!code-vb[VbLINQBasicOps#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_7.vb)]  
  
     [!code-vb[VbLINQBasicOps#8](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_8.vb)]  
  
 Weitere Informationen zur Verwendung der `Select` -Klausel in Visual Basic finden Sie unter [Select-Klausel](../../../../visual-basic/language-reference/queries/select-clause.md).  
  
## <a name="joining-data-join-and-group-join"></a>Verknüpfen von Daten (Join und Group Join)  
 Sie können mehr als eine Datenquelle im Kombinieren der `From` -Klausel auf unterschiedliche Weise. Beispielsweise wird der folgende Code verwendet zwei Datenquellen und implizit kombiniert Eigenschaften beide in das Ergebnis. Die Abfrage wählt Studenten, deren Nachnamen mit einem Vokal beginnen.  
  
 [!code-vb[VbLINQBasicOps#9](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_9.vb)]  
  
> [!NOTE]
>  Sie können diesen Code ausführen, mit der Liste der Schüler in erstellten [Vorgehensweise: Erstellen Sie eine Liste der Elemente](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).  
  
 Die `Join` -Schlüsselwort ist äquivalent zu einer `INNER JOIN` in SQL. Dabei werden zwei Auflistungen, die basierend auf übereinstimmenden Schlüsselwerten zwischen Elementen in die beiden Auflistungen. Die Abfrage gibt ganz oder teilweise die Elemente der Auflistung, die übereinstimmende Schlüsselwerte aufweisen. Im folgende Code wird z. B. die Aktion des vorherigen impliziten Joins dupliziert.  
  
 [!code-vb[VbLINQBasicOps#10](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_10.vb)]  
  
 `Group Join`Sammlungen in einer einzelnen hierarchischen Auflistung wie kombiniert eine `LEFT JOIN` in SQL. Weitere Informationen finden Sie unter [Join-Klausel](../../../../visual-basic/language-reference/queries/join-clause.md) und [Group Join-Klausel](../../../../visual-basic/language-reference/queries/group-join-clause.md).  
  
## <a name="grouping-data-group-by"></a>Gruppieren von Daten (Gruppieren nach)  
 Sie können Hinzufügen einer `Group By` -Klausel, um die Elemente in einem Abfrageergebnis gemäß einem oder mehreren Feldern der Elemente zu gruppieren. Im folgende Code werden z. B. Studenten nach Jahr Klasse gruppiert.  
  
 [!code-vb[VbLINQBasicOps#11](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_11.vb)]  
  
 Wenn Sie diesen Code mit der Liste der Schüler in erstellten ausführen [Vorgehensweise: Erstellen Sie eine Liste der Elemente](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), die Ausgabe der `For Each` -Anweisung ist:  
  
 Jahr: Junior  
  
 Tucker verbleibenden, Michael  
  
 Garcia Hugo  
  
 Garcia Sarah  
  
 Tucker und die verbleibenden Lance  
  
 Jahr: Senior  
  
 Omelchenko Svetlana  
  
 Osada Michiko  
  
 Fakhouri Fadi  
  
 Feng "," Hanying  
  
 Kiel, Oliver  
  
 Jahr: neunte Klasse  
  
 Mortensen Sven  
  
 Garcia Cesar  
  
 Die Variante, die im folgenden Code gezeigt Bestellungen der Jahre Klasse, und klicken Sie dann der Studenten innerhalb jedes Jahr nach dem Nachnamen sortiert.  
  
 [!code-vb[VbLINQBasicOps#12](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_12.vb)]  
  
 Weitere Informationen zu `Group By`, finden Sie unter [Group By-Klausel](../../../../visual-basic/language-reference/queries/group-by-clause.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Collections.Generic.IEnumerable%601>  
 [Getting Started with LINQ in Visual Basic (Erste Schritte mit LINQ in Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [Abfragen](../../../../visual-basic/language-reference/queries/queries.md)  
 [Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
