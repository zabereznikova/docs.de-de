---
title: "Grundlegende Abfrageoperationen (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Datenquellen [LINQ in Visual Basic]"
  - "JOIN-Klausel [LINQ in Visual Basic]"
  - "Sortieren von Daten [LINQ in Visual Basic]"
  - "Projektionen [LINQ in Visual Basic]"
  - "LINQ [Visual Basic], Abfrageoperationen"
  - "ORDER BY-Klausel [LINQ in Visual Basic]"
  - "Verknüpfen von Daten [LINQ in Visual Basic]"
  - "Abfragen [LINQ in Visual Basic], grundlegende Vorgänge"
  - "Auswählen von Daten [LINQ in Visual Basic]"
  - "GROUP BY-Klausel [LINQ in Visual Basic]"
  - "Gruppieren von Daten [LINQ in Visual Basic]"
  - "SELECT-Klausel [LINQ in Visual Basic]"
ms.assetid: 1146f6d0-fcb8-4f4d-8223-c9db52620d21
caps.latest.revision: 37
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 35
---
# Grundlegende Abfrageoperationen (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Dieses Thema enthält eine kurze Einführung in [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext-md.md)]\-Ausdrücke in Visual Basic und in einige der typischen Vorgänge bei einer Abfrage.  Weitere Informationen finden Sie unter den folgenden Themen:  
  
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [Queries](../../../../visual-basic/language-reference/queries/queries.md)  
  
 [Exemplarische Vorgehensweise: Schreiben von Abfragen in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## Angeben der Datenquelle \(From\)  
 In einer [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]\-Abfrage ist der erste Schritt das Angeben der Datenquelle, für die eine Abfrage durchgeführt werden soll.  Dadurch wechselt die `From`\-Klausel in einer Abfrage immer zuerst. Abfrageoperatoren wählen aus und entstehende das Ergebnis auf dem Typ der Quelle.  
  
 [!code-vb[VbLINQBasicOps#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_1.vb)]  
  
 Die `From`\-Klausel gibt die Datenquelle, `customers` und die *Bereichsvariable* `cust` an.  Die Bereichsvariable ist vergleichbar mit einer Schleifeniterationsvariablen, mit dem Unterschied, dass in einem Abfrageausdruck keine wirkliche Iteration stattfindet.  Wenn die Abfrage ausgeführt wird, häufig durch Verwendung einer `For Each`\-Schleife, dient die Bereichsvariable als Verweis auf jedes darauf folgende Element in `customers`.  Da der Compiler den Typ von `cust` per Rückschluss ableiten kann, müssen Sie es nicht explizit angeben.  Beispiele für Abfragen, die mit und ohne explizite Typisierung geschrieben werden, finden Sie unter [Type Relationships in Query Operations \(Visual Basic\)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).  
  
 Weitere Informationen zur Verwendung der `From`\-Klausel in Visual Basic finden Sie unter [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md).  
  
## Filtern von Daten \(Where\)  
 Die wahrscheinlich üblichste Abfrageoperation ist das Anwenden eines Filters in Form eines booleschen Ausdrucks.  Die Abfrage gibt dann nur jene Elemente zurück, für die der Ausdruck den Wert true hat.  Eine `Where`\-Klausel wird verwendet, um die Filterung auszuführen.  Der Filter gibt an, welche Elemente in der Datenquelle in der resultierenden Sequenz eingeschlossen werden sollen.  Im folgenden Beispiel sind nur jene Kunden enthalten, die eine Adresse in London haben.  
  
 [!code-vb[VbLINQBasicOps#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_2.vb)]  
  
 Sie können logische Operatoren wie `And` and `Or` zum Kombinieren von Filterausdrücken in einer `Where`\-Klausel verwenden.  Um beispielsweise nur die Kunden zurückzugeben, die aus London stammen und den Namen Devon haben, verwenden Sie folgenden Code:  
  
```vb#  
Where cust.City = "London" And cust.Name = "Devon"   
```  
  
 Um Kunden aus London oder Paris zurückzugeben, verwenden Sie den folgenden Code:  
  
```vb#  
Where cust.City = "London" Or cust.City = "Paris"   
```  
  
 Weitere Informationen zur Verwendung der `Where`\-Klausel in Visual Basic finden Sie unter [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).  
  
## Sortieren von Daten \(Order By\)  
 Es ist oft praktisch, zurückgegebene Daten in einer bestimmten Reihenfolge zu sortieren.  Mit der `Order By`\-Klausel können die Elemente in der zurückgegebenen Sequenz anhand eines bestimmten Felds oder anhand bestimmter Felder sortiert werden.  Zum Beispiel sortiert die folgende Abfrage die Ergebnisse auf Grundlage der `Name`\-Eigenschaft.  Da `Name` eine Zeichenfolge ist, werden die zurückgegebenen Daten alphabetisch sortiert, von A bis Z.  
  
 [!code-vb[VbLINQBasicOps#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_3.vb)]  
  
 Um die Ergebnisse in umgekehrter Reihenfolge zu sortieren \(von Z bis A\), verwenden Sie die `Order By...Descending`\-Klausel.  Der Standard ist `Ascending`, wenn weder `Ascending` noch `Descending` angegeben ist.  
  
 Weitere Informationen zur Verwendung der `Order By`\-Klausel in Visual Basic finden Sie unter [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
## Auswählen von Daten \(Select\)  
 Die `Select`\-Klausel gibt die Form und den Inhalt zurückgegebener Elemente an.  Sie können beispielsweise angeben, ob Ihre Ergebnisse aus vollständigen `Customer`\-Objekten bestehen, nur einer `Customer`\-Eigenschaft, einer Teilmenge von Eigenschaften, einer Kombination von Eigenschaften aus verschiedenen Datenquellen oder einem neuen Ergebnistyp, der auf einer Berechnung basiert.  Wenn die `Select`\-Klausel ein anderes Ergebnis als eine Kopie des Quellelements zurückgibt, wird der Vorgang als *Projektion* bezeichnet.  
  
 Um eine Auflistung abzurufen, die aus vollständigen `Customer`\-Objekten besteht, wählen Sie die Bereichsvariable selbst aus:  
  
 [!code-vb[VbLINQBasicOps#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_4.vb)]  
  
 Wenn die `Customer`\-Instanz ein großes Objekt mit vielen Feldern ist und Sie nur den Namen abrufen möchten, können Sie `cust.Name` auswählen, wie im folgenden Beispiel gezeigt.  Der lokale Typrückschluss erkennt, dass dies den Ergebnistyp aus einer Auflistung von `Customer`\-Objekten in eine Auflistung von Zeichenfolgen ändert.  
  
 [!code-vb[VbLINQBasicOps#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_5.vb)]  
  
 Um mehrere Felder aus der Datenquelle auszuwählen, haben Sie zwei Möglichkeiten:  
  
-   Geben Sie in der `Select`\-Klausel die Felder an, die Sie in das Ergebnis einschließen möchten.  Der Compiler definiert einen anonymen Typ, der über diese Felder als Eigenschaften verfügt.  Weitere Informationen finden Sie unter [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
     Da die zurückgegebenen Elemente im folgenden Beispiel Instanzen eines anonymen Typs sind, können Sie auf den Typ an anderer Stelle im Code nicht durch den Namen verweisen.  Der vom Compiler festgelegte Name für den Typ enthält Zeichen, die in normalem Visual Basic\-Code nicht gültig sind.  Im folgenden Beispiel sind die Elemente in der Auflistung, die von der Abfrage in `londonCusts4` zurückgegeben werden, Instanzen eines anonymen Typs.  
  
     [!code-vb[VbLINQBasicOps#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_6.vb)]  
  
     \- oder \-  
  
-   Definieren Sie einen benannten Typ, der die Felder enthält, die Sie in das Ergebnis einschließen möchten, und erstellen und initialisieren Sie die Instanzen des Typs in der `Select`\-Klausel.  Verwenden Sie diese Option nur, wenn Sie einzelne Ergebnisse außerhalb der Auflistung verwenden möchten, in der sie zurückgegeben werden, oder wenn Sie sie als Parameter in Methodenaufrufen übergeben müssen.  Der Typ von `londonCusts5` im folgenden Beispiel ist IEnumerable\(Of NamePhone\).  
  
     [!code-vb[VbLINQBasicOps#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_7.vb)]  
  
     [!code-vb[VbLINQBasicOps#8](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_8.vb)]  
  
 Weitere Informationen zur Verwendung der `Select`\-Klausel in Visual Basic finden Sie unter [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).  
  
## Verknüpfen von Daten \(Join und Group Join\)  
 Sie können mehr als eine Datenquelle in der `From`\-Klausel auf mehrere Weisen kombinieren.  Der folgende Code verwendet beispielsweise zwei Datenquellen und kombiniert deren Eigenschaften indirekt im Ergebnis.  Die Abfrage wählt Studierende aus, deren Nachnamen mit einem Vokal beginnen.  
  
 [!code-vb[VbLINQBasicOps#9](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_9.vb)]  
  
> [!NOTE]
>  Sie können diesen Code mit der in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md) erstellten Liste von Studierenden ausführen.  
  
 Das `Join`\-Schlüsselwort ist äquivalent zu einem `INNER JOIN`\-Schlüsselwort in SQL.  Es kombiniert zwei Auflistungen auf Grundlage von übereinstimmenden Schlüsselwerten in den beiden Auflistungen.  Die Abfrage gibt alle oder nur einen Teil der Auflistungselemente zurück, die übereinstimmende Schlüsselwerte aufweisen.  Im folgenden Code wird z. B. die Aktion des vorherigen impliziten Joins dupliziert.  
  
 [!code-vb[VbLINQBasicOps#10](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_10.vb)]  
  
 `Group Join` kombiniert Auflistungen in eine einzelne hierarchische Auflistung, genau wie ein `LEFT JOIN`\-Schlüsselwort in SQL.  Weitere Informationen finden Sie unter [Join Clause](../../../../visual-basic/language-reference/queries/join-clause.md) und unter [Group Join Clause](../../../../visual-basic/language-reference/queries/group-join-clause.md).  
  
## Gruppieren von Daten \(Group By\)  
 Sie können eine `Group By`\-Klausel hinzufügen, um die Elemente in einem Abfrageergebnis gemäß einem oder mehreren Feldern von Elementen zu gruppieren.  Zum Beispiel werden mit dem folgenden Code Studierende anhand des Jahrgangs gruppiert.  
  
 [!code-vb[VbLINQBasicOps#11](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_11.vb)]  
  
 Wenn Sie diesen Code mit der in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md) erstellten Liste der Studierenden ausführen, lautet die Ausgabe der `For Each`\-Anweisung:  
  
 Jahr: Junior  
  
 Tucker, Michael  
  
 Garcia, Hugo  
  
 Garcia, Debra  
  
 Tucker, Lance  
  
 Jahr: Senior  
  
 Omelchenko, Svetlana  
  
 Osada, Michiko  
  
 Fakhouri, Fadi  
  
 Feng, Hanying  
  
 Adams, Terry  
  
 Jahr: Freshman \(Student im ersten Jahr\)  
  
 Mortensen, Sven  
  
 Garcia, Cesar  
  
 Mit der folgenden Codevariation werden die Jahrgänge sortiert und anschließend die Studierenden innerhalb des Jahrgangs nach Nachname.  
  
 [!code-vb[VbLINQBasicOps#12](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_12.vb)]  
  
 Weitere Informationen über `Group By` finden Sie unter [Group By\-Klausel](../../../../visual-basic/language-reference/queries/group-by-clause.md).  
  
## Siehe auch  
 <xref:System.Collections.Generic.IEnumerable%601>   
 [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Queries](../../../../visual-basic/language-reference/queries/queries.md)   
 [Standard Query Operators Overview](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Basic LINQ Query Operations](../../../../csharp/programming-guide/concepts/linq/basic-linq-query-operations.md)