---
title: Parameterliste (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- parameters [Visual Basic], Visual Basic
- parameters [Visual Basic], lists
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- arguments [Visual Basic], Visual Basic
- procedures [Visual Basic], parameter lists
ms.assetid: 5d737319-0c34-4df9-a23d-188fc840becd
ms.openlocfilehash: 147a2501219db9f1f1c10f9cf1a81aa395b5ec2b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="parameter-list-visual-basic"></a>Parameterliste (Visual Basic)
Gibt die Parameter, die eine Prozedur erwartet wird, wenn sie aufgerufen wird. Mehrere Parameter werden durch Kommas getrennt. Im folgenden ist die Syntax für einen Parameter.  
  
## <a name="syntax"></a>Syntax  
  
```  
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]   
parametername[( )] [ As parametertype ] [ = defaultvalue ]  
```  
  
## <a name="parts"></a>Teile  
 `attributelist`  
 Dies ist optional. Liste der Attribute, die für diesen Parameter gelten. Setzen Sie die [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md) in spitzen Klammern ("`<`"und"`>`").  
  
 `Optional`  
 Dies ist optional. Gibt an, dass dieser Parameter nicht erforderlich ist, wenn die Prozedur aufgerufen wird.  
  
 `ByVal`  
 Dies ist optional. Gibt an, dass die Prozedur kann nicht ersetzen oder erneutes Zuweisen der Variable-Element dem entsprechenden Argument im aufrufenden Code zugrunde liegt.  
  
 `ByRef`  
 Dies ist optional. Gibt an, dass die Prozedur die zugrunde liegende Variable-Element im aufrufenden Code genauso ändern kann wie der aufrufende Code selbst.  
  
 `ParamArray`  
 Dies ist optional. Gibt an, dass der letzte Parameter in der Parameterliste ein optionales Array von Elementen des Typs angegebenen Daten. Auf diese Weise können den aufrufenden Code eine beliebige Anzahl von Argumenten an die Prozedur übergeben.  
  
 `parametername`  
 Erforderlich. Der Name der lokalen Variablen, die den Parameter darstellt.  
  
 `parametertype`  
 Erforderlich, wenn `Option Strict` ist `On`. Der Datentyp der lokalen Variablen, die den Parameter darstellt.  
  
 `defaultvalue`  
 Erforderlich für `Optional` Parameter. Jeder Konstante oder einen konstanten Ausdruck, der den Datentyp des Parameters ergibt. Wenn der Typ ist `Object`, oder eine Klasse, Schnittstelle, Array oder eine Struktur, der Standardwert kann nur `Nothing`.  
  
## <a name="remarks"></a>Hinweise  
 Parameter sind in Klammern eingeschlossen sind und durch Kommas getrennt. Ein Parameter kann mit einem beliebigen Datentyp deklariert werden. Wenn Sie keinen angeben `parametertype`, wird standardmäßig `Object`.  
  
 Wenn der aufrufende Code die Prozedur aufruft, übergibt er eine *Argument* an jeden erforderlichen Parameter. Weitere Informationen finden Sie unter [Unterschiede zwischen Parametern und Argumenten](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).  
  
 Das Argument, das der Aufrufcode an jeden Parameter übergibt ist ein Zeiger auf eine zugrunde liegende Element im aufrufenden Code. Wenn dieses Element ist *nicht variables* (eine Konstante, Literal, Enumeration oder Ausdruck), es ist nicht möglich, für jeden Code, um ihn zu ändern. Es ist ein *Variable* Element (eine deklarierte Variable, Feld, Eigenschaft, Arrayelement oder Structure-Element), können Sie der Aufrufcode ändern. Weitere Informationen finden Sie unter [Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).  
  
 Wenn ein Variable-Element übergeben wird `ByRef`, die Prozedur können sie auch ändern. Weitere Informationen finden Sie unter [Unterschiede zwischen übergibt ein Argument nach Wert und nach Referenz](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
## <a name="rules"></a>Regeln  
  
-   **Klammern.** Wenn Sie eine Parameterliste angeben, muss er in Klammern gesetzt werden. Wenn keine Parameter vorhanden sind, können Sie weiterhin Klammern einschließen einer leeren Liste. Dies verbessert die Lesbarkeit des Codes, durch die Klärung, dass das Element eine Prozedur ist.  
  
-   **Optionale Parameter.** Bei Verwendung der `Optional` Modifizierer für einen Parameter, alle nachfolgenden Parameter in der Liste muss ebenfalls optional und werden deklariert, indem die `Optional` Modifizierer.  
  
     Jeder Optionaler Parameter-Deklaration angeben muss die `defaultvalue` Klausel.  
  
     Weitere Informationen finden Sie unter [optionale Parameter](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).  
  
-   **Parameterarrays.** Sie müssen angeben, `ByVal` für eine `ParamArray` Parameter.  
  
     Sie können nicht beide verwenden `Optional` und `ParamArray` in derselben Parameterliste.  
  
     Weitere Informationen finden Sie unter [Parameterarrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).  
  
-   **Übergabemechanismus.** Ist der standardmäßige Mechanismus für jedes Argument `ByVal`, was bedeutet, dass die Prozedur kann nicht geändert werden die zugrunde liegenden Variable-Element. Jedoch, wenn das Element ein Verweistyp ist, kann die Prozedur den Inhalt oder die Member des zugrunde liegenden Objekts ändern, obwohl sie nicht ersetzen oder das Objekt selbst zuweisen.  
  
-   **Parameternamen.** Wenn der Datentyp des Parameters ein Array ist, führen Sie die `parametername` sofort in Klammern einschließen. Weitere Informationen zu Parameternamen finden Sie unter [deklarierte Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine `Function` Prozedur, die zwei Parameter definiert.  
  
 [!code-vb[VbVbalrStatements#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/parameter-list_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.InteropServices.DllImportAttribute>  
 [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Übersicht über Attribute](../../../visual-basic/programming-guide/concepts/attributes/index.md)  
 [Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
