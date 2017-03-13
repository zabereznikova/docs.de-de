---
title: "Option Strict Statement | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Strict"
  - "vb.OptionStrict"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Strict keyword"
  - "Option Strict statement"
  - "conversions, implicit"
  - "late binding"
  - "implicit conversions"
ms.assetid: 5883e0c1-a920-4274-8e46-b0ff047eaee5
caps.latest.revision: 49
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 49
---
# Option Strict Statement
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Schränkt die impliziten Datentypkonvertierungen auf ausschließlich Erweiterungskonvertierungen ein, lässt eine späte Bindung nicht zu und lässt keine implizite Typisierung zu, die einen `Object`\-Typ ergibt.  
  
## Syntax  
  
```  
Option Strict { On | Off }  
```  
  
## Teile  
  
|||  
|-|-|  
|Begriff|Definition|  
|`On`|Optional.  Aktiviert die `Option Strict`\-Überprüfung.|  
|`Off`|Optional.  Deaktiviert die `Option Strict`\-Überprüfung.|  
  
## Hinweise  
 Wenn `Option Strict On` oder `Option Strict` in einer Datei angezeigt wird, verursachen die folgenden Bedingungen einen Kompilierungsfehler:  
  
-   Implizite Einschränkungskonvertierungen  
  
-   Spätes Binden  
  
-   Implizite Typisierung, die zu einem `Object`\-Typ führt  
  
> [!NOTE]
>  In den Warnungskonfigurationen, die Sie unter [Seite "Kompilieren", Projekt\-Designer \(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic) festlegen können, gibt es drei Einstellungen, die den drei Bedingungen entsprechen, die einen Kompilierungsfehler verursachen.  Informationen zum Verwenden dieser Einstellungen finden Sie unter [So legen Sie Warnungskonfigurationen in der IDE fest](../../../visual-basic/language-reference/statements/option-strict-statement.md#conditions) weiter unten in diesem Thema.  
  
 Die `Option Strict Off`\-Anweisung deaktiviert Fehler\- und Warnungsüberprüfung für alle drei Bedingungen, selbst wenn die zugeordneten IDE\-Einstellungen angeben, diese Fehler oder Warnungen zu aktivieren.  Die `Option Strict On` Anweisung wechselt Fehler und Warnungen Überprüfung für alle drei Bedingungen ein, auch wenn die zugeordneten IDE\-Einstellungen angeben, um diese Fehler oder Warnungen zu deaktivieren.  
  
 Bei Verwendung der `Option Strict`\-Anweisung muss diese vor allen anderen Codeanweisungen in einer Datei angeordnet sein.  
  
 Wenn Sie das `Option Strict` zu `On`, Visual Basic\-Prüfungen, ob Datentypen für alle Programmierelemente angegeben werden.  Datentypen können explizit angegeben werden oder angegeben werden, indem Sie einen lokalen Typrückschluss verwendet.  Die Angabe von Datentypen für alle Programmierelemente wird, aus folgenden Gründen empfohlen:  
  
-   Dadurch wird die IntelliSense\-Unterstützung für die von Ihnen erstellten Variablen und Parameter aktiviert.  Ihnen werden die Eigenschaften und andere Member bei der Eingabe im Code angezeigt.  
  
-   Der Compiler damit kann eine Typüberprüfung durchführen.  Mit der Typüberprüfung können Sie Anweisungen suchen, die aufgrund von Typkonvertierungsfehlern zur Laufzeit fehlschlagen können.  Außerdem werden Aufrufe von Methoden für Objekte, die diese Methoden nicht unterstützen, angegeben.  
  
-   Dies beschleunigt die Ausführung des Codes.  Ein Grund dafür ist, dass, wenn Sie keinen Datentyp für ein Programmierelement angeben, der Visual Basic\-Compiler ihr den `Object` Typ zuweist.  Kompilierter Code müsste zwischen `Object` und anderen Datentypen hin und her konvertieren, wodurch die Leistung reduziert.  
  
## Implizite Einschränkungskonvertierungsfehler  
 Implizite Einschränkungskonvertierungsfehler treten auf, wenn eine implizite Datentypkonvertierung vorliegt, die eine einschränkende Konvertierung ist.  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] kann viele Datentypen in andere Datentypen konvertieren.  Ein Datenverlust kann auftreten, wenn der Wert eines Datentyps in einen Datentyp mit geringerer Genauigkeit oder kleinerer Kapazität konvertiert wird.  Ein Laufzeitfehler tritt auf, wenn so eine einschränkende Konvertierung fehlschlägt.  `Option Strict` stellt Kompilierzeitbenachrichtigung dieser einschränkenden Konvertierungen sicher, damit sie vermieden werden können.  Weitere Informationen finden Sie unter [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) und [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
 Zu Konvertierungen, die Fehler verursachen können, gehören implizite Konvertierungen in Ausdrücken.  Weitere Informationen finden Sie unter den folgenden Themen:  
  
-   [\+ Operator](../../../visual-basic/language-reference/operators/addition-operator.md)  
  
-   [\+\= Operator](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
  
-   [\\ Operator](../../../visual-basic/language-reference/operators/integer-division-operator.md)  
  
-   [\/\= Operator](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
  
-   [Char Data Type](../../../visual-basic/language-reference/data-types/char-data-type.md)  
  
 Wenn Sie Zeichenfolgen verketten, indem Sie [& Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md) verwenden, werden alle Konvertierungen in Zeichenfolgen als erweiternd betrachtet.  Diese Konvertierungen generieren also keinen impliziten Einschränkungskonvertierungsfehler, auch wenn `Option Strict` aktiviert ist.  
  
 Wenn Sie eine Methode mit einem Argument aufrufen, bei dem sich der Datentyp vom entsprechenden Parameter unterscheidet, verursacht eine einschränkende Konvertierung einen Kompilierungsfehler, wenn `Option Strict` aktiviert ist.  Sie können den Kompilierungsfehler vermeiden, indem Sie eine Erweiterungskonvertierung oder eine explizite Konvertierung verwenden.  
  
 Implizite Einschränkungskonvertierungsfehler werden zur Kompilierzeit für Konvertierungen von den Elementen in einer `For Each…Next`\-Auflistung zur Schleifensteuerungsvariablen unterdrückt.  Dies erfolgt auch, wenn `Option Strict` aktiviert ist.  Weitere Informationen finden Sie im Abschnitt "Eingrenzende Konvertierungen" unter [For Each...Next\-Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
## Fehler für späte Bindung  
 Ein Objekt wird spät gebunden, wenn es einer Eigenschaft oder Methode einer Variablen zugeordnet wird, für die der Typ `Object` deklariert wurde.  Weitere Informationen finden Sie unter [Early and Late Binding](../../../visual-basic/programming-guide/language-features/early-late-binding/early-and-late-binding.md).  
  
## Implizite Objekttypfehler  
 Implizite Objekttypfehler treten auf, wenn ein geeigneter Typ nicht für eine deklarierte Variable abgeleitet werden kann, sodass ein Typ von `Object` abgeleitet wird.  Dies geschieht hauptsächlich, wenn Sie eine `Dim`\-Anweisung verwenden, um eine Variable zu deklarieren, ohne eine `As`\-Klausel zu verwenden, und wenn `Option Infer` deaktiviert ist.  Weitere Informationen finden Sie unter [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) und [Visual Basic Language Specification](../../../visual-basic/reference/language-specification.md).  
  
 Für Methodenparameter ist die `As`\-Klausel optional, wenn `Option Strict` deaktiviert ist.  Sobald jedoch ein Parameter eine `As`\-Klausel verwendet, muss sie von allen Parametern verwendet werden.  Wenn `Option Strict` aktiviert ist, ist die `As`\-Klausel für jede Parameterdefinition erforderlich.  
  
 Wenn Sie eine Variable ohne Verwendung einer `As`\-Klausel deklarieren und auf `Nothing` festlegen, ist die Variable vom Typ `Object`.  Es tritt in diesem kein Kompilierungsfehler auf, wenn `Option Strict` aktiviert ist und `Option Infer` aktiviert ist.  Ein Beispiel hierfür ist `Dim something = Nothing`.  
  
### Typen und Werte von Standarddaten  
 Die folgende Tabelle beschreibt die Ergebnisse der verschiedenen Kombinationen der Angabe von Datentyp und Initialisierung in einer [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
|||||  
|-|-|-|-|  
|Datentyp angegeben?|Initialisierung angegeben?|Beispiel|Ergebnis|  
|Nein|Nein|`Dim qty`|Wenn `Option Strict` deaktiviert ist \(Standard\), wird die Variable auf `Nothing` festgelegt.<br /><br /> Wenn `Option Strict` aktiviert ist, tritt ein Kompilierungsfehler auf.|  
|Nein|Ja|`Dim qty = 5`|Wenn `Option Infer` aktiviert ist \(Standard\), hat die Variable den Datentyp der Initialisierung.  Weitere Informationen finden Sie unter [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Wenn `Option Infer` aus ist und `Option Strict` aus ist, nimmt die Variable den Datentyp von `Object`.<br /><br /> Wenn `Option Infer` deaktiviert ist und `Option Strict` aktiviert ist, tritt ein Kompilierungsfehler auf.|  
|Ja|Nein|`Dim qty As Integer`|Die Variable wird auf den Standardwert für den Datentyp initialisiert.  Weitere Informationen finden Sie unter [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).|  
|Ja|Ja|`Dim qty  As Integer = 5`|Wenn der Datentyp der Initialisierung nicht in den angegebenen Datentyp konvertiert werden kann, tritt ein Kompilierungsfehler auf.|  
  
## Wenn eine Option Strict\-Anweisung nicht vorhanden ist  
 Wenn der Quellcode keine `Option Strict`\-Anweisung enthält, wird die Einstellung **Option strict** auf der [Seite "Kompilieren", Projekt\-Designer \(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic) verwendet.  **Seite Kompilieren** enthält Einstellungen, die zusätzliche Kontrolle über die Bedingungen bereitstellen, die einen Fehler generieren.  
  
 Wenn Sie den Befehlszeilencompiler verwenden, können Sie die [\/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)\-Compileroption verwenden, um eine Einstellung für `Option Strict` anzugeben.  
  
### So legen Sie Option Strict in der IDE fest  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
1.  Wählen Sie im **Projektmappen\-Explorer** ein Projekt aus.  Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  Weitere Informationen finden Sie unter [Introduction to the Project Designer](http://msdn.microsoft.com/de-de/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Legen Sie auf der Registerkarte **Kompilieren** den Wert im Feld **Option Strict** fest.  
  
###  <a name="conditions"></a> So legen Sie Warnungskonfigurationen in der IDE fest  
 Wenn Sie [Seite "Kompilieren", Projekt\-Designer \(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic) anstelle einer `Option Strict`\-Anweisung verwenden, haben Sie zusätzliche Kontrolle über die Bedingungen, die Fehler generieren.  Der Abschnitt **Warnungskonfigurationen** auf der Seite **Kompilieren** verfügt über Einstellungen, die mit den drei Bedingungen übereinstimmen, die einen Kompilierungsfehler verursachen, wenn `Option Strict` aktiviert ist.  Nachfolgend diese Einstellungen:  
  
-   **Implizite Konvertierung**  
  
-   **Späte Bindung; Aufruf könnte zur Laufzeit einen Fehler verursachen**  
  
-   **Impliziter Typ; Objekt angenommen**  
  
 Wenn Sie **Option Strict** auf **On** festlegen, werden alle drei Warnungskonfigurationseinstellungen auf **Fehler** festgelegt.  Wenn Sie **Option Strict** auf **Off** festlegen, werden alle drei Einstellungen auf **Keine** festgelegt.  
  
 Sie können jede Warnungskonfigurationseinstellung einzeln in **Keine**, **Warnung** oder **Fehler** ändern.  Wenn alle drei Warnungskonfigurationseinstellungen auf **Fehler** festgelegt sind, wird `On` im `Option strict`\-Feld angezeigt.  Wenn alle drei auf **Keine** festgelegt sind, wird `Off` in diesem Feld angezeigt.  Für jede andere Kombination dieser Einstellungen wird **\(benutzerdefiniert\)** angezeigt.  
  
### So legen Sie die Option Strict\-Standardeinstellung für neue Projekte fest  
 Wenn Sie ein Projekt erstellen, wird die Einstellung **Option Strict** auf der Registerkarte **Kompilieren** auf die Einstellung **Option Strict** im Dialogfeld **Optionen** festgelegt.  
  
 Klicken Sie im Menü **Extras** auf **Optionen**, um `Option Strict` im Dialogfeld festzulegen.  Erweitern Sie im Dialogfeld **Optionen** die Option **Projekte und Projektmappen**, und klicken Sie dann auf **VB\-Standard**.  Die ursprüngliche Standardeinstellung in **VB\-Standard** ist `Off`.  
  
### So legen Sie Option Strict in der Befehlszeile fest  
 Fügen Sie die [\/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)\-Compileroption in den **vbc**\-Befehl ein.  
  
## Beispiel  
 In den folgenden Beispielen werden Kompilierungsfehler veranschaulicht, die durch implizite Typkonvertierungen verursacht werden, die einschränkende Konvertierungen sind.  Diese Kategorie von Fehlern entspricht der Bedingung **Implizite Konvertierung** auf der Seite **Kompilieren**.  
  
 [!code-vb[VbVbalrStatements#161](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_1.vb)]  
  
## Beispiel  
 Im folgenden Beispiel wird ein Kompilierungsfehler veranschaulicht, der durch späte Bindung verursacht wurde.  Diese Kategorie von Fehlern entspricht der Bedingung **Späte Bindung; Aufruf könnte zur Laufzeit einen Fehler verursachen** auf der Seite **Kompilieren**.  
  
 [!code-vb[VbVbalrStatements#162](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_2.vb)]  
  
## Beispiel  
 Die folgenden Beispiele veranschaulichen die Fehler, die durch Variablen verursacht werden, die mit einem impliziten Typ von `Object` deklariert werden.  Diese Kategorie von Fehlern entspricht der Bedingung **Impliziter Typ; Objekt angenommen** auf der Seite **Kompilieren**.  
  
 [!code-vb[VbVbalrStatements#163](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_3.vb)]  
  
 [!code-vb[VbVbalrStatements#164](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_4.vb)]  
  
## Siehe auch  
 [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Seite "Kompilieren", Projekt\-Designer \(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic)   
 [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md)   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [How to: Access Members of an Object](../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)   
 [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)   
 [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)   
 [Späte Bindung in Office\-Lösungen](/office-dev/office-dev/late-binding-in-office-solutions)   
 [\/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)   
 [VB\-Standard, Projekte, Dialogfeld "Optionen"](/visual-studio/ide/reference/visual-basic-defaults-projects-options-dialog-box)