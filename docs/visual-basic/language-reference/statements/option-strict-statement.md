---
title: Option Strict Statement
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
ms.openlocfilehash: 9c86ae6be86591445dde3cc4e7bdd38aa4a7f0fa
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404342"
---
# <a name="option-strict-statement"></a>Option Strict Statement
Schränkt implizite Datentyp Konvertierungen auf erweiternde Konvertierungen ein, lässt spätes Binden nicht zu und lässt die implizite Typisierung nicht zu, die zu einem- `Object` Typ führt.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Option Strict { On | Off }  
```  
  
## <a name="parts"></a>Bestandteile  
  
|Begriff|Definition|  
|---|---|  
|`On`|Dies ist optional. Aktiviert die über `Option Strict` Prüfung.|  
|`Off`|Optional. Deaktiviert die über `Option Strict` Prüfung.|  
  
## <a name="remarks"></a>Bemerkungen  
 Wenn `Option Strict On` oder `Option Strict` in einer Datei angezeigt wird, führen die folgenden Bedingungen zu einem Kompilierzeitfehler:  
  
- Implizite Eingrenzungskonvertierungen  
  
- Spätes Binden  
  
- Implizites Typisierung der Ergebnisse in einem `Object`-Typ  
  
> [!NOTE]
> In den Warnungs Konfigurationen, die Sie auf der [Seite "kompilieren", Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)festlegen können, gibt es drei Einstellungen, die den drei Bedingungen entsprechen, die einen Kompilierzeitfehler verursachen. Weitere Informationen zur Verwendung dieser Einstellungen finden Sie unter so [legen Sie Warnungs Konfigurationen in der IDE weiter](option-strict-statement.md#conditions) unten in diesem Thema fest.  
  
 `Option Strict Off`Mit der-Anweisung wird die Fehler-und Warnungs Überprüfung für alle drei Bedingungen deaktiviert, auch wenn die zugeordneten IDE-Einstellungen angeben, um diese Fehler oder Warnungen zu aktivieren. Die `Option Strict On` -Anweisung aktiviert die Fehler-und Warnungs Überprüfung für alle drei Bedingungen, auch wenn die zugeordneten IDE-Einstellungen angeben, um diese Fehler oder Warnungen zu deaktivieren.  
  
 Wenn Sie verwendet wird, muss die- `Option Strict` Anweisung vor allen anderen Code Anweisungen in einer Datei angezeigt werden.  
  
 Wenn Sie `Option Strict` auf festlegen `On` , wird Visual Basic überprüft, ob die Datentypen für alle Programmier Elemente angegeben werden. Datentypen können explizit angegeben oder mit lokalem Typrückschluss angegeben werden. Die Angabe von Datentypen für alle Programmier Elemente wird aus den folgenden Gründen empfohlen:  
  
- Sie ermöglicht die IntelliSense-Unterstützung für Ihre Variablen und Parameter. Auf diese Weise können Sie Ihre Eigenschaften und anderen Member anzeigen, wenn Sie Code eingeben.  
  
- Der Compiler kann die Typüberprüfung durchführen. Die Typüberprüfung hilft Ihnen, Anweisungen zu finden, die zur Laufzeit aufgrund von Typkonvertierungs Fehlern fehlschlagen können. Außerdem werden Aufrufe von Methoden für Objekte identifiziert, die diese Methoden nicht unterstützen.  
  
- Es beschleunigt die Ausführung von Code. Ein Grund hierfür ist, dass der Visual Basic Compiler dem Typ den Typ zuweist, wenn Sie keinen Datentyp für ein Programmier Element angeben `Object` . Der kompilierte Code muss möglicherweise zwischen und anderen Datentypen hin-und herkonvertiert `Object` werden, wodurch die Leistung reduziert wird.  
  
## <a name="implicit-narrowing-conversion-errors"></a>Implizite einschränkende Konvertierungs Fehler  
 Implizite Eingrenzungskonvertierungsfehler treten auf, wenn eine implizite Datentypkonvertierung vorhanden ist, die eine Eingrenzungskonvertierung ist.  
  
 Visual Basic können viele Datentypen in andere Datentypen konvertieren. Ein Datenverlust kann auftreten, wenn der Wert eines Datentyps in einen Datentyp konvertiert wird, der weniger Genauigkeit oder eine geringere Kapazität aufweist. Ein Laufzeitfehler tritt auf, wenn eine solche einschränkende Konvertierung fehlschlägt. `Option Strict`stellt die Benachrichtigung zur Kompilierzeit dieser einschränkenden Konvertierungen sicher, sodass Sie Sie vermeiden können. Weitere Informationen finden Sie unter [implizite und explizite Konvertierungen](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) sowie [erweiternde und einschränkende Konvertierungen](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
 Konvertierungen, die Fehler verursachen können, sind implizite Konvertierungen, die in Ausdrücken auftreten. Weitere Informationen finden Sie in den folgenden Themen:  
  
- [+-Operator](../operators/addition-operator.md)  
  
- [Operator + =](../operators/addition-assignment-operator.md)  
  
- [\-Operator (Visual Basic)](../operators/integer-division-operator.md)  
  
- [Operator/= (Visual Basic)](../operators/floating-point-division-assignment-operator.md)  
  
- [Char-Datentyp](../data-types/char-data-type.md)  
  
 Wenn Sie Zeichen folgen mithilfe des [&-Operators](../operators/concatenation-operator.md)verketten, werden alle Konvertierungen in die Zeichen folgen als Erweiterung betrachtet. Daher generieren diese Konvertierungen keinen impliziten einschränkenden Konvertierungs Fehler, auch wenn `Option Strict` auf on.  
  
 Wenn Sie eine Methode aufrufen, die über ein Argument mit einem anderen Datentyp als den entsprechenden Parameter verfügt, bewirkt eine einschränkende Konvertierung einen Kompilierzeitfehler, wenn `Option Strict` auf ON fest steht. Sie können den Kompilierzeitfehler vermeiden, indem Sie eine erweiternde Konvertierung oder eine explizite Konvertierung verwenden.  
  
 Implizite einschränkende Konvertierungs Fehler werden zur Kompilierzeit für Konvertierungen von Elementen in einer Auflistung `For Each…Next` in die Schleifen Steuerungs Variable unterdrückt. Dies tritt auch dann `Option Strict` auf, wenn auf on. Weitere Informationen finden Sie im Abschnitt "einschränkende Konvertierungen" unter [for each... Next-Anweisung](for-each-next-statement.md).  
  
## <a name="late-binding-errors"></a>Fehler bei späterer Bindung  
 Ein Objekt wird spät gebunden, wenn es einer Eigenschaft oder Methode einer Variable zugeordnet wird, für die der Typ `Object` deklariert wurde. Weitere Informationen finden Sie unter [frühe und späte Bindung](../../programming-guide/language-features/early-late-binding/index.md).  
  
## <a name="implicit-object-type-errors"></a>Implizite Objekttyp Fehler  
 Implizite Objekttypfehler treten auf, wenn ein entsprechender Typ nicht für eine deklarierte Variable hergeleitet werden kann, also wir ein Typ von `Object` hergeleitet. Dies tritt vorwiegend auf, wenn Sie eine `Dim`-Anweisung verwenden, um eine Variable ohne die Verwendung einer `As`-Klausel deklarieren und `Option Infer` deaktiviert ist. Weitere Informationen finden Sie unter [Option Infer-Anweisung](option-infer-statement.md) und [Visual Basic-Sprachspezifikation](../../reference/language-specification/index.md).  
  
 Bei Methoden Parametern ist die- `As` Klausel optional, wenn deaktiviert `Option Strict` ist. Wenn jedoch ein Parameter eine-Klausel verwendet `As` , muss er alle ihn verwenden. Wenn `Option Strict` auf ON fest steht, ist die- `As` Klausel für jede Parameterdefinition erforderlich.  
  
 Wenn Sie eine Variable deklarieren, ohne eine `As` -Klausel zu verwenden und diese auf festzulegen `Nothing` , hat die Variable den Typ `Object` . In diesem Fall tritt kein Kompilierzeitfehler auf, wenn `Option Strict` auf on und `Option Infer` on ist. Ein Beispiel hierfür ist `Dim something = Nothing` .  
  
### <a name="default-data-types-and-values"></a>Standarddatentypen und -werte  
 In der folgenden Tabelle werden die Ergebnisse verschiedener Kombinationen der Angabe von Datentyp und Initialisierer in einer [Dim-Anweisung](dim-statement.md)beschrieben.  
  
|Datentyp angegeben?|Initialisierung angegeben?|Beispiel|Ergebnis|  
|---|---|---|---|  
|Nein|Nein|`Dim qty`|Wenn `Option Strict` deaktiviert ist (Standard), ist die Variable auf `Nothing` eingestellt.<br /><br /> Wenn `Option Strict` aktiviert ist, tritt ein Kompilierzeitfehler auf.|  
|Nein |Ja|`Dim qty = 5`|Wenn `Option Infer` aktiviert ist (Standard), übernimmt die Variable den Datentyp des Initialisierers an. Siehe [lokaler Typrückschluss](../../programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Wenn `Option Infer` und `Option Strict` ausgeschaltet sind, nimmt die Variable den Datentyp des `Object` an.<br /><br /> Wenn `Option Infer` deaktiviert ist und `Option Strict` aktiviert ist, tritt ein Kompilierzeitfehler auf.|  
|Ja|Nein|`Dim qty As Integer`|Die Variable wird auf den Standardwert für den Datentyp initialisiert. Weitere Informationen finden Sie unter [Dim-Anweisung](dim-statement.md).|  
|Ja|Ja|`Dim qty  As Integer = 5`|Wenn der Datentyp der Initialisierung nicht in den angegebenen Datentyp konvertiert werden kann, tritt ein Fehler während der Kompilierung auf.|  
  
## <a name="when-an-option-strict-statement-is-not-present"></a>Wenn eine Option Strict-Anweisung nicht vorhanden ist  
 Wenn der Quellcode keine- `Option Strict` Anweisung enthält, wird die **Option Strict** -Einstellung auf der [Seite "kompilieren", Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) verwendet. Die **Seite Kompilieren** verfügt über Einstellungen, die eine zusätzliche Kontrolle über die Bedingungen bereitstellen, die einen Fehler generieren.  
  
 Wenn Sie den Befehlszeilen Compiler verwenden, können Sie die [-optionstrict-](../../reference/command-line-compiler/optionstrict.md) Compileroption verwenden, um eine Einstellung für anzugeben `Option Strict` .  
  
### <a name="to-set-option-strict-in-the-ide"></a>So legen Sie "Option Strict" in der IDE fest  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
1. Wählen Sie in **Projektmappen-Explorer**ein Projekt aus. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  
  
2. Legen Sie auf der Registerkarte **Kompilieren** den Wert im Feld **Option Strict** fest.  
  
### <a name="to-set-warning-configurations-in-the-ide"></a><a name="conditions"></a>So legen Sie Warnungs Konfigurationen in der IDE fest  
 Wenn Sie die [Seite kompilieren, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) anstelle einer- `Option Strict` Anweisung verwenden, haben Sie zusätzliche Kontrolle über die Bedingungen, die Fehler generieren. Der Abschnitt **Warnungs Konfigurationen** der **Seite Kompilieren** weist Einstellungen auf, die den drei Bedingungen entsprechen, die einen Kompilierzeitfehler verursachen, wenn `Option Strict` auf ON fest steht. Die drei Einstellungen sind die folgenden:  
  
- **Implizite Konvertierung**  
  
- **Späte Bindung; Aufruf könnte zur Laufzeit einen Fehler verursachen**  
  
- **Impliziter Typ; Objekt wird angenommen**  
  
 Wenn Sie **Option Strict** auf **Ein** festlegen, werden alle drei Warnungskonfigurationseinstellungen auf **Fehler** festgelegt. Wenn Sie **Option Strict** auf **Aus** festlegen werden alle drei Einstellungen auf **Keine** festgelegt.  
  
 Sie können individuell jede Warnungskonfigurationseinstellung auf **Keine**, **Warnung** oder **Fehler** festlegen. Wenn alle drei Warnungs Konfigurationseinstellungen auf **Fehler**festgelegt sind, wird `On` im `Option strict` Feld angezeigt. Wenn alle drei auf **None**festgelegt sind, wird `Off` in diesem Feld angezeigt. Für jede andere Kombination dieser Einstellungen erscheint **(benutzerdefiniert)**.  
  
### <a name="to-set-the-option-strict-default-setting-for-new-projects"></a>So legen Sie die Option strikte Standardeinstellung für neue Projekte fest  
 Wenn Sie ein Projekt erstellen, wird die **Option Strict** -Einstellung auf der Registerkarte **Kompilieren** auf die **Option Strict** -Einstellung im Dialogfeld **Optionen** festgelegt.  
  
 Um `Option Strict` in diesem Dialogfeld festzulegen, klicken **Tools** Sie im Menü Extras auf **Optionen**. Erweitern Sie im Dialogfeld **Optionen****Projekte und Lösungen**, und klicken Sie dann auf **VB Defaults**. Die ursprüngliche Standardeinstellung in **VB-Standardeinstellungen** ist `Off` .  
  
### <a name="to-set-option-strict-on-the-command-line"></a>So legen Sie "Option Strict" in der Befehlszeile fest  
 Schließen Sie die [-optionstrict-](../../reference/command-line-compiler/optionstrict.md) Compileroption in den **vbc** -Befehl ein.  
  
## <a name="example"></a>Beispiel  
 Die folgenden Beispiele veranschaulichen Kompilierzeitfehler, die von impliziten Typkonvertierungen verursacht werden, die einschränkende Konvertierungen sind. Diese Kategorie von Fehlern entspricht der **impliziten Konvertierungs** Bedingung auf der **Seite Kompilieren**.  
  
 [!code-vb[VbVbalrStatements#161](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class13.vb#161)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein Kompilierzeitfehler veranschaulicht, der durch eine späte Bindung verursacht wurde. Diese Kategorie von Fehlern entspricht der **späten Bindung; der Aufruf könnte bei der Laufzeit** auf der Seite " **Kompilieren**" fehlschlagen.  
  
 [!code-vb[VbVbalrStatements#162](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class13.vb#162)]  
  
## <a name="example"></a>Beispiel  
 In den folgenden Beispielen werden Fehler veranschaulicht, die durch Variablen verursacht werden, die mit einem impliziten Typ von deklariert werden `Object` . Diese Kategorie von Fehlern entspricht dem **impliziten Typ; das Objekt** wird auf der **Seite "kompilieren**" als Bedingung angenommen.  
  
 [!code-vb[VbVbalrStatements#163](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class13.vb#163)]  
  
 [!code-vb[VbVbalrStatements#164](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class13.vb#164)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Implizite und explizite Konvertierungen](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Seite „Kompilieren“, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [Option Explicit-Anweisung](option-explicit-statement.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Vorgehensweise: Zugreifen auf Member eines Objekts](../../programming-guide/language-features/variables/how-to-access-members-of-an-object.md)
- [Eingebettete Ausdrücke in XML](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [Gelockerte Delegatenkonvertierung](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [Late Binding in Office Solutions](/visualstudio/vsto/late-binding-in-office-solutions)
- [-optionstrict](../../reference/command-line-compiler/optionstrict.md)
- [VB-Standard, Projekte, Dialogfeld „Optionen“](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
