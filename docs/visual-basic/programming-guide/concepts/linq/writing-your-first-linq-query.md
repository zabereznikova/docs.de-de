---
title: "Schreiben der ersten LINQ-Abfrage (Visual Basic) | Microsoft Docs"
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
  - "Abfragen [LINQ in Visual Basic], Schreiben"
  - "LINQ-Abfragen [Visual Basic]"
  - "LINQ [Visual Basic], Schreiben von Abfragen"
ms.assetid: 4affb732-3e9b-4479-aa31-1f9bd8183cbe
caps.latest.revision: 56
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 54
---
# Schreiben der ersten LINQ-Abfrage (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Eine *Abfrage* ist ein Ausdruck, der Daten von einer Datenquelle abruft.  Abfragen werden in einer dedizierten Abfragesprache ausgedrückt.  Im Laufe der Zeit wurden verschiedene Sprachen für verschiedene Datenquellen entwickelt, beispielsweise SQL für relationale Datenbanken und XQuery für XML.  Aus diesem Grund muss der Anwendungsentwickler für jeden Typ von Datenquelle oder Datenformat die jeweilige Abfragesprache erlernen.  
  
 [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext-md.md)] vereinfacht diese Situation durch die Bereitstellung eines konsistenten Modells zum Arbeiten mit Daten in verschiedenen Arten von Datenquellen und Formaten.  In einer [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]\-Abfrage arbeiten Sie immer mit Objekten.  Sie verwenden dieselben grundlegenden Codierungsmuster für die Abfrage und Transformation von Daten in XML\-Dokumenten, SQL\-Datenbanken, ADO.NET\-Datasets und \-Entitäten, .NET Framework\-Auflistungen sowie allen anderen Quellen und Formaten, für die ein [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]\-Anbieter verfügbar ist.  In diesem Dokument werden die drei Phasen der Erstellung und die Verwendung grundlegender [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]\-Abfragen beschrieben.  
  
 ![Link zu Video](../../../../csharp/programming-guide/concepts/linq/media/playvideo.png "PlayVideo") Unter [How Do I: Get Started with LINQ?](http://go.microsoft.com/fwlink/?LinkId=133021) finden Sie eine Videodemonstration zum Thema.  
  
## Drei Phasen einer Abfrageoperation  
 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]\-Abfrageoperationen bestehen aus drei Aktionen:  
  
1.  Abrufen der Datenquelle oder der Datenquellen  
  
2.  Erstellen der Abfrage  
  
3.  Ausführen der Abfrage  
  
 In [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] sind die Ausführung einer Abfrage und die Erstellung der Abfrage voneinander getrennte Vorgänge.  Sie rufen Daten nicht einfach ab, indem Sie eine Abfrage erstellen.  Dieser Punkt wird weiter unten in diesem Thema ausführlich erläutert.  
  
 Im folgenden Beispiel werden die drei Teile einer Abfrageoperation veranschaulicht.  Im Beispiel wird ein Array von Ganzzahlen als zweckmäßige Datenquelle zur Demonstration der Vorgehensweise verwendet.  Dieselben Konzepte gelten jedoch auch für andere Datenquellen.  
  
> [!NOTE]
>  Klicken Sie auf [Seite "Kompilieren", Projekt\-Designer \(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic) stellen Sie sicher, dass **Option Infer** zu **Ein** festgelegt ist.  
  
 [!code-vb[VbLINQFirstQuery#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/writing-your-first-linq-_1.vb)]  
  
 Ausgabe:  
  
 `0 2 4 6`  
  
## Die Datenquelle  
 Da es sich bei der Datenquelle im vorherigen Beispiel um ein Array handelt, unterstützt sie implizit die generische <xref:System.Collections.Generic.IEnumerable%601>\-Schnittstelle.  Dadurch kann ein Array als Datenquelle für eine [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]\-Abfrage verwendet werden.  Typen, die <xref:System.Collections.Generic.IEnumerable%601> oder eine abgeleitete Schnittstelle wie generische <xref:System.Linq.IQueryable%601> unterstützen, werden als *abfragbare Typen* aufgerufen.  
  
 Da das Array ein abfragbarer Typ ist, ist keine Änderung oder besondere Behandlung erforderlich, um es als [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]\-Datenquelle zu verwenden.  Dasselbe gilt für jeden Auflistungstyp, der <xref:System.Collections.Generic.IEnumerable%601>, einschließlich generischer <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.Dictionary%602> unterstützt, und andere Klassen in der .NET Framework\-Klassenbibliothek erfüllt.  
  
 Wenn die Quelldaten nicht bereits <xref:System.Collections.Generic.IEnumerable%601> implementieren, wird ein [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] Anbieter erforderlich, um die Funktionen der *Standardabfrageoperatoren* für diese Datenquelle implementiert.  So übernimmt beispielsweise [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] die Aufgabe, ein XML\-Dokument in einen abfragbaren <xref:System.Xml.Linq.XElement>\-Typ zu laden, wie im folgenden Beispiel dargestellt.  Weitere Informationen über Standardabfrageoperatoren finden Sie unter [Standard Query Operators Overview](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
 [!code-vb[VbLINQFirstQuery#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/writing-your-first-linq-_2.vb)]  
  
 Mit [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq-md.md)] erstellen Sie zuerst eine objektrelationale Zuordnung zur Entwurfszeit, entweder manuell oder über [Object Relational Designer \(O\/R\-Designer\)](/visual-studio/data-tools/linq-to-sql-tools-in-visual-studio2).  Sie schreiben die Abfragen anhand der Objekte, und zur Laufzeit übernimmt [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq-md.md)] die Kommunikation mit der Datenbank.  Im folgenden Beispiel stellt `customers` eine bestimmte Tabelle in der Datenbank dar, und <xref:System.Data.Linq.Table%601> unterstützt die generische <xref:System.Linq.IQueryable%601>.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 Weitere Informationen zum Erstellen bestimmter Typen von Datenquellen finden Sie in der Dokumentation der verschiedenen [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]\-Anbieter.  \(Eine Liste dieser Anbieter finden Sie unter [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md).\) Die Grundregel ist einfach: Eine [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]\-Datenquelle ist jedes Objekt, das die generische <xref:System.Collections.Generic.IEnumerable%601>\-Schnittstelle oder eine Schnittstelle unterstützt, die von ihr erbt.  
  
> [!NOTE]
>  Typen wie <xref:System.Collections.ArrayList>, die die nicht generische <xref:System.Collections.IEnumerable>\-Schnittstelle unterstützen, können ebenso als [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]\-Datenquellen verwendet werden.  Ein Beispiel, in dem eine <xref:System.Collections.ArrayList> verwendet wird, finden Sie unter [How to: Query an ArrayList with LINQ](../Topic/How%20to:%20Query%20an%20ArrayList%20with%20LINQ.md).  
  
## Die Abfrage  
 In der Abfrage geben Sie an, welche Informationen Sie aus der Datenquelle oder den Datenquellen abrufen möchten.  Sie haben auch die Möglichkeit, anzugeben, wie diese Informationen vor der Rückgabe sortiert, gruppiert oder strukturiert werden sollen.  Um das Erstellen von Abfragen zu ermöglichen, wurde eine neue Abfragesyntax in die Visual Basic\-Sprache integriert.  
  
 Wenn die Abfrage im folgenden Beispiel ausgeführt wird, gibt sie alle geraden Zahlen aus einem Ganzzahlen\-Array, `numbers`, zurück.  
  
 [!code-vb[VbLINQFirstQuery#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/writing-your-first-linq-_1.vb)]  
  
 Der Abfrageausdruck enthält drei Klauseln: `From`, `Where` und `Select`.  Die spezielle Funktion und der Zweck jeder Abfrageausdrucksklausel werden in [Grundlegende Abfrageoperationen \(Visual Basic\)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md) erläutert.  Weitere Informationen finden Sie unter [Queries](../../../../visual-basic/language-reference/queries/queries.md).  Beachten Sie, dass in [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] eine Abfragedefinition häufig in einer Variablen gespeichert und später ausgeführt wird.  Die Abfragevariable, wie `evensQuery` im vorherigen Beispiel, muss ein abfragbarer Typ sein. Der Typ von `evensQuery` ist `IEnumerable(Of Integer)` zugewiesen, vom Compiler, der lokalen Typrückschlusses.  
  
 Beachten Sie, dass die Abfragevariable selbst keine Aktion ausführt und keine Daten zurückgibt.  Sie speichert nur die Abfragedefinition.  Im vorherigen Beispiel wird die Abfrage durch die `For Each`\-Schleife ausgeführt.  
  
## Abfrageausführung  
 Die Ausführung einer Abfrage erfolgt getrennt von der Erstellung einer Abfrage.  Beim Erstellen der Abfrage wird die Abfrage definiert. Das Ausführen wird jedoch durch einen anderen Mechanismus ausgelöst.  Eine Abfrage kann ausgeführt werden, sobald sie definiert ist \(*unmittelbare Ausführung*\), oder die Definition kann gespeichert und die Abfrage kann später ausgeführt werden \(*verzögerte Ausführung*\).  
  
### Verzögerte Ausführung  
 Eine typische [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]\-Abfrage sieht ähnlich der Abfrage im vorherigen Beispiel aus, in dem `evensQuery` definiert wird.  Dabei wird die Abfrage erstellt, jedoch nicht sofort ausgeführt.  Stattdessen wird die Abfragedefinition in der Abfragevariablen `evensQuery` gespeichert.  Die Abfrage wird später ausgeführt, in der Regel unter Verwendung einer `For Each`\-Schleife, die eine Sequenz von Werten zurückgibt, oder durch Anwendung eines Standardabfrageoperators wie `Count` oder `Max`.  Dieser Vorgang wird als *verzögerte Ausführung* bezeichnet.  
  
 [!code-vb[VbLINQFirstQuery#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/writing-your-first-linq-_3.vb)]  
  
 Bei einer Sequenz von Werten greifen Sie auf die abgerufenen Daten unter Verwendung der Iterationsvariablen in der `For Each`\-Schleife zu \(im vorherigen Beispiel `number`\).  Da die Abfragevariable `evensQuery` die Abfragedefinition und nicht die Abfrageergebnisse enthält, können Sie die Abfrage beliebig oft ausführen, indem Sie die Abfragevariable mehrfach verwenden.  Sie könnten beispielsweise über eine Datenbank in Ihrer Anwendung verfügen, die ständig durch eine separate Anwendung aktualisiert wird.  Nach Erstellen einer Abfrage, mit der Daten aus dieser Datenbank abgerufen werden, können Sie eine `For Each`\-Schleife verwenden, um die Abfrage wiederholt auszuführen, sodass jedes Mal die neuesten Daten abgerufen werden.  
  
 Das folgende Beispiel veranschaulicht die Funktionsweise der verzögerten Ausführung.  Nachdem `evensQuery2` definiert und mit einer `For Each`\-Schleife ausgeführt wurde, wie in den vorherigen Beispielen, ändern sich einige Elemente in der Datenquelle `numbers`.  Anschließend führt eine zweite `For Each`\-Schleife erneut `evensQuery2` aus.  Beim zweiten Mal sind die Ergebnisse anders, da die `For Each`\-Schleife die Abfrage erneut ausführt, und zwar unter Verwendung der neuen Werte in `numbers`.  
  
 [!code-vb[VbLINQFirstQuery#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/writing-your-first-linq-_4.vb)]  
  
 Ausgabe:  
  
 `Evens in original array:`  
  
 `0 2 4 6`  
  
 `Evens in changed array:`  
  
 `0 10 2 22 8`  
  
### Unmittelbare Ausführung  
 Bei der verzögerten Ausführung von Abfragen wird die Abfragedefinition für die spätere Ausführung in einer Abfragevariablen gespeichert.  Bei der unmittelbaren Ausführung wird die Abfrage zum Zeitpunkt ihrer Definition ausgeführt.  Die Abfrage wird ausgelöst, indem Sie eine Methode anwenden, für die ein Zugriff auf einzelne Elemente des Abfrageergebnisses erforderlich ist.  Die unmittelbare Ausführung wird häufig durch die Verwendung eines der Standardabfrageoperatoren erzwungen, die einzelne Werte zurückgeben.  Beispiele sind `Count`, `Max`, `Average` und `First`.  Diese Standardabfrageoperatoren führen die Abfrage aus, sobald sie angewendet werden, um ein einzelnes Ergebnis zu berechnen und zurückzugeben.  Weitere Informationen über Standardabfrageoperatoren, die einzelne Werte zurückgeben, finden Sie unter [Aggregation Operations](../../../../visual-basic/programming-guide/concepts/linq/aggregation-operations.md), [Element Operations](../../../../visual-basic/programming-guide/concepts/linq/element-operations.md) und [Quantifier Operations](../../../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md).  
  
 Die folgende Abfrage gibt die Anzahl der geraden Zahlen in einem Ganzzahlen\-Array zurück.  Die Abfragedefinition wird nicht gespeichert, und `numEvens` ist eine einfache `Integer`.  
  
 [!code-vb[VbLINQFirstQuery#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/writing-your-first-linq-_5.vb)]  
  
 Das gleiche Ergebnis lässt sich mithilfe der `Aggregate`\-Methode erzielen.  
  
 [!code-vb[VbLINQFirstQuery#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/writing-your-first-linq-_6.vb)]  
  
 Sie können die Ausführung einer Abfrage auch erzwingen, indem Sie die `ToList`\- oder die `ToArray`\-Methode für eine Abfrage \(unmittelbar\) oder eine Abfragevariable \(verzögert\) aufrufen, wie im folgenden Code gezeigt.  
  
 [!code-vb[VbLINQFirstQuery#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/writing-your-first-linq-_7.vb)]  
  
 In den vorherigen Beispielen ist `evensQuery3` eine Abfragevariable, `evensList` ist jedoch eine Liste, und `evensArray` ist ein Array.  
  
 Die Verwendung von `ToList` oder `ToArray` zum Erzwingen einer unmittelbaren Ausführung ist besonders nützlich in Szenarien, in denen Sie die Abfrage sofort ausführen und die Ergebnisse in einem einzigen Auflistungsobjekt zwischenspeichern möchten.  Weitere Informationen über diese Methoden finden Sie unter [Converting Data Types](../../../../visual-basic/programming-guide/concepts/linq/converting-data-types.md).  
  
 Sie können das Ausführen einer Abfrage auch durch Verwendung einer `IEnumerable`\-Methode veranlassen, z. B. der <xref:Microsoft.VisualBasic.Collection.System%23Collections%23IEnumerable%23GetEnumerator%2A>\-Methode.  
  
## Demovideos zu ähnlichen Themen  
 [Gewusst wie: Erste Schritte mit LINQ](http://go.microsoft.com/fwlink/?LinkId=133021)  
  
 [Gewusst\-wie\-Video: Schreiben von Abfragen in Visual Basic](http://go.microsoft.com/fwlink/?LinkID=100356)  
  
## Siehe auch  
 [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [LINQ\-Beispiele](../Topic/LINQ%20Samples.md)   
 [Übersicht über den O\/R\-Designer](../Topic/LINQ%20to%20SQL%20Tools%20in%20Visual%20Studio1.md)   
 [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Standard Query Operators Overview](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Queries](../../../../visual-basic/language-reference/queries/queries.md)