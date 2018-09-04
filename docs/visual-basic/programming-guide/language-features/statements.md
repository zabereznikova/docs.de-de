---
title: Anweisungen in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], declaring
- colons (:) [Visual Basic]
- constants [Visual Basic], defining
- underlines
- constants [Visual Basic], statements
- blue underline [Visual Basic]
- procedures [Visual Basic], statements
- variables [Visual Basic], assigning
- line breaks [Visual Basic], in code
- executable statements [Visual Basic]
- variables [Visual Basic], defining
- statements [Visual Basic], about statements
ms.assetid: fcfdee1a-82b7-4846-98f7-9ca3f5160089
ms.openlocfilehash: e66acae5e98d561883f4ad59853dfd862c8ebfee
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43506289"
---
# <a name="statements-in-visual-basic"></a>Anweisungen in Visual Basic

Eine Anweisung in Visual Basic ist eine vollständige Anweisung. Sie können Schlüsselwörter, Operatoren, Variablen, Konstanten und Ausdrücke enthalten. Jede Anweisung gehört zu einer der folgenden Kategorien:

- **Deklarationsanweisungen**, dem Benennen Sie eine Variable, Konstante oder Prozedur, und können auch einen Datentyp angeben.

- **Ausführbare Anweisungen**, das Initiieren von Aktionen auf. Diese Anweisungen können eine Methode oder Funktion aufrufen, und können eine Schleife oder branch mithilfe von Codeblöcken. Ausführbare Anweisungen enthalten **Zuweisungsanweisungen**, die einen Wert oder Ausdruck zuweisen, um eine Variable oder Konstante.

Dieses Thema beschreibt die einzelnen Kategorien. In diesem Thema wird außerdem beschrieben, wie Sie mehrere Anweisungen in einer einzelnen Zeile zu kombinieren und um eine Anweisung über mehrere Zeilen den Vorgang fortzusetzen.

## <a name="declaration-statements"></a>Deklarationsanweisungen

Sie verwenden die deklarationsanweisungen, einen Namen und Prozeduren, Variablen, Eigenschaften, Arrays und Konstanten zu definieren. Wenn Sie ein Programmierelement deklarieren, können Sie auch die-Datentyp, Zugriffsebene und Umfang definieren. Weitere Informationen finden Sie unter [Merkmale der deklarierten Elemente](./declared-elements/declared-element-characteristics.md).

Das folgende Beispiel enthält drei Deklarationen.

[!code-vb[VbVbalrStatements#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#80)]

Die erste Deklaration ist die `Sub` Anweisung. Zusammen mit der entsprechenden `End Sub` -Anweisung deklariert eine Prozedur namens `applyFormat`. Außerdem wird angegeben, die `applyFormat` ist `Public`, was bedeutet, dass jeder Code, der darauf verweisen kann aufgerufen werden kann.

Die zweite Deklaration ist die `Const` -Anweisung, die die Konstante deklariert `limit`unter Angabe der `Integer` -Datentyp und Wert 33.

Die dritte Deklaration ist die `Dim` -Anweisung, die die Variable deklariert `thisWidget`. Der Datentyp ist ein bestimmtes Objekt, d. h. ein Objekt erstellt, aus der `Widget` Klasse. Sie können eine Variable eines beliebigen Typs elementarer Datentyp oder einen beliebigen Objekttyp an, der in der Anwendung verfügbar gemacht wird, die Sie verwenden, deklarieren.

### <a name="initial-values"></a>Anfangswerte

Wenn der Code mit einer deklarationsanweisung ausgeführt wird, reserviert Visual Basic den erforderlichen Speicher für das deklarierte Element. Wenn das Element einen Wert enthält, von Visual Basic auf den Standardwert für seinen Datentyp initialisiert. Weitere Informationen finden Sie unter "Verhalten" in [Dim-Anweisung](../../language-reference/statements/dim-statement.md).

Sie können einen Anfangswert einer Variablen als Teil der Deklaration zuweisen, wie im folgende Beispiel veranschaulicht.

[!code-vb[VbVbalrStatements#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#81)]

Wenn eine Variable ein Objekt ist, können Sie explizit erstellen eine Instanz der Klasse mithilfe von dessen Deklaration die [New-Operator](../../../visual-basic/language-reference/operators/new-operator.md) -Schlüsselwort, wie im folgenden Beispiel veranschaulicht.

[!code-vb[VbVbalrStatements#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#82)]

Beachten Sie, dass der Anfangswert, die, den Sie, in einer deklarationsanweisung angeben, keiner Variablen zugewiesen ist, bis die Ausführung der Anweisung für die Attributdeklaration erreicht. Bis zu diesem Zeitpunkt enthält die Variable den Standardwert für seinen Datentyp.

## <a name="executable-statements"></a>Ausführbare Anweisungen

Eine ausführbare Anweisung führt eine Aktion. Sie können Aufrufen einer Prozedur, einer Verzweigung zu einer anderen Stelle im Code durchlaufen mehrere-Anweisungen oder Auswerten eines Ausdrucks. Eine zuweisungsanweisung ist ein Sonderfall, der eine ausführbare Anweisung.

Im folgenden Beispiel wird ein `If...Then...Else` -programmverzweigung, um verschiedene Codeblöcke, die anhand des Werts einer Variablen auszuführen. Jeder Codeblock eine `For...Next` Schleife ausgeführt wird, eine angegebene Anzahl von Malen.

[!code-vb[VbVbalrStatements#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#83)]

Die `If` Anweisung im vorherigen Beispiel überprüft den Wert des Parameters `clockwise`. Wenn der Wert ist `True`, ruft der `spinClockwise` -Methode der `aWidget`. Wenn der Wert ist `False`, ruft der `spinCounterClockwise` -Methode der `aWidget`. Die `If...Then...Else` Kontrollstruktur endet mit `End If`.

Die `For...Next` Schleife in jedem Block Ruft die entsprechende Methode eine Anzahl von Malen gleich dem Wert, der die `revolutions` Parameter.

## <a name="assignment-statements"></a>Zuweisungsanweisungen

Zuweisungsanweisungen Zuweisungsvorgänge, die bestehen, erstellen den Wert auf der rechten Seite des Zuweisungsoperators auszuführen (`=`) und speichern ihn in das Element auf der linken Seite, wie im folgenden Beispiel.

[!code-vb[VbVbalrStatements#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#73)]

Im vorherigen Beispiel speichert die zuweisungsanweisung den literalen Wert "42" in der Variablen `v`.

### <a name="eligible-programming-elements"></a>Geeignete Programmierelemente

Das Programmierelement auf der linken Seite des Zuweisungsoperators muss annehmen und einen Wert zu speichern. Dies bedeutet, dass es muss eine Variable oder Eigenschaft, die nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md), oder es muss ein Arrayelement. Im Kontext einer zuweisungsanweisung, dieses Element bezeichnet ein *Lvalue*, für die "Linker Wert."

Der Wert auf der rechten Seite des Zuweisungsoperators wird durch einen Ausdruck generiert, die eine beliebige Kombination aus Literalen, Konstanten, Variablen, Eigenschaften, Elemente des Arrays, andere Ausdrücke oder Funktionsaufrufe enthalten kann. Dies wird anhand des folgenden Beispiels veranschaulicht.

[!code-vb[VbVbalrStatements#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#74)]

Im vorherige Beispiel fügt den Wert, der in der Variablen `y` auf den Wert in der Variablen `z`, und fügt dann den vom Aufruf der Funktion zurückgegebenen Wert `findResult`. Der Gesamtwert der dieser Ausdruck wird dann in der Variablen gespeichert `x`.

### <a name="data-types-in-assignment-statements"></a>Datentypen in zuweisungsanweisungen

Zusätzlich zu numerischen Werten, der Zuweisungsoperator kann auch zugewiesen `String` Werte, wie im folgende Beispiel veranschaulicht.

[!code-vb[VbVbalrStatements#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#75)]

Sie können auch zuweisen `Boolean` Werte, mit eine `Boolean` literal oder ein `Boolean` -Ausdruck, wie im folgenden Beispiel veranschaulicht.

[!code-vb[VbVbalrStatements#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#76)]

Auf ähnliche Weise können Sie die Programmierelemente der entsprechenden Werte zuweisen der `Char`, `Date`, oder `Object` -Datentyp. Sie können auch eine Objektinstanz zuweisen, auf ein Element deklariert, um die Klasse aus der dieser Instanz erstellt wird.

### <a name="compound-assignment-statements"></a>Verbundzuweisungsanweisungen

*Verbundanweisungen für Zuordnung* zuerst führen einen Vorgang für einen Ausdruck ein, bevor Sie ihn auf ein Programmierelement zuweisen. Das folgende Beispiel zeigt einen der folgenden Operatoren, `+=`, die inkrementiert des Wert der Variablen auf der linken Seite des Operators durch den Wert des Ausdrucks auf der rechten Seite.

[!code-vb[VbVbalrStatements#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#77)]

Im vorherige Beispiel wird 1 auf den Wert der `n`, und speichert dann diesen neuen Wert in `n`. Dies ist die Kurzform entspricht der folgenden Anweisung:

[!code-vb[VbVbalrStatements#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#78)]

Eine Vielzahl von Vorgängen für zusammengesetzte Zuweisung kann mithilfe von Operatoren dieses Typs ausgeführt werden. Eine Liste dieser Operatoren und Weitere Informationen dazu finden Sie [Zuweisungsoperatoren](../../../visual-basic/language-reference/operators/assignment-operators.md).

Der Zuweisungsoperator für die Verkettung (`&=`) eignet sich für das Hinzufügen einer Zeichenfolge am Ende einer bereits vorhandenen Zeichenfolgen, wie im folgende Beispiel veranschaulicht.

[!code-vb[VbVbalrStatements#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#79)]

### <a name="type-conversions-in-assignment-statements"></a>Typkonvertierung in Zuweisungsanweisungen

Der Wert, die, den Sie eine Variable, Eigenschaft oder Array-Elements zuweisen, muss einen Datentyp aufweisen, die für dieses Zielelement geeignet sein. Im Allgemeinen sollten Sie zum Generieren eines Werts, den gleichen Datentyp wie das Zielelement. Einige Typen können jedoch bei der Zuweisung zu anderen Typen konvertiert werden.

Weitere Informationen zum Konvertieren von Datentypen, finden Sie unter [Typkonvertierung in Visual Basic](./data-types/type-conversions.md). Kurz gesagt, konvertiert Visual Basic automatisch einen Wert eines bestimmten Typs in einen anderen Typ, den erweitert werden kann. Ein *eine erweiternde Konvertierung* ist eines, immer zur Laufzeit erfolgreich ist und keine Daten zu verlieren. Visual Basic konvertiert z. B. eine `Integer` Wert `Double` bei Bedarf, da `Integer` erweitert, um `Double`. Weitere Informationen finden Sie unter [Widening and Narrowing Conversions](./data-types/widening-and-narrowing-conversions.md).

*Einschränkende Konvertierungen* (diejenigen, die nicht erweiternde werden) enthalten ein Risiko Fehler zur Laufzeit oder Daten verloren gehen. Sie können eine einschränkende Konvertierung explizit ausführen, mit der eine Typkonvertierungsfunktion, oder Sie können den Compiler an, führen alle Konvertierungen implizit durch Festlegen von verweisen `Option Strict Off`. Weitere Informationen finden Sie unter [implizite und explizite Konvertierungen](./data-types/implicit-and-explicit-conversions.md).

## <a name="putting-multiple-statements-on-one-line"></a>Mehrere Anweisungen platzieren in einer Zeile

Sie haben mehrere Anweisungen in einer einzelnen Zeile, die durch Doppelpunkt getrennte (`:`) Zeichen. Dies wird anhand des folgenden Beispiels veranschaulicht.

[!code-vb[VbVbalrStatements#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#70)]

Obwohl gelegentlich praktisch ist, wird diese Form der Syntax Ihr Code schwer zu lesen und zu verwalten. Daher empfiehlt es sich, dass Sie eine Anweisung auf eine Zeile beibehalten.

## <a name="continuing-a-statement-over-multiple-lines"></a>Fortsetzen einer Anweisung über mehrere Zeilen

Eine Anweisung ist in der Regel in einer Zeile passt, aber wenn er zu lang ist, können Sie es weiterhin, auf die nächste Zeile, die über eine Zeilenfortsetzungszeichenfolge, besteht ein Leerzeichen, gefolgt von einem Unterstrich (`_`) gefolgt von einem Wagenrücklauf. Im folgenden Beispiel die `MsgBox` ausführbare Anweisung wird fortgesetzt, mehr als zwei Zeilen.

[!code-vb[VbVbalrStatements#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#71)]

### <a name="implicit-line-continuation"></a>Implizite zeilenfortsetzung

In vielen Fällen können Sie eine Anweisung auf der nächsten Zeile fortfahren, ohne den Unterstrich enthalten (`_`). Die folgenden Syntaxelemente weiterhin implizit die Anweisung in der nächsten Zeile des Codes.

- Nach einem Komma (`,`). Zum Beispiel:

   [!code-vb[VbVbalrLineContinuation#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#1)]

- Nach der öffnenden Klammer (`(`) oder vor einer schließenden Klammer (`)`). Zum Beispiel:

   [!code-vb[VbVbalrLineContinuation#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#2)]

- Nach einer öffnenden geschweiften Klammer (`{`) oder vor einer schließenden geschweiften Klammer (`}`). Zum Beispiel:

    [!code-vb[VbVbalrLineContinuation#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#3)]

    Weitere Informationen finden Sie unter [Objektinitialisierer: benannte und anonyme Typen](./objects-and-classes/object-initializers-named-and-anonymous-types.md) oder [Auflistungsinitialisierer](./collection-initializers/index.md).

- Nach dem ein Öffnen eines eingebetteten Ausdrucks (`<%=`) oder vor dem Ende eines eingebetteten Ausdrucks (`%>`) in ein XML-Literal. Zum Beispiel:

   [!code-vb[VbVbalrLineContinuation#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#4)]

   Weitere Informationen finden Sie unter [eingebettete Ausdrücke in XML](./xml/embedded-expressions-in-xml.md).

- Nach dem Verkettungsoperator (`&`). Zum Beispiel:

   [!code-vb[VbVbcnConventions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/vb/Class1.vb#9)]

   Weitere Informationen finden Sie unter [Operatoren sortiert nach Funktionalität](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).

- Nach dem Zuweisungsoperatoren (`=`, `&=`, `:=`, `+=`, `-=`, `*=`, `/=`, `\=`, `^=`, `<<=`, `>>=`). Zum Beispiel:

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   Weitere Informationen finden Sie unter [Operatoren sortiert nach Funktionalität](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).

- Nach binären Operatoren (`+`, `-`, `/`, `*`, `Mod`, `<>`, `<`, `>`, `<=`, `>=`, `^`, `>>`, `<<`, `And`, `AndAlso`, `Or`, `OrElse`, `Like`, `Xor`) in einem Ausdruck. Zum Beispiel:

   [!code-vb[VbVbalrLineContinuation#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#7)]

   Weitere Informationen finden Sie unter [Operatoren sortiert nach Funktionalität](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).

- Nach der `Is` und `IsNot` Operatoren. Zum Beispiel:

   [!code-vb[VbVbalrLineContinuation#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#8)]

   Weitere Informationen finden Sie unter [Operatoren sortiert nach Funktionalität](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).

- Nach dem Element qualifiziererzeichens (`.`) und vor den Namen des Members. Zum Beispiel:

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   Allerdings müssen Sie ein Zeilenfortsetzungszeichen einschließen (`_`) folgen eines qualifiziererzeichens Member, bei der Verwendung der `With` -Anweisung oder die Werte in der Initialisierungsliste für einen Typ angibt. Empfiehlt sich die Aufteilung der Zeile nach der Zuweisungsoperator (z. B. `=`) bei Verwendung `With` Anweisungen oder Objektlisten-Initialisierung. Zum Beispiel:

   [!code-vb[VbVbalrLineContinuation#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#14)]

   Weitere Informationen finden Sie unter [mit... With-Anweisung](../../../visual-basic/language-reference/statements/with-end-with-statement.md) oder [Objektinitialisierer: benannte und anonyme Typen](./objects-and-classes/object-initializers-named-and-anonymous-types.md).

- Nach dem ein XML-Achseneigenschaften-Qualifizierer (`.` oder `.@` oder `...`). Sie müssen jedoch ein Zeilenfortsetzungszeichen einschließen (`_`) Wenn Sie einen Memberqualifizierer angeben, bei der Verwendung der `With` Schlüsselwort. Zum Beispiel:

   [!code-vb[VbVbalrLineContinuation#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#9)]

   Weitere Informationen finden Sie unter [XML-Achseneigenschaften](../../../visual-basic/language-reference/xml-axis/index.md).

- Nach einer kleiner-als-Zeichen (<) oder vor einem größer-als-Zeichen (`>`) Wenn Sie ein Attribut angeben. Auch nach einem größer-als-Zeichen (`>`) Wenn Sie ein Attribut angeben. Sie müssen jedoch ein Zeilenfortsetzungszeichen einschließen (`_`) Wenn Sie Attribute auf Assemblyebene oder Modulebene angeben. Zum Beispiel:

   [!code-vb[VbVbalrLineContinuation#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#10)]

   Weitere Informationen finden Sie unter [Übersicht über Attribute](../../../visual-basic/programming-guide/concepts/attributes/index.md).

- Vor und nach Abfrageoperatoren (`Aggregate`, `Distinct`, `From`, `Group By`, `Group Join`, `Join`, `Let`, `Order By`, `Select`, `Skip`, `Skip While`, `Take`, `Take While`, `Where`, `In`, `Into`, `On`, `Ascending`, und `Descending`). Sie können nicht unterbrechen, eine Linie zwischen dem Schlüsselwort mit Abfrageoperatoren, die mehrere Schlüsselwörter bestehen (`Order By`, `Group Join`, `Take While`, und `Skip While`). Zum Beispiel:

   [!code-vb[VbVbalrLineContinuation#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#11)]

   Weitere Informationen finden Sie unter [Abfragen](../../../visual-basic/language-reference/queries/index.md).

- Nach der `In` -Schlüsselwort in einer `For Each` Anweisung. Zum Beispiel:

   [!code-vb[VbVbalrLineContinuation#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#12)]

   Weitere Informationen finden Sie unter [für jede... Nächste Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md).

- Nach der `From` Schlüsselwort in einem Auflistungsinitialisierer. Zum Beispiel:

   [!code-vb[VbVbalrLineContinuation#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#13)]

   Weitere Informationen finden Sie unter [Auflistungsinitialisierer](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).

## <a name="adding-comments"></a>Hinzufügen von Kommentaren

Quellcode ist nicht immer selbsterklärend sind, auch für den Programmierer, der es geschrieben hat. Damit können ihren Code zu dokumentieren, stellen die meisten Programmierer aus diesem Grund der großzügigen Verwendung von eingebetteten Kommentaren. Kommentare im Code können es sich um eine Prozedur oder eine bestimmte Anweisung für alle Benutzer lesen oder zu einem späteren Zeitpunkt mit der Arbeit erläutern. Visual Basic Kommentare werden während der Kompilierung ignoriert, und sie haben keine Auswirkungen, den kompilierten Code.

Kommentarzeilen beginnen mit einem Apostroph (`'`) oder `REM` gefolgt von einem Leerzeichen. Sie können eine beliebige Stelle im Code, mit Ausnahme von innerhalb einer Zeichenfolge hinzugefügt werden. Um einen Kommentar an eine Anweisung angefügt werden soll, fügen Sie ein Apostroph oder `REM` nach der Anweisung, gefolgt von den Kommentar. Kommentare können auch auf eine separate Zeile wechseln. Das folgende Beispiel zeigt diese Möglichkeiten.

[!code-vb[VbVbalrStatements#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#72)]

## <a name="checking-compilation-errors"></a>Überprüfen von Kompilierungsfehlern

Wenn Sie nach dem Sie eine einzige Zeile Code eingeben, wird eine blaue Wellenlinie (eine Fehlermeldung kann auch angezeigt werden) die Zeile mit, besteht ein Syntaxfehler in der Anweisung. Sie müssen feststellen, was mit der Anweisung falsch ist (durch Suchen Sie in der Taskliste aus, oder mit dem Mauszeiger auf den Fehler mit dem Mauszeiger auf ein, und lesen die Fehlermeldung) und zu korrigieren. Bis Sie alle Syntaxfehler im Code behoben haben, wird das Programm nicht ordnungsgemäß zu kompilieren.

## <a name="related-sections"></a>Verwandte Abschnitte

|Begriff|Definition|
|---|---|
|[Zuweisungsoperatoren](../../../visual-basic/language-reference/operators/assignment-operators.md)|Enthält Links zu Sprachreferenzseiten Zuweisungsoperatoren wie z. B. `=`, `*=`, und `&=`.|
|[Operatoren und Ausdrücke](./operators-and-expressions/index.md)|Zeigt, wie Elemente mit Operatoren zum erzielen neuer Werte kombinieren.|
|[Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)|Erfahren, wie eine einzelne Anweisung in mehrere Zeilen aufteilen und wie Sie mehrere Anweisungen in der gleichen Zeile platzieren.|
|[Gewusst wie: Bezeichnen von Anweisungen](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)|Veranschaulicht, wie eine einzige Zeile Code zu bezeichnen.|
