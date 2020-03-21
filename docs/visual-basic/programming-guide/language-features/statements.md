---
title: Anweisungen
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
ms.openlocfilehash: f63f0f0212913f95baab2a8a43c4b7f25a859cd9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401466"
---
# <a name="statements-in-visual-basic"></a>Anweisungen in Visual Basic

Eine Anweisung in Visual Basic ist eine vollständige Anweisung. Sie kann Schlüsselwörter, Operatoren, Variablen, Konstanten und Ausdrücke enthalten. Jede Anweisung gehört zu einer der folgenden Kategorien:

- **Deklarationsanweisungen**, die eine Variable, Konstante oder Prozedur benennen und auch einen Datentyp angeben können.

- **Ausführbare Anweisungen**, die Aktionen initiieren. Diese Anweisungen können eine Methode oder Funktion aufrufen und durch Codeblöcke schleifen oder verzweigen. Ausführbare Anweisungen umfassen **Zuweisungsanweisungen**, die einer Variablen oder Konstante einen Wert oder Ausdruck zuweisen.

In diesem Thema werden die einzelnen Kategorien beschrieben. Außerdem wird in diesem Thema beschrieben, wie mehrere Anweisungen in einer einzelnen Zeile kombiniert und eine Anweisung über mehrere Zeilen hinweg fortgesetzt wird.

## <a name="declaration-statements"></a>Deklarationsanweisungen

Mithilfe von Deklarationsanweisungen können Sie Prozeduren, Variablen, Eigenschaften, Arrays und Konstanten benennen und definieren. Wenn Sie ein Programmierelement deklarieren, können Sie auch dessen Datentyp, Zugriffsebene und Bereich definieren. Weitere Informationen finden Sie unter [Erklärte Elementeigenschaften](./declared-elements/declared-element-characteristics.md).

Das folgende Beispiel enthält drei Deklarationen.

[!code-vb[VbVbalrStatements#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#80)]

Die erste Erklärung `Sub` ist die Anweisung. Zusammen mit `End Sub` der übereinstimmenden Anweisung `applyFormat`wird eine Prozedur mit dem Namen deklariert. Es gibt auch `applyFormat` `Public`an, dass dies ist , was bedeutet, dass jeder Code, der darauf verweisen kann, ihn aufrufen kann.

Die zweite Deklaration ist `Const` die `limit`Anweisung, `Integer` die die Konstante deklariert, die den Datentyp und den Wert 33 angibt.

Die dritte Deklaration ist `Dim` die `thisWidget`Anweisung, die die Variable deklariert. Der Datentyp ist ein bestimmtes Objekt, `Widget` nämlich ein Objekt, das aus der Klasse erstellt wurde. Sie können eine Variable für einen beliebigen elementaren Datentyp oder für einen beliebigen Objekttyp deklarieren, der in der von Ihnen verwendeten Anwendung verfügbar gemacht wird.

### <a name="initial-values"></a>Anfangswerte

Wenn der Code, der eine Deklarationsanweisung enthält, ausgeführt wird, reserviert Visual Basic den für das deklarierte Element erforderlichen Speicher. Wenn das Element einen Wert enthält, initialisiert Visual Basic es auf den Standardwert für seinen Datentyp. Weitere Informationen finden Sie unter "Verhalten" in [Dim-Anweisung](../../language-reference/statements/dim-statement.md).

Sie können einer Variablen als Teil ihrer Deklaration einen Anfangswert zuweisen, wie das folgende Beispiel veranschaulicht.

[!code-vb[VbVbalrStatements#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#81)]

Wenn eine Variable eine Objektvariable ist, können Sie explizit eine Instanz ihrer Klasse erstellen, wenn Sie sie mithilfe des Schlüsselworts [New Operator](../../../visual-basic/language-reference/operators/new-operator.md) deklarieren, wie das folgende Beispiel veranschaulicht.

[!code-vb[VbVbalrStatements#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#82)]

Beachten Sie, dass der Anfangswert, den Sie in einer Deklarationsanweisung angeben, einer Variablen erst zugewiesen wird, wenn die Ausführung ihre Deklarationsanweisung erreicht hat. Bis zu diesem Zeitpunkt enthält die Variable den Standardwert für ihren Datentyp.

## <a name="executable-statements"></a>Ausführbare Anweisungen

Eine ausführbare Anweisung führt eine Aktion aus. Es kann eine Prozedur aufrufen, an eine andere Stelle im Code verzweigen, mehrere Anweisungen durchlaufen oder einen Ausdruck auswerten. Eine Zuweisungsanweisung ist ein Sonderfall einer ausführbaren Anweisung.

Im folgenden Beispiel `If...Then...Else` wird eine Steuerelementstruktur verwendet, um verschiedene Codeblöcke basierend auf dem Wert einer Variablen auszuführen. Innerhalb jedes Codeblocks `For...Next` wird eine Schleife eine bestimmte Anzahl von Malen ausgeführt.

[!code-vb[VbVbalrStatements#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#83)]

Die `If` Anweisung im vorherigen Beispiel überprüft `clockwise`den Wert des Parameters . Wenn der `True`Wert ist `spinClockwise` , `aWidget`ruft er die Methode von auf. Wenn der `False`Wert ist `spinCounterClockwise` , `aWidget`ruft er die Methode von auf. Die `If...Then...Else` Steuerungsstruktur `End If`endet mit .

Die `For...Next` Schleife innerhalb jedes Blocks ruft die entsprechende Methode mehrmals `revolutions` auf, die dem Wert des Parameters entspricht.

## <a name="assignment-statements"></a>Zuweisungsanweisungen

Zuordnungsanweisungen führen Zuordnungsvorgänge aus, die darin bestehen, den`=`Wert auf der rechten Seite des Zuweisungsoperators ( ) zu nehmen und im Element auf der linken Seite zu speichern, wie im folgenden Beispiel.

[!code-vb[VbVbalrStatements#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#73)]

Im vorherigen Beispiel speichert die Zuweisungsanweisung den Literalwert 42 in der Variablen `v`.

### <a name="eligible-programming-elements"></a>Zulässige Programmierelemente

Das Programmierelement auf der linken Seite des Zuweisungsoperators muss in der Lage sein, einen Wert zu akzeptieren und zu speichern. Dies bedeutet, dass es sich um eine Variable oder Eigenschaft handelt, die nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)ist, oder um ein Arrayelement. Im Kontext einer Zuweisungsanweisung wird ein solches Element manchmal als *lvalue*für "linker Wert" bezeichnet.

Der Wert auf der rechten Seite des Zuweisungsoperators wird durch einen Ausdruck generiert, der aus einer beliebigen Kombination von Literalen, Konstanten, Variablen, Eigenschaften, Arrayelementen, anderen Ausdrücken oder Funktionsaufrufen bestehen kann. Dies wird anhand des folgenden Beispiels veranschaulicht.

[!code-vb[VbVbalrStatements#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#74)]

Im vorherigen Beispiel wird der `y` in der Variablen `z`gehaltene Wert zu dem in `findResult`der Variablen gehaltenen Wert addiert, und dann wird der vom Aufruf zurückgegebene Wert an function hinzugefügt. Der Gesamtwert dieses Ausdrucks wird `x`dann in der Variablen gespeichert.

### <a name="data-types-in-assignment-statements"></a>Datentypen in Zuweisungsanweisungen

Neben numerischen Werten kann der Zuweisungsoperator auch Werte zuweisen, `String` wie das folgende Beispiel zeigt.

[!code-vb[VbVbalrStatements#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#75)]

Sie können `Boolean` auch Werte zuweisen, indem Sie entweder ein `Boolean` Literal oder einen `Boolean` Ausdruck verwenden, wie das folgende Beispiel veranschaulicht.

[!code-vb[VbVbalrStatements#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#76)]

Ebenso können Sie Programmierelementen des `Char`, `Date`oder `Object` Datentyps entsprechende Werte zuweisen. Sie können einem Element, das als Der Klasse deklariert wurde, aus der diese Instanz erstellt wird, auch eine Objektinstanz zuweisen.

### <a name="compound-assignment-statements"></a>Zusammengesetzte Zuweisungsanweisungen

*Zusammengesetzte Zuweisungsanweisungen* führen zunächst einen Vorgang für einen Ausdruck aus, bevor sie einem Programmierelement zugewiesen werden. Das folgende Beispiel veranschaulicht einen `+=`dieser Operatoren, , der den Wert der Variablen auf der linken Seite des Operators um den Wert des Ausdrucks auf der rechten Seite erhöht.

[!code-vb[VbVbalrStatements#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#77)]

Im vorherigen Beispiel wird 1 `n`zum Wert von hinzugefügt `n`und dieser neue Wert dann in gespeichert. Es ist eine Abkürzung, die der folgenden Aussage entspricht:

[!code-vb[VbVbalrStatements#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#78)]

Eine Vielzahl von zusammengesetzten Zuordnungsvorgängen kann mit Operatoren dieses Typs ausgeführt werden. Eine Liste dieser Operatoren und weitere Informationen zu diesen Operatoren finden Sie unter [Zuweisungsoperatoren](../../../visual-basic/language-reference/operators/assignment-operators.md).

Der Verkettungszuweisungsoperator (`&=`) ist nützlich, um eine Zeichenfolge am Ende bereits vorhandener Zeichenfolgen hinzuzufügen, wie das folgende Beispiel veranschaulicht.

[!code-vb[VbVbalrStatements#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#79)]

### <a name="type-conversions-in-assignment-statements"></a>Typkonvertierungen in Zuordnungsanweisungen

Der Wert, den Sie einer Variablen, Eigenschaft oder einem Arrayelement zuweisen, muss einen Datentyp aufweisen, der diesem Zielelement entspricht. Im Allgemeinen sollten Sie versuchen, einen Wert desselben Datentyps wie den wert des Zielelements zu generieren. Einige Typen können jedoch während der Zuweisung in andere Typen konvertiert werden.

Informationen zum Konvertieren zwischen Datentypen finden Sie unter [Typkonvertierungen in Visual Basic](./data-types/type-conversions.md). Kurz gesagt, Visual Basic konvertiert automatisch einen Wert eines bestimmten Typs in einen anderen Typ, auf den es erweitert wird. Eine *Erweiterungskonvertierung* ist eine Konvertierung, die immer zur Laufzeit erfolgreich ist und keine Daten verliert. Visual Basic konvertiert z. `Integer` B. einen Wert in `Double` ggf. , da `Integer` er auf `Double`erweitert wird. Weitere Informationen finden Sie unter [Widening and Narrowing Conversions](./data-types/widening-and-narrowing-conversions.md).

*Einschränkende Konvertierungen* (die sich nicht erweitern) bergen das Risiko eines Ausfalls zur Laufzeit oder eines Datenverlusts. Sie können eine Eingrenzungskonvertierung explizit mithilfe einer Typkonvertierungsfunktion durchführen oder den Compiler `Option Strict Off`anweisen, alle Konvertierungen implizit durchzuführen, indem Sie festlegen. Weitere Informationen finden Sie unter [Implizite und explizite Konvertierungen](./data-types/implicit-and-explicit-conversions.md).

## <a name="putting-multiple-statements-on-one-line"></a>Setzen mehrerer Anweisungen in einer Zeile

Sie können mehrere Anweisungen in einer einzelnen`:`Zeile haben, die durch das Doppelpunkt ( ) getrennt sind. Dies wird anhand des folgenden Beispiels veranschaulicht.

[!code-vb[VbVbalrStatements#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#70)]

Obwohl diese Form der Syntax gelegentlich praktisch ist, ist es schwierig, den Code zu lesen und zu verwalten. Daher wird empfohlen, eine Anweisung für eine Zeile beizubehalten.

## <a name="continuing-a-statement-over-multiple-lines"></a>Fortsetzen einer Anweisung über mehrere Zeilen

Eine Anweisung passt normalerweise in eine Zeile, aber wenn sie zu lang ist, können Sie sie in der nächsten Zeile mit`_`einer Zeilenfortsetzungssequenz fortsetzen, die aus einem Leerzeichen gefolgt von einem Unterstrichzeichen ( ) gefolgt von einer Wagenrückgabe besteht. Im folgenden Beispiel `MsgBox` wird die ausführbare Anweisung über zwei Zeilen fortgesetzt.

[!code-vb[VbVbalrStatements#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#71)]

### <a name="implicit-line-continuation"></a>Implizite Linienfortsetzung

In vielen Fällen können Sie eine Anweisung in der nächsten aufeinanderfolgenden Zeile fortsetzen, ohne das Unterstrichzeichen (`_`) zu verwenden. Die folgenden Syntaxelemente setzen die Anweisung in der nächsten Codezeile implizit fort.

- Nach einem Komma (`,`). Beispiel:

   [!code-vb[VbVbalrLineContinuation#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#1)]

- Nach einer offenen Klammer`(`( ) oder vor einer`)`schließenden Klammer ( ). Beispiel:

   [!code-vb[VbVbalrLineContinuation#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#2)]

- Nach einer offenen geschweiften Klammer (`{`)`}`oder vor einer schließenden geschweiften Klammer ( ). Beispiel:

    [!code-vb[VbVbalrLineContinuation#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#3)]

    Weitere Informationen finden Sie unter [Objektinitialisierer: Benannte und anonyme Typen](./objects-and-classes/object-initializers-named-and-anonymous-types.md) oder [Auflistungsinitialisierer](./collection-initializers/index.md).

- Nach einem geöffneten`<%=`eingebetteten Ausdruck ( )`%>`oder vor dem Schließen eines eingebetteten Ausdrucks ( ) innerhalb eines XML-Literals. Beispiel:

   [!code-vb[VbVbalrLineContinuation#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#4)]

   Weitere Informationen finden Sie unter [Eingebettete Ausdrücke in XML](./xml/embedded-expressions-in-xml.md).

- Nach dem Verkettungsoperator (`&`). Beispiel:

   [!code-vb[VbVbcnConventions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/vb/Class1.vb#9)]

   Weitere Informationen finden Sie unter [Operatoren, die nach Funktionalität aufgelistet sind.](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)

- Nach der`=`Zuweisung `&=`operatoren `-=` `*=`( `/=` `\=`, `^=` `<<=`, `>>=` `:=` `+=`, , , , , , , , , . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . Beispiel:

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   Weitere Informationen finden Sie unter [Operatoren, die nach Funktionalität aufgelistet sind.](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)

- Nach binären`+` `-`Operatoren ( `<>` `<`, `>` `<=`, `>=` `/` `^`, `>>` `<<` `And` `*` `Mod`, `AndAlso`, `Or` `OrElse`, `Like` `Xor`, , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , Beispiel:

   [!code-vb[VbVbalrLineContinuation#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#7)]

   Weitere Informationen finden Sie unter [Operatoren, die nach Funktionalität aufgelistet sind.](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)

- Nach `Is` dem `IsNot` und Operatoren. Beispiel:

   [!code-vb[VbVbalrLineContinuation#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#8)]

   Weitere Informationen finden Sie unter [Operatoren, die nach Funktionalität aufgelistet sind.](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)

- Nach einem Memberqualifiziererzeichen (`.`) und vor dem Membernamen. Beispiel:

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   Sie müssen jedoch ein Zeilenfortsetzungszeichen (`_`) nach einem Memberqualifiziererzeichen einschließen, wenn Sie die `With` Anweisung verwenden oder Werte in der Initialisierungsliste für einen Typ angeben. Erwägen Sie, die Zeile nach dem `=`Zuweisungsoperator `With` (z. B. ) zu brechen, wenn Sie Anweisungen oder Objektinitialisierungslisten verwenden. Beispiel:

   [!code-vb[VbVbalrLineContinuation#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#14)]

   Weitere Informationen finden Sie [unter Mit... Beenden mit Anweisungs-](../../../visual-basic/language-reference/statements/with-end-with-statement.md) oder [Objektinitialisierern: Benannte und anonyme Typen](./objects-and-classes/object-initializers-named-and-anonymous-types.md).

- Nach einem XML-Achseneigenschaftsqualifizierer (`.` oder `.@` oder `...`). Sie müssen jedoch ein Zeilenfortsetzungszeichen (`_`) einschließen, wenn `With` Sie einen Memberqualifizierer angeben, wenn Sie das Schlüsselwort verwenden. Beispiel:

   [!code-vb[VbVbalrLineContinuation#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#9)]

   Weitere Informationen finden Sie unter [XML-Achseneigenschaften](../../../visual-basic/language-reference/xml-axis/index.md).

- Nach einem weniger als Zeichen (<) oder vor`>`einem größer als Zeichen ( ), wenn Sie ein Attribut angeben. Auch nach einem größer`>`als Zeichen ( ), wenn Sie ein Attribut angeben. Sie müssen jedoch ein Zeilenfortsetzungszeichen (`_`) einschließen, wenn Sie Attribute auf Baugruppen- oder Modulebene angeben. Beispiel:

   [!code-vb[VbVbalrLineContinuation#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#10)]

   Weitere Informationen finden Sie unter [Attributübersicht](../../../visual-basic/programming-guide/concepts/attributes/index.md).

- Vor und nach`Aggregate`Abfrageoperatoren ( `Join` `Let`, `Order By` `Select` `Skip` `Skip While` `Take` `Take While` `Distinct` `From`, , `Group By`, `Where` `In` `Into` `On` `Ascending` `Descending` `Group Join`, , , , , , , , , , , , , , , , , , , , und . Sie können keine Linie zwischen den Schlüsselwörtern von Abfrageoperatoren`Order By` `Group Join`unterbrechen, die aus mehreren Schlüsselwörtern ( , , `Take While`, und `Skip While`) bestehen. Beispiel:

   [!code-vb[VbVbalrLineContinuation#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#11)]

   Weitere Informationen finden Sie unter [Abfragen](../../../visual-basic/language-reference/queries/index.md).

- Nach `In` dem Schlüsselwort in einer `For Each` Anweisung. Beispiel:

   [!code-vb[VbVbalrLineContinuation#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#12)]

   Weitere Informationen finden Sie unter [Für jeden... Nächste Erklärung](../../../visual-basic/language-reference/statements/for-each-next-statement.md).

- Nach `From` dem Schlüsselwort in einem Auflistungsinitialisierer. Beispiel:

   [!code-vb[VbVbalrLineContinuation#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#13)]

   Weitere Informationen finden Sie unter [Auflistungsinitialisierer](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).

## <a name="adding-comments"></a>Hinzufügen von Kommentaren

Quellcode ist nicht immer selbsterklärend, auch für den Programmierer, der ihn geschrieben hat. Um ihren Code zu dokumentieren, verwenden die meisten Programmierer daher liberale Kommentare. Kommentare im Code können jedem, der später liest oder damit arbeitet, eine Prozedur oder eine bestimmte Anweisung erklären. Visual Basic ignoriert Kommentare während der Kompilierung und wirkt sich nicht auf den kompilierten Code aus.

Kommentarzeilen beginnen mit einem Apostroph (`'`) oder `REM` gefolgt von einem Leerzeichen. Sie können an einer beliebigen Stelle im Code hinzugefügt werden, außer innerhalb einer Zeichenfolge. Um einen Kommentar an eine Anweisung anzufügen, `REM` fügen Sie einen Apostroph oder nach der Anweisung ein, gefolgt vom Kommentar. Kommentare können auch auf ihrer eigenen separaten Zeile gehen. Das folgende Beispiel veranschaulicht diese Möglichkeiten.

[!code-vb[VbVbalrStatements#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#72)]

## <a name="checking-compilation-errors"></a>Überprüfen von Kompilierungsfehlern

Wenn nach dem Eingeben einer Codezeile die Zeile mit einer welligen blauen Unterstreichung angezeigt wird (möglicherweise wird auch eine Fehlermeldung angezeigt), liegt ein Syntaxfehler in der Anweisung vor. Sie müssen herausfinden, was mit der Anweisung falsch ist (indem Sie in der Aufgabenliste suchen oder mit dem Mauszeiger über den Fehler zeigen und die Fehlermeldung lesen) und sie korrigieren. Solange Sie nicht alle Syntaxfehler im Code behoben haben, kann das Programm nicht ordnungsgemäß kompiliert werden.

## <a name="related-sections"></a>Verwandte Abschnitte

|Begriff|Definition|
|---|---|
|[Zuweisungsoperatoren](../../../visual-basic/language-reference/operators/assignment-operators.md)|Enthält Links zu Sprachreferenzseiten, `=`die `*=`Zuweisungsoperatoren wie , und `&=`.|
|[Operatoren und Ausdrücke](./operators-and-expressions/index.md)|Zeigt, wie Elemente mit Operatoren kombiniert werden, um neue Werte zu erzielen.|
|[Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)|Zeigt, wie eine einzelne Anweisung in mehrere Zeilen aufgeteilt wird und wie mehrere Anweisungen in derselben Zeile platziert werden.|
|[Gewusst wie: Bezeichnen von Anweisungen](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)|Zeigt, wie eine Codezeile beschriftet wird.|
