---
title: Schreiben von Abfragen in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ [Visual Basic], walkthroughs
- LINQ [Visual Basic], writing queries
- writing LINQ queries [Visual Basic]
ms.assetid: f0045808-b9fe-4d31-88d1-473d9957211e
ms.openlocfilehash: 256075ad5de5b88595dd4be7f199a74b5912c082
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046550"
---
# <a name="walkthrough-writing-queries-in-visual-basic"></a>Exemplarische Vorgehensweise: Schreiben von Abfragen in Visual Basic

In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Sie Visual Basic sprach [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] Funktionen verwenden können, um Abfrage Ausdrücke zu schreiben. In der exemplarischen Vorgehensweise wird veranschaulicht, wie Abfragen für eine Liste von Student-Objekten erstellt werden, wie die Abfragen ausgeführt werden und wie diese geändert werden. Die Abfragen enthalten mehrere Features, einschließlich Objektinitialisierer, lokaler Typrückschluss und anonymer Typen.

Nachdem Sie diese exemplarische Vorgehensweise durchgearbeitet haben, können Sie mit den Beispielen und der Dokumentation für den [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] jeweiligen Anbieter fortfahren, an dem Sie interessiert sind. [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]zu den [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]Anbietern gehören, LINQ to DataSet [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]und.

## <a name="create-a-project"></a>Erstellen eines Projekts

### <a name="to-create-a-console-application-project"></a>So erstellen Sie ein Konsolen Anwendungsprojekt

1. Starten Sie Visual Studio.

2. Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.

3. Klicken Sie in der Liste **installierte Vorlagen** auf **Visual Basic**.

4. Klicken Sie in der Liste der Projekttypen auf **Konsolenanwendung**. Geben Sie im Feld **Name** einen Namen für das Projekt ein, und klicken Sie dann auf **OK**.

    Ein Projekt wird erstellt. Standardmäßig enthält Sie einen Verweis auf "System. Core. dll". Außerdem enthält die Liste der **importierten Namespaces** auf der [Seite "Verweise", Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic) den <xref:System.Linq?displayProperty=nameWithType> Namespace.

5. Vergewissern Sie sich, dass auf der [Seite Kompilieren der Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)die **Option ableiten** **auf on**festgelegt ist.

## <a name="add-an-in-memory-data-source"></a>Hinzufügen einer in-Memory-Datenquelle

Die Datenquelle für die Abfragen in dieser exemplarischen Vorgehensweise ist eine `Student` Liste von Objekten. Jedes `Student` -Objekt enthält einen Vornamen, einen Nachnamen, ein Klassen Jahr und einen akademischen Rang im studentenkörper.

### <a name="to-add-the-data-source"></a>So fügen Sie die Datenquelle hinzu

- Definieren Sie `Student` eine-Klasse, und erstellen Sie eine Liste von Instanzen der-Klasse.

  > [!IMPORTANT]
  > Der Code, der zum Definieren `Student` der-Klasse und zum Erstellen der in den Beispielen für exemplarische Vorgehens [Weise verwendeten Liste benötigt wird, finden Sie unter Gewusst wie: Erstellen Sie eine Liste von](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)Elementen. Sie können es von dort kopieren und in Ihr Projekt einfügen. Der neue Code ersetzt den Code, der beim Erstellen des Projekts aufgetreten ist.

### <a name="to-add-a-new-student-to-the-students-list"></a>So fügen Sie der Liste "Students" einen neuen Studenten hinzu

- Befolgen Sie das Muster in `getStudents` der-Methode, um der Liste `Student` eine weitere Instanz der-Klasse hinzuzufügen. Durch das Hinzufügen des Studenten werden Objektinitialisierer eingeführt. Weitere Informationen finden [Sie unter Objektinitialisierer: Benannte und anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).

## <a name="create-a-query"></a>Erstellen einer Abfrage

Bei der Ausführung der in diesem Abschnitt hinzugefügten Abfrage wird eine Liste der Schüler/Studenten erstellt, deren Academic Rank Sie in die Top-10 einfügt. Da die Abfrage jedes Mal das `Student` gesamte Objekt auswählt, ist `IEnumerable(Of Student)`der Typ des Abfrage Ergebnisses. Der Typ der Abfrage wird jedoch in der Regel nicht in den Abfrage Definitionen angegeben. Stattdessen verwendet der Compiler den lokalen Typrückschluss, um den Typ zu bestimmen. Weitere Informationen finden Sie unter [lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md). Die Bereichs Variable `currentStudent`der Abfrage,, fungiert als Verweis auf jede `Student` Instanz in der Quelle, `students`und bietet Zugriff auf die Eigenschaften der einzelnen Objekte in `students`.

### <a name="to-create-a-simple-query"></a>So erstellen Sie eine einfache Abfrage

1. Suchen Sie den Speicherort `Main` in der-Methode des Projekts, das wie folgt gekennzeichnet ist:

    [!code-vb[VbLINQWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#1)]

    Kopieren Sie den folgenden Code, und fügen Sie ihn in ein.

    [!code-vb[VbLINQWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#2)]

2. Bewegen Sie den Mauszeiger `studentQuery` auf den Code, um zu überprüfen, ob der vom `IEnumerable(Of Student)`Compiler zugewiesene Typ ist.

## <a name="run-the-query"></a>Ausführen der Abfrage

Die- `studentQuery` Variable enthält die Definition der Abfrage, nicht die Ergebnisse der Abfrage Ausführung. Ein typischer Mechanismus zum Ausführen einer Abfrage ist eine `For Each` -Schleife. Der Zugriff auf jedes Element in der zurückgegebenen Sequenz erfolgt über die Schleifen Iterations Variable. Weitere Informationen zur Abfrage Ausführung finden Sie unter [Schreiben Ihrer ersten LINQ-Abfrage](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).

### <a name="to-run-the-query"></a>So führen Sie die Abfrage aus

1. Fügen Sie die `For Each` folgende-Schleife unterhalb der Abfrage in Ihrem Projekt hinzu.

    [!code-vb[VbLINQWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#3)]

2. Bewegen Sie den Mauszeiger über die Schleifen Steuerungs `studentRecord` Variable, um den zugehörigen Datentyp anzuzeigen. Der Typ von `studentRecord` wird als abgeleitet `Student`, weil `studentQuery` eine Auflistung von `Student` -Instanzen zurückgibt.

3. Erstellen und führen Sie die Anwendung aus, indem Sie STRG + F5 drücken. Notieren Sie sich die Ergebnisse im Konsolenfenster.

## <a name="modify-the-query"></a>Ändern der Abfrage

Es ist einfacher, Abfrageergebnisse zu scannen, wenn Sie in einer bestimmten Reihenfolge vorliegen. Sie können die zurückgegebene Sequenz basierend auf allen verfügbaren Feldern sortieren.

### <a name="to-order-the-results"></a>So sortieren Sie die Ergebnisse

1. Fügen Sie die `Order By` folgende Klausel zwischen `Where` der-Anweisung `Select` und der-Anweisung der Abfrage hinzu. Die `Order By` -Klausel sortiert die Ergebnisse alphabetisch von A bis Z, gemäß dem Nachnamen der einzelnen Schüler/Studenten.

    ```
    Order By currentStudent.Last Ascending
    ```

2. Fügen Sie der Abfrage beide Felder hinzu, um nach Nachname und Vorname zu sortieren:

    ```
    Order By currentStudent.Last Ascending, currentStudent.First Ascending
    ```

    Sie können auch angeben `Descending` , um von Z bis A zu sortieren.

3. Erstellen und führen Sie die Anwendung aus, indem Sie STRG + F5 drücken. Notieren Sie sich die Ergebnisse im Konsolenfenster.

### <a name="to-introduce-a-local-identifier"></a>So führen Sie einen lokalen Bezeichner ein

1. Fügen Sie den Code in diesem Abschnitt hinzu, um einen lokalen Bezeichner in den Abfrage Ausdruck einzuführen. Der lokale Bezeichner enthält ein Zwischenergebnis. Im folgenden Beispiel `name` ist ein Bezeichner, der eine Verkettung der vor-und Nachnamen des Studenten enthält. Ein lokaler Bezeichner kann zur einfacheren Verwendung verwendet werden, oder er kann die Leistung verbessern, indem er die Ergebnisse eines Ausdrucks speichert, die andernfalls mehrmals berechnet werden.

    [!code-vb[VbLINQWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#4)]

2. Erstellen und führen Sie die Anwendung aus, indem Sie STRG + F5 drücken. Notieren Sie sich die Ergebnisse im Konsolenfenster.

### <a name="to-project-one-field-in-the-select-clause"></a>So projizieren Sie ein Feld in der SELECT-Klausel

1. Fügen Sie die Abfrage `For Each` und die Schleife aus diesem Abschnitt hinzu, um eine Abfrage zu erstellen, die eine Sequenz erzeugt, deren Elemente sich von den Elementen in der Quelle unterscheiden. Im folgenden Beispiel handelt es sich bei der Quelle um eine `Student` Auflistung von-Objekten, es wird jedoch nur ein Member jedes-Objekts zurückgegeben: der Vorname der Schüler/Studenten, deren Nachname "Garcia" ist. Da `currentStudent.First` eine Zeichenfolge ist, ist `IEnumerable(Of String)`der Datentyp der Sequenz, `studentQuery3` die von zurückgegeben wird, eine Sequenz von Zeichen folgen. Wie in den vorherigen Beispielen wird die Zuweisung eines Datentyps für `studentQuery3` den Compiler beibehalten, um mithilfe des lokalen Typrückschlusses festzustellen.

    [!code-vb[VbLINQWalkthrough#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#5)]

2. Bewegen Sie den Mauszeiger `studentQuery3` auf den Code, um zu überprüfen, ob `IEnumerable(Of String)`der zugewiesene Typ ist.

3. Erstellen und führen Sie die Anwendung aus, indem Sie STRG + F5 drücken. Notieren Sie sich die Ergebnisse im Konsolenfenster.

### <a name="to-create-an-anonymous-type-in-the-select-clause"></a>So erstellen Sie einen anonymen Typ in der SELECT-Klausel

1. Fügen Sie den Code aus diesem Abschnitt hinzu, um zu sehen, wie anonyme Typen in Abfragen verwendet werden. Sie verwenden Sie in Abfragen, wenn Sie mehrere Felder aus der Datenquelle zurückgeben möchten, anstatt die Daten`currentStudent` Sätze (Datensätze in vorherigen Beispielen) oder`First` einzelne Felder (im vorherigen Abschnitt) zu vervollständigen. Anstatt einen neuen benannten Typ zu definieren, der die Felder enthält, die Sie in das Ergebnis einschließen möchten, geben Sie die Felder `Select` in der-Klausel an, und der Compiler erstellt einen anonymen Typ mit diesen Feldern als Eigenschaften. Weitere Informationen finden Sie unter [Anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).

    Im folgenden Beispiel wird eine Abfrage erstellt, die den Namen und den Rang der Senioren mit dem akademischen Rang zwischen 1 und 10 in der Reihenfolge des akademischen Rang zurückgibt. In diesem Beispiel muss der Typ von `studentQuery4` abgeleitet werden, da die `Select` -Klausel eine Instanz eines anonymen Typs zurückgibt und ein anonymer Typ keinen verwendbaren Namen hat.

    [!code-vb[VbLINQWalkthrough#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#6)]

2. Erstellen und führen Sie die Anwendung aus, indem Sie STRG + F5 drücken. Notieren Sie sich die Ergebnisse im Konsolenfenster.

## <a name="additional-examples"></a>Weitere Beispiele

Nachdem Sie sich nun mit den Grundlagen vertraut gemacht haben, finden Sie im folgenden eine Liste zusätzlicher Beispiele zum veranschaulichen [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] der Flexibilität und Leistungsfähigkeit von Abfragen. Jedem Beispiel wird eine kurze Beschreibung der Funktionsweise vorangestellt. Bewegen Sie den Mauszeiger über die Abfrageergebnis Variable für jede Abfrage, um den abzurufbaren Typ anzuzeigen. Verwenden Sie `For Each` eine-Schleife, um die Ergebnisse zu erzielen.

[!code-vb[VbLINQWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#7)]

## <a name="additional-information"></a>Zusätzliche Informationen

Nachdem Sie mit den grundlegenden Konzepten der Arbeit mit Abfragen vertraut sind, können Sie die Dokumentation und die Beispiele für den spezifischen [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Anbietertyp lesen, an dem Sie interessiert sind:

- [LINQ to Objects](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)

- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)

- [LINQ to XML](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)

- [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)

## <a name="see-also"></a>Siehe auch

- [Language-Integrated Query (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)
- [Getting Started with LINQ in Visual Basic (Erste Schritte mit LINQ in Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Objektinitialisierer: Benannte und anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Abfragen](../../../../visual-basic/language-reference/queries/index.md)
