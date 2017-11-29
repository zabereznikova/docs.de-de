---
title: Eigenschaftenprozeduren (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cbdf49d5c3eb5ef71b25a060d62f55f19098f445
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="property-procedures-visual-basic"></a>Eigenschaftenprozeduren (Visual Basic)
Eine Eigenschaftenprozedur besteht aus einer Reihe von [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Anweisungen, die eine benutzerdefinierte Eigenschaft für ein Modul, eine Klasse oder eine Struktur zu bearbeiten. -Eigenschaftenprozeduren werden auch bekannt als *Eigenschaftenaccessoren*.  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]bietet die folgenden Eigenschaftenprozeduren:  
  
-   Ein `Get` Prozedur gibt den Wert einer Eigenschaft zurück. Sie wird aufgerufen, wenn Sie Zugriff auf die Eigenschaft in einem Ausdruck.  
  
-   Ein `Set` Prozedur wird eine Eigenschaft auf einen Wert, z. B. einen Objektverweis. Sie wird aufgerufen, wenn Sie die Eigenschaft einen Wert zuweisen.  
  
 Sie definieren Eigenschaftenprozeduren in der Regel paarweise mit der `Get` und `Set` -Anweisungen, aber Sie können auch einzeln definiert, wenn die Eigenschaft schreibgeschützt ist ([Get-Anweisung](../../../../visual-basic/language-reference/statements/get-statement.md)) oder lesegeschützt ([festlegen Anweisung](../../../../visual-basic/language-reference/statements/set-statement.md)).  
  
 Sie lassen die `Get` und `Set` Verfahren, wenn Sie eine automatisch implementierte Eigenschaft verwenden. Weitere Informationen finden Sie unter [Automatisch implementierte Eigenschaften](./auto-implemented-properties.md).  
  
 Sie können Eigenschaften in Klassen, Strukturen und Module definieren. Eigenschaften sind `Public` standardmäßig, d. h. können von überall aus Anrufen in Ihrer Anwendung, die die Eigenschaft Container zugreifen können.  
  
 Einen Vergleich von Eigenschaften und Variablen, finden Sie unter [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](./differences-between-properties-and-variables.md).  
  
## <a name="declaration-syntax"></a>Deklarationssyntax  
 Eine Eigenschaft selbst wird durch einen Codeblock eingefasst definiert die [Property-Anweisung](../../../../visual-basic/language-reference/statements/property-statement.md) und die `End Property` Anweisung. Innerhalb dieses Blocks erscheint jede-Eigenschaftenprozedur als interner Block, die in einer deklarationsanweisung eingeschlossen (`Get` oder `Set`) und die entsprechenden `End` Deklaration.  
  
 Die Syntax zum Deklarieren einer Eigenschaft und die zugehörigen Prozeduren lautet wie folgt:  
  
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
  
 Die `Modifiers` festlegbaren Zugriffsebene und Informationen zum Überladen, überschreiben, freigeben und shadowing, sowie, ob die Eigenschaft schreibgeschützt oder lesegeschützt ist. Die `AccessLevel` auf die `Get` oder `Set` Prozedur kann auf jeder Ebene, die restriktiver ist als die Zugriffsebene für die Eigenschaft selbst angegeben ist. Weitere Informationen finden Sie unter [Property-Anweisung](../../../../visual-basic/language-reference/statements/property-statement.md).  
  
### <a name="data-type"></a>Datentyp  
 Datentyp für eine Eigenschaft und die Zugriffsebene für Dienstprinzipalname werden definiert, der `Property` -Anweisung nicht in den Eigenschaftenprozeduren. Eine Eigenschaft kann nur einen Datentyp aufweisen. Sie können nicht angenommen, eine Eigenschaft zum Speichern von definieren eine `Decimal` Wert aber abrufen eine `Double` Wert.  
  
### <a name="access-level"></a>Zugriffsebene  
 Allerdings können Sie definieren eine principal Zugriffsebene für eine Eigenschaft und die Zugriffsebene in einer der Eigenschaftenprozeduren weiter einschränken. Beispielsweise können Sie definieren eine `Public` Eigenschaft definieren und anschließend eine `Private Set` Prozedur. Die `Get` Prozedur bleibt `Public`. Sie können die Zugriffsebene in nur einem der Verfahren für eine Eigenschaft ändern können, und Sie nur diese restriktiver als die Zugriffsebene für Dienstprinzipalname. Weitere Informationen finden Sie unter [wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen](./how-to-declare-a-property-with-mixed-access-levels.md).  
  
## <a name="parameter-declaration"></a>Parameterdeklaration  
 Deklarieren Sie jeden Parameter genauso wie Sie für [Sub-Prozeduren](./sub-procedures.md), außer dass der Übergabemechanismus Transportservers `ByVal`.  
  
 Die Syntax für jeden Parameter in der Parameterliste lautet wie folgt:  
  
 `[Optional] ByVal [ParamArray] parametername As datatype`  
  
 Wenn der Parameter optional ist, müssen Sie auch einen Standardwert als Teil der Deklaration angeben. Die Syntax zum Angeben der Standardwert lautet wie folgt:  
  
 `Optional ByVal parametername As datatype = defaultvalue`  
  
## <a name="property-value"></a>Eigenschaftswert  
 In einer `Get` Prozedur, den Rückgabewert mit dem aufrufenden Ausdruck wie den Wert der Eigenschaft angegeben wird.  
  
 In einem `Set` Prozedur, der neue Eigenschaftswert wird auf den Parameter übergeben der `Set` Anweisung. Wenn Sie einen Parameter explizit deklarieren, müssen Sie es mit dem gleichen Datentyp wie die Eigenschaft deklarieren. Wenn Sie kein Parameter deklariert, verwendet der Compiler impliziten Parameter `Value` zur Darstellung der neue Wert der Eigenschaft zugewiesen werden soll.  
  
## <a name="calling-syntax"></a>Aufrufen der Syntax  
 Sie aufrufen eine Eigenschaftenprozedur implizit durch einen Verweis auf die Eigenschaft. Sie verwenden den Namen der Eigenschaft, die gleiche Weise wie den Namen einer Variablen mit dem Unterschied, dass Sie Werte für alle Argumente angeben müssen, die nicht optional sind, und müssen Sie die Argumentliste in Klammern einschließen. Wenn keine Argumente übergeben werden, können Sie die Klammern optional weglassen.  
  
 Die Syntax für einen impliziten Aufruf einer `Set` Prozedur lautet wie folgt:  
  
 `propertyname[(argumentlist)] = expression`  
  
 Die Syntax für einen impliziten Aufruf einer `Get` Prozedur lautet wie folgt:  
  
 `lvalue = propertyname[(argumentlist)]`  
  
 `Do While (propertyname[(argumentlist)] > expression)`  
  
### <a name="illustration-of-declaration-and-call"></a>Abbildung der Deklaration und Aufruf  
 Die folgende Eigenschaft speichert einen vollständigen Namen als zwei konstituierende Namen, den Vornamen und den Nachnamen an. Wenn der aufrufende Code liest `fullName`die `Get` Prozedur kombiniert die beiden konstituierenden Namen und gibt den vollständigen Namen zurück. Wenn der aufrufende Code einen neuen vollständigen Name weist das `Set` Prozedur versucht, die sie in zwei konstituierende Namen aufzulösen. Wenn sie ein Leerzeichen nicht gefunden wird, wird er alle als den Vornamen gespeichert.  
  
 [!code-vb[VbVbcnProcedures#8](./codesnippet/VisualBasic/property-procedures_1.vb)]  
  
 Das folgende Beispiel zeigt typische Aufrufe der Eigenschaftenprozeduren `fullName`.  
  
 [!code-vb[VbVbcnProcedures#9](./codesnippet/VisualBasic/property-procedures_2.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)  
 [Function-Prozeduren](./function-procedures.md)  
 [Operatorprozeduren](./operator-procedures.md)  
 [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)  
 [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](./differences-between-properties-and-variables.md)  
 [Gewusst wie: Erstellen einer Eigenschaft](./how-to-create-a-property.md)  
 [Gewusst wie: Aufrufen einer Eigenschaftenprozedur](./how-to-call-a-property-procedure.md)  
 [Vorgehensweise: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic](./how-to-declare-and-call-a-default-property.md)  
 [Gewusst wie: Ablegen eines Werts in einer Eigenschaft](./how-to-put-a-value-in-a-property.md)  
 [Gewusst wie: Abrufen eines Werts aus einer Eigenschaft](./how-to-get-a-value-from-a-property.md)
