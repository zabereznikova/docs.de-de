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
ms.openlocfilehash: 09fe53f4bc2b6d025b762c6595c5337263456bae
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401978"
---
# <a name="statements-in-visual-basic"></a>Anweisungen in Visual Basic

Eine Anweisung in Visual Basic ist eine umfassende Anweisung. Sie kann Schlüsselwörter, Operatoren, Variablen, Konstanten und Ausdrücke enthalten. Jede-Anweisung gehört zu einer der folgenden Kategorien:

- **Deklarations Anweisungen**, die eine Variable, eine Konstante oder eine Prozedur benennen und auch einen Datentyp angeben können.

- **Ausführbare Anweisungen**, die Aktionen initiieren. Diese Anweisungen können eine Methode oder eine Funktion aufzurufen, und Sie können Code Blöcke Schleifen oder verzweigen. Ausführbare Anweisungen enthalten **Zuweisungs Anweisungen**, mit denen einer Variablen oder einer Konstante ein Wert oder Ausdruck zugewiesen wird.

In diesem Thema werden die einzelnen Kategorien beschrieben. Außerdem wird in diesem Thema beschrieben, wie Sie mehrere-Anweisungen in einer einzelnen Zeile kombinieren und wie Sie eine Anweisung über mehrere Zeilen hinweg fortsetzen.

## <a name="declaration-statements"></a>Deklarationsanweisungen

Deklarations Anweisungen werden verwendet, um Prozeduren, Variablen, Eigenschaften, Arrays und Konstanten zu benennen und zu definieren. Wenn Sie ein Programmier Element deklarieren, können Sie auch den Datentyp, die Zugriffsebene und den Gültigkeitsbereich definieren. Weitere Informationen finden Sie unter [deklarierte Element Eigenschaften](./declared-elements/declared-element-characteristics.md).

Das folgende Beispiel enthält drei Deklarationen.

[!code-vb[VbVbalrStatements#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#80)]

Die erste Deklaration ist die- `Sub` Anweisung. In Verbindung mit der entsprechenden- `End Sub` Anweisung wird eine Prozedur mit dem Namen deklariert `applyFormat` . Außerdem wird angegeben, `applyFormat` dass `Public` den Wert hat. Dies bedeutet, dass jeder Code, der darauf verweisen kann, ihn abrufen kann.

Die zweite Deklaration ist die `Const` -Anweisung, die die Konstante deklariert `limit` `Integer` und den Datentyp und den Wert 33 angibt.

Die dritte Deklaration ist die- `Dim` Anweisung, die die Variable deklariert `thisWidget` . Der-Datentyp ist ein bestimmtes Objekt, nämlich ein Objekt, das aus der-Klasse erstellt wird `Widget` . Sie können eine Variable als einen beliebigen elementaren Datentyp oder einen beliebigen Objekttyp deklarieren, der in der von Ihnen verwendeten Anwendung verfügbar gemacht wird.

### <a name="initial-values"></a>Anfangswerte

Wenn der Code, der eine Deklarations Anweisung enthält, ausgeführt wird, reserviert Visual Basic den erforderlichen Arbeitsspeicher für das deklarierte Element. Wenn das Element einen Wert enthält, Visual Basic es mit dem Standardwert für seinen Datentyp initialisiert. Weitere Informationen finden Sie unter "Verhalten" in der [Dim-Anweisung](../../language-reference/statements/dim-statement.md).

Sie können einen Anfangswert einer Variablen als Teil der Deklaration zuweisen, wie im folgenden Beispiel veranschaulicht.

[!code-vb[VbVbalrStatements#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#81)]

Wenn eine Variable eine Objekt Variable ist, können Sie explizit eine Instanz Ihrer Klasse erstellen, wenn Sie Sie mit dem New- [Operator](../../language-reference/operators/new-operator.md) Schlüsselwort deklarieren, wie im folgenden Beispiel veranschaulicht.

[!code-vb[VbVbalrStatements#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#82)]

Beachten Sie, dass der anfängliche Wert, den Sie in einer Deklarations Anweisung angeben, keiner Variablen zugewiesen wird, bis die Ausführung die Deklarations Anweisung erreicht. Bis zu diesem Zeitpunkt enthält die Variable den Standardwert für ihren Datentyp.

## <a name="executable-statements"></a>Ausführbare Anweisungen

Eine ausführbare Anweisung führt eine Aktion aus. Sie kann eine Prozedur aufzurufen, an eine andere Stelle im Code verzweigen, mehrere Anweisungen durchlaufen oder einen Ausdruck auswerten. Eine Zuweisungsanweisung ist ein Sonderfall einer ausführbaren Anweisung.

Im folgenden Beispiel wird eine- `If...Then...Else` Steuerelement Struktur verwendet, um verschiedene Code Blöcke basierend auf dem Wert einer Variablen auszuführen. Innerhalb jedes Code Blocks wird eine- `For...Next` Schleife so oft wie angegeben ausgeführt.

[!code-vb[VbVbalrStatements#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#83)]

Die- `If` Anweisung im vorherigen Beispiel überprüft den Wert des-Parameters `clockwise` . Wenn der Wert ist `True` , wird die- `spinClockwise` Methode von aufgerufen `aWidget` . Wenn der Wert ist `False` , wird die- `spinCounterClockwise` Methode von aufgerufen `aWidget` . Die- `If...Then...Else` Steuerelement Struktur endet mit `End If` .

Die- `For...Next` Schleife in jedem Block Ruft die entsprechende-Methode so oft auf, wie der Wert des- `revolutions` Parameters.

## <a name="assignment-statements"></a>Zuweisungs Anweisungen

Zuweisungs Anweisungen führen Zuweisungs Vorgänge aus, die dazu führen, dass der Wert auf der rechten Seite des Zuweisungs Operators ( `=` ) übernommen und im-Element auf der linken Seite gespeichert wird, wie im folgenden Beispiel gezeigt.

[!code-vb[VbVbalrStatements#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#73)]

Im vorherigen Beispiel speichert die Zuweisungsanweisung den Literalwert 42 in der Variablen `v` .

### <a name="eligible-programming-elements"></a>Berechtigte Programmier Elemente

Das-Programmier Element auf der linken Seite des Zuweisungs Operators muss in der Lage sein, einen Wert zu akzeptieren und zu speichern. Dies bedeutet, dass es sich um eine Variable oder eine Eigenschaft [handelt, die nicht Schreib](../../language-reference/modifiers/readonly.md)geschützt ist, oder um ein Array Element sein muss. Im Kontext einer Zuweisungsanweisung wird ein solches Element manchmal als " *Lvalue*" für "Left Value" bezeichnet.

Der Wert auf der rechten Seite des Zuweisungs Operators wird von einem Ausdruck generiert, der aus einer beliebigen Kombination aus Literalen, Konstanten, Variablen, Eigenschaften, Array Elementen, anderen Ausdrücken oder Funktionsaufrufen bestehen kann. Dies wird anhand des folgenden Beispiels veranschaulicht.

[!code-vb[VbVbalrStatements#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#74)]

Im vorangehenden Beispiel wird der in Variable enthaltene Wert dem Wert hinzugefügt `y` , der in der Variablen gespeichert `z` ist `findResult` Der Gesamtwert dieses Ausdrucks wird dann in der Variablen gespeichert `x` .

### <a name="data-types-in-assignment-statements"></a>Datentypen in Zuweisungs Anweisungen

Zusätzlich zu numerischen Werten kann der Zuweisungs Operator auch Werte zuweisen `String` , wie im folgenden Beispiel veranschaulicht.

[!code-vb[VbVbalrStatements#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#75)]

Sie können auch `Boolean` Werte zuweisen, indem Sie entweder einen `Boolean` Literalwert oder einen `Boolean` Ausdruck verwenden, wie im folgenden Beispiel veranschaulicht.

[!code-vb[VbVbalrStatements#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#76)]

Entsprechend können Sie den Programmier Elementen des-,-oder- `Char` `Date` `Object` Datentyps geeignete Werte zuweisen. Sie können einem Element, von dem diese Instanz erstellt wurde, auch eine Objektinstanz zuweisen.

### <a name="compound-assignment-statements"></a>Verbund Zuweisungs Anweisungen

*Verbund Zuweisungs Anweisungen* führen zuerst einen Vorgang für einen Ausdruck aus, bevor er einem Programmier Element zugewiesen wird. Das folgende Beispiel veranschaulicht einen dieser Operatoren, `+=` , der den Wert der Variablen links vom Operator um den Wert des Ausdrucks auf der rechten Seite erhöht.

[!code-vb[VbVbalrStatements#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#77)]

Im vorangehenden Beispiel wird 1 zum Wert von addiert `n` , und dann wird der neue Wert in gespeichert `n` . Dies ist eine kurz Entsprechung der folgenden-Anweisung:

[!code-vb[VbVbalrStatements#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#78)]

Eine Vielzahl von zusammengesetzten Zuweisungs Vorgängen kann mithilfe von Operatoren dieses Typs ausgeführt werden. Eine Liste dieser Operatoren und weitere Informationen zu diesen Operatoren finden Sie unter [Zuweisungs Operatoren](../../language-reference/operators/assignment-operators.md).

Der Verkettungs Zuweisungs Operator ( `&=` ) eignet sich zum Hinzufügen einer Zeichenfolge am Ende bereits vorhandener Zeichen folgen, wie im folgenden Beispiel veranschaulicht.

[!code-vb[VbVbalrStatements#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#79)]

### <a name="type-conversions-in-assignment-statements"></a>Typkonvertierungen in Zuweisungs Anweisungen

Der Wert, den Sie einer Variablen, einer Eigenschaft oder einem Array Element zuweisen, muss einen Datentyp aufweisen, der für dieses Ziel Element geeignet ist. Im Allgemeinen sollten Sie versuchen, einen Wert desselben Datentyps wie das Ziel Element zu generieren. Einige Typen können jedoch während der Zuweisung in andere Typen konvertiert werden.

Informationen zum Konvertieren von Datentypen finden Sie unter [Typkonvertierungen in Visual Basic](./data-types/type-conversions.md). Kurz gesagt konvertiert Visual Basic automatisch einen Wert eines bestimmten Typs in einen anderen Typ, in den er erweitert wird. Eine *erweiternde Konvertierung* ist eine in, die zur Laufzeit immer erfolgreich ist und keine Daten verliert. Beispielsweise konvertiert Visual Basic einen- `Integer` Wert nach Bedarf in `Double` , da `Integer` zu erweitert wird `Double` . Weitere Informationen finden Sie unter [Widening and Narrowing Conversions](./data-types/widening-and-narrowing-conversions.md).

Einschränkende *Konvertierungen* (solche, die nicht erweitert werden) verursachen ein Risiko eines Fehlers zur Laufzeit oder eines Daten Verlusts. Sie können eine einschränkende Konvertierung explizit durchführen, indem Sie eine Typkonvertierungs Funktion verwenden, oder Sie können den Compiler anweisen, alle Konvertierungen implizit durch Festlegen von auszuführen `Option Strict Off` . Weitere Informationen finden Sie unter [implizite und explizite Konvertierungen](./data-types/implicit-and-explicit-conversions.md).

## <a name="putting-multiple-statements-on-one-line"></a>Einfügen mehrerer Anweisungen in einer Zeile

Sie können über mehrere-Anweisungen in einer einzelnen Zeile verfügen, die durch den Doppelpunkt () getrennt sind `:` . Dies wird anhand des folgenden Beispiels veranschaulicht.

[!code-vb[VbVbalrStatements#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#70)]

Obwohl dies gelegentlich praktisch ist, macht diese Art von Syntax Ihren Code schwer zu lesen und zu warten. Daher wird empfohlen, dass Sie eine Anweisung in einer Zeile aufbewahren.

## <a name="continuing-a-statement-over-multiple-lines"></a>Fortsetzen einer Anweisung über mehrere Zeilen

Eine-Anweisung passt in der Regel in eine Zeile, aber wenn Sie zu lang ist, können Sie Sie mit einer Zeilen Fortsetzungs Sequenz fortsetzen, die aus einem Leerzeichen gefolgt von einem Unterstrich ( `_` ) gefolgt von einem Wagen Rücklauf Zeichen besteht. Im folgenden Beispiel `MsgBox` wird die ausführbare Anweisung über zwei Zeilen hinweg fortgesetzt.

[!code-vb[VbVbalrStatements#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#71)]

### <a name="implicit-line-continuation"></a>Implizite Zeilen Fortsetzung

In vielen Fällen können Sie eine Anweisung in der nächsten aufeinander folgenden Zeile fortsetzen, ohne den Unterstrich () zu verwenden `_` . Die folgenden Syntax Elemente setzen implizit die-Anweisung in der nächsten Codezeile fort.

- Nach einem Komma ( `,` ). Beispiel:

   [!code-vb[VbVbalrLineContinuation#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#1)]

- Nach einer öffnenden Klammer ( `(` ) oder vor einer schließenden Klammer ( `)` ). Beispiel:

   [!code-vb[VbVbalrLineContinuation#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#2)]

- Nach einer öffnenden geschweiften Klammer ( `{` ) oder vor einer schließenden geschweiften Klammer ( `}` ). Beispiel:

    [!code-vb[VbVbalrLineContinuation#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#3)]

    Weitere Informationen finden Sie unter [Objektinitialisierer: benannte und anonyme Typen](./objects-and-classes/object-initializers-named-and-anonymous-types.md) oder sammlungsinitialisierer. [Collection Initializers](./collection-initializers/index.md)

- Nach einem geöffneten eingebetteten Ausdruck ( `<%=` ) oder vor dem Schließen eines eingebetteten Ausdrucks ( `%>` ) innerhalb eines XML-Literals. Beispiel:

   [!code-vb[VbVbalrLineContinuation#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#4)]

   Weitere Informationen finden Sie unter [eingebettete Ausdrücke in XML](./xml/embedded-expressions-in-xml.md).

- Nach dem Verkettungs Operator ( `&` ). Beispiel:

   [!code-vb[VbVbcnConventions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/vb/Class1.vb#9)]

   Weitere Informationen finden Sie unter [von der-Funktionalität aufgeführte Operatoren](../../language-reference/operators/operators-listed-by-functionality.md).

- Nach Zuweisungs Operatoren ( `=` , `&=` , `:=` , `+=` , `-=` , `*=` , `/=` , `\=` , `^=` , `<<=` , `>>=` ). Beispiel:

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   Weitere Informationen finden Sie unter [von der-Funktionalität aufgeführte Operatoren](../../language-reference/operators/operators-listed-by-functionality.md).

- Nach binären Operatoren ( `+` , `-` , `/` , `*` , `Mod` , `<>` , `<` , `>` , `<=` , `>=` , `^` , `>>` , `<<` , `And` , `AndAlso` , `Or` , `OrElse` , `Like` , `Xor` ) innerhalb eines Ausdrucks. Beispiel:

   [!code-vb[VbVbalrLineContinuation#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#7)]

   Weitere Informationen finden Sie unter [von der-Funktionalität aufgeführte Operatoren](../../language-reference/operators/operators-listed-by-functionality.md).

- Nach den `Is` `IsNot` Operatoren und. Beispiel:

   [!code-vb[VbVbalrLineContinuation#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#8)]

   Weitere Informationen finden Sie unter [von der-Funktionalität aufgeführte Operatoren](../../language-reference/operators/operators-listed-by-functionality.md).

- Nach einem Member-Qualifiziererzeichen ( `.` ) und vor dem Elementnamen. Beispiel:

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   Sie müssen jedoch ein Zeilen Fortsetzungs Zeichen ( `_` ) nach einem Member-Qualifiziererzeichen einschließen, wenn Sie die- `With` Anweisung verwenden oder Werte in der Initialisierungs Liste für einen Typ angeben. Unterbrechen Sie die Zeile nach dem Zuweisungs Operator (z. b `=` .), wenn Sie- `With` Anweisungen oder Objekt Initialisierungs Listen verwenden. Beispiel:

   [!code-vb[VbVbalrLineContinuation#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#14)]

   Weitere Informationen finden Sie unter [with... Ende mit Anweisungs](../../language-reference/statements/with-end-with-statement.md) [-oder Objektinitialisierern: benannte und anonyme Typen](./objects-and-classes/object-initializers-named-and-anonymous-types.md).

- Nach einem XML-Achsen Eigenschaften Qualifizierer ( `.` oder `.@` oder `...` ). Sie müssen jedoch ein Zeilen Fortsetzungs Zeichen () einschließen, `_` Wenn Sie einen Member-Qualifizierer angeben, wenn Sie das- `With` Schlüsselwort verwenden. Beispiel:

   [!code-vb[VbVbalrLineContinuation#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#9)]

   Weitere Informationen finden Sie unter [XML-Achsen Eigenschaften](../../language-reference/xml-axis/index.md).

- Nach einem kleiner-als-Zeichen (<) oder vor einem größer-als-Zeichen ( `>` ), wenn Sie ein Attribut angeben. Auch nach einem größer-als-Zeichen ( `>` ), wenn Sie ein Attribut angeben. Sie müssen jedoch ein Zeilen Fortsetzungs Zeichen () einschließen, `_` Wenn Sie Attribute auf Assemblyebene oder auf Modulebene angeben. Beispiel:

   [!code-vb[VbVbalrLineContinuation#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#10)]

   Weitere Informationen finden Sie unter [Übersicht über Attribute](../concepts/attributes/index.md).

- Vor und nach Abfrage Operatoren ( `Aggregate` , `Distinct` , `From` , `Group By` , `Group Join` , `Join` , `Let` , `Order By` , `Select` , `Skip` , `Skip While` , `Take` , `Take While` , `Where` , `In` , `Into` , `On` , `Ascending` und `Descending` ). Sie können eine Linie zwischen den Schlüsselwörtern von Abfrage Operatoren, die aus mehreren Schlüsselwörtern bestehen, nicht unterbrechen ( `Order By` , `Group Join` , `Take While` und `Skip While` ). Beispiel:

   [!code-vb[VbVbalrLineContinuation#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#11)]

   Weitere Informationen finden Sie unter [Abfragen](../../language-reference/queries/index.md).

- Nach dem- `In` Schlüsselwort in einer- `For Each` Anweisung. Beispiel:

   [!code-vb[VbVbalrLineContinuation#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#12)]

   Weitere Informationen finden Sie unter [for each... Next-Anweisung](../../language-reference/statements/for-each-next-statement.md).

- Nach dem- `From` Schlüsselwort in einem Auflistungsinitialisierer. Beispiel:

   [!code-vb[VbVbalrLineContinuation#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#13)]

   Weitere Informationen finden Sie unter [Auflistungsinitialisierer](collection-initializers/index.md).

## <a name="adding-comments"></a>Hinzufügen von Kommentaren

Der Quellcode ist nicht immer selbsterklärend, auch wenn der Programmierer ihn geschrieben hat. Um Ihren Code zu dokumentieren, machen die meisten Programmierer eine liberale Verwendung von eingebetteten Kommentaren. Kommentare in Code können eine Prozedur oder eine bestimmte Anweisung für alle Personen erläutern, die Sie später lesen oder bearbeiten. Visual Basic ignoriert Kommentare während der Kompilierung und wirkt sich nicht auf den kompilierten Code aus.

Kommentarzeilen beginnen mit einem Apostroph ( `'` ) oder `REM` gefolgt von einem Leerzeichen. Sie können an beliebiger Stelle im Code hinzugefügt werden, außer innerhalb einer Zeichenfolge. Um einen Kommentar an eine Anweisung anzufügen, fügen Sie einen Apostroph oder `REM` nach der Anweisung ein, gefolgt vom Kommentar. Kommentare können auch in einer eigenen separaten Zeile angezeigt werden. Im folgenden Beispiel werden diese Möglichkeiten veranschaulicht.

[!code-vb[VbVbalrStatements#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#72)]

## <a name="checking-compilation-errors"></a>Prüfen von Kompilierungs Fehlern

Wenn nach dem Eingeben einer Codezeile die Zeile mit einer wellenförmigen blauen Unterstreichung angezeigt wird (möglicherweise wird auch eine Fehlermeldung angezeigt), gibt es einen Syntax Fehler in der-Anweisung. Sie müssen herausfinden, was bei der Anweisung falsch ist (indem Sie die Aufgabenliste durchsuchen oder mit dem Mauszeiger auf den Fehler zeigen und die Fehlermeldung lesen) und korrigieren. Wenn Sie alle Syntax Fehler in Ihrem Code korrigiert haben, kann das Programm nicht ordnungsgemäß kompiliert werden.

## <a name="related-sections"></a>Verwandte Abschnitte

|Begriff|Definition|
|---|---|
|[Zuweisungsoperatoren](../../language-reference/operators/assignment-operators.md)|Stellt Links zu Sprachreferenz Seiten bereit, die Zuweisungs Operatoren wie `=` , `*=` und abdecken `&=` .|
|[Operatoren und Ausdrücke](./operators-and-expressions/index.md)|Zeigt, wie Elemente mit Operatoren kombiniert werden, um neue Werte zu erhalten.|
|[Vorgehensweise: Umbrechen und Zusammenfassen von Anweisungen in Code](../program-structure/how-to-break-and-combine-statements-in-code.md)|Zeigt, wie Sie eine einzelne Anweisung in mehrere Zeilen unterbrechen und wie Sie mehrere Anweisungen in derselben Zeile platzieren.|
|[Vorgehensweise: Label-Anweisungen](../program-structure/how-to-label-statements.md)|Zeigt, wie eine Codezeile beschriftet wird.|
