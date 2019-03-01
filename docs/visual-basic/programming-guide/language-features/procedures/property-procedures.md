---
title: Eigenschaftenprozeduren (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Set statement [Visual Basic], Property procedures
- Visual Basic code, procedures
- return values [Visual Basic], Property procedures
- syntax [Visual Basic], Property procedures
- procedures [Visual Basic], property
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], custom
- property procedures
- Get statement [Visual Basic], property procedures
ms.assetid: 46a98379-e1a2-45dd-a48c-b51213f5ab07
ms.openlocfilehash: d0a0003409f0abc277d92f4e68981d9ffd901a41
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56971532"
---
# <a name="property-procedures-visual-basic"></a>Eigenschaftenprozeduren (Visual Basic)
Eine Eigenschaftenprozedur ist eine Reihe von Visual Basic-Anweisungen, die eine benutzerdefinierte Eigenschaft in einem Modul, Klasse oder Struktur zu ändern. -Eigenschaftenprozeduren werden, auch bekannt als *Eigenschaftenaccessoren*.  
  
 Visual Basic bietet für die folgenden Verfahren für die Eigenschaft:  
  
-   Ein `Get` Prozedur gibt den Wert einer Eigenschaft zurück. Wird aufgerufen, wenn Sie die Eigenschaft in einem Ausdruck zugreifen.  
  
-   Ein `Set` Prozedur setzt eine Eigenschaft auf einen Wert fest. Wird aufgerufen, wenn Sie die Eigenschaft einen Wert zuweisen.  
  
 Sie Eigenschaftenprozeduren in der Regel paarweise mit definieren die `Get` und `Set` -Anweisungen, aber Sie können auch einzeln definiert, wenn die Eigenschaft schreibgeschützt ist ([Get Statement](../../../../visual-basic/language-reference/statements/get-statement.md)) oder nur Schreibzugriff ([festlegen Anweisung](../../../../visual-basic/language-reference/statements/set-statement.md)).  
  
 Können Sie weglassen der `Get` und `Set` Verfahren, wenn Sie eine automatisch implementierte Eigenschaft zu verwenden. Weitere Informationen finden Sie unter [Automatisch implementierte Eigenschaften](./auto-implemented-properties.md).  
  
 Sie können Eigenschaften in Klassen, Strukturen und Module definieren. Eigenschaften sind `Public` standardmäßig die bedeutet, dass Sie von überall aus aufrufen können in Ihrer Anwendung, die Container der Eigenschaft zugreifen können.  
  
 Einen Vergleich von Eigenschaften und Variablen finden Sie unter [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](./differences-between-properties-and-variables.md).  
  
## <a name="declaration-syntax"></a>Deklarationssyntax  
 Eine Eigenschaft selbst wird durch einen Codeblock eingefasst definiert die [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) und `End Property` Anweisung. Innerhalb dieses Blocks an, die für jede Eigenschaftenprozedur als interner Block einer deklarationsanweisung angegeben eingefasst wird angezeigt (`Get` oder `Set`) und den entsprechenden `End` Deklaration.  
  
 Die Syntax zum Deklarieren einer Eigenschaft und die zugehörigen Prozeduren ist wie folgt aus:  
  
```  
[Default] [Modifiers] Property PropertyName[(ParameterList)] [As DataType]  
    [AccessLevel] Get  
        ' Statements of the Get procedure.  
        ' The following statement returns an expression as the property's value.  
        Return Expression  
    End Get  
    [AccessLevel] Set[(ByVal NewValue As DataType)]  
        ' Statements of the Set procedure.  
        ' The following statement assigns newvalue as the property's value.  
        LValue = NewValue  
    End Set  
End Property  
- or -  
[Default] [Modifiers] Property PropertyName [(ParameterList)] [As DataType]  
```  
  
 Die `Modifiers` festlegbaren Zugriffsebene und Informationen zu überladen, überschreiben, freigeben und shadowing, sowie, ob die Eigenschaft schreibgeschützt oder lesegeschützt ist. Die `AccessLevel` auf die `Get` oder `Set` Prozedur kann jeder Ebene, die restriktiver ist als die Zugriffsebene für die Eigenschaft selbst angegeben sein. Weitere Informationen finden Sie unter [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md).  
  
### <a name="data-type"></a>Datentyp  
 Der Datentyp einer Eigenschaft und der Dienstprinzipal Zugriff auf werden definiert, der `Property` -Anweisung nicht in der Eigenschaftenprozeduren. Eine Eigenschaft kann nur einen Datentyp verfügen. Angenommen, Sie eine Eigenschaft zum Speichern von definieren können kein `Decimal` Wert aber Abrufen einer `Double` Wert.  
  
### <a name="access-level"></a>Zugriffsebene  
 Allerdings können Sie definieren einen Dienstprinzipal Zugriff auf für eine Eigenschaft und die Zugriffsebene in einer der Eigenschaftenprozeduren weiter einzuschränken. Beispielsweise können Sie definieren eine `Public` Eigenschaft, und klicken Sie dann definieren Sie eine `Private Set` Verfahren. Die `Get` Prozedur bleibt `Public`. Sie können die Zugriffsebene in eine der Prozeduren für eine Eigenschaft ändern können, und Sie nur es restriktiver ist als die Zugriffsebene des dienstprinzipals. Weitere Informationen finden Sie unter [Vorgehensweise: Deklarieren Sie eine Eigenschaft mit gemischten Zugriffsebenen](./how-to-declare-a-property-with-mixed-access-levels.md).  
  
## <a name="parameter-declaration"></a>Parameterdeklaration  
 Jeder Parameter deklariert die gleiche Weise für [Sub-Prozeduren](./sub-procedures.md), außer dass muss der Übergabemechanismus sein `ByVal`.  
  
 Die Syntax für jeden Parameter in der Liste der Parameter lautet wie folgt aus:  
  
 `[Optional] ByVal [ParamArray] parametername As datatype`  
  
 Wenn der Parameter optional ist, müssen Sie auch einen Standardwert als Teil der Deklaration angeben. Die Syntax zum Angeben der Standardwert ist wie folgt aus:  
  
 `Optional ByVal parametername As datatype = defaultvalue`  
  
## <a name="property-value"></a>Eigenschaftswert  
 In einem `Get` Verfahren der Rückgabewert dem aufrufenden Ausdruck als Wert der Eigenschaft angegeben wird.  
  
 In einem `Set` Verfahren wird der neue Eigenschaftswert auf den Parameter übergeben die `Set` Anweisung. Wenn Sie einen Parameter explizit deklarieren, müssen Sie es mit dem gleichen Datentyp wie die Eigenschaft deklarieren. Wenn Sie keinen Parameter deklarieren, verwendet der Compiler die impliziten Parameter `Value` zur Darstellung des neuen Wert der Eigenschaft zugewiesen werden.  
  
## <a name="calling-syntax"></a>Die Syntax aufrufen  
 Sie aufrufen eine Eigenschaftenprozedur implizit durch einen Verweis auf die Eigenschaft. Sie verwenden den Namen der Eigenschaft, die gleiche Weise, die Sie verwenden den Namen einer Variablen mit dem Unterschied, dass Sie Werte für alle Argumente angeben müssen, die nicht optional sind, und müssen Sie die Argumentliste in Klammern einschließen. Wenn keine Argumente angegeben werden, können Sie die Klammern optional weglassen.  
  
 Die Syntax für einen impliziten Aufruf einer `Set` Verfahren lautet wie folgt:  
  
 `propertyname[(argumentlist)] = expression`  
  
 Die Syntax für einen impliziten Aufruf einer `Get` Verfahren lautet wie folgt:  
  
 `lvalue = propertyname[(argumentlist)]`  
  
 `Do While (propertyname[(argumentlist)] > expression)`  
  
### <a name="illustration-of-declaration-and-call"></a>Abbildung der Deklaration und Aufruf  
 Die folgende Eigenschaft speichert einen vollständigen Namen als zwei enthaltenen Namen, der Vorname und Nachname. Wenn der aufrufende Code liest `fullName`, `Get` Prozedur kombiniert die beiden zugehörigen Namen und gibt den vollständigen Namen zurück. Wenn der aufrufende Code einen neuen vollständigen Namen, weist der `Set` Prozedur versucht, die in zwei enthaltenen Namen aufzulösen. Wenn sie ein Leerzeichen nicht gefunden wird, es alle als den ersten Namen gespeichert.  
  
 [!code-vb[VbVbcnProcedures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#8)]  
  
 Das folgende Beispiel zeigt die typischen Aufrufe an die Eigenschaftenprozeduren von `fullName`.  
  
 [!code-vb[VbVbcnProcedures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>Siehe auch
- [Verfahren](./index.md)
- [Function-Prozeduren](./function-procedures.md)
- [Operatorprozeduren](./operator-procedures.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](./differences-between-properties-and-variables.md)
- [Vorgehensweise: Erstellen Sie eine Eigenschaft](./how-to-create-a-property.md)
- [Vorgehensweise: Aufrufen einer Eigenschaftenprozedur](./how-to-call-a-property-procedure.md)
- [Vorgehensweise: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Vorgehensweise: Das Ablegen eines Werts in einer Eigenschaft](./how-to-put-a-value-in-a-property.md)
- [Vorgehensweise: Abrufen eines Werts aus einer Eigenschaft](./how-to-get-a-value-from-a-property.md)
