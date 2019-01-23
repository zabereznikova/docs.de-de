---
title: 'Vorgehensweise: Kombinieren von Daten mit LINQ mithilfe von Joins (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], joins
- joins [LINQ in Visual Basic]
- Join clause [LINQ in Visual Basic]
- Group Join clause [Visual Basic]
- joining [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 5b00a478-035b-41c6-8918-be1a97728396
ms.openlocfilehash: fd1025d056dfb11d2253a39defb384c1d05efa32
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54553697"
---
# <a name="how-to-combine-data-with-linq-by-using-joins-visual-basic"></a>Vorgehensweise: Kombinieren von Daten mit LINQ mithilfe von Joins (Visual Basic)
Visual Basic bietet die `Join` und `Group Join` -Abfrageklauseln, um den Inhalt mehrerer Sammlungen basierend auf häufig verwendete Werte zwischen den Sammlungen kombinieren können. Diese Werte werden als bezeichnet *Schlüssel* Werte. Mit relationale Datenbank vertraute Entwickler erkennt die `Join` -Klausel als ein INNER JOIN und `Group Join` -Klausel so effektiv einen LEFT OUTER JOIN.  
  
 In die Beispielen in diesem Thema veranschaulichen einige Möglichkeiten zum Kombinieren von Daten mithilfe der `Join` und `Group Join` -Abfrageklauseln.  
  
## <a name="create-a-project-and-add-sample-data"></a>Erstellen eines Projekts und Hinzufügen von Beispieldaten  
  
#### <a name="to-create-a-project-that-contains-sample-data-and-types"></a>Ein Projekt zu erstellen, die Beispieldaten und Typen enthält.  
  
1.  Um die Beispiele in diesem Thema auszuführen, öffnen Sie Visual Studio, und fügen Sie ein neues Visual Basic-Konsolenanwendungsprojekt hinzu. Doppelklicken Sie auf die Datei "Module1.vb" von Visual Basic erstellt.  
  
2.  In den Beispielen in diesem Thema verwenden die `Person` und `Pet` Typen und Daten aus dem folgenden Codebeispiel. Kopieren Sie diesen Code in der Standardeinstellung `Module1` Modul von Visual Basic erstellt.  
  
     [!code-vb[VbLINQHowTos#1](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_1.vb)]  
    [!code-vb[VbLINQHowTos#2](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_2.vb)]  
  
## <a name="perform-an-inner-join-by-using-the-join-clause"></a>Führen Sie eine innere Verknüpfung mithilfe der Join-Klausel  
 Ein INNER JOIN, werden die Daten aus beiden Auflistungen kombiniert. Elemente, die bei denen entspricht die angegebenen Schlüsselwerten werden eingeschlossen. Alle Elemente der beiden Auflistungen, die nicht über ein übereinstimmendes Element in die andere Auflistung verfügen, werden ausgeschlossen.  
  
 In Visual Basic LINQ bietet zwei Optionen zum Ausführen eines inneren Joins: eine implizite Verknüpfung und eine explizite Verknüpfung.  
  
 Eine implizite Verknüpfung gibt an, die Auflistungen verknüpft werden, eine `From` Klausel und die entsprechenden Schlüsselfelder im identifiziert eine `Where` Klausel. Visual Basic wird implizit die beiden Auflistungen, die basierend auf den angegebenen Schlüssel Feldern verknüpft.  
  
 Sie können die expliziten Join angeben, indem die `Join` -Klausel, wenn bestimmte, zu welcher Schlüssel für die Verwendung in der Verknüpfung Felder sein sollen. In diesem Fall eine `Where` -Klausel kann weiterhin verwendet werden, um die Ergebnisse der Abfrage zu filtern.  
  
#### <a name="to-perform-an-inner-join-by-using-the-join-clause"></a>Ein Inner Join ausführen, mithilfe der Join-Klausel  
  
1.  Fügen Sie den folgenden Code der `Module1` Modul in Ihrem Projekt aus, um Beispiele für beide eine implizite und explizite innere Verknüpfung anzuzeigen.  
  
     [!code-vb[VbLINQHowTos#4](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_3.vb)]  
  
## <a name="perform-a-left-outer-join-by-using-the-group-join-clause"></a>Führen Sie eine linke äußere Verknüpfung mit dem Group Join-Klausel  
 LEFT OUTER JOIN enthält alle Elemente aus der Auflistung der linken Seite des Joins und nur übereinstimmende Werte aus der Auflistung der rechten Seite des Joins. Alle Elemente aus der Auflistung der rechten Seite des Joins, die nicht über ein übereinstimmendes Element in der linken Auflistung verfügen, werden aus dem Abfrageergebnis ausgeschlossen.  
  
 Die `Group Join` Klausel ausführt, aktiviert ist, einem LEFT OUTER JOIN. Der Unterschied zwischen als LEFT OUTER JOIN in der Regel bezeichnet wird und was die `Group Join` Klausel zurückgegeben wird, die die `Group Join` Klausel Ergebnisse für Servergruppen aus der Auflistung der rechten Seite des Joins für jedes Element in der linken Auflistung. In einer relationalen Datenbank gibt LEFT OUTER JOIN, dass ein nicht gruppierte Ergebnis in dem jedes Element in der Abfrage führen übereinstimmende Elemente aus beiden Auflistungen in der Verknüpfung enthält. In diesem Fall werden die Elemente aus der Auflistung der linken Seite des Joins für jedes passende Element aus der rechten Auflistung wiederholt. Es wird angezeigt, wie dies aussieht, wenn Sie das nächste Verfahren ausführen.  
  
 Sie können die Ergebnisse Abrufen einer `Group Join` Abfrage als nicht gruppierte Ergebnis durch das Erweitern Ihrer Abfrage aus, um ein Element für jede gruppierte Abfrageergebnis zurück. Um dies zu erreichen, müssen Sie sicherstellen, dass Sie für Abfragen die `DefaultIfEmpty` -Methode der gruppierte Auflistung. Dadurch wird sichergestellt, dass Elemente aus der Auflistung der linken Seite des Joins immer noch im Abfrageergebnis enthalten sind, auch wenn sie keine übereinstimmenden Ergebnisse aus der Auflistung von rechten verfügen. Sie können Code hinzufügen, um Ihrer Abfrage einen Standardwert für das Ergebnis angeben, wenn kein übereinstimmender Wert aus der Auflistung der rechten Seite des Joins vorhanden ist.  
  
#### <a name="to-perform-a-left-outer-join-by-using-the-group-join-clause"></a>Um einen Left Outer Join ausführen, indem Sie mit der Group Join-Klausel  
  
1.  Fügen Sie den folgenden Code der `Module1` Modul in Ihrem Projekt aus, um Beispiele für eine gruppierte linke äußere Verknüpfung und einen nicht gruppierten linken äußeren Join anzuzeigen.  
  
     [!code-vb[VbLINQHowTos#3](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_4.vb)]  
  
## <a name="perform-a-join-by-using-a-composite-key"></a>Ausführen einer Verknüpfung mithilfe eines zusammengesetzten Schlüssels  
 Können Sie die `And` -Schlüsselwort in einer `Join` oder `Group Join` -Klausel, um die mehrfachen Schlüsselfelder verwenden, beim Abgleich zu identifizieren. Werte aus den zu verknüpfenden Auflistungen. Die `And` -Schlüsselwort Gibt an, dass alle Felder müssen für die angegebenen zu verknüpfenden Elemente übereinstimmen.  
  
#### <a name="to-perform-a-join-by-using-a-composite-key"></a>Für einen Join mithilfe eines zusammengesetzten Schlüssels  
  
1.  Fügen Sie den folgenden Code der `Module1` Modul in Ihrem Projekt aus, um Beispiele für einen Join anzuzeigen, die einen zusammengesetzten Schlüssel verwendet.  
  
     [!code-vb[VbLINQHowTos#5](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_5.vb)]  
  
## <a name="run-the-code"></a>Führen Sie den Code  
  
#### <a name="to-add-code-to-run-the-examples"></a>Hinzufügen von Code zum Ausführen der Beispiele  
  
1.  Ersetzen Sie die `Sub Main` in die `Module1` Modul in Ihrem Projekt durch den folgenden Code zum Ausführen der Beispiele in diesem Thema.  
  
     [!code-vb[VbLINQHowTos#6](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_6.vb)]  
  
2.  Drücken Sie F5, um die Beispiele ausführen.  
  
## <a name="see-also"></a>Siehe auch
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Join-Klausel](../../../../visual-basic/language-reference/queries/join-clause.md)
- [Group Join-Klausel](../../../../visual-basic/language-reference/queries/group-join-clause.md)
- [From-Klausel](../../../../visual-basic/language-reference/queries/from-clause.md)
- [Where-Klausel](../../../../visual-basic/language-reference/queries/where-clause.md)
- [Abfragen](../../../../visual-basic/language-reference/queries/index.md)
- [Datentransformationen mit LINQ (C#)](../../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md)
