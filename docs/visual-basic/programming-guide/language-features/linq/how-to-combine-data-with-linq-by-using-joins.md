---
title: 'Vorgehensweise: Kombinieren von Daten mit LINQ mithilfe von Joins'
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], joins
- joins [LINQ in Visual Basic]
- Join clause [LINQ in Visual Basic]
- Group Join clause [Visual Basic]
- joining [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 5b00a478-035b-41c6-8918-be1a97728396
ms.openlocfilehash: de8c4ec3ab8a0f2335c034231c661380420fd31b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405003"
---
# <a name="how-to-combine-data-with-linq-by-using-joins-visual-basic"></a>Gewusst wie: Kombinieren von Daten mit LINQ mithilfe von Joins (Visual Basic)
Visual Basic stellt die `Join` -und- `Group Join` Abfrage Klauseln bereit, mit denen Sie den Inhalt mehrerer Auflistungen basierend auf gemeinsamen Werten zwischen den Auflistungen kombinieren können. Diese Werte werden als *Schlüssel* Werte bezeichnet. Entwickler, die mit relationalen Datenbankkonzepten vertraut sind, erkennen die `Join` -Klausel als inneren Join und die- `Group Join` Klausel als einen linken äußeren Join.  
  
 Die Beispiele in diesem Thema veranschaulichen einige Möglichkeiten zum Kombinieren von Daten mithilfe der `Join` `Group Join` Abfrage Klauseln und.  
  
## <a name="create-a-project-and-add-sample-data"></a>Erstellen eines Projekts und Hinzufügen von Beispiel Daten  
  
#### <a name="to-create-a-project-that-contains-sample-data-and-types"></a>So erstellen Sie ein Projekt, das Beispiel Daten und-Typen enthält  
  
1. Öffnen Sie Visual Studio, und fügen Sie ein neues Visual Basic Konsolen Anwendungsprojekt hinzu, um die Beispiele in diesem Thema auszuführen. Doppelklicken Sie auf die durch Visual Basic erstellte Datei Module1. vb.  
  
2. In den Beispielen in diesem Thema werden der-Typ und der- `Person` `Pet` Typ sowie die Daten aus dem folgenden Codebeispiel verwendet. Kopieren Sie diesen Code in das Standardmodul, das `Module1` von Visual Basic erstellt wurde.  
  
     [!code-vb[VbLINQHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#1)]  
    [!code-vb[VbLINQHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#2)]  
  
## <a name="perform-an-inner-join-by-using-the-join-clause"></a>Ausführen einer inneren Verknüpfung mithilfe der Join-Klausel  
 Ein innerer Join kombiniert Daten aus zwei Auflistungen. Elemente, für die die angegebenen Schlüsselwerte Stimmen, werden eingeschlossen. Alle Elemente aus einer Auflistung, die nicht über ein übereinstimmendes Element in der anderen Sammlung verfügen, werden ausgeschlossen.  
  
 In Visual Basic bietet LINQ zwei Optionen für die Durchführung eines inneren Joins: einen impliziten Join und einen expliziten Join.  
  
 Ein impliziter Join gibt die Auflistungen an, die in einer-Klausel miteinander verknüpft werden sollen, `From` und identifiziert die übereinstimmenden Schlüsselfelder `Where` Visual Basic die zwei Auflistungen implizit auf der Grundlage der angegebenen Schlüsselfelder verbindet.  
  
 Sie können einen expliziten Join angeben, indem Sie die- `Join` Klausel verwenden, wenn Sie spezifisch sein möchten, welche Schlüsselfelder im Join verwendet werden sollen. In diesem Fall kann eine- `Where` Klausel weiterhin verwendet werden, um die Abfrageergebnisse zu filtern.  
  
#### <a name="to-perform-an-inner-join-by-using-the-join-clause"></a>So führen Sie einen inneren Join mithilfe der Join-Klausel aus  
  
1. Fügen Sie dem- `Module1` Modul in Ihrem Projekt den folgenden Code hinzu, um Beispiele für einen impliziten und einen expliziten inneren Join anzuzeigen.  
  
     [!code-vb[VbLINQHowTos#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#4)]  
  
## <a name="perform-a-left-outer-join-by-using-the-group-join-clause"></a>Ausführen eines Left Outer Join mithilfe der Group Join-Klausel  
 Ein linker äußerer Join schließt alle Elemente aus der linksseitigen Auflistung des Joins und nur übereinstimmende Werte aus der rechten Auflistung der Verknüpfung ein. Alle Elemente aus der rechten Auflistung des Joins, die nicht über ein übereinstimmendes Element in der Auflistung auf der linken Seite verfügen, werden aus dem Abfrageergebnis ausgeschlossen.  
  
 Die- `Group Join` Klausel führt in der Tat einen Left Outer Join aus. Der Unterschied zwischen dem, der in der Regel als linker äußerer Join bezeichnet wird, und der `Group Join` Rückgabe der Klausel besteht darin, dass die- `Group Join` Klausel Ergebnisse aus der rechten Auflistung des Joins für jedes Element in der linken Auflistung gruppiert. In einer relationalen Datenbank gibt ein linker äußerer Join ein nicht gruppiertes Ergebnis zurück, in dem jedes Element im Abfrageergebnis übereinstimmende Elemente aus beiden Auflistungen im Join enthält. In diesem Fall werden die Elemente aus der linksseitigen Auflistung der Verknüpfung für jedes übereinstimmende Element aus der rechten Auflistung wiederholt. Wenn Sie das nächste Verfahren ausführen, sehen Sie, wie es aussieht.  
  
 Sie können die Ergebnisse einer `Group Join` Abfrage als nicht gruppiertes Ergebnis abrufen, indem Sie die Abfrage so erweitern, dass ein Element für jedes gruppierte Abfrageergebnis zurückgegeben wird. Um dies zu erreichen, müssen Sie sicherstellen, dass Sie die- `DefaultIfEmpty` Methode der gruppierten Auflistung Abfragen. Dadurch wird sichergestellt, dass Elemente aus der linksseitigen Auflistung des Joins weiterhin im Abfrageergebnis enthalten sind, auch wenn Sie über keine übereinstimmenden Ergebnisse aus der rechten Auflistung verfügen. Sie können der Abfrage Code hinzufügen, um einen Standard Ergebniswert bereitzustellen, wenn kein übereinstimmender Wert aus der rechtsseitigen Auflistung des Joins vorhanden ist.  
  
#### <a name="to-perform-a-left-outer-join-by-using-the-group-join-clause"></a>So führen Sie einen Left Outer Join mithilfe der Group Join-Klausel aus  
  
1. Fügen Sie dem- `Module1` Modul in Ihrem Projekt den folgenden Code hinzu, um Beispiele für einen gruppierten linken äußeren Join und einen nicht gruppierten linken äußeren Join anzuzeigen.  
  
     [!code-vb[VbLINQHowTos#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#3)]  
  
## <a name="perform-a-join-by-using-a-composite-key"></a>Ausführen eines Joins mithilfe eines zusammengesetzten Schlüssels  
 Sie können das- `And` Schlüsselwort in einer- `Join` oder- `Group Join` Klausel verwenden, um mehrere Schlüsselfelder zu identifizieren, die beim Abgleichen von Werten aus den verbundenen Auflistungen verwendet Das `And` Schlüsselwort gibt an, dass alle angegebenen Schlüsselfelder für Elemente, die verknüpft werden sollen, entsprechen müssen.  
  
#### <a name="to-perform-a-join-by-using-a-composite-key"></a>So führen Sie einen Join mit einem zusammengesetzten Schlüssel aus  
  
1. Fügen Sie dem- `Module1` Modul in Ihrem Projekt den folgenden Code hinzu, um Beispiele für einen Join anzuzeigen, der einen zusammengesetzten Schlüssel verwendet.  
  
     [!code-vb[VbLINQHowTos#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#5)]  
  
## <a name="run-the-code"></a>Ausführen des Codes  
  
#### <a name="to-add-code-to-run-the-examples"></a>So fügen Sie Code zum Ausführen der Beispiele hinzu  
  
1. Ersetzen `Sub Main` Sie im- `Module1` Modul in Ihrem Projekt durch den folgenden Code, um die Beispiele in diesem Thema auszuführen.  
  
     [!code-vb[VbLINQHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#6)]  
  
2. Drücken Sie F5, um die Beispiele auszuführen.  
  
## <a name="see-also"></a>Weitere Informationen

- [LINQ](index.md)
- [Einführung in LINQ in Visual Basic](introduction-to-linq.md)
- [Join-Klausel](../../../language-reference/queries/join-clause.md)
- [Group Join-Klausel](../../../language-reference/queries/group-join-clause.md)
- [From-Klausel](../../../language-reference/queries/from-clause.md)
- [WHERE-Klausel](../../../language-reference/queries/where-clause.md)
- [Abfragen](../../../language-reference/queries/index.md)
- [Daten Transformationen mit LINQ (c#)](../../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md)
