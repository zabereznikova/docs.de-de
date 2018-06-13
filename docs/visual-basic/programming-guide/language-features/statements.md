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
ms.openlocfilehash: 9953fb949c58c074169596dcf48b6df5e7b8f0af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655720"
---
# <a name="statements-in-visual-basic"></a>Anweisungen in Visual Basic
Eine Anweisung in Visual Basic ist eine vollständige Anweisung. Sie können Schlüsselwörter, Operatoren, Variablen, Konstanten und Ausdrücke enthalten. Jede Anweisung gehört zu einer der folgenden Kategorien:  
  
-   **Deklarationsanweisungen**, die eine Variable, Konstante oder Prozedur benennen und können auch einen Datentyp angeben.  
  
-   **Ausführbare Anweisungen**, Initiieren von Aktionen. Diese Anweisungen können eine Methode oder Funktion aufrufen, und diese Schleife oder über Codeblöcke verzweigen können. Ausführbare Anweisungen enthalten **Zuweisungsanweisungen**, die einen Wert oder Ausdruck zuweisen, um eine Variable oder Konstante.  
  
 Dieses Thema beschreibt die einzelnen Kategorien. Darüber hinaus wird in diesem Thema wie mehrere Anweisungen in einer einzelnen Zeile zu kombinieren und eine Anweisung über mehrere Zeilen zu fortfahren.  
  
## <a name="declaration-statements"></a>Deklarationsanweisungen  
 Sie verwenden die deklarationsanweisungen benennen und Prozeduren, Variablen, Eigenschaften, Arrays und Konstanten definiert. Wenn Sie ein Programmierelement deklarieren, können Sie auch seinen Datentyp, die Zugriffsebene und den Bereich definieren. Weitere Informationen finden Sie unter [Elementmerkmale deklariert](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).  
  
 Das folgende Beispiel enthält drei Deklarationen.  
  
 [!code-vb[VbVbalrStatements#80](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_1.vb)]  
  
 Die erste Deklaration ist die `Sub` Anweisung. Zusammen mit der entsprechenden `End Sub` -Anweisung deklariert eine Prozedur namens `applyFormat`. Es gibt auch an, die `applyFormat` ist `Public`, was bedeutet, dass jeglicher Code, der darauf verweisen kann, die sie aufrufen kann.  
  
 Die zweite Deklaration ist die `Const` -Anweisung, die die Konstante deklariert `limit`unter Angabe der `Integer` -Datentyp und den Wert 33.  
  
 Die dritte Deklaration ist die `Dim` -Anweisung, die die Variable deklariert `thisWidget`. Der Datentyp ist ein bestimmtes Objekt, d. h. ein Objekt erstellt, aus der `Widget` Klasse. Sie können eine Variable eines beliebigen elementaren Datentyp oder einen beliebigen Objekttyp, der in der Anwendung verfügbar gemacht wird, die Sie verwenden, deklarieren.  
  
### <a name="initial-values"></a>Anfangswerte  
 Wenn der Code mit einer deklarationsanweisung ausgeführt wird, reserviert Visual Basic den erforderlichen Speicher für das deklarierte Element. Wenn das Element einen Wert enthält, von Visual Basic auf den Standardwert für seinen Datentyp initialisiert. Weitere Informationen finden Sie unter "Verhalten" in [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
 Sie können eine Variable als Teil der Deklaration einen Anfangswert zuweisen, wie im folgenden Beispiel veranschaulicht.  
  
 [!code-vb[VbVbalrStatements#81](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_2.vb)]  
  
 Wenn eine Variable ein Objekt ist, können Sie explizit erstellen eine Instanz der Klasse beim Deklarieren mithilfe der [New-Operator](../../../visual-basic/language-reference/operators/new-operator.md) -Schlüsselwort, wie im folgenden Beispiel veranschaulicht.  
  
 [!code-vb[VbVbalrStatements#82](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_3.vb)]  
  
 Beachten Sie, dass der Anfangswert in einer deklarationsanweisung Ihnen angegebenen keiner Variablen zugewiesen ist, bis die Ausführung seiner deklarationsanweisung erreicht. Bis zu diesem Zeitpunkt enthält die Variable den Standardwert für seinen Datentyp.  
  
## <a name="executable-statements"></a>Ausführbare Anweisungen  
 Eine ausführbare Anweisung führt eine Aktion. Sie können Aufrufen einer Prozedur, einer Verzweigung zu einer anderen Stelle im Code durchlaufen mehrere-Anweisungen oder Auswerten eines Ausdrucks. Eine zuweisungsanweisung ist ein Sonderfall, der eine ausführbare Anweisung.  
  
 Im folgenden Beispiel wird ein `If...Then...Else` steuern die Struktur, um verschiedene Codeblöcke anhand des Werts einer Variablen führen. Jeder Codeblock eine `For...Next` Schleife ausgeführt wird, eine angegebene Anzahl von Malen.  
  
 [!code-vb[VbVbalrStatements#83](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_4.vb)]  
  
 Die `If` Anweisung im vorherigen Beispiel überprüft den Wert des Parameters `clockwise`. Wenn der Wert `True`, ruft er die `spinClockwise` Methode `aWidget`. Wenn der Wert `False`, ruft er die `spinCounterClockwise` Methode `aWidget`. Die `If...Then...Else` Kontrollstruktur endet mit `End If`.  
  
 Die `For...Next` -Schleife in jedem Block Ruft die entsprechende Methode eine Anzahl von Malen gleich dem Wert, der die `revolutions` Parameter.  
  
## <a name="assignment-statements"></a>Zuweisungsanweisungen  
 Zuweisungsanweisungen datensammlungssicherheit Zuweisungsvorgängen bestehen, wobei des Werts auf der rechten Seite des Zuweisungsoperators (`=`) und speichern es in das Element auf der linken Seite, wie im folgenden Beispiel gezeigt.  
  
 [!code-vb[VbVbalrStatements#73](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_5.vb)]  
  
 Im vorherigen Beispiel speichert die zuweisungsanweisung den literalen Wert 42 in der Variablen `v`.  
  
### <a name="eligible-programming-elements"></a>Geeignete Programmierelemente  
 Das Programmierelement auf der linken Seite des Zuweisungsoperators muss annehmen und einen Wert zu speichern. Es muss daher eine Variable oder eine Eigenschaft, die nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md), oder es muss ein Arrayelement. Im Rahmen einer zuweisungsanweisung derartiges Element bezeichnet ein *Lvalue*, für "Linker Wert."  
  
 Der Wert auf der rechten Seite des Zuweisungsoperators wird durch einen Ausdruck generiert, die eine beliebige Kombination von Literalen, Konstanten, Variablen, Eigenschaften, Elemente des Arrays, andere Ausdrücke oder Funktionsaufrufe umfassen kann. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbalrStatements#74](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_6.vb)]  
  
 Das obige Beispiel fügt den Wert, der in der Variablen `y` auf den Wert in der Variablen `z`, und fügt dann durch Aufruf der Funktion zurückgegebenen Wert `findResult`. Der Gesamtwert dieses Ausdrucks wird dann in der Variablen gespeichert `x`.  
  
### <a name="data-types-in-assignment-statements"></a>Datentypen in Zuweisungsanweisungen  
 Zusätzlich zu numerischen Werten der Zuweisungsoperator kann auch zugewiesen `String` Werte, wie im folgenden Beispiel veranschaulicht.  
  
 [!code-vb[VbVbalrStatements#75](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_7.vb)]  
  
 Sie können auch zuweisen `Boolean` Werte entweder eine `Boolean` literal oder ein `Boolean` Ausdruck, wie im folgenden Beispiel wird veranschaulicht.  
  
 [!code-vb[VbVbalrStatements#76](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_8.vb)]  
  
 Auf ähnliche Weise Programmierelemente der entsprechenden Werte zuweisen werden kann die `Char`, `Date`, oder `Object` -Datentyp. Sie können auch eine Objektinstanz zuweisen, auf ein Element deklariert, um die Klasse aus der dieser Instanz erstellt wird.  
  
### <a name="compound-assignment-statements"></a>Zusammengesetzte Zuweisungsanweisungen  
 *Zuweisung verbundanweisungen* zuerst führen eine Operation für einen Ausdruck ein, bevor Sie es auf ein Programmierelement zuweisen. Das folgende Beispiel zeigt einen der folgenden Operatoren `+=`, der inkrementiert des Wert der Variablen auf der linken Seite des Operators durch den Wert des Ausdrucks auf der rechten Seite.  
  
 [!code-vb[VbVbalrStatements#77](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_9.vb)]  
  
 Das obige Beispiel fügt 1 auf den Wert der `n`, und speichert diesen neuen Wert im `n`. Es ist eine Kurzschreibweise, entspricht der folgenden Anweisung:  
  
 [!code-vb[VbVbalrStatements#78](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_10.vb)]  
  
 Eine Vielzahl von Vorgängen verbundzuweisung kann mithilfe von Operatoren dieses Typs ausgeführt werden. Eine Liste dieser Operatoren und Weitere Informationen finden Sie unter [Zuweisungsoperatoren](../../../visual-basic/language-reference/operators/assignment-operators.md).  
  
 Die Verkettung-Zuweisungsoperator (`&=`) eignet sich zum Hinzufügen einer Zeichenfolge am Ende einer bereits vorhandenen Zeichenfolgen, wie im folgenden Beispiel veranschaulicht.  
  
 [!code-vb[VbVbalrStatements#79](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_11.vb)]  
  
### <a name="type-conversions-in-assignment-statements"></a>Konvertierungen in Zuweisungsanweisungen  
 Der Wert, den Sie auf eine Variable, eine Eigenschaft oder ein Arrayelement zuweisen muss mit einem Zielelement entsprechenden Datentyp sein. Im Allgemeinen sollten Sie einen Wert des gleichen Datentyps wie für das Zielelement zu generieren. Einige Typen können jedoch bei der Zuordnung in andere Typen konvertiert werden.  
  
 Informationen zum Konvertieren zwischen Datentypen finden Sie unter [Konvertierungen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md). Kurz gesagt, konvertiert Visual Basic automatisch einen Wert eines bestimmten Typs in einen anderen Typ, den erweitert werden kann. Ein *erweiternde Konvertierung* ist eine in, das immer zur Laufzeit erfolgreich ist und keine Daten zu verlieren. Beispielsweise konvertiert Visual Basic ein `Integer` Wert `Double` Wenn geeignet, da `Integer` erweitert wird, um `Double`. Weitere Informationen finden Sie unter [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
 *Einschränkende Konvertierungen* (diejenigen, die keine erweiternde sind) ein Risiko für Fehler bei der Ausführung oder Verlust von Daten ausführen. Sie können eine einschränkende Konvertierung explizit ausführen, mit der eine Typkonvertierungsfunktion, oder Sie können den Compiler an, führen alle Konvertierungen implizit durch Festlegen von verweisen `Option Strict Off`. Weitere Informationen finden Sie unter [implizite und explizite Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).  
  
## <a name="putting-multiple-statements-on-one-line"></a>Mehrere Anweisungen platzieren in einer Zeile  
 Können Sie mehrere Anweisungen in einer einzelnen Zeile durch Doppelpunkt getrennte haben (`:`) Zeichen. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbalrStatements#70](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_12.vb)]  
  
 Obwohl gelegentlich es bequem erscheint, wird diese Form der Syntax der Code schwer zu lesen und zu verwalten. Daher wird empfohlen, dass Sie eine Anweisung zu einer Zeile beibehalten.  
  
## <a name="continuing-a-statement-over-multiple-lines"></a>Fortsetzen einer Anweisung über mehrere Zeilen  
 Eine Anweisung ist in der Regel in einer Zeile passt, aber bei er zu lang ist, können Sie es weiterhin, auf die nächste Zeile, die über eine Zeilenfortsetzungszeichenfolge, besteht ein Leerzeichen, gefolgt von einem Unterstrich (`_`) gefolgt von einem Wagenrücklauf. Im folgenden Beispiel die `MsgBox` ausführbare Anweisung über zwei Zeilen fortgesetzt wird.  
  
 [!code-vb[VbVbalrStatements#71](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_13.vb)]  
  
### <a name="implicit-line-continuation"></a>Implizite Zeilenfortsetzung  
 In vielen Fällen können Sie eine Anweisung in der nächsten Zeile fortsetzen, ohne Verwendung der Unterstrich (_). Die folgende Tabelle enthält die Syntaxelemente, die die Anweisung implizit auf die nächste Zeile des Codes zu fortfahren.  
  
|Syntax-element|Beispiel|  
|---|---|  
|Nach einem Komma (`,`).|[!code-vb[VbVbalrLineContinuation#1](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_14.vb)]|  
|Nach einer öffnenden Klammer (`(`) oder vor einer schließenden Klammer (`)`).|[!code-vb[VbVbalrLineContinuation#2](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_15.vb)]|  
|Nach einer öffnenden geschweiften Klammer (`{`) oder vor einer schließenden geschweiften Klammer (`}`).|[!code-vb[VbVbalrLineContinuation#3](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_16.vb)]<br /><br /> Weitere Informationen finden Sie unter [Objektinitialisierer: benannte und anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) oder [Auflistungsinitialisierer](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).|  
|Nachdem ein offenes eingebetteter Ausdruck (`<%=`) oder vor dem Schließen eines eingebetteten Ausdrucks (`%>`) in ein XML-Literal.|[!code-vb[VbVbalrLineContinuation#4](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_17.vb)]<br /><br /> Weitere Informationen finden Sie unter [eingebettete Ausdrücke in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).|  
|Nach dem Verkettungsoperator (`&`).|[!code-vb[VbVbcnConventions#9](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_18.vb)]<br /><br /> Weitere Informationen finden Sie unter [Operatoren sortiert nach Funktionalität](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).|  
|Nach Zuweisungsoperatoren (`=`, `&=`, `:=`, `+=`, `-=`, `*=`, `/=`, `\=`, `^=`, `<<=`, `>>=`).|[!code-vb[VbVbalrLineContinuation#5](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_19.vb)]<br /><br /> Weitere Informationen finden Sie unter [Operatoren sortiert nach Funktionalität](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).|  
|Nach binären Operatoren (`+`, `-`, `/`, `*`, `Mod`, `<>`, `<`, `>`, `<=`, `>=`, `^`, `>>`, `<<`, `And`, `AndAlso`, `Or`, `OrElse`, `Like`, `Xor`) innerhalb eines Ausdrucks.|[!code-vb[VbVbalrLineContinuation#7](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_20.vb)]<br /><br /> Weitere Informationen finden Sie unter [Operatoren sortiert nach Funktionalität](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).|  
|Nach der `Is` und `IsNot` Operatoren.|[!code-vb[VbVbalrLineContinuation#8](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_21.vb)]<br /><br /> Weitere Informationen finden Sie unter [Operatoren sortiert nach Funktionalität](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).|  
|Nach dem Element qualifiziererzeichens (`.`) und vor dem Membernamen. Sie müssen jedoch ein Zeilenfortsetzungszeichen (_) ein qualifiziererzeichens Element folgen, bei der Verwendung einschließen der `With` -Anweisung oder die Werte in der Initialisierungsliste für einen Typ angibt. Teilen Sie die Zeile nach der Zuweisungsoperator (z. B. `=`) beim Verwenden `With` Anweisungen oder Objektlisten-Initialisierung.|[!code-vb[VbVbalrLineContinuation#5](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_19.vb)]<br />[!code-vb[VbVbalrLineContinuation#14](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_22.vb)]<br /><br /> Weitere Informationen finden Sie unter [mit... With-Anweisung](../../../visual-basic/language-reference/statements/with-end-with-statement.md) oder [Objektinitialisierer: benannte und anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).|  
|Nach einem XML-Achseneigenschaften-Qualifizierer (`.` oder `.@` oder `...`). Sie müssen jedoch ein Zeilenfortsetzungszeichen (_) einschließen, wenn Sie einen Memberqualifizierer angeben, bei der Verwendung der `With` Schlüsselwort.|[!code-vb[VbVbalrLineContinuation#9](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_23.vb)]<br /><br /> Weitere Informationen finden Sie unter [XML-Achseneigenschaften](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md).|  
|Nach einem kleiner-als-Zeichen (<) oder vor einem größer-als-Zeichen (`>`) Wenn Sie ein Attribut angeben. Außerdem nach einem größer-als-Zeichen (`>`) Wenn Sie ein Attribut angeben. Allerdings müssen Sie Zeilenfortsetzungszeichen (_) einschließen, wenn Sie Attribute auf Assemblyebene oder Modulebene angeben.|[!code-vb[VbVbalrLineContinuation#10](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_24.vb)]<br /><br /> Weitere Informationen finden Sie unter [Übersicht über Attribute](../../../visual-basic/programming-guide/concepts/attributes/index.md).|  
|Vor und nach Abfrageoperatoren (`Aggregate`, `Distinct`, `From`, `Group By`, `Group Join`, `Join`, `Let`, `Order By`, `Select`, `Skip`, `Skip While`, `Take`, `Take While`, `Where`, `In`, `Into`, `On`, `Ascending`, und `Descending`). Sie können nicht unterbrochen, eine Linie zwischen den Schlüsselwörtern von Abfrageoperatoren, die mehrere Schlüsselwörter bestehen (`Order By`, `Group Join`, `Take While`, und `Skip While`).|[!code-vb[VbVbalrLineContinuation#11](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_25.vb)]<br /><br /> Weitere Informationen finden Sie unter [Abfragen](../../../visual-basic/language-reference/queries/queries.md).|  
|Nach der `In` -Schlüsselwort in einer `For Each` Anweisung.|[!code-vb[VbVbalrLineContinuation#12](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_26.vb)]<br /><br /> Weitere Informationen finden Sie unter [für jede... Nächste Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md).|  
|Nach der `From` -Schlüsselwort in einem Auflistungsinitialisierer.|[!code-vb[VbVbalrLineContinuation#13](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_27.vb)]<br /><br /> Weitere Informationen finden Sie unter [Auflistungsinitialisierer](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).|  
  
## <a name="adding-comments"></a>Hinzufügen von Kommentaren  
 Quellcode ist nicht immer selbsterklärend, auch für den Programmierer, der geschrieben wurde. Damit ihren Code zu dokumentieren, müssen daher die meisten Programmierer mit der großzügigen Verwendung von eingebetteten Kommentaren. Kommentare im Code erläutert eine Prozedur oder eine bestimmte Anweisung lesen oder zu einem späteren Zeitpunkt mit der Arbeit. Visual Basic Kommentare während der Kompilierung ignoriert und haben sie den kompilierten Code keine Auswirkungen.  
  
 Kommentarzeilen beginnen mit einem Apostroph (`'`) oder `REM` gefolgt von einem Leerzeichen. Sie können eine beliebige Stelle im Code, mit Ausnahme von innerhalb einer Zeichenfolge hinzugefügt werden. Um einen Kommentar an eine Anweisung angefügt werden soll, fügen Sie ein Apostroph oder `REM` nach der Anweisung, gefolgt von den Kommentar. Kommentare können auch auf eine separate Zeile wechseln. Das folgende Beispiel zeigt diese Möglichkeiten.  
  
 [!code-vb[VbVbalrStatements#72](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_28.vb)]  
  
## <a name="checking-compilation-errors"></a>Überprüfen von Kompilierungsfehlern  
 Wenn nach der Eingabe einer Codezeile ist die Zeile mit einer blauen Wellenlinie (eine Fehlermeldung kann auch angezeigt werden), besteht ein Syntaxfehler in der Anweisung. Sie müssen herausfinden, was das Problem mit der Anweisung ist (durch Suchen in der Taskliste aus, oder mit dem Mauszeiger auf den Fehler mit dem Mauszeiger auf ein, und lesen die Fehlermeldung) und zu korrigieren. Bis Sie alle Syntaxfehler im Code behoben haben, wird das Programm nicht ordnungsgemäß zu kompilieren.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
  
|Begriff|Definition|  
|---|---|  
|[Zuweisungsoperatoren](../../../visual-basic/language-reference/operators/assignment-operators.md)|Enthält Links zu Sprachreferenzseiten Zuweisungsoperatoren wie z. B. abdecken `=`, `*=`, und `&=`.|  
|[Operatoren und Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)|Zeigt, wie Elemente mit Operatoren, um neue Werte zu kombinieren.|  
|[Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)|Erfahren, wie eine einzelne Anweisung in mehrere Zeilen aufgeteilt und mehrere Anweisungen in der gleichen Zeile platziert.|  
|[Gewusst wie: Bezeichnen von Anweisungen](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)|Zeigt, wie eine Codezeile zu bezeichnen.|
