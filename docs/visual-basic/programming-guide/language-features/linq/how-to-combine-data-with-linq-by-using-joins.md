---
title: 'Gewusst wie: Kombinieren von Daten mit LINQ mithilfe von Joins (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- queries [LINQ in Visual Basic], joins
- joins [LINQ in Visual Basic]
- Join clause [LINQ in Visual Basic]
- Group Join clause [Visual Basic]
- joining [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 5b00a478-035b-41c6-8918-be1a97728396
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 432be646ce4353fd4627a34f363e7562f6181e92
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-combine-data-with-linq-by-using-joins-visual-basic"></a>Gewusst wie: Kombinieren von Daten mit LINQ mithilfe von Joins (Visual Basic)
Visual Basic bietet die `Join` und `Group Join` Abfrageklauseln, um den Inhalt mehrerer Sammlungen basierend auf häufig verwendete Werte zwischen den Sammlungen kombinieren können. Diese Werte werden als bezeichnet *Schlüssel* Werte. Mit relationalen Datenbanken vertraute Entwickler erkennt die `Join` -Klausel wie eine INNER JOIN und die `Group Join` -Klausel so effektiv einen LEFT OUTER JOIN.  
  
 In den Beispielen in diesem Thema veranschaulichen einige Möglichkeiten zum Kombinieren von Daten mithilfe der `Join` und `Group Join` Abfrageklauseln.  
  
## <a name="create-a-project-and-add-sample-data"></a>Erstellen eines Projekts und Hinzufügen von Beispieldaten  
  
#### <a name="to-create-a-project-that-contains-sample-data-and-types"></a>So erstellen Sie ein Projekt enthält, die Beispieldaten und Typen  
  
1.  Öffnen Sie Visual Studio, und fügen Sie ein neues Visual Basic-Konsolenanwendungsprojekt hinzu, zum Ausführen der Beispiele in diesem Thema. Doppelklicken Sie auf die Datei "Module1.vb" von Visual Basic erstellt.  
  
2.  In den Beispielen in diesem Thema verwenden die `Person` und `Pet` Typen und Daten aus dem folgenden Codebeispiel. Kopieren Sie diesen Code in der Standardeinstellung `Module1` Modul von Visual Basic erstellt.  
  
     [!code-vb[VbLINQHowTos#1](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_1.vb)]  
    [!code-vb[VbLINQHowTos#2](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_2.vb)]  
  
## <a name="perform-an-inner-join-by-using-the-join-clause"></a>Führen Sie eine innere Verknüpfung mithilfe der Join-Klausel  
 Ein INNER JOIN werden Daten aus zwei Sammlungen kombiniert. Elemente, die für die die angegebenen Schlüsselwerte übereinstimmen, sind enthalten. Alle Elemente aus einer Auflistung, die nicht über ein übereinstimmendes Element in die andere Auflistung verfügen, werden ausgeschlossen.  
  
 In Visual Basic LINQ bietet zwei Optionen zum Ausführen eines INNER Joins: eines impliziten Joins und expliziten Join.  
  
 Eine implizite Verknüpfung gibt an, die Auflistungen verknüpft werden, eine `From` Klausel und identifiziert die übereinstimmenden Felder in einer `Where` Klausel. Visual Basic wird implizit die beiden Auflistungen, die basierend auf den angegebenen Schlüsselfeldern verknüpft.  
  
 Sie können die expliziten Join angeben, mit der `Join` -Klausel, wenn bestimmte über Schlüssel Felder, um die im Join verwendet werden sollen. In diesem Fall eine `Where` -Klausel kann weiterhin zum Filtern der Abfrageergebnisse verwendet werden.  
  
#### <a name="to-perform-an-inner-join-by-using-the-join-clause"></a>Ein Inner Join ausführen, mithilfe der Join-Klausel  
  
1.  Fügen Sie folgenden Code, der `Module1` Modul in Ihrem Projekt, um Beispiele für beide eine implizite und explizite innere Verknüpfung finden Sie unter.  
  
     [!code-vb[VbLINQHowTos#4](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_3.vb)]  
  
## <a name="perform-a-left-outer-join-by-using-the-group-join-clause"></a>Führen Sie eine linke äußere Verknüpfung mit dem Group Join-Klausel  
 LEFT OUTER JOIN schließt alle Elemente aus der linken Auflistung von Joins und nur übereinstimmende Werte aus der Auflistung der rechten Seite des Joins. Alle Elemente aus der Auflistung der rechten Seite des Joins, die nicht über ein entsprechendes Element in der linken Auflistung verfügen, werden aus dem Abfrageergebnis ausgeschlossen.  
  
 Die `Group Join` -Klausel übernimmt zwei, tatsächlich einen LEFT OUTER JOIN. Der Unterschied zwischen was als LEFT OUTER JOIN in der Regel bezeichnet wird und was die `Group Join` -Klausel zurückgegeben wird, die die `Group Join` Klausel Gruppen Ergebnisse aus der Auflistung der rechten Seite des Joins für jedes Element in der linken Auflistung. In einer relationalen Datenbank gibt LEFT OUTER JOIN, dass eine nicht gruppierte Ergebnis in dem jedes Element in der Abfrage ergeben übereinstimmenden Elemente aus beiden Auflistungen, in dem Join enthält. In diesem Fall werden die Elemente aus der Auflistung der linken Seite des Joins für jedes übereinstimmende Element aus der rechten Auflistung wiederholt. Sie sehen, wie dies aussieht, wenn Sie das nächste Verfahren abgeschlossen.  
  
 Sie können die Ergebnisse Abrufen einer `Group Join` Abfrage als nicht gruppierte Ergebnis durch das Erweitern Ihrer Abfrage aus, um ein Element für jeden gruppierten Abfrageergebnis zurückgegeben. Um dies zu erreichen, müssen Sie sicherstellen, dass Sie eine in Abfrage der `DefaultIfEmpty` -Methode der gruppierte Auflistung. Dadurch wird sichergestellt, dass Elemente aus der Auflistung der linken Seite des Joins weiterhin im Abfrageergebnis enthalten sind, auch wenn sie keine passenden Ergebnisse aus der rechten Auflistung verfügen. Sie können Code hinzufügen, zu der Abfrage, die einen Standardwert für das Ergebnis versorgen, wenn kein übereinstimmender Wert aus der Auflistung der rechten Seite des Joins.  
  
#### <a name="to-perform-a-left-outer-join-by-using-the-group-join-clause"></a>Um einen Left Outer Join ausführen, indem Sie mit der Group Join-Klausel  
  
1.  Fügen Sie folgenden Code, der `Module1` Modul in Ihrem Projekt, um Beispiele für eine gruppierte linke äußere Verknüpfung und eines nicht gruppierten linken äußeren Joins finden Sie unter.  
  
     [!code-vb[VbLINQHowTos#3](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_4.vb)]  
  
## <a name="perform-a-join-by-using-a-composite-key"></a>Ausführen einer Verknüpfung mithilfe eines zusammengesetzten Schlüssels  
 Sie können die `And` -Schlüsselwort in eine `Join` oder `Group Join` -Klausel, um die mehrfachen Schlüsselfelder verwenden, beim Ermitteln von Übereinstimmungen zu identifizieren-Statuswerte zu verknüpfenden Auflistungen. Die `And` -Schlüsselwort Gibt an, dass alle angegebenen Schlüsselfelder übereinstimmen nach Elementen verknüpft werden sollen.  
  
#### <a name="to-perform-a-join-by-using-a-composite-key"></a>Für einen Join mit einem zusammengesetzten Schlüssel  
  
1.  Fügen Sie folgenden Code, der `Module1` Modul in Ihrem Projekt aus, um Beispiele für einen Join anzuzeigen, die einen zusammengesetzten Schlüssel verwendet.  
  
     [!code-vb[VbLINQHowTos#5](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_5.vb)]  
  
## <a name="run-the-code"></a>Führen Sie den Code  
  
#### <a name="to-add-code-to-run-the-examples"></a>Hinzufügen von Code zum Ausführen der Beispiele  
  
1.  Ersetzen Sie die `Sub Main` in die `Module1` Modul in Ihrem Projekt durch den folgenden Code zum Ausführen der Beispiele in diesem Thema.  
  
     [!code-vb[VbLINQHowTos#6](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_6.vb)]  
  
2.  Drücken Sie F5, um die Beispiele auszuführen.  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Join-Klausel](../../../../visual-basic/language-reference/queries/join-clause.md)  
 [Group Join-Klausel](../../../../visual-basic/language-reference/queries/group-join-clause.md)  
 [From-Klausel](../../../../visual-basic/language-reference/queries/from-clause.md)  
 [Where-Klausel](../../../../visual-basic/language-reference/queries/where-clause.md)  
 [Abfragen](../../../../visual-basic/language-reference/queries/queries.md)  
 [Datentransformationen mit LINQ (C#)](../../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md)
