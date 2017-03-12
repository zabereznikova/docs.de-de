---
title: "join-Klausel (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "join"
  - "join_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "join-Klausel [C#]"
  - "join-Schlüsselwort [C#]"
ms.assetid: 76e9df84-092c-41a6-9537-c3f1cbd7f0fb
caps.latest.revision: 29
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 29
---
# join-Klausel (C#-Referenz)
Die `join`\-Klausel ist nützlich, um Elemente aus unterschiedlichen Quellsequenzen, die keine direkte Beziehung im Objektmodell haben, zuzuweisen.  Die einzige Anforderung ist, dass die Elemente in jeder Quelle einige Werte gemeinsam nutzen, die auf Gleichheit verglichen werden können.  Ein Lebensmittelanbieter hat beispielsweise eine Liste mit Anbietern bestimmter Produkte und eine Liste mit Käufern.  Eine `join`\-Klausel kann z. B. verwendet werden, um eine Liste mit Anbietern und Käufern für dieses Produkt zu erstellen, die sich alle in der angegebenen Region befinden.  
  
 Eine `join`\-Klausel verwendet zwei Quellsequenzen als Eingabe.  Die Elemente in jeder Sequenz müssen entweder eine Eigenschaft sein oder eine Eigenschaft enthalten, die mit einer entsprechenden Eigenschaft in der anderen Sequenz verglichen werden kann.  Die `join`\-Klausel vergleicht die angegebenen Schlüssel mithilfe des speziellen `equals`\-Schlüsselworts auf Gleichheit.  Alle von der `join`\-Klausel ausgeführten Joins sind Equijoins.  Die Form der Ausgabe einer `join`\-Klausel ist vom speziellen Typ des Joins, den Sie ausführen, abhängig.  Die folgenden drei Jointypen kommen am häufigsten vor:  
  
-   Innerer Join  
  
-   Group Join  
  
-   Linker äußerer Join  
  
## Innerer Join  
 Im folgenden Beispiel wird ein einfacher innerer Equijoin veranschaulicht.  Diese Abfrage erzeugt eine flache Sequenz von "Produktname\/Kategorie"\-Paaren.  Die gleiche Kategoriezeichenfolge wird in mehreren Elementen angezeigt.  Wenn ein Element aus `categories` nicht über entsprechende `products` verfügt, wird diese Kategorie nicht in den Ergebnissen angezeigt.  
  
 [!code-cs[cscsrefQueryKeywords#24](../../../csharp/language-reference/keywords/codesnippet/csharp/csquerykeywords/Join.cs#24)]  
  
 Weitere Informationen finden Sie unter [Gewusst wie: Ausführen innerer Verknüpfungen](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md).  
  
## Group Join  
 Eine `join`\-Klausel mit einem `into`\-Ausdruck wird als Group Join bezeichnet.  
  
 [!code-cs[cscsrefQueryKeywords#25](../../../csharp/language-reference/keywords/codesnippet/csharp/csquerykeywords/Join.cs#25)]  
  
 Ein Group Join erzeugt eine hierarchische Ergebnissequenz, in der Elemente in der linken Quellsequenz einem oder mehr entsprechenden Elementen in der rechten Quellsequenz zugeordnet werden.  Ein Group Join hat keine Entsprechung im relationalen Sinn; es ist im Grunde eine Sequenz von Objektarrays.  
  
 Wenn keine Elemente aus der rechten Quellsequenz gefunden werden, die mit einem Element in der linken Quelle übereinstimmen, erzeugt die `join`\-Klausel ein leeres Array für dieses Element.  Der Group Join ist im Grunde ein innerer Equijoin, mit der Ausnahme, dass die Ergebnissequenz in Gruppen organisiert ist.  
  
 Wenn Sie die Ergebnisse eines Group Joins auswählen, können Sie auf die Elemente zugreifen, jedoch nicht den Entsprechungsschlüssel identifizieren.  Es ist daher im Allgemeinen sinnvoller, die Ergebnisse des Group Joins zu einem neuen Typ zusammenzufassen, der auch den Schlüsselnamen enthält, wie im vorherigen Beispiel gezeigt.  
  
 Sie können natürlich auch das Ergebnis eines Group Joins als Generator einer anderen Unterabfrage verwenden:  
  
 [!code-cs[cscsrefQueryKeywords#26](../../../csharp/language-reference/keywords/codesnippet/csharp/csquerykeywords/Join.cs#26)]  
  
 Weitere Informationen finden Sie unter [Gewusst wie: Ausführen von Gruppenverknüpfungen](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-grouped-joins.md).  
  
## Linker äußerer Join  
 In einem linken äußeren Join werden alle Elemente in der linken Quellsequenz zurückgegeben, selbst dann, wenn es keine entsprechenden Elemente in der rechten Sequenz gibt.  Um einen linken äußeren Join in [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)] durchzuführen, verwenden Sie die `DefaultIfEmpty`\-Methode zusammen mit einem Group Join, um ein rechtes Standardelement anzugeben, das erstellt wird, wenn es keine Entsprechung für ein linkes Element gibt.  Sie können `null` als Standardwert für einen beliebigen Referenztyp verwenden, oder Sie können einen benutzerdefinierten Standardtyp festlegen.  Im folgenden Beispiel wird ein benutzerdefinierter Standardtyp gezeigt:  
  
 [!code-cs[cscsrefQueryKeywords#27](../../../csharp/language-reference/keywords/codesnippet/csharp/csquerykeywords/Join.cs#27)]  
  
 Weitere Informationen finden Sie unter [Gewusst wie: Ausführen linker äußerer Verknüpfungen](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-left-outer-joins.md).  
  
## Der Gleichheitsoperator  
 Eine `join`\-Klausel führt einen Equijoin aus.  Das heißt, Sie können Übereinstimmungen nur auf der Gleichheit von zwei Schlüsseln basieren.  Andere Vergleichstypen, z. B. "größer als" oder "ungleich", werden nicht unterstützt.  Um sicherzustellen, dass alle Joins Equijoins sind, verwendet die `join`\-Klausel das `equals`\-Schlüsselwort anstelle des Operators `==`.  Das `equals`\-Schlüsselwort kann nur in einer `join`\-Klausel verwendet werden und unterscheidet sich in einem wichtigen Aspekt vom Operator `==`.  Bei `equals` nutzt der linke Schlüssel die äußere Quellsequenz, und der rechte Schlüssel nutzt die innere Quelle.  Die äußere Quelle befindet sich nur links von `equals` im Bereich, und die innere Quelle ist nur rechts eingebunden.  
  
## Nicht\-Equijoins  
 Sie können mit mehreren `from`\-Klauseln Nicht\-Equijoins, Cross Joins und andere benutzerdefinierte Joinoperationen durchführen, um neue Sequenzen einzeln in eine Abfrage einzuführen.  Weitere Informationen finden Sie unter [Gewusst wie: Ausführen von benutzerdefinierten Verknüpfungsoperationen](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-custom-join-operations.md).  
  
## Joins für Objektauflistungen im Vergleich zurelationalen Tabellen  
 In einem [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)]\-Abfrageausdruck werden Joinoperationen für Objektauflistungen ausgeführt.  Objektauflistungen können nicht auf genau die gleiche Art wie zwei relationale Tabellen verknüpft werden.  In [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)] sind explizite `join`\-Klauseln nur erforderlich, wenn zwei Quellsequenzen nicht durch eine Beziehung gebunden sind.  Bei der Arbeit mit [!INCLUDE[vbtecdlinq](../../../csharp/includes/vbtecdlinq-md.md)] werden Fremdschlüsseltabellen im Objektmodell als Eigenschaften der Primärtabelle dargestellt.  In der Northwind\-Datenbank weist die Customer\-Tabelle beispielsweise eine Fremdschlüsselbeziehung mit der Orders\-Tabelle auf.  Wenn Sie die Tabellen dem Objektmodell zuordnen, weist die Customer\-Klasse eine Orders\-Eigenschaft auf, die die Auflistung von Bestellungen, die diesem Kunden zugewiesen sind, enthält.  Im Grunde wurde der Join bereits für Sie hergestellt.  
  
 Weitere Informationen zum Abfragen von verknüpften Tabellen im Kontext von [!INCLUDE[vbtecdlinq](../../../csharp/includes/vbtecdlinq-md.md)] finden Sie unter [Vorgehensweise: Zuordnen von Datenbankbeziehungen](../Topic/How%20to:%20Map%20Database%20Relationships.md).  
  
## Zusammengesetzte Schlüssel  
 Mit einem zusammengesetzten Schlüssel können Sie mehrere Werte auf Gleichheit prüfen.  Weitere Informationen finden Sie unter [Gewusst wie: Verknüpfen mithilfe eines zusammengesetzten Schlüssels](../../../csharp/programming-guide/linq-query-expressions/how-to-join-by-using-composite-keys.md).  Zusammengesetzte Schlüssel können auch in einer `group`\-Klausel verwendet werden.  
  
## Beispiel  
 Im folgenden Beispiel werden die Ergebnisse eines inneren Joins, eines Group Joins und eines linken äußeren Joins der gleichen Datenquellen mit den gleichen übereinstimmenden Schlüsseln verglichen.  Diesen Beispielen wird zusätzlicher Code hinzugefügt, um die Ergebnisse in der Konsolenanzeige zu erläutern.  
  
 [!code-cs[cscsrefQueryKeywords#23](../../../csharp/language-reference/keywords/codesnippet/csharp/csquerykeywords/Join.cs#23)]  
  
## Hinweise  
 Eine `join`\-Klausel, der nicht `into` folgt, wird in einen <xref:System.Linq.Enumerable.Join%2A>\-Methodenaufruf übersetzt.  Eine `join`\-Klausel, der `into` folgt, wird in einen <xref:System.Linq.Enumerable.GroupJoin%2A>\-Methodenaufruf übersetzt.  
  
## Siehe auch  
 [Abfrageschlüsselwörter \(LINQ\)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [LINQ\-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Join Operations](../../../visual-basic/programming-guide/concepts/linq/join-operations.md)   
 [group\-Klausel](../../../csharp/language-reference/keywords/group-clause.md)   
 [Gewusst wie: Ausführen linker äußerer Verknüpfungen](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-left-outer-joins.md)   
 [Gewusst wie: Ausführen innerer Verknüpfungen](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md)   
 [Gewusst wie: Ausführen von Gruppenverknüpfungen](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-grouped-joins.md)   
 [Gewusst wie: Sortieren der Ergebnisse einer Join\-Klausel](../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md)   
 [Gewusst wie: Verknüpfen mithilfe eines zusammengesetzten Schlüssels](../../../csharp/programming-guide/linq-query-expressions/how-to-join-by-using-composite-keys.md)   
 [Gewusst wie: Installieren von Beispieldatenbanken](../Topic/How%20to:%20Install%20Sample%20Databases.md)