---
title: Grundlegende Abfrageoperationen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
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
caps.latest.revision: 37
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 87ff9173b5ff72385c8ecdc3ff13735e7be2a21d
ms.lasthandoff: 03/13/2017

---
# <a name="basic-query-operations-visual-basic"></a>Grundlegende Abfrageoperationen (Visual Basic)
Dieses Thema enthält eine kurze Einführung in [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] Ausdrücke in Visual Basic und einige typische Arten von Vorgängen, die Sie in einer Abfrage ausführen. Weitere Informationen finden Sie unter den folgenden Themen:  
  
 [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [Abfragen](../../../../visual-basic/language-reference/queries/queries.md)  
  
 [Exemplarische Vorgehensweise: Schreiben von Abfragen in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a>Angeben der Datenquelle (von)  
 In einer [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] Abfrage der erste Schritt ist die Datenquelle an, die Sie abfragen möchten. Aus diesem Grund die `From` -Klausel in einer Abfrage immer zuerst eintritt. Abfrageoperatoren wählen und Form des Ergebnisses basierend auf den Typ der Quelle.  
  
 [!code-vb[VbLINQBasicOps&#1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_1.vb)]  
  
 Die `From` -Klausel gibt die Datenquelle `customers`, und ein *Bereichsvariable*, `cust`. Die Bereichsvariable ist wie eine Schleifeniterationsvariable, mit dem Unterschied, dass in einem Abfrageausdruck keine wirkliche Iteration stattfindet. Wenn die Abfrage ausgeführt wird, häufig mit einem `For Each` -Schleife, dient die Bereichsvariable als Verweis auf jedes darauf folgende Element in `customers`. Da der Compiler den Typ ableiten kann `cust`, Sie müssen nicht explizit angeben. Beispiele für Abfragen mit und ohne explizite Typisierung geschrieben wird, finden Sie unter [Typbeziehungen in Abfrageoperationen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).  
  
 Weitere Informationen zur Verwendung der `From` -Klausel in Visual Basic finden Sie unter [From-Klausel](../../../../visual-basic/language-reference/queries/from-clause.md).  
  
## <a name="filtering-data-where"></a>Filtern von Daten (Where)  
 Die üblichste Abfrageoperation ist wahrscheinlich ein Filters in Form eines booleschen Ausdrucks anwenden. Die Abfrage gibt dann nur die Elemente, für die der Ausdruck wahr ist. Ein `Where` -Klausel wird verwendet, um die Filterung auszuführen. Der Filter gibt die Elemente in der Datenquelle in der resultierenden Sequenz eingeschlossen. Im folgenden Beispiel werden nur die Kunden, die eine Adresse in London haben enthalten.  
  
 [!code-vb[VbLINQBasicOps&#2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_2.vb)]  
  
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
 Es ist häufig sinnvoll, um die zurückgegebene Daten in einer bestimmten Reihenfolge zu sortieren. Die `Order By` -Klausel bewirkt, dass die Elemente in der zurückgegebenen Sequenz ein angegebenes Feld oder Felder sortiert werden. Zum Beispiel sortiert die folgende Abfrage die Ergebnisse auf Grundlage der `Name` Eigenschaft. Da `Name` ist eine Zeichenfolge, die zurückgegebenen Daten alphabetisch sortiert, von A bis Z.  
  
 [!code-vb[VbLINQBasicOps&3;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_3.vb)]  
  
 Verwenden Sie die Ergebnisse in umgekehrter Reihenfolge von Z bis A Sortieren der `Order By...Descending` Klausel. Der Standardwert ist `Ascending` Wenn weder `Ascending` noch `Descending` angegeben ist.  
  
 Weitere Informationen zur Verwendung der `Order By` -Klausel in Visual Basic finden Sie unter [Order By-Klausel](../../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
## <a name="selecting-data-select"></a>Auswählen von Daten (Select)  
 Die `Select` -Klausel gibt die Form und Inhalt der zurückgegebenen Elemente an. Sie können beispielsweise angeben, ob die Ergebnisse der vollständigen bestehen `Customer` Objekte, von denen nur eine `Customer` -Eigenschaft, die eine Teilmenge der Eigenschaften, die eine Kombination von Eigenschaften aus verschiedenen Datenquellen oder einem neuen Ergebnistyp basierend auf der Berechnung. Wenn die `Select` -Klausel erzeugt etwas anderes als eine Kopie des Quellelements, der Vorgang wird aufgerufen, ein *Projektion*.  
  
 Um eine Auflistung abzurufen, der vollständigen besteht `Customer` Objekte, wählen Sie die Bereichsvariable selbst:  
  
 [!code-vb[VbLINQBasicOps&4;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_4.vb)]  
  
 Wenn ein `Customer` Instanz ist ein großes Objekt, das viele Felder verfügt und Sie abrufen möchten lediglich den Namen, können Sie auswählen `cust.Name`, wie im folgenden Beispiel gezeigt. Lokaler Typrückschluss erkennt, dass dadurch den Ergebnistyp aus einer Auflistung von `Customer` -Objekten, die eine Auflistung von Zeichenfolgen.  
  
 [!code-vb[VbLINQBasicOps&5;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_5.vb)]  
  
 Um mehrere Felder aus der Datenquelle auswählen, haben Sie zwei Optionen:  
  
-   In der `Select` -Klausel, geben Sie die Felder, die im Ergebnis enthalten sein sollen. Der Compiler definieren einen anonymen Typ, der diese Felder als Eigenschaften verfügt. Weitere Informationen finden Sie unter [anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
     Da die zurückgegebenen Elemente im folgenden Beispiel Instanzen eines anonymen Typs sind, verweisen nicht Sie auf den Typ anhand des Namens an anderer Stelle in Ihrem Code. Der vom Compiler festgelegte Name für den Typ enthält Zeichen, die in normalem Visual Basic-Code nicht gültig sind. Im folgenden Beispiel werden die Elemente in der Auflistung, die von der Abfrage im zurückgegebenen `londonCusts4` sind Instanzen eines anonymen Typs  
  
     [!code-vb[VbLINQBasicOps&6;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_6.vb)]  
  
     - oder -   
  
-   Definieren Sie einen benannten Typ, der die Felder, die Sie verwenden möchten enthält, in das Ergebnis einschließen, erstellen und initialisieren Sie die Instanzen des Typs in der `Select` Klausel. Verwenden Sie diese Option nur, wenn Sie einzelne Ergebnisse außerhalb der Auflistung verwendet, in der sie zurückgegeben werden, oder wenn Sie sie in Methodenaufrufe als Parameter übergeben. Der Typ des `londonCusts5` im folgenden Beispiel ist IEnumerable (Of NamePhone).  
  
     [!code-vb[VbLINQBasicOps&#7;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_7.vb)]  
  
     [!code-vb[VbLINQBasicOps&#8;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_8.vb)]  
  
 Weitere Informationen zur Verwendung der `Select` -Klausel in Visual Basic finden Sie unter [Select-Klausel](../../../../visual-basic/language-reference/queries/select-clause.md).  
  
## <a name="joining-data-join-and-group-join"></a>Verknüpfen von Daten (Join und Group Join)  
 Sie können mehr als eine Datenquelle in Kombinieren der `From` -Klausel auf mehrere Weisen. Im folgende Code wird beispielsweise verwendet zwei Datenquellen und implizit kombiniert Eigenschaften beide im Ergebnis. Die Abfrage wählt Studierende, deren Nachnamen mit einem Vokal beginnen.  
  
 [!code-vb[VbLINQBasicOps&#9;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_9.vb)]  
  
> [!NOTE]
>  Führen Sie diesen Code mit der erstellten Liste von Studierenden [Gewusst wie: Erstellen einer Liste von Elementen](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).  
  
 Die `Join` -Schlüsselwort ist äquivalent zu einer `INNER JOIN` in SQL. Kombiniert zwei Sammlungen basierend auf übereinstimmenden Schlüsselwerten zwischen Elementen in beiden Auflistungen. Die Abfrage gibt alle oder einen Teil der Elemente der Auflistung, die übereinstimmende Schlüsselwerte aufweisen. Im folgende Code wird z. B. die Aktion des vorherigen impliziten Joins dupliziert.  
  
 [!code-vb[VbLINQBasicOps&#10;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_10.vb)]  
  
 `Group Join`Sammlungen in einer einzelnen hierarchischen Auflistung wie kombiniert eine `LEFT JOIN` in SQL. Weitere Informationen finden Sie unter [Join-Klausel](../../../../visual-basic/language-reference/queries/join-clause.md) und [Group Join-Klausel](../../../../visual-basic/language-reference/queries/group-join-clause.md).  
  
## <a name="grouping-data-group-by"></a>Gruppieren von Daten (Group By)  
 Sie können Hinzufügen einer `Group By` -Klausel, um die Elemente in einem Abfrageergebnis gemäß einem oder mehreren Feldern der Elemente zu gruppieren. Im folgende Code werden z. B. Studierenden Klasse Jahr gruppiert.  
  
 [!code-vb[VbLINQBasicOps&#11;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_11.vb)]  
  
 Wenn Sie diesen Code mit der Liste der Schüler in erstellte ausführen [wie: Erstellen einer Liste von Elementen](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), die Ausgabe der `For Each` -Anweisung ist:  
  
 Jahr: Junior  
  
 Tucker, Michael  
  
 Garcia, Hugo  
  
 Garcia, Sarah  
  
 Tucker Lance  
  
 Jahr: Senior  
  
 Omelchenko Svetlana  
  
 Osada Michiko  
  
 Fakhouri Fadi  
  
 Feng Heiko  
  
 Adams, Thomas  
  
 Jahr: neunte Klasse  
  
 Mortensen Sven  
  
 Garcia, Cesar  
  
 Die Variante, die im folgenden Code gezeigt Jahrgänge sortiert und anschließend die Kursteilnehmer innerhalb jedes Jahres nach Nachnamen.  
  
 [!code-vb[VbLINQBasicOps&#12;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_12.vb)]  
  
 Weitere Informationen zu `Group By`, finden Sie unter [Group By-Klausel](../../../../visual-basic/language-reference/queries/group-by-clause.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>   
 [Erste Schritte mit LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Abfragen](../../../../visual-basic/language-reference/queries/queries.md)   
 [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
