---
title: "How to: Combine Data with LINQ by Using Joins (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "queries [LINQ in Visual Basic], joins"
  - "joins [LINQ in Visual Basic]"
  - "Join clause [LINQ in Visual Basic]"
  - "Group Join clause [Visual Basic]"
  - "joining [LINQ in Visual Basic]"
  - "queries [LINQ in Visual Basic], how-to topics"
ms.assetid: 5b00a478-035b-41c6-8918-be1a97728396
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# How to: Combine Data with LINQ by Using Joins (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Visual Basic stellt die Abfrageklauseln `Join` und `Group Join` bereit, mit denen Sie die Inhalte mehrerer Auflistungen auf Grundlage gemeinsamer Werte kombinieren können.  Diese Werte werden als *Schlüsselwerte* bezeichnet.  Mit relationalen Datenbanken vertraute Entwickler erkennen, dass die `Join`\-Klausel einem INNER JOIN und die `Group Join`\-Klausel praktisch einem LEFT OUTER JOIN entspricht.  
  
 In den Beispielen dieses Themas werden einige Möglichkeiten zum Kombinieren von Daten mit den Abfrageklauseln `Join` und `Group Join` veranschaulicht.  
  
## Erstellen eines Projekts und Hinzufügen von Beispieldaten  
  
#### So erstellen Sie ein Projekt mit Beispieldaten und \-typen  
  
1.  Um die Beispiele dieses Themas auszuführen, öffnen Sie Visual Studio und fügen ein neues Visual Basic\-Konsolenanwendungsprojekt hinzu.  Doppelklicken Sie auf die von Visual Basic erstellte Datei Module1.vb.  
  
2.  In den Beispielen dieses Themas werden die Typen `Person` und `Pet` und Daten aus den folgenden Codebeispielen verwendet.  Kopieren Sie diesen Code in das von Visual Basic erstellte Standardmodul `Module1`.  
  
     [!code-vb[VbLINQHowTos#1](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_1.vb)]  
    [!code-vb[VbLINQHowTos#2](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_2.vb)]  
  
## Ausführen eines inneren Joins mithilfe der Join\-Klausel  
 Ein INNER JOIN kombiniert Daten aus zwei Auflistungen.  Es werden die Elemente eingeschlossen, bei denen die angegebenen Schlüsselwerte übereinstimmen.  Alle Elemente der beiden Auflistungen, für die es in der jeweils anderen Auflistung kein passendes Element gibt, werden ausgeschlossen.  
  
 LINQ stellt in Visual Basic zwei Optionen zum Ausführen eines INNER JOIN bereit: einen impliziten Join und einen expliziten Join.  
  
 Bei einem impliziten Join werden die zu verknüpfenden Auflistungen in einer `From`\-Klausel angegeben und die entsprechenden Schlüsselfelder in einer `Where`\-Klausel identifiziert.  Visual Basic verknüpft die beiden Auflistungen implizit auf Grundlage der angegebenen Schlüsselfelder.  
  
 Einen expliziten Join können Sie mit der `Join`\-Klausel angeben, wenn Sie genau festlegen möchten, welche Schlüsselfelder in dem Join verwendet werden sollen.  In diesem Fall kann weiterhin eine `Where`\-Klausel verwendet werden, um die Abfrageergebnisse zu filtern.  
  
#### So führen Sie einen inneren Join mithilfe der Join\-Klausel aus  
  
1.  Fügen Sie Ihrem Projekt im Modul `Module1` den folgenden Code hinzu, um Beispiele sowohl für einen impliziten als auch für einen expliziten inneren Join zu erhalten.  
  
     [!code-vb[VbLINQHowTos#4](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_3.vb)]  
  
## Ausführen eines linken äußeren Joins mithilfe der Group Join\-Klausel  
 Mit LEFT OUTER JOIN werden alle Elemente der Auflistung auf der linken Seite des Joins und nur die passenden Werte der Auflistung auf der rechten Seite des Joins eingeschlossen.  Die Elemente der Auflistung auf der rechten Seite des Joins, für die es in der Auflistung auf der linken Seite des Joins kein passendes Element gibt, werden aus dem Abfrageergebnis ausgeschlossen.  
  
 Die `Group Join`\-Klausel verhält sich praktisch wie ein LEFT OUTER JOIN.  Der Unterschied zwischen einem normalen LEFT OUTER JOIN und der Rückgabe der `Group Join`\-Klausel besteht darin, dass die Ergebnisse aus der Auflistung auf der rechten Seite des Joins bei der `Group Join`\-Klausel für jedes Element der Auflistung auf der linken Seite des Joins gruppiert werden.  In einer relationalen Datenbank wird bei einem LEFT OUTER JOIN ein nicht gruppiertes Ergebnis zurückgegeben, bei dem jedes Element des Abfrageergebnisses passende Elemente aus beiden Auflistungen des Joins enthält.  In diesem Fall werden die Elemente der Auflistung auf der linken Seite des Joins für jedes passende Element der Auflistung auf der rechten Seite des Joins wiederholt.  Sie werden diese Darstellung deutlicher erkennen, wenn Sie das nächste Verfahren durchführen.  
  
 Sie können die Ergebnisse einer `Group Join`\-Abfrage ohne Gruppierung abrufen, indem Sie die Abfrage so erweitern, dass für jedes gruppierte Abfrageergebnis ein Element zurückgegeben wird.  Zu diesem Zweck müssen Sie sicherstellen, dass Sie die Abfrage mithilfe der `DefaultIfEmpty`\-Methode der gruppierten Auflistung ausführen.  Dadurch wird sichergestellt, dass im Abfrageergebnis auch Elemente der Auflistung auf der linken Seite des Joins eingeschlossen werden, wenn es keine passenden Ergebnisse in der Auflistung auf der rechten Seite gibt.  Sie können Ihrer Abfrage Code zum Bereitstellen eines Standardergebnisses hinzufügen, wenn es in der Auflistung auf der rechten Seite des Joins keinen passenden Wert gibt.  
  
#### So führen Sie einen linken äußeren Join mithilfe der Group Join\-Klausel aus  
  
1.  Fügen Sie Ihrem Projekt im Modul `Module1` den folgenden Code hinzu, um Beispiele sowohl für einen gruppierten als auch für einen nicht gruppierten linken äußeren Join zu erhalten.  
  
     [!code-vb[VbLINQHowTos#3](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_4.vb)]  
  
## Ausführen eines Joins mithilfe eines zusammengesetzten Schlüssels  
 Mit dem `And`\-Schlüsselwort können Sie in einer `Join`\-Klausel oder einer `Group Join`\-Klausel mehrere zu verwendende Schlüsselfelder zum Vergleichen der Werte aus den zu verknüpfenden Auflistungen festlegen.  Mit dem `And`\-Schlüsselwort geben Sie an, dass für die zu verknüpfenden Elemente alle angegebenen Schlüsselfelder übereinstimmen müssen.  
  
#### So führen Sie einen Join mithilfe eines zusammengesetzten Schlüssels aus  
  
1.  Fügen Sie Ihrem Projekt im Modul `Module1` den folgenden Code hinzu, um Beispiele für einen Join anzuzeigen, der einen zusammengesetzten Schlüssel verwendet.  
  
     [!code-vb[VbLINQHowTos#5](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_5.vb)]  
  
## Ausführen des Codes  
  
#### So fügen Sie Code hinzu, um die Beispiele auszuführen  
  
1.  Ersetzen Sie in Ihrem Projekt im Modul `Module1` `Sub Main` durch den folgenden Code, um die Beispiele dieses Themas auszuführen.  
  
     [!code-vb[VbLINQHowTos#6](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_6.vb)]  
  
2.  Drücken Sie F5, um die Beispiele auszuführen.  
  
## Siehe auch  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Join Clause](../../../../visual-basic/language-reference/queries/join-clause.md)   
 [Group Join Clause](../../../../visual-basic/language-reference/queries/group-join-clause.md)   
 [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md)   
 [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md)   
 [Queries](../../../../visual-basic/language-reference/queries/queries.md)   
 [Datentransformationen mit LINQ \(C\#\)](../../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md)