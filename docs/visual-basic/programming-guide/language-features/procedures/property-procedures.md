---
title: Eigenschaftenprozeduren (Visual Basic) | Microsoft-Dokumentation
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
- Set statement, Property procedures
- Visual Basic code, procedures
- return values, Property procedures
- syntax, Property procedures
- procedures, property
- Visual Basic code, properties
- procedures, calling
- properties [Visual Basic], custom
- property procedures
- Get statement, property procedures
ms.assetid: 46a98379-e1a2-45dd-a48c-b51213f5ab07
caps.latest.revision: 22
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f21d4c7d9bd8f14bbe7284bc08399e7ba6b466c3
ms.lasthandoff: 03/13/2017

---
# <a name="property-procedures-visual-basic"></a>Eigenschaftenprozeduren (Visual Basic)
Eine Eigenschaftenprozedur ist eine Reihe von [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] -Anweisungen, die eine benutzerdefinierte Eigenschaft für ein Modul, Klasse oder Struktur zu bearbeiten. Eigenschaftenprozeduren sind auch bekannt als *Eigenschaftenaccessoren*.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]enthält die folgenden Eigenschaftenprozeduren:  
  
-   Ein `Get` Prozedur gibt den Wert einer Eigenschaft zurück. Es wird aufgerufen, wenn Sie die Eigenschaft in einem Ausdruck zugreifen.  
  
-   Ein `Set` -Prozedur legt eine Eigenschaft auf einen Wert fest. Sie wird aufgerufen, wenn Sie die Eigenschaft einen Wert zuweisen.  
  
 Sie definieren Property-Prozeduren in der Regel paarweise mit den `Get` und `Set` -Anweisungen, sondern Sie können auch einzeln definiert, wenn die Eigenschaft schreibgeschützt ist ([Get-Anweisung](../../../../visual-basic/language-reference/statements/get-statement.md)) oder lesegeschützt ([Set-Anweisung](../../../../visual-basic/language-reference/statements/set-statement.md)).  
  
 Sie lassen die `Get` und `Set` Verfahren, wenn Sie eine automatisch implementierte Eigenschaft verwenden. Weitere Informationen finden Sie unter [automatisch implementierte Eigenschaften](./auto-implemented-properties.md).  
  
 Sie können Eigenschaften in Klassen, Strukturen und Module definieren. Eigenschaften sind `Public` standardmäßig, d. h. Sie können sie von überall aus aufrufen in der Anwendung, die Container der Eigenschaft zugreifen können.  
  
 Einen Vergleich von Eigenschaften und Variablen finden Sie unter [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](./differences-between-properties-and-variables.md).  
  
## <a name="declaration-syntax"></a>Deklarationssyntax  
 Eine Eigenschaft selbst wird durch einen Codeblock in definiert die [Property-Anweisung](../../../../visual-basic/language-reference/statements/property-statement.md) und der `End Property` Anweisung. In diesem Block jede Eigenschaftenprozedur angezeigt wird, als interne eingeschlossen, die innerhalb einer deklarationsanweisung (`Get` oder `Set`) und der entsprechenden `End` Deklaration.  
  
 Die Syntax zum Deklarieren einer Eigenschaft und ihrer Prozeduren lautet wie folgt:  
  
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
  
 Die `Modifiers` können geben Zugriffsebene und Informationen zum Überladen, überschreiben, freigeben und shadowing, sowie, ob die Eigenschaft schreibgeschützt oder lesegeschützt ist. Die `AccessLevel` auf der `Get` oder `Set` Prozedur kann auf jeder Ebene, die restriktiver als die Zugriffsebene für die Eigenschaft selbst angegeben ist. Weitere Informationen finden Sie unter [Property-Anweisung](../../../../visual-basic/language-reference/statements/property-statement.md).  
  
### <a name="data-type"></a>Datentyp  
 Der Datentyp einer Eigenschaft und principal Zugriffsebene werden definiert, der `Property` -Anweisung nicht in den Eigenschaftenprozeduren. Eine Eigenschaft kann nur einen Datentyp aufweisen. Angenommen, Sie eine Eigenschaft zum Speichern von definieren können eine `Decimal` Wert aber Abrufen einer `Double` Wert.  
  
### <a name="access-level"></a>Zugriffsebene  
 Sie können eine principal Zugriffsebene für eine Eigenschaft definieren und die Zugriffsebene in einer der Eigenschaftenprozeduren weiter einschränken. Sie können z. B. definieren eine `Public` Eigenschaft und definieren Sie dann ein `Private Set` Verfahren. Die `Get` Prozedur bleibt `Public`. Sie können die Zugriffsebene in nur einer der Prozeduren einer Eigenschaft ändern können, und Sie nur es restriktiver ist als der Prinzipal Zugriff auf. Weitere Informationen finden Sie unter [Gewusst wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen](./how-to-declare-a-property-with-mixed-access-levels.md).  
  
## <a name="parameter-declaration"></a>Parameterdeklaration  
 Sie deklarieren jeden Parameter auf die gleiche Weise bei [Sub-Prozeduren](./sub-procedures.md), außer dass die Methode übergeben werden muss `ByVal`.  
  
 Die Syntax für jeden Parameter in der Parameterliste lautet wie folgt:  
  
 `[Optional] ByVal [ParamArray] parametername As datatype`  
  
 Wenn der Parameter optional ist, müssen Sie auch einen Standardwert als Teil der Deklaration angeben. Die Syntax zum Angeben der Standardwert lautet wie folgt:  
  
 `Optional ByVal parametername As datatype = defaultvalue`  
  
## <a name="property-value"></a>Eigenschaftswert  
 In einer `Get` Prozedur, der Rückgabewert für den aufrufenden Ausdruck als Wert der Eigenschaft bereitgestellt wird.  
  
 In einem `Set` Verfahren wird der neue Wert der Eigenschaft an den Parameter des übergeben der `Set` Anweisung. Wenn Sie einen Parameter explizit deklarieren, müssen Sie es mit dem gleichen Datentyp wie die Eigenschaft deklarieren. Wenn Sie keine Parameter deklariert, verwendet der Compiler die impliziten Parameter `Value` zur Darstellung des neuen Wert der Eigenschaft zugewiesen werden.  
  
## <a name="calling-syntax"></a>Aufrufen der Syntax  
 Sie aufrufen eine Eigenschaftenprozedur implizit durch einen Verweis auf die Eigenschaft. Sie verwenden den Namen der Eigenschaft, die gleiche Weise wie der Name einer Variablen mit dem Unterschied, dass Sie Werte für alle Argumente angeben müssen, die nicht optional sind, und Sie müssen die Argumentliste in Klammern einschließen. Wenn keine Argumente angegeben sind, können Sie die Klammern auch weglassen.  
  
 Die Syntax für einen impliziten Aufruf einer `Set` Prozedur lautet wie folgt:  
  
 `propertyname[(argumentlist)] = expression`  
  
 Die Syntax für einen impliziten Aufruf einer `Get` Prozedur lautet wie folgt:  
  
 `lvalue = propertyname[(argumentlist)]`  
  
 `Do While (propertyname[(argumentlist)] > expression)`  
  
### <a name="illustration-of-declaration-and-call"></a>Darstellung von Deklaration und Aufruf  
 Die folgende Eigenschaft speichert einen vollständigen Namen als zwei konstituierende Namen, den Vornamen und den Nachnamen ein. Wenn der aufrufende Code liest `fullName`der `Get` kombiniert die beiden konstituierenden Namen und gibt den vollständigen Namen. Wenn der aufrufende Code einen neuen vollständigen Namen zuweist der `Set` Prozedur versucht, den Namen in zwei konstituierende Namen aufzulösen. Wenn ein Leerzeichen nicht findet, gespeichert als der erste Name.  
  
 [!code-vb[VbVbcnProcedures&#8;](./codesnippet/VisualBasic/property-procedures_1.vb)]  
  
 Das folgende Beispiel zeigt die normale Aufrufe an die Property-Prozeduren des `fullName`.  
  
 [!code-vb[VbVbcnProcedures&#9;](./codesnippet/VisualBasic/property-procedures_2.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)   
 [Function-Prozeduren](./function-procedures.md)   
 [Operatorprozeduren](./operator-procedures.md)   
 [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md)   
 [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](./differences-between-properties-and-variables.md)   
 [Gewusst wie: Erstellen einer Eigenschaft](./how-to-create-a-property.md)   
 [Gewusst wie: Aufrufen einer Eigenschaftenprozedur](./how-to-call-a-property-procedure.md)   
 [Gewusst wie: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic](./how-to-declare-and-call-a-default-property.md)   
 [Gewusst wie: Ablegen eines Werts in einer Eigenschaft](./how-to-put-a-value-in-a-property.md)   
 [Gewusst wie: Abrufen eines Werts aus einer Eigenschaft](./how-to-get-a-value-from-a-property.md)
