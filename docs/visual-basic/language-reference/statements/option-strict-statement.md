---
title: Option Strict-Anweisung | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Strict
- vb.OptionStrict
dev_langs:
- VB
helpviewer_keywords:
- Strict keyword
- Option Strict statement
- conversions, implicit
- late binding
- implicit conversions
ms.assetid: 5883e0c1-a920-4274-8e46-b0ff047eaee5
caps.latest.revision: 49
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 3bf0d4939f24c38392d7ca4764c41d12366067b5
ms.lasthandoff: 03/13/2017

---
# <a name="option-strict-statement"></a>Option Strict Statement
Schränkt impliziter datentypkonvertierungen nur erweiternden Konvertierung lässt nicht zu spät, und lässt keine implizite Typisierung, bei denen ein `Object` Typ.  
  
## <a name="syntax"></a>Syntax  
  
```  
Option Strict { On | Off }  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`On`|Optional. Ermöglicht `Option Strict` überprüfen.|  
|`Off`|Optional. Deaktiviert die `Option Strict` überprüfen.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn `Option Strict On` oder `Option Strict` in einer Datei wird unter folgenden Umständen einen Fehler während der Kompilierung:  
  
-   Implizite einschränkende Konvertierungen  
  
-   Spätes Binden  
  
-   Implizite Typisierung, bei denen ein `Object` Typ  
  
> [!NOTE]
>  Warnung-Konfigurationen, die Sie auf festlegen, können die [Seite kompilieren, Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic), es gibt drei Einstellungen, die drei Bedingungen entsprechen, die einen Kompilierungsfehler verursachen. Informationen zur Verwendung dieser Einstellung finden Sie unter [Warnungskonfigurationen in der IDE festlegen](../../../visual-basic/language-reference/statements/option-strict-statement.md#conditions) weiter unten in diesem Thema.  
  
 Die `Option Strict Off` Anweisung deaktiviert die Fehler und Warnung-Prüfung für alle drei Bedingungen, selbst wenn die zugehörigen IDE-Einstellungen angeben, um diese Fehler oder Warnungen aktivieren. Die `Option Strict On` schaltet Anweisung Fehler und Warnung-Prüfung für alle drei Bedingungen, auch wenn die zugehörigen IDE-Einstellungen angeben, um diese Fehler oder Warnungen zu deaktivieren.  
  
 Wenn verwendet, die `Option Strict` Anweisung muss vor allen anderen codeanweisungen in einer Datei angezeigt werden.  
  
 Wenn Sie die Option `Option Strict` , `On`, Visual Basic überprüft, dass die Datentypen für alle Programmierelemente angegeben werden. Datentypen können explizit angegeben oder mit lokalen Typrückschluss angegeben werden. Die Angabe von Datentypen für alle Programmierelemente wird aus den folgenden Gründen empfohlen:  
  
-   Sie können IntelliSense-Unterstützung für die Variablen und Parameter. Dadurch können Sie die Eigenschaften und andere Member zu sehen, wie Sie Code eingeben.  
  
-   Sie können den Compiler an, zu überprüfen. Überprüfung des Typs hilft Ihnen, Anweisungen zu suchen, die zur Laufzeit aufgrund Typkonvertierungsfehler fehlschlagen kann. Es gibt zudem Aufrufe von Methoden für Objekte, die diese Methoden nicht unterstützen.  
  
-   Es beschleunigt die Ausführung von Code. Ein Grund hierfür ist, wenn Sie einen Datentyp für ein Programmierelement nicht angeben, die Visual Basic-Compiler weist die `Object` Typ. Kompilierte Code müsste zwischen konvertieren `Object` und anderen Datentypen, die Leistung reduziert wird.  
  
## <a name="implicit-narrowing-conversion-errors"></a>Implizite einschränkende Konvertierungsfehler  
 Implizite einschränkende Konvertierungsfehler auftreten, wenn eine implizite datentypkonvertierung, die eine einschränkende Konvertierung vorhanden ist.  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]kann viele Datentypen in andere Datentypen konvertieren. Es können Datenverluste auftreten, wenn der Wert von einem Datentyp in einen Datentyp konvertiert wird, die geringere Genauigkeit oder kleinerer Kapazität verfügt. Ein Laufzeitfehler tritt auf, wenn so eine einschränkende Konvertierung ein Fehler auftritt. `Option Strict`wird während der Kompilierung Bekanntgabe dieser einschränkenden Konvertierungen sichergestellt, damit Sie diese vermeiden können. Weitere Informationen finden Sie unter [implizite und explizite Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) und [Widening und einschränkende Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
 Konvertierungen, die Fehler verursachen können enthalten implizite Konvertierungen, die auftreten, in Ausdrücken. Weitere Informationen finden Sie unter den folgenden Themen:  
  
-   [+-Operator](../../../visual-basic/language-reference/operators/addition-operator.md)  
  
-   [+=-Operator](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
  
-   [\-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)  
  
-   [/ =-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
  
-   [Char-Datentyp](../../../visual-basic/language-reference/data-types/char-data-type.md)  
  
 Beim Verketten von Zeichenfolgen mithilfe der [& Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md), alle Konvertierungen, die Zeichenfolgen werden als erweiternde sein. Damit diese Umwandlungen keine implizite einschränkende Konvertierungsfehler, auch wenn generieren `Option Strict` ist.  
  
 Wenn Sie eine Methode, die ein Argument, das einen anderen Datentyp als der entsprechende Parameter verfügt aufrufen, verursacht eine einschränkende Konvertierung einen Kompilierungsfehler, wenn `Option Strict` ist. Sie können die Kompilierungsfehler vermeiden, mit einer erweiternden Konvertierung oder eine explizite Konvertierung.  
  
 Implizite einschränkende Konvertierungsfehler unterdrückt werden, während der Kompilierung für Konvertierungen von den Elementen in einem `For Each…Next` -Auflistung, um die Schleifensteuerungsvariable. Dies tritt auf, selbst wenn `Option Strict` ist. Weitere Informationen finden Sie im Bereich "Einschränkende Konvertierungen" [für jede... Nächste Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
## <a name="late-binding-errors"></a>Fehler für späte Bindung  
 Ein Objekt wird spät gebunden, wenn er zugewiesen wurde, auf eine Eigenschaft oder Methode einer Variablen, die deklariert wird, vom Typ `Object`. Weitere Informationen finden Sie unter [Early und späte Bindung](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md).  
  
## <a name="implicit-object-type-errors"></a>Objekt implizite Typfehler  
 Implizite Objekt Typ-Fehler auftreten, wenn möglich ein geeigneten Typ hergeleitet für eine deklarierte Variable, also eine Art von `Object` abgeleitet wird. In erster Linie der Fall, wenn Sie eine `Dim` -Anweisung zum Deklarieren einer Variablen ohne Verwendung einer `As` -Klausel, und `Option Infer` ist deaktiviert. Weitere Informationen finden Sie unter [Option Infer-Anweisung](../../../visual-basic/language-reference/statements/option-infer-statement.md) und [Visual Basic Language Specification](../../../visual-basic/reference/language-specification.md).  
  
 Für Methodenparameter die `As` Klausel ist optional, wenn `Option Strict` deaktiviert ist. Jedoch, wenn ein Parameter verwendet eine `As` -Klausel, alle verwenden dieses. Wenn `Option Strict` ist, werden die `As` -Klausel ist für jede Parameterdefinition erforderlich.  
  
 Wenn Sie eine Variable, ohne deklarieren eine `As` -Klausel und geben sie `Nothing`, die Variable besitzt einen Typ von `Object`. Keine Kompilierungsfehler tritt auf, in diesem Fall bei `Option Strict` eingeschaltet und `Option Infer` ist. Ein Beispiel hierfür ist `Dim something = Nothing`.  
  
### <a name="default-data-types-and-values"></a>Standarddatentypen und -werte  
 Die folgende Tabelle beschreibt die Ergebnisse der verschiedenen Kombinationen der Angabe von Datentyp und Initialisierung in einer [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
|Datentyp angegeben?|Initialisierung angegeben?|Beispiel|Ergebnis|  
|---|---|---|---|  
|Nein|Nein|`Dim qty`|Wenn `Option Strict` deaktiviert ist (Standard), ist die Variable auf `Nothing` eingestellt.<br /><br /> Wenn `Option Strict` aktiviert ist, tritt ein Kompilierungsfehler auf.|  
|Nein|Ja|`Dim qty = 5`|Wenn `Option Infer` aktiviert ist (Standard), übernimmt die Variable den Datentyp des Initialisierers an. Finden Sie unter [lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Wenn `Option Infer` und `Option Strict` ausgeschaltet sind, nimmt die Variable den Datentyp des `Object` an.<br /><br /> Wenn `Option Infer` deaktiviert ist und `Option Strict` aktiviert ist, tritt ein Kompilierungsfehler auf.|  
|Ja|Nein|`Dim qty As Integer`|Die Variable wird auf den Standardwert für den Datentyp initialisiert. Weitere Informationen finden Sie unter [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md).|  
|Ja|Ja|`Dim qty  As Integer = 5`|Wenn der Datentyp der Initialisierung nicht in den angegebenen Datentyp konvertiert werden kann, tritt ein Fehler während der Kompilierung auf.|  
  
## <a name="when-an-option-strict-statement-is-not-present"></a>Wenn eine Option Strict-Anweisung nicht vorhanden ist  
 Enthält der Quellcode kein `Option Strict` -Anweisung, die **Option strict** auf der [Seite kompilieren, Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) verwendet wird. Die **Seite Kompilieren** Einstellungen, die zusätzliche Kontrolle über die Vorschriften zu ermöglichen, die einen Fehler generiert hat.  
  
 Wenn Sie den Befehlszeilencompiler verwenden, können Sie die [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) (Compileroption), geben Sie eine Einstellung für `Option Strict`.  
  
### <a name="to-set-option-strict-in-the-ide"></a>So legen Sie Option Strict in der IDE fest  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
1.  In **Projektmappen-Explorer**, wählen Sie ein Projekt. Auf der **Projekt** Menü klicken Sie auf **Eigenschaften**. Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Auf der **Kompilieren** legen Sie den Wert der **Option Strict** Feld.  
  
###  <a name="conditions"></a>Warnungskonfigurationen in der IDE festlegen  
 Bei Verwendung der [Seite kompilieren, Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) statt einer `Option Strict` -Anweisung müssen Sie zusätzliche Kontrolle über den Umständen, die zu Fehlern führen. Die **Warnungskonfigurationen** Teil der **Seite Kompilieren** Einstellungen, die drei Bedingungen entsprechen, der einen Kompilierungsfehler verursacht, hat beim `Option Strict` ist. Im folgenden sind diese Einstellungen:  
  
-   **Implizite Konvertierung**  
  
-   **Späte Bindung; Aufruf könnte zur Laufzeit fehlschlagen.**  
  
-   **Impliziter Typ; Objekt wird angenommen.**  
  
 Wenn Sie die Option **Option Strict** zu **auf**, auf alle drei dieser Warnung Konfiguration Einstellungen festgelegt sind **Fehler**. Beim Festlegen **Option Strict** auf **aus**, alle drei Einstellungen festgelegt **keine**.  
  
 Sie können jede Warnungskonfiguration auf einzeln ändern **keine**, **Warnung**, oder **Fehler**. Wenn alle drei Einstellungen für die Warnung-Konfiguration, um festgelegt werden **Fehler**, `On` wird in der `Option strict` ein. Wenn alle drei, um festgelegt werden **keine**, `Off` in diesem Feld angezeigt. Für eine beliebige Kombination dieser Einstellungen **(Benutzerdefiniert)** angezeigt wird.  
  
### <a name="to-set-the-option-strict-default-setting-for-new-projects"></a>Die Einstellung der Option Strict für neue Projekte festlegen  
 Wenn Sie ein Projekt erstellen die **Option Strict** auf der **Kompilieren** Registerkarte auf festgelegt ist die **Option Strict** festlegen in der **Optionen** im Dialogfeld.  
  
 Festzulegende `Option Strict` in diesem Dialogfeld auf die **Tools** Menü klicken Sie auf **Optionen**. In der **Optionen** Dialogfeld erweitern Sie **Projekte und Projektmappen**, und klicken Sie dann auf **VB-Standard**. Die ursprüngliche Standardeinstellung in **VB-Standard** ist `Off`.  
  
### <a name="to-set-option-strict-on-the-command-line"></a>Option Strict in der Befehlszeile festlegen  
 Enthalten die [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) -Compileroption in der **Vbc** Befehl.  
  
## <a name="example"></a>Beispiel  
 Die folgenden Beispiele veranschaulichen Kompilierungsfehler verursacht durch implizite Konvertierungen, die nur eine annähernde Entsprechung sind. Diese Kategorie von Fehlern entspricht der **implizite Konvertierung** Bedingung auf den **Seite Kompilieren**.  
  
 [!code-vb[VbVbalrStatements&#161;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_1.vb)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt einen Kompilierungsfehler verursacht durch späte Bindung. Diese Kategorie von Fehlern entspricht der **späte Bindung; Aufruf könnte zur Laufzeit nicht ausgeführt** Bedingung auf den **Seite Kompilieren**.  
  
 [!code-vb[VbVbalrStatements&#162;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_2.vb)]  
  
## <a name="example"></a>Beispiel  
 Die folgenden Beispiele veranschaulichen von Variablen, die mit einem impliziten Typ deklariert sind verursachten `Object`. Diese Kategorie von Fehlern entspricht der **impliziter Typ;** Bedingung auf den **Seite Kompilieren**.  
  
 [!code-vb[VbVbalrStatements&#163;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_3.vb)]  
  
 [!code-vb[VbVbalrStatements&#164;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_4.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Erweiternde und eingrenzende Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Implizite und explizite Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Seite „Kompilieren“, Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic)   
 [Option Explicit-Anweisung](../../../visual-basic/language-reference/statements/option-explicit-statement.md)   
 [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Gewusst wie: Zugreifen auf Member eines Objekts](../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)   
 [Eingebettete Ausdrücke in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)   
 [Gelockerte Delegatenkonvertierung](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)   
 [Späte Bindung in Office-Projektmappen](https://msdn.microsoft.com/library/3xxe951d)   
 [/ optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)   
 [VB-Standard, Projekte, Dialogfeld „Optionen“](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
