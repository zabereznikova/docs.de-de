---
title: Option Strict Statement
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "49"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 238f64001b097b86306e0ed9630bd5df2e6a189f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="option-strict-statement"></a>Option Strict Statement
Implizite datentypkonvertierungen nur erweiterungskonvertierungen beschränkt, lässt spätes Binden und lässt keine implizite Typisierung, die in einem `Object` Typ.  
  
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
 Wenn `Option Strict On` oder `Option Strict` in einer Datei wird unter folgenden Umständen einen Fehler während der Kompilierung:  
  
-   Implizite Eingrenzungskonvertierungen  
  
-   Spätes Binden  
  
-   Implizites Typisierung der Ergebnisse in einem `Object`-Typ  
  
> [!NOTE]
>  In der Warnungskonfigurationen, die Sie setzen können die [Seite kompilieren, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), es gibt drei Einstellungen, die drei Bedingungen entsprechen, die dazu führen, einen Fehler während der Kompilierung dass. Informationen zur Verwendung dieser Einstellungen finden Sie unter [Warnungskonfigurationen in der IDE festlegen](../../../visual-basic/language-reference/statements/option-strict-statement.md#conditions) weiter unten in diesem Thema.  
  
 Die `Option Strict Off` Anweisung wird deaktiviert Fehler- und die Warnung wird für alle drei Bedingungen überprüft, auch wenn die entsprechenden IDE-Einstellungen angeben, um diese Fehler oder Warnungen zu aktivieren. Die `Option Strict On` Anweisung aktiviert die Fehler- und Warnung Prüfung für alle drei Bedingungen, selbst wenn die entsprechenden IDE-Einstellungen angeben, um diese Fehler oder Warnungen zu deaktivieren.  
  
 Wenn verwendet, die `Option Strict` -Anweisung muss vor allen anderen Codes-Anweisungen in einer Datei stehen.  
  
 Bei Festlegung `Option Strict` zu `On`, Visual Basic überprüft, dass die Datentypen für alle Programmierelemente angegeben werden. Datentypen können explizit angegeben oder mithilfe von lokalem Typrückschluss angegeben werden. Das Festlegen von Datentypen für alle Programmierelemente wird, den folgenden Gründen empfohlen:  
  
-   Dadurch werden IntelliSense-Unterstützung für die Variablen und Parametern. Dadurch können Sie ihre Eigenschaften und andere Elemente anzeigen, während der Eingabe von Code.  
  
-   Sie können den Compiler an, führen Sie die Überprüfung des Typs. Typüberprüfung erleichtert das Ermitteln von Anweisungen, die zur Laufzeit aufgrund Typkonvertierungsfehler fehlschlagen kann. Außerdem ermittelt es für Aufrufe von Methoden für Objekte, die diese Methoden nicht unterstützen.  
  
-   Sie beschleunigt die Ausführung von Code. Ein Grund dafür ist, dass wenn Sie einen Datentyp für ein Programmierelement nicht angeben, die Visual Basic-Compiler weist die `Object` Typ. Kompilierte Code möglicherweise zwischen hin und her konvertiert `Object` und anderen Datentypen, die Leistung wird reduziert.  
  
## <a name="implicit-narrowing-conversion-errors"></a>Implizite einschränkende Konvertierungsfehler  
 Implizite Eingrenzungskonvertierungsfehler treten auf, wenn eine implizite Datentypkonvertierung vorhanden ist, die eine Eingrenzungskonvertierung ist.  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]Viele Datentypen können in andere Datentypen konvertiert werden. Es können Datenverluste auftreten, wenn der Wert von einem Datentyp in einen Datentyp konvertiert wird, die weniger genau ist oder eine kleinere Kapazität aufweist. Ein Laufzeitfehler tritt auf, wenn so eine einschränkende Konvertierung ein Fehler auftritt. `Option Strict`wird sichergestellt, dass während der Kompilierung Benachrichtigung dieser einschränkende Konvertierungen, damit Sie sie vermeiden können. Weitere Informationen finden Sie unter [implizite und explizite Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) und [Widening und einschränkende Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
 Konvertierungen, die Fehler verursachen können einbinden implizite Konvertierungen, die auftreten, in den Ausdrücken. Weitere Informationen finden Sie unter den folgenden Themen:  
  
-   [+-Operator](../../../visual-basic/language-reference/operators/addition-operator.md)  
  
-   [+=-Operator](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
  
-   [\-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)  
  
-   [/ =-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
  
-   [Char-Datentyp](../../../visual-basic/language-reference/data-types/char-data-type.md)  
  
 Beim Verketten von Zeichenfolgen mithilfe der [&-Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md), alle Konvertierungen, die Zeichenfolgen gelten als erweiternde sein. Damit dieser Konvertierungen eine implizite einschränkende Konvertierungsfehler, auch wenn keine generieren `Option Strict` befindet sich auf.  
  
 Wenn Sie eine Methode, die ein Argument verfügt, die einen Datentyp, der sich von dem entsprechenden Parameter aufweist aufrufen, verursacht eine einschränkende Konvertierung einen Fehler während der Kompilierung, wenn `Option Strict` befindet sich auf. Sie können den Zeitpunkt der Kompilierung Fehler vermeiden, indem Sie eine erweiternde Konvertierung oder eine explizite Konvertierung.  
  
 Implizite einschränkende Konvertierungsfehler unterdrückt werden, zum Zeitpunkt der Kompilierung für Konvertierungen von den Elementen in einem `For Each…Next` -Auflistung, um die Loop-Steuerelementvariable. Dies tritt auf, selbst wenn `Option Strict` befindet sich auf. Weitere Informationen finden Sie im Abschnitt "Einschränkende Konvertierungen" [für jede... Nächste Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
## <a name="late-binding-errors"></a>Späte Bindung Fehler  
 Ein Objekt wird spät gebunden, wenn es einer Eigenschaft oder Methode einer Variable zugeordnet wird, für die der Typ `Object` deklariert wurde. Weitere Informationen finden Sie unter [frühe und späte Bindung](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md).  
  
## <a name="implicit-object-type-errors"></a>Implizite Objekttypfehler  
 Implizite Objekttypfehler treten auf, wenn ein entsprechender Typ nicht für eine deklarierte Variable hergeleitet werden kann, also wir ein Typ von `Object` hergeleitet. Dies tritt vorwiegend auf, wenn Sie eine `Dim`-Anweisung verwenden, um eine Variable ohne die Verwendung einer `As`-Klausel deklarieren und `Option Infer` deaktiviert ist. Weitere Informationen finden Sie unter [Option Infer-Anweisung](../../../visual-basic/language-reference/statements/option-infer-statement.md) und [Visual Basic-Sprachspezifikation](../../../visual-basic/reference/language-specification/index.md).  
  
 Für die Parameter der Methode die `As` -Klausel ist optional Wenn `Option Strict` ist deaktiviert. Jedoch, wenn ein Parameter verwendet ein `As` -Klausel, alle verwenden dieses. Wenn `Option Strict` ist, wird die `As` -Klausel für jede Parameterdefinition erforderlich ist.  
  
 Wenn eine Variable zu, ohne deklarieren eine `As` Klausel und legen Sie dafür `Nothing`, hat die Variable einen Typ von `Object`. Keine Fehler während der Kompilierung tritt in diesem Fall auf, wenn `Option Strict` befindet sich auf und `Option Infer` befindet sich auf. Ein Beispiel hierfür ist `Dim something = Nothing`.  
  
### <a name="default-data-types-and-values"></a>Standarddatentypen und -werte  
 Die folgende Tabelle beschreibt die Ergebnisse der verschiedenen Kombinationen der Angabe von Datentyp und Initialisierung in einer [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
|Datentyp angegeben?|Initialisierung angegeben?|Beispiel|Ergebnis|  
|---|---|---|---|  
|Nein|Nein|`Dim qty`|Wenn `Option Strict` deaktiviert ist (Standard), ist die Variable auf `Nothing` eingestellt.<br /><br /> Wenn `Option Strict` aktiviert ist, tritt ein Kompilierungsfehler auf.|  
|Nein|Ja|`Dim qty = 5`|Wenn `Option Infer` aktiviert ist (Standard), übernimmt die Variable den Datentyp des Initialisierers an. Finden Sie unter [lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Wenn `Option Infer` und `Option Strict` ausgeschaltet sind, nimmt die Variable den Datentyp des `Object` an.<br /><br /> Wenn `Option Infer` deaktiviert ist und `Option Strict` aktiviert ist, tritt ein Kompilierungsfehler auf.|  
|Ja|Nein|`Dim qty As Integer`|Die Variable wird auf den Standardwert für den Datentyp initialisiert. Weitere Informationen finden Sie unter [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md).|  
|Ja|Ja|`Dim qty  As Integer = 5`|Wenn der Datentyp der Initialisierung nicht in den angegebenen Datentyp konvertiert werden kann, tritt ein Fehler während der Kompilierung auf.|  
  
## <a name="when-an-option-strict-statement-is-not-present"></a>Wenn eine Option Strict-Anweisung nicht vorhanden ist  
 Wenn der Quellcode nicht enthält ein `Option Strict` -Anweisung, die **Option strict** festlegen für die [Seite kompilieren, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) verwendet wird. Die **Seite "Kompilieren"** Einstellungen, die zusätzliche Kontrolle über die Bedingungen angeben, die einen Fehler generiert hat.  
  
 Wenn Sie den Befehlszeilencompiler verwenden, können Sie mithilfe der [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) (Compileroption), geben Sie eine Einstellung für `Option Strict`.  
  
### <a name="to-set-option-strict-in-the-ide"></a>Option Strict festlegen, in der IDE  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
1.  Wählen Sie im **Projektmappen-Explorer** ein Projekt aus. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Auf der **Kompilieren** Registerkarte, legen Sie den Wert der **Option Strict** Feld.  
  
###  <a name="conditions"></a>Warnungskonfigurationen in der IDE festlegen  
 Bei Verwendung der [Seite kompilieren, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) anstelle von einer `Option Strict` -Anweisung, haben Sie zusätzliche Kontrolle über die Bedingungen, die Fehler generieren. Die **Warnungskonfigurationen** Teil der **Seite "Kompilieren"** verfügt über Einstellungen, die drei Bedingungen entsprechen, die dazu führen, einen Fehler während der Kompilierung dass, beim `Option Strict` befindet sich auf. Die drei Einstellungen sind die folgenden:  
  
-   **Implizite Konvertierung**  
  
-   **Späte Bindung; Aufruf könnte zur Laufzeit einen Fehler verursachen**  
  
-   **Impliziter Typ; Objekt wird angenommen**  
  
 Wenn Sie **Option Strict** auf **Ein** festlegen, werden alle drei Warnungskonfigurationseinstellungen auf **Fehler** festgelegt. Wenn Sie **Option Strict** auf **Aus** festlegen werden alle drei Einstellungen auf **Keine** festgelegt.  
  
 Sie können individuell jede Warnungskonfigurationseinstellung auf **Keine**, **Warnung** oder **Fehler** festlegen. Wenn alle drei Warnungskonfigurationseinstellungen auf **Fehler** festgelegt sind, erscheint `On` im `Option strict`-Feld. Wenn alle drei Einstellungen auf **Keine** festgelegt sind, erscheint `Off` im Feld. Für jede andere Kombination dieser Einstellungen erscheint **(benutzerdefiniert)**.  
  
### <a name="to-set-the-option-strict-default-setting-for-new-projects"></a>Festlegen der Option Strict Standardeinstellung für neue Projekte  
 Bei der Erstellung eines Projekts die **Option Strict** festlegen, auf die **Kompilieren** auf die Registerkarte "festgelegt ist die **Option Strict** festlegen in der **Optionen** Das Dialogfeld.  
  
 Festzulegende `Option Strict` in diesem Dialogfeld auf die **Tools** Menü klicken Sie auf **Optionen**. Erweitern Sie im Dialogfeld **Optionen** **Projekte und Lösungen**, und klicken Sie dann auf **VB Defaults**. Die ursprüngliche Standardeinstellung in **VB-Standard** ist `Off`.  
  
### <a name="to-set-option-strict-on-the-command-line"></a>Option Strict in der Befehlszeile festlegen  
 Enthalten die [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) -Compileroption in der **Vbc** Befehl.  
  
## <a name="example"></a>Beispiel  
 Die folgenden Beispiele veranschaulichen die Kompilierungsfehlern durch implizite Konvertierungen, die nur eine annähernde Entsprechung sind verursacht. Diese Kategorie von Fehlern entspricht der **implizite Konvertierung** Bedingung auf die **Seite "Kompilieren"**.  
  
 [!code-vb[VbVbalrStatements#161](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_1.vb)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht einen Fehler während der Kompilierung verursacht durch späte Bindung. Diese Kategorie von Fehlern entspricht der **späte Bindung; Aufruf kann Fehler verursachen zur Laufzeit** Bedingung auf die **Seite "Kompilieren"**.  
  
 [!code-vb[VbVbalrStatements#162](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_2.vb)]  
  
## <a name="example"></a>Beispiel  
 Die folgenden Beispiele veranschaulichen von Variablen, die mit einem impliziten Typ deklariert sind verursachten `Object`. Diese Kategorie von Fehlern entspricht der **impliziter Typ; davon ausgegangen, dass** Bedingung auf die **Seite "Kompilieren"**.  
  
 [!code-vb[VbVbalrStatements#163](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_3.vb)]  
  
 [!code-vb[VbVbalrStatements#164](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_4.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Erweiternde und eingrenzende Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Implizite und explizite Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Seite „Kompilieren“, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)  
 [Option Explicit-Anweisung](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Gewusst wie: Zugreifen auf Member eines Objekts](../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)  
 [Eingebettete Ausdrücke in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)  
 [Gelockerte Delegatenkonvertierung](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)  
 [Spätes Binden in Office-Projektmappen](https://msdn.microsoft.com/library/3xxe951d)  
 [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [VB-Standard, Projekte, Dialogfeld „Optionen“](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
