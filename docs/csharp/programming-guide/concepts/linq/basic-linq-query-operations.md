---
title: "Basic LINQ Query Operations (C#) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "orderby clause [LINQ in C#]"
  - "ordering data [LINQ in C#]"
  - "selecting data [LINQ in C#]"
  - "queries [LINQ in C#], basic operations"
  - "grouping data [LINQ in C#]"
  - "data sources [LINQ in C#]"
  - "sorting data [LINQ in C#]"
  - "projections [LINQ in C#]"
  - "filtering data [LINQ in C#]"
  - "joining data [LINQ in C#]"
  - "select clause [LINQ in C#]"
  - "LINQ [C#], basic query operations"
  - "join clause [LINQ in C#]"
  - "group clause [LINQ in C#]"
ms.assetid: a7ea3421-1cf4-4df7-832a-aa22fe6379e9
caps.latest.revision: 39
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 37
---
# Basic LINQ Query Operations (C#)
Dieses Thema enthält eine kurze Einführung in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]\-Abfrageausdrücke und einige der typischen Vorgänge in einer Abfrage.  Detaillierte Informationen finden Sie in folgenden Themen:  
  
 [LINQ\-Abfrageausdrücke](../../../../csharp/programming-guide/linq-query-expressions/index.md)  
  
 [Standard Query Operators Overview](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
  
 [Walkthrough: Writing Queries in C\#](../../../../csharp/programming-guide/concepts/linq/walkthrough-writing-queries-linq.md)  
  
> [!NOTE]
>  Wenn Sie bereits mit einer Abfragesprache wie SQL oder XQuery vertraut sind, können Sie den größten Teil dieses Themas überspringen.  Lesen Sie die Informationen zur "`from`\-Klausel" im nächsten Abschnitt, um mehr über die Reihenfolge von Klauseln in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]\-Abfrageausdrücken zu erfahren.  
  
## Erhalten einer Datenquelle  
 In einer [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]\-Abfrage besteht der erste Schritt im Angeben der Datenquelle.  In C\#, wie in den meisten Programmiersprachen, muss eine Variable vor der Verwendung deklariert werden.  In einer [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]\-Abfrage steht die `from`\-Klausel zuerst, um die Datenquelle \(`customers`\) und die *Bereichsvariable* \(`cust`\) einzuführen.  
  
 [!code-cs[csLINQGettingStarted#23](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_1.cs)]  
  
 Die Bereichsvariable ist vergleichbar mit der Iterationsvariablen in einer `foreach`\-Schleife, mit dem Unterschied, dass in einem Abfrageausdruck keine wirkliche Iteration stattfindet.  Wenn die Abfrage ausgeführt wird, dient die Bereichsvariable als Verweis auf jedes darauf folgende Element in `customers`.  Da der Compiler den Typ von `cust` per Rückschluss ableiten kann, müssen Sie es nicht explizit angeben.  Zusätzliche Bereichsvariablen können von einer `let`\-Klausel eingeführt werden.  Weitere Informationen finden Sie unter [let\-Klausel](../../../../csharp/language-reference/keywords/let-clause.md).  
  
> [!NOTE]
>  Für nicht generische Datenquellen, wie z. B. <xref:System.Collections.ArrayList>, muss die Bereichsvariable explizit typisiert werden.  Weitere Informationen finden Sie unter [How to: Query an ArrayList with LINQ](../Topic/How%20to:%20Query%20an%20ArrayList%20with%20LINQ.md) und unter [from\-Klausel](../../../../csharp/language-reference/keywords/from-clause.md).  
  
## Filtern  
 Die wahrscheinlich üblichste Abfrageoperation ist das Anwenden eines Filters in Form eines booleschen Ausdrucks.  Der Filter bewirkt, dass die Abfrage nur jene Elemente zurückgibt, für die der Ausdruck den Wert true hat.  Das Ergebnis wird durch Verwendung der `where`\-Klausel erzeugt.  Der aktive Filter gibt an, welche Elemente aus der Quellsequenz ausgeschlossen werden sollen.  Im folgenden Beispiel werden nur jene `customers` zurückgegeben, die eine Adresse in London aufweisen.  
  
 [!code-cs[csLINQGettingStarted#24](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_2.cs)]  
  
 Sie können die bekannten logischen C\#\-Operatoren `AND` und `OR` verwenden, um so viele Filterausdrücke wie möglich in der `where`\-Klausel anzuwenden.  Um beispielsweise nur die Kunden zurückzugeben, die aus "London" stammen und \(`AND`\) den Namen "Devon" haben, verwenden Sie folgenden Code:  
  
 [!code-cs[csLINQGettingStarted#25](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_3.cs)]  
  
 Um Kunden aus London oder Paris zurückzugeben, würden Sie folgenden Code schreiben:  
  
 [!code-cs[csLINQGettingStarted#26](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_4.cs)]  
  
 Weitere Informationen finden Sie unter [where\-Klausel](../../../../csharp/language-reference/keywords/where-clause.md).  
  
## Sortierung  
 Oft ist es hilfreich, die zurückgegebenen Daten zu sortieren.  Mit der `orderby`\-Klausel können die Elemente in der zurückgegebenen Sequenz anhand des Standardvergleichs für den zu sortierenden Typ sortiert werden.  Zum Beispiel kann die folgende Abfrage erweitert werden, um die Ergebnisse auf Grundlage der `Name`\-Eigenschaft zu sortieren.  Da `Name` eine Zeichenfolge ist, führt der Standardvergleich eine alphabetische Sortierung von A bis Z aus.  
  
 [!code-cs[csLINQGettingStarted#27](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_5.cs)]  
  
 Um die Ergebnisse in umgekehrter Reihenfolge zu sortieren \(von Z bis A\), verwenden Sie die `orderby…descending`\-Klausel.  
  
 Weitere Informationen finden Sie unter [orderby\-Klausel](../../../../csharp/language-reference/keywords/orderby-clause.md).  
  
## Gruppierung  
 Die `group`\-Klausel ermöglicht Ihnen, die Ergebnisse auf Grundlage eines Schlüssels zu gruppieren, den Sie angeben.  Sie können beispielsweise angeben, dass die Ergebnisse anhand von `City` sortiert werden, sodass sich alle Kunden aus London oder Paris in einzelnen Gruppen befinden.  In diesem Beispiel ist `cust.City` der Schlüssel.  
  
 [!code-cs[csLINQGettingStarted#28](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_6.cs)]  
  
 Wenn Sie eine Abfrage mit einer `group`\-Klausel abschließen, haben die Ergebnisse die Form einer Liste mit Listen.  Jedes Element in der Liste ist ein Objekt, das einen `Key`\-Member und eine Elementliste aufweist, die unter diesem Schlüssel gruppiert werden.  Wenn Sie eine Abfrage durchlaufen, die eine Sequenz von Gruppen erzeugt, müssen Sie eine geschachtelte `foreach`\-Schleife verwenden.  Die äußere Schleife durchläuft jede Gruppe, und die innere Schleife durchläuft die Member jeder Gruppe.  
  
 Wenn Sie auf die Ergebnisse einer Gruppenoperation verweisen müssen, können Sie das `into`\-Schlüsselwort zum Erstellen eines Bezeichners verwenden, der weitergehend abgefragt werden kann.  Die folgende Abfrage gibt nur jene Gruppen zurück, die mehr als zwei Kunden enthalten:  
  
 [!code-cs[csLINQGettingStarted#29](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_7.cs)]  
  
 Weitere Informationen finden Sie unter [group\-Klausel](../../../../csharp/language-reference/keywords/group-clause.md).  
  
## Verknüpfen  
 Joinoperationen erstellen Zuordnungen zwischen Sequenzen, die nicht explizit in den Datenquellen modelliert werden.  Beispielsweise können Sie einen Join ausführen, um alle Kunden und Verteiler zu suchen, die über denselben Speicherort verfügen.  In [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] wird die `join`\-Klausel immer für Objektauflistungen anstatt für Datenbanktabellen ausgeführt.  
  
 [!code-cs[csLINQGettingStarted#36](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_8.cs)]  
  
 In [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] müssen Sie `join` nicht so häufig verwenden wie in SQL, da die Fremdschlüssel in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] im Objektmodell als Eigenschaften dargestellt werden, die eine Elementauflistung enthalten.  Zum Beispiel enthält ein `Customer`\-Objekt eine Auflistung von `Order`\-Objekten.  Statt einen Join auszuführen, greifen Sie auf die Reihenfolgen mit der Punktnotation zu:  
  
```  
from order in Customer.Orders...  
```  
  
 Weitere Informationen finden Sie unter [join\-Klausel](../../../../csharp/language-reference/keywords/join-clause.md).  
  
## Auswählen \(Projektionen\)  
 Die `select`\-Klausel erzeugt die Ergebnisse der Abfrage und gibt die "Form" oder den Typ jedes zurückgegebenen Elements an.  Sie können beispielsweise angeben, ob Ihre Ergebnisse aus vollständigen `Customer`\-Objekten, nur einem Member, einer Teilmenge von Membern oder einem ganz anderen Ergebnistyp, der auf einer Berechnung oder einer neuen Objekterstellung basiert, bestehen soll.  Wenn die `select`\-Klausel ein anderes Ergebnis als eine Kopie des Quellelements zurückgibt, wird der Vorgang als *Projektion* bezeichnet.  Die Verwendung von Projektionen für die Datentransformation ist ein leistungsstarkes Merkmal von [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]\-Abfrageausdrücken.  Weitere Informationen finden Sie unter [Datentransformationen mit LINQ \(C\#\)](../../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md) und unter [select\-Klausel](../../../../csharp/language-reference/keywords/select-clause.md).  
  
## Siehe auch  
 [Getting Started with LINQ in C\#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [LINQ\-Abfrageausdrücke](../../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Walkthrough: Writing Queries in C\#](../../../../csharp/programming-guide/concepts/linq/walkthrough-writing-queries-linq.md)   
 [Abfrageschlüsselwörter \(LINQ\)](../../../../csharp/language-reference/keywords/query-keywords.md)   
 [Anonyme Typen](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [Grundlegende Abfrageoperationen \(Visual Basic\)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md)