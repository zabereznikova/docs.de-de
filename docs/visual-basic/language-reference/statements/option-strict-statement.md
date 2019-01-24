---
title: Option Strict-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Strict
- vb.OptionStrict
helpviewer_keywords:
- Strict keyword [Visual Basic]
- Option Strict statement [Visual Basic]
- conversions [Visual Basic], implicit
- late binding [Visual Basic]
- implicit conversions [Visual Basic]
ms.assetid: 5883e0c1-a920-4274-8e46-b0ff047eaee5
ms.openlocfilehash: e686b3e371b24f14637476f9a7fd5455f1b2b86c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580797"
---
# <a name="option-strict-statement"></a>Option Strict Statement
Implizite datentypkonvertierungen auf erweiternde Konvertierungen eingeschränkt und lässt keine späte Bindung lässt keine impliziten Typisierung der Ergebnisse in eine `Object` Typ.  
  
## <a name="syntax"></a>Syntax  
  
```  
Option Strict { On | Off }  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`On`|Dies ist optional. Ermöglicht `Option Strict` überprüfen.|  
|`Off`|Dies ist optional. Deaktiviert die `Option Strict` überprüfen.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn `Option Strict On` oder `Option Strict` wird in einer Datei, die folgenden Bedingungen dazu führen, dass einen Fehler während der Kompilierung:  
  
-   Implizite Eingrenzungskonvertierungen  
  
-   Spätes Binden  
  
-   Implizites Typisierung der Ergebnisse in einem `Object`-Typ  
  
> [!NOTE]
>  Die Warnung-Konfigurationen, die Sie für festlegen können die [Seite "Kompilieren", Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), es gibt drei Einstellungen, die mit den drei Bedingungen entsprechen, die dazu führen, einen Fehler während der Kompilierung dass. Informationen dazu, wie Sie diese Einstellungen verwenden, finden Sie unter [Warnungskonfigurationen festlegen, in der IDE](../../../visual-basic/language-reference/statements/option-strict-statement.md#conditions) weiter unten in diesem Thema.  
  
 Die `Option Strict Off` Anweisung deaktiviert die Fehler und die Warnung überprüfen alle drei Bedingungen, selbst wenn die zugehörigen IDE-Einstellungen angeben, um diese Fehler oder Warnungen zu aktivieren. Die `Option Strict On` Anweisung aktiviert die Fehler- und Warnung überprüfen alle drei Bedingungen, selbst wenn die zugehörigen IDE-Einstellungen angeben, um diese Fehler oder Warnungen zu deaktivieren.  
  
 Wenn verwendet, die `Option Strict` Anweisung muss vor allen anderen codeanweisungen in einer Datei verwendet werden.  
  
 Wenn Sie festlegen, `Option Strict` zu `On`, Visual Basic überprüft, dass die Datentypen für alle Programmiersprachen Elemente angegeben werden. Datentypen können explizit angegeben werden oder mithilfe von lokalem Typrückschluss angegeben werden. Angabe von Datentypen für alle Programmierelemente wird, den folgenden Gründen empfohlen:  
  
-   Sie können IntelliSense-Unterstützung für Ihre Variablen und Parameter. Dadurch können Sie die Eigenschaften und andere Member zu sehen, wie Sie Code eingeben.  
  
-   Sie können den Compiler an, führen Sie die Überprüfung des Typs. Typüberprüfung können Sie die Anweisungen zu finden, die aufgrund von Fehler bei der datentypkonvertierung zur Laufzeit fehlschlagen können. Er gibt außerdem Aufrufe von Methoden für Objekte, die diese Methoden nicht unterstützen.  
  
-   Es beschleunigt die Ausführung von Code. Ein Grund hierfür ist, wenn Sie einen Datentyp für ein Programmierelement nicht angeben, die Visual Basic-Compiler weist die `Object` Typ. Kompilierte Code möglicherweise zwischen hin und her konvertiert `Object` und andere Datentypen, die Leistung verringert.  
  
## <a name="implicit-narrowing-conversion-errors"></a>Implizite Eingrenzungskonvertierungsfehler treten  
 Implizite Eingrenzungskonvertierungsfehler treten auf, wenn eine implizite Datentypkonvertierung vorhanden ist, die eine Eingrenzungskonvertierung ist.  
  
 Visual Basic können viele Datentypen in andere Datentypen konvertieren. Es können Datenverluste auftreten, wenn der Wert von einem Datentyp in einen Datentyp konvertiert wird, die geringere Genauigkeit oder eine kleinere Kapazität aufweist. Ein Laufzeitfehler tritt auf, wenn eine solche einschränkende Konvertierung ein Fehler auftritt. `Option Strict` Stellt die Benachrichtigung während der Kompilierung dieser einschränkenden Konvertierungen sicher, damit Sie diese vermeiden können. Weitere Informationen finden Sie unter [implizite und explizite Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) und [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
 Konvertierungen, die zu Fehlern führen können enthalten implizite Konvertierungen, die auftreten, in Ausdrücken. Weitere Informationen finden Sie unter den folgenden Themen:  
  
-   [+-Operator](../../../visual-basic/language-reference/operators/addition-operator.md)  
  
-   [+=-Operator](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
  
-   [\-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)  
  
-   [/ =-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
  
-   [Char-Datentyp](../../../visual-basic/language-reference/data-types/char-data-type.md)  
  
 Beim Verketten von Zeichenfolgen mithilfe der [& Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md), gelten alle Konvertierungen auf die Zeichenfolgen erweiternde sein. Damit diese Konvertierungen nicht, eine implizite einschränkende Konvertierungsfehler, auch wenn generiert werden `Option Strict` ist.  
  
 Wenn Sie eine Methode, die ein Argument, das einen Datentyp, der sich von dem entsprechenden Parameter aufweist aufrufen, verursacht eine einschränkende Konvertierung einen Fehler während der Kompilierung, wenn `Option Strict` ist. Sie können die Kompilierungsfehler vermeiden, über eine erweiternde Konvertierung oder eine explizite Konvertierung.  
  
 Implizite eingrenzungskonvertierungsfehler treten unterdrückt werden, zum Zeitpunkt der Kompilierung für Konvertierungen aus den Elementen in einem `For Each…Next` -Auflistung, um die Schleifensteuerungsvariable. Dies tritt auf, auch wenn `Option Strict` ist. Weitere Informationen finden Sie im Abschnitt "Einschränkende Konvertierungen" in [für jede... Nächste Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
## <a name="late-binding-errors"></a>Späte Bindung Fehler  
 Ein Objekt wird spät gebunden, wenn es einer Eigenschaft oder Methode einer Variable zugeordnet wird, für die der Typ `Object` deklariert wurde. Weitere Informationen finden Sie unter [frühes und spätes Binden](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md).  
  
## <a name="implicit-object-type-errors"></a>Implizite Objekttypfehler  
 Implizite Objekttypfehler treten auf, wenn ein entsprechender Typ nicht für eine deklarierte Variable hergeleitet werden kann, also wir ein Typ von `Object` hergeleitet. Dies tritt vorwiegend auf, wenn Sie eine `Dim`-Anweisung verwenden, um eine Variable ohne die Verwendung einer `As`-Klausel deklarieren und `Option Infer` deaktiviert ist. Weitere Informationen finden Sie unter [Option Infer-Anweisung](../../../visual-basic/language-reference/statements/option-infer-statement.md) und [Visual Basic-Sprachspezifikation](../../../visual-basic/reference/language-specification/index.md).  
  
 Für die Parameter der Methode die `As` -Klausel ist optional Wenn `Option Strict` ist deaktiviert. Jedoch einen Parameter verwendet eine `As` -Klausel jeweils müssen verwenden. Wenn `Option Strict` ist, wird die `As` -Klausel ist erforderlich für jede Parameterdefinition.  
  
 Wenn Sie eine Variable, ohne deklarieren eine `As` Klausel und legen ihn auf `Nothing`, hat die Variable ein `Object`. Keine Kompilierungsfehler tritt auf, in diesem Fall beim `Option Strict` befindet sich auf und `Option Infer` ist. Ein Beispiel hierfür ist `Dim something = Nothing`.  
  
### <a name="default-data-types-and-values"></a>Standarddatentypen und -werte  
 Die folgende Tabelle beschreibt die Ergebnisse der verschiedenen Kombinationen der Angabe von Datentyp und Initialisierung in einer [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
|Datentyp angegeben?|Initialisierung angegeben?|Beispiel|Ergebnis|  
|---|---|---|---|  
|Nein|Nein|`Dim qty`|Wenn `Option Strict` deaktiviert ist (Standard), ist die Variable auf `Nothing` eingestellt.<br /><br /> Wenn `Option Strict` aktiviert ist, tritt ein Kompilierungsfehler auf.|  
|Nein|Ja|`Dim qty = 5`|Wenn `Option Infer` aktiviert ist (Standard), übernimmt die Variable den Datentyp des Initialisierers an. Finden Sie unter [lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Wenn `Option Infer` und `Option Strict` ausgeschaltet sind, nimmt die Variable den Datentyp des `Object` an.<br /><br /> Wenn `Option Infer` deaktiviert ist und `Option Strict` aktiviert ist, tritt ein Kompilierungsfehler auf.|  
|Ja|Nein|`Dim qty As Integer`|Die Variable wird auf den Standardwert für den Datentyp initialisiert. Weitere Informationen finden Sie unter [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md).|  
|Ja|Ja|`Dim qty  As Integer = 5`|Wenn der Datentyp der Initialisierung nicht in den angegebenen Datentyp konvertiert werden kann, tritt ein Fehler während der Kompilierung auf.|  
  
## <a name="when-an-option-strict-statement-is-not-present"></a>Wenn eine Option Strict-Anweisung nicht vorhanden ist  
 Wenn der Quellcode kein `Option Strict` -Anweisung, die **Option strict** festlegen auf die [Seite "Kompilieren", Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) wird verwendet. Die **Seite "Kompilieren"** verfügt über Einstellungen, die zusätzliche Kontrolle über die Bedingungen zu bieten, die einen Fehler generieren.  
  
 Wenn Sie den Befehlszeilencompiler verwenden, können Sie mithilfe der [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) -Compileroption verwenden, um eine Einstellung für geben `Option Strict`.  
  
### <a name="to-set-option-strict-in-the-ide"></a>Option Strict festlegen, in der IDE  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
1.  Wählen Sie im **Projektmappen-Explorer** ein Projekt aus. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  
  
2.  Auf der **Kompilieren** Registerkarte, legen Sie den Wert der **Option Strict** Feld.  
  
###  <a name="conditions"></a> Festlegen von Warnungskonfigurationen in der IDE  
 Bei Verwendung der [Seite "Kompilieren", Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) statt einer `Option Strict` -Anweisung, haben Sie zusätzliche Kontrolle über die Bedingungen, die zu Fehlern führen. Die **Warnungskonfigurationen** Teil der **Seite "Kompilieren"** verfügt über Einstellungen, die mit den drei Bedingungen entsprechen, die dazu führen, einen Fehler während der Kompilierung dass bei `Option Strict` ist. Die drei Einstellungen sind die folgenden:  
  
-   **Implizite Konvertierung**  
  
-   **Späte Bindung; Aufruf könnte zur Laufzeit einen Fehler verursachen**  
  
-   **Impliziter Typ; Objekt wird angenommen**  
  
 Wenn Sie **Option Strict** auf **Ein** festlegen, werden alle drei Warnungskonfigurationseinstellungen auf **Fehler** festgelegt. Wenn Sie **Option Strict** auf **Aus** festlegen werden alle drei Einstellungen auf **Keine** festgelegt.  
  
 Sie können individuell jede Warnungskonfigurationseinstellung auf **Keine**, **Warnung** oder **Fehler** festlegen. Wenn alle drei Warnungskonfigurationseinstellungen auf **Fehler** festgelegt sind, erscheint `On` im `Option strict`-Feld. Wenn alle drei Einstellungen auf **Keine** festgelegt sind, erscheint `Off` im Feld. Für jede andere Kombination dieser Einstellungen erscheint **(benutzerdefiniert)**.  
  
### <a name="to-set-the-option-strict-default-setting-for-new-projects"></a>Die Einstellung der Option Strict für neue Projekte festlegen  
 Wenn Sie ein Projekt erstellen der **Option Strict** festlegen auf der **Kompilieren** auf die Registerkarte "festgelegt ist die **Option Strict** festlegen in der **Optionen** Das Dialogfeld.  
  
 Festzulegende `Option Strict` in diesem Dialogfeld auf die **Tools** Menü klicken Sie auf **Optionen**. Erweitern Sie im Dialogfeld **Optionen** **Projekte und Lösungen**, und klicken Sie dann auf **VB Defaults**. Die ursprüngliche Standardeinstellung in **VB Defaults** ist `Off`.  
  
### <a name="to-set-option-strict-on-the-command-line"></a>Option Strict in der Befehlszeile festlegen  
 Enthalten die [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) -Compileroption in der **Vbc** Befehl.  
  
## <a name="example"></a>Beispiel  
 Die folgenden Beispiele veranschaulichen die Kompilierungsfehler, die durch implizite typkonvertierungen, die nur eine annähernde sind verursacht werden. Diese Kategorie von Fehlern entspricht der **implizite Konvertierung** -Bedingung in die **Seite "Kompilieren"**.  
  
 [!code-vb[VbVbalrStatements#161](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_1.vb)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt einen Fehler während der Kompilierung, die durch die späte Bindung verursacht. Diese Kategorie von Fehlern entspricht der **späte Bindung; Aufruf könnte zur Laufzeit nicht ausgeführt** -Bedingung in die **Seite "Kompilieren"**.  
  
 [!code-vb[VbVbalrStatements#162](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_2.vb)]  
  
## <a name="example"></a>Beispiel  
 Die folgenden Beispiele veranschaulichen von Variablen, die mit einem impliziten Typs deklariert werden verursachten Fehler `Object`. Diese Kategorie von Fehlern entspricht der **impliziter Typ; Objekt wird davon ausgegangen, dass** -Bedingung in die **Seite "Kompilieren"**.  
  
 [!code-vb[VbVbalrStatements#163](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_3.vb)]  
  
 [!code-vb[VbVbalrStatements#164](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_4.vb)]  
  
## <a name="see-also"></a>Siehe auch

- [Erweiternde und eingrenzende Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Implizite und explizite Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Seite „Kompilieren“, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [Option Explicit-Anweisung](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Vorgehensweise: Zugreifen auf Member eines Objekts](../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)
- [Eingebettete Ausdrücke in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [Gelockerte Delegatenkonvertierung](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [Spätes Binden in Office-Projektmappen](/visualstudio/vsto/late-binding-in-office-solutions)
- [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [VB-Standard, Projekte, Dialogfeld „Optionen“](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
