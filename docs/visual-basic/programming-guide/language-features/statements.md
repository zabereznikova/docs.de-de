---
title: Anweisungen in Visual Basic | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- variables [Visual Basic], declaring
- colons (:)
- constants, defining
- underlines
- constants, statements
- blue underline
- procedures, statements
- variables [Visual Basic], assigning
- line breaks, in code
- executable statements
- variables [Visual Basic], defining
- statements [Visual Basic], about statements
ms.assetid: fcfdee1a-82b7-4846-98f7-9ca3f5160089
caps.latest.revision: 30
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 001ea1cb5e651b95f808eefd47fd468f556550a1
ms.lasthandoff: 03/13/2017

---
# <a name="statements-in-visual-basic"></a>Anweisungen in Visual Basic
Eine Anweisung in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] ist eine vollständige Instruktion. Sie können Schlüsselwörter, Operatoren, Variablen, Konstanten und Ausdrücke enthalten. Jede Anweisung gehört zu einer der folgenden Kategorien:  
  
-   **Deklarationsanweisungen**, die eine Variable, eine Konstante oder eine Prozedur benennen und können auch einen Datentyp angeben.  
  
-   **Ausführbare Anweisungen**, die Aktionen initiieren. Diese Anweisungen können eine Methode oder Funktion aufrufen, und diese Schleife oder über Codeblöcke verzweigen können. Ausführbare Anweisungen enthalten **Zuweisungsanweisungen**, die einen Wert oder Ausdruck zuweisen, um eine Variable oder Konstante.  
  
 Dieses Thema beschreibt jede Kategorie an. Darüber hinaus wird in diesem Thema wie zum Kombinieren mehrerer Anweisungen in einer einzelnen Zeile und eine Anweisung über mehrere Zeilen fortfahren.  
  
## <a name="declaration-statements"></a>Deklarationsanweisungen  
 Sie verwenden die Methodendeklaration benennen und Definieren von Prozeduren, Variablen, Eigenschaften, Arrays und Konstanten. Wenn Sie ein Programmierelement deklarieren, können Sie auch seinen Datentyp, die Zugriffsebene und den Bereich definieren. Weitere Informationen finden Sie unter [Declared Element Characteristics](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).  
  
 Das folgende Beispiel enthält drei Deklarationen.  
  
 [!code-vb[VbVbalrStatements&#80;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_1.vb)]  
  
 Die erste Deklaration ist die `Sub` Anweisung. Zusammen mit der entsprechenden `End Sub` -Anweisung deklariert eine Prozedur namens `applyFormat`. Es gibt auch an, die `applyFormat` ist `Public`, was bedeutet, dass jeder Code, der darauf verweisen kann, die sie aufrufen kann.  
  
 Die zweite Deklaration ist die `Const` -Anweisung, die die Konstante deklariert `limit`unter Angabe der `Integer` -Datentyp und den Wert 33.  
  
 Die dritte Deklaration ist die `Dim` -Anweisung, die die Variable deklariert `thisWidget`. Der Datentyp ist ein bestimmtes Objekt, d. h. ein Objekt aus der `Widget` Klasse. Sie deklarieren eine Variable eines beliebigen elementaren Datentyp oder einen beliebigen Objekttyp, der in der Anwendung verfügbar gemacht wird, die Sie verwenden.  
  
### <a name="initial-values"></a>Anfangswerte  
 Wenn der Code mit einer deklarationsanweisung ausgeführt wird, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] reserviert den erforderlichen Speicher für das deklarierte Element. Wenn das Element einen Wert enthält [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] mit dem Standardwert für seinen Datentyp initialisiert. Weitere Informationen finden Sie unter "Verhalten" in [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
 Sie können eine Variable als Teil der Deklaration einen Anfangswert zuweisen, wie im folgenden Beispiel veranschaulicht.  
  
 [!code-vb[VbVbalrStatements&#81;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_2.vb)]  
  
 Wenn eine Variable ein Objekt ist, können Sie explizit erstellen eine Instanz ihrer Klasse beim Deklarieren mithilfe der [Operator New](../../../visual-basic/language-reference/operators/new-operator.md) -Schlüsselwort, wie im folgenden Beispiel veranschaulicht wird.  
  
 [!code-vb[VbVbalrStatements&#82;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_3.vb)]  
  
 Beachten Sie, dass der Anfangswert, den Sie in einer deklarationsanweisung angeben, keiner Variablen zugewiesen ist, bis die Ausführung die Anweisung für die Attributdeklaration erreicht. Bis zu diesem Zeitpunkt enthält die Variable den Standardwert für seinen Datentyp.  
  
## <a name="executable-statements"></a>Ausführbare Anweisungen  
 Eine ausführbare Anweisung führt eine Aktion. Sie können Aufrufen einer Prozedur, einer Verzweigung zu einer anderen Stelle im Code durchlaufen mehrere Anweisungen oder Auswerten eines Ausdrucks. Eine Zuweisung ist ein Sonderfall, der eine ausführbare Anweisung.  
  
 Im folgenden Beispiel wird ein `If...Then...Else` steuern die Struktur, um verschiedene Codeblöcke basierend auf dem Wert einer Variablen auszuführen. Jeder Codeblock ein `For...Next` Schleife ausgeführt wird, eine angegebene Anzahl von Malen.  
  
 [!code-vb[VbVbalrStatements&83;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_4.vb)]  
  
 Die `If` Anweisung im vorherigen Beispiel überprüft den Wert des Parameters `clockwise`. Wenn der Wert `True`, ruft es die `spinClockwise` Methode `aWidget`. Wenn der Wert `False`, ruft es die `spinCounterClockwise` Methode `aWidget`. Die `If...Then...Else` Kontrollstruktur endet mit `End If`.  
  
 Die `For...Next` -Schleife in jedem Block Ruft die entsprechende Methode eine Anzahl von Malen gleich dem Wert, der die `revolutions` Parameter.  
  
## <a name="assignment-statements"></a>Zuweisungsanweisungen  
 Zuweisungsanweisungen ausführen Zuweisungsvorgängen bestehen, wobei des Werts auf der rechten Seite des Zuweisungsoperators (`=`) und speichern es in das Element auf der linken Seite, wie im folgenden Beispiel.  
  
 [!code-vb[VbVbalrStatements&#73;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_5.vb)]  
  
 Im vorangehenden Beispiel speichert die Zuweisung den literalen Wert 42 in der Variablen `v`.  
  
### <a name="eligible-programming-elements"></a>Geeignete Programmierelemente  
 Das Programmierelement auf der linken Seite des Zuweisungsoperators muss annehmen und einen Wert zu speichern. Es muss daher eine Variable oder eine Eigenschaft, die nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md), oder es muss ein Arrayelement sein. Dieses Element wird im Kontext einer zuweisungsanweisung, manchmal bezeichnet ein *Lvalue*, für "Linker Wert."  
  
 Der Wert auf der rechten Seite des Zuweisungsoperators wird durch einen Ausdruck generiert, die eine beliebige Kombination von Literalen, Konstanten, Variablen, Eigenschaften, Arrayelementen, andere Ausdrücke oder Funktionsaufrufe enthalten kann. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbalrStatements&#74;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_6.vb)]  
  
 Im vorherigen Beispiel fügt den Wert in der Variablen `y` auf den Wert in der Variablen `z`, und fügt dann den Aufruf der Funktion zurückgegebenen Wert `findResult`. Der Gesamtwert dieses Ausdrucks wird dann in der Variablen gespeichert `x`.  
  
### <a name="data-types-in-assignment-statements"></a>Datentypen in Zuweisungsanweisungen  
 Zusätzlich zu numerischen Werten der Zuweisungsoperator kann auch zugewiesen `String` Werte, wie im folgenden Beispiel veranschaulicht.  
  
 [!code-vb[VbVbalrStatements&#75;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_7.vb)]  
  
 Kann auch zugewiesen `Boolean` Werte entweder eine `Boolean` literal oder ein `Boolean` Ausdruck, wie im folgenden Beispiel wird veranschaulicht.  
  
 [!code-vb[VbVbalrStatements&#76;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_8.vb)]  
  
 Auf ähnliche Weise können Werte zugewiesen werden entsprechende auf Programmierelemente, der die `Char`, `Date`, oder `Object` -Datentyp. Sie können auch eine Objektinstanz zuweisen, auf ein Element deklariert, der Klasse, von dem diese Instanz erstellt wird.  
  
### <a name="compound-assignment-statements"></a>Zusammengesetzte Zuweisungsanweisungen  
 *Zusammengesetzte zuweisungsanweisungen* führen Sie zuerst eine Operation auf einem Ausdruck, bevor Sie ihn auf ein Programmierelement zuweisen. Das folgende Beispiel zeigt einen der folgenden Operatoren `+=`, wodurch erhöht, wird der Wert der Variablen auf der linken Seite des Operators durch den Wert des Ausdrucks auf der rechten Seite.  
  
 [!code-vb[VbVbalrStatements&#77;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_9.vb)]  
  
 Im vorherigen Beispiel wird 1 auf den Wert der `n`, und speichert dann diesen neuen Wert in `n`. Dies ist die Kurzform der folgenden Anweisung entspricht:  
  
 [!code-vb[VbVbalrStatements&#78;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_10.vb)]  
  
 Eine Vielzahl von Vorgängen für zusammengesetzte Zuweisung kann mithilfe von Operatoren dieses Typs ausgeführt werden. Eine Liste dieser Operatoren und Weitere Informationen finden Sie unter [Zuweisungsoperatoren](../../../visual-basic/language-reference/operators/assignment-operators.md).  
  
 Der Verkettungszuweisungsoperator (`&=`) eignet sich zum Hinzufügen einer Zeichenfolge am Ende einer bereits vorhandenen Zeichenfolge, wie im folgende Beispiel veranschaulicht.  
  
 [!code-vb[VbVbalrStatements&#79;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_11.vb)]  
  
### <a name="type-conversions-in-assignment-statements"></a>Typumwandlungen in Zuweisungsanweisungen  
 Der Wert, den Sie auf eine Variable, eine Eigenschaft oder ein Arrayelement zuweisen muss ein Zielelement entsprechenden Datentyp sein. Im Allgemeinen sollten Sie einen Wert von dem Datentyp des Zielelements zu generieren. Einige Typen können jedoch während der Zuweisung in andere Typen konvertiert werden.  
  
 Informationen über das Konvertieren von Datentypen finden Sie unter [Typumwandlungen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md). Kurz gesagt, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] konvertiert automatisch einen Wert eines bestimmten Typs in einen anderen Typ, der erweitert werden kann. Ein *erweiternden Konvertierung* ist zur stets zur Laufzeit erfolgreich ist und keine Daten zu verlieren. Beispielsweise [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] konvertiert ein `Integer` Wert `Double` Wenn erforderlich, da `Integer` Erweiterung in `Double`. Weitere Informationen finden Sie unter [Widening und einschränkende Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
 *Einschränkende Konvertierungen* (die nicht erweiternde sind) das Risiko von Fehler zur Laufzeit oder der Verlust von Daten führen. Sie können eine einschränkende Konvertierung explizit ausführen, mit der eine Konvertierungsfunktion oder Sie können den Compiler alle Konvertierungen implizit durch Festlegen ausführen leiten `Option Strict Off`. Weitere Informationen finden Sie unter [implizite und explizite Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).  
  
## <a name="putting-multiple-statements-on-one-line"></a>Mehrere Anweisungen platzieren in einer Zeile  
 Stehen Ihnen mehrere Anweisungen in einer einzelnen Zeile durch den Doppelpunkt getrennt werden (`:`) Zeichen. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbalrStatements&#70;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_12.vb)]  
  
 Obwohl nur selten sinnvoll ist, wird diese Form der Syntax der Code schwer zu lesen und zu verwalten. Daher wird empfohlen, dass Sie eine Anweisung in einer Zeile beibehalten.  
  
## <a name="continuing-a-statement-over-multiple-lines"></a>Fortsetzen einer Anweisung über mehrere Zeilen  
 Eine Anweisung passt normalerweise in einer Zeile, aber wenn er zu lang ist, können Sie es weiterhin, in der nächsten Zeile, die mit einer Zeilenfortsetzungszeichenfolge, besteht aus einem Leerzeichen, gefolgt von einem Unterstrich (`_`) gefolgt von einem Wagenrücklauf. Im folgenden Beispiel die `MsgBox` ausführbare Anweisung wird über zwei Zeilen fortgesetzt.  
  
 [!code-vb[VbVbalrStatements&#71;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_13.vb)]  
  
### <a name="implicit-line-continuation"></a>Implizite Zeilenfortsetzung  
 In vielen Fällen können Sie eine Anweisung in der nächsten Zeile fortsetzen, ohne mit dem Unterstrich (_). Die folgende Tabelle enthält die Syntaxelemente, die die Anweisung implizit in der nächsten Zeile des Codes fortgesetzt.  
  
|Syntaxelemente|Beispiel|  
|---|---|  
|Nach einem Komma (`,`).|[!code-vb[VbVbalrLineContinuation&#1;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_14.vb)]|  
|Nach der öffnenden Klammer (`(`) oder vor einer schließenden Klammer (`)`).|[!code-vb[VbVbalrLineContinuation&#2;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_15.vb)]|  
|Nach einer öffnenden geschweiften Klammer (`{`) oder vor einer schließenden geschweiften Klammer (`}`).|[!code-vb[VbVbalrLineContinuation&3;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_16.vb)]<br /><br /> Weitere Informationen finden Sie unter [Objektinitialisierer: benannte und anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) oder [Auflistungsinitialisierer](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).|  
|Nach dem Öffnen eines eingebetteten Ausdrucks (`<%=`) oder vor dem Ende eines eingebetteten Ausdrucks (`%>`) in einem XML-Literal.|[!code-vb[VbVbalrLineContinuation&4;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_17.vb)]<br /><br /> Weitere Informationen finden Sie unter [eingebettete Ausdrücke in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).|  
|Nach dem Verkettungsoperator (`&`).|[!code-vb[VbVbcnConventions&#9;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_18.vb)]<br /><br /> Weitere Informationen finden Sie unter [Operatoren sortiert nach Funktionalität](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).|  
|After assignment operators (`=`, `&=`, `:=`, `+=`, `-=`, `*=`, `/=`, `\=`, `^=`, `<<=`, `>>=`).|[!code-vb[VbVbalrLineContinuation&5;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_19.vb)]<br /><br /> Weitere Informationen finden Sie unter [Operatoren sortiert nach Funktionalität](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).|  
|After binary operators (`+`, `-`, `/`, `*`, `Mod`, `<>`, `<`, `>`, `<=`, `>=`, `^`, `>>`, `<<`, `And`, `AndAlso`, `Or`, `OrElse`, `Like`, `Xor`) within an expression.|[!code-vb[VbVbalrLineContinuation&#7;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_20.vb)]<br /><br /> Weitere Informationen finden Sie unter [Operatoren sortiert nach Funktionalität](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).|  
|Nach der `Is` und `IsNot` Operatoren.|[!code-vb[VbVbalrLineContinuation&#8;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_21.vb)]<br /><br /> Weitere Informationen finden Sie unter [Operatoren sortiert nach Funktionalität](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).|  
|Nach einem Element Qualifiziererzeichen (`.`) und vor dem Membernamen. Sie müssen jedoch ein Zeilenfortsetzungszeichen (_) eine Member-Qualifizierer-Zeichen folgt, bei Verwendung der einschließen der `With` -Anweisung oder die Werte in der Initialisierungsliste für einen Typ. Teilen Sie die Zeile nach der Zuweisungsoperator (z. B. `=`) bei Verwendung `With` -Anweisungen oder Objektlisten-Initialisierung.|[!code-vb[VbVbalrLineContinuation&5;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_19.vb)]<br />[!code-vb[VbVbalrLineContinuation&14;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_22.vb)]<br /><br /> Weitere Informationen finden Sie unter [mit... With-Anweisung](../../../visual-basic/language-reference/statements/with-end-with-statement.md) oder [Objektinitialisierer: benannte und anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).|  
|Nachdem ein XML-Achseneigenschaften-Qualifizierer (`.` oder `.@` oder `...`). Sie müssen jedoch ein Zeilenfortsetzungszeichen (_) einschließen, wenn Sie einen Memberqualifizierer angeben, bei der Verwendung der `With` Schlüsselwort.|[!code-vb[VbVbalrLineContinuation&#9;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_23.vb)]<br /><br /> Weitere Informationen finden Sie unter [XML-Achseneigenschaften](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md).|  
|Nach einem kleiner-als-Zeichen (<) or="" before="" a="" greater-than="" sign=""></)>`>`) Wenn Sie ein Attribut angeben. Außerdem nach einem größer-als-Zeichen (`>`) Wenn Sie ein Attribut angeben. Allerdings müssen Sie ein Zeilenfortsetzungszeichen (_) einschließen, wenn Sie Attribute auf Assemblyebene oder Modulebene angeben.|[!code-vb[VbVbalrLineContinuation&#10;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_24.vb)]<br /><br /> Weitere Informationen finden Sie unter [Attributes Overview](../../../visual-basic/programming-guide/concepts/attributes/index.md).|  
|Before and after query operators (`Aggregate`, `Distinct`, `From`, `Group By`, `Group Join`, `Join`, `Let`, `Order By`, `Select`, `Skip`, `Skip While`, `Take`, `Take While`, `Where`, `In`, `Into`, `On`, `Ascending`, and `Descending`). Sie können keine Zeilenumbruch zwischen den Schlüsselwörtern von Abfrageoperatoren, die aus mehreren Schlüsselwörtern bestehen (`Order By`, `Group Join`, `Take While`, und `Skip While`).|[!code-vb[VbVbalrLineContinuation&#11;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_25.vb)]<br /><br /> Weitere Informationen finden Sie unter [Abfragen](../../../visual-basic/language-reference/queries/queries.md).|  
|Nach der `In` -Schlüsselwort in einer `For Each` Anweisung.|[!code-vb[VbVbalrLineContinuation&#12;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_26.vb)]<br /><br /> Weitere Informationen finden Sie unter [für jede... Nächste Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md).|  
|Nach dem `From` Schlüsselwort in einem Auflistungsinitialisierer.|[!code-vb[VbVbalrLineContinuation&#13;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_27.vb)]<br /><br /> Weitere Informationen finden Sie unter [Auflistungsinitialisierer](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).|  
  
## <a name="adding-comments"></a>Hinzufügen von Kommentaren  
 Quellcode ist nicht immer selbsterklärend, selbst für den Programmierer geschrieben hat. Den Code zu dokumentieren stellen, daher die meisten Programmierer eingebettete Kommentare verwenden. Kommentare im Code können eine Prozedur oder eine bestimmte Anweisung lesen oder zu einem späteren Zeitpunkt mit der Arbeit erläutern. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Kommentare werden während der Kompilierung ignoriert und nicht den kompilierten Code beeinflusst.  
  
 Kommentarzeilen beginnen mit einem Apostroph (`'`) oder `REM` gefolgt von einem Leerzeichen. Sie können an einer beliebigen Stelle im Code, außer in einer Zeichenfolge hinzugefügt werden. Wenn Sie einen Kommentar an eine Anweisung anhängen möchten, fügen Sie ein Apostroph oder `REM` nach der Anweisung, gefolgt von den Kommentar. Kommentare können auch auf eine separate Zeile wechseln. Das folgende Beispiel zeigt diese Optionen.  
  
 [!code-vb[VbVbalrStatements&#72;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_28.vb)]  
  
## <a name="checking-compilation-errors"></a>Überprüfen von Kompilierungsfehlern  
 Wenn Sie nach der Eingabe einer Codezeile die Zeile wird durch eine blaue wellenförmige (eine Fehlermeldung kann auch angezeigt werden), ist es in der Anweisung ein Syntaxfehler. Sie müssen herausfinden, was in der Anweisung ist (Suchen in der Aufgabenliste oder der Fehler mit der Maus mit der Maus und die Fehlermeldung lesen) und korrigieren. Bis Sie alle Syntaxfehler im Code behoben haben, wird das Programm nicht ordnungsgemäß kompiliert.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
  
|Begriff|Definition|  
|---|---|  
|[Zuweisungsoperatoren](../../../visual-basic/language-reference/operators/assignment-operators.md)|Enthält Links zu Sprachreferenzseiten Zuweisungsoperatoren wie z. B. `=`, `*=`, und `&=`.|  
|[Operatoren und Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)|Zeigt, wie Elemente mit Operatoren, um neue Werte zu kombinieren.|  
|[Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)|Erfahren, wie Sie eine einzelne Anweisung in mehrere Zeilen aufgeteilt und wie mehrere Anweisungen in der gleichen Zeile platziert.|  
|[Gewusst wie: Bezeichnen von Anweisungen](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)|Zeigt, wie eine Codezeile bezeichnet.|
