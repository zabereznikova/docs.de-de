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
ms.openlocfilehash: 4ecb0b4a8fc154a179bc5d9d74ce9821cf4fea75
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56982166"
---
# <a name="parameter-list-visual-basic"></a>Parameterliste (Visual Basic)
Gibt die Parameter, die eine Prozedur erwartet wird, wenn sie aufgerufen wird. Mehrere Parameter werden durch Kommas getrennt. Folgendes ist die Syntax für einen Parameter.  
  
## <a name="syntax"></a>Syntax  
  
```  
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]   
parametername[( )] [ As parametertype ] [ = defaultvalue ]  
```  
  
## <a name="parts"></a>Teile  
 `attributelist`  
 Dies ist optional. Liste der Attribute, die an diesen Parameter angewendet werden. Setzen Sie die [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md) in spitzen Klammern ("`<`"und"`>`").  
  
 `Optional`  
 Dies ist optional. Gibt an, dass dieser Parameter nicht erforderlich ist, wenn die Prozedur aufgerufen wird.  
  
 `ByVal`  
 Dies ist optional. Gibt an, dass die Prozedur kann nicht ersetzt oder neuzuweisung der zugrunde liegenden das entsprechende Argument im aufrufenden Code Variable-Element.  
  
 `ByRef`  
 Dies ist optional. Gibt an, dass die Prozedur den zugrunde liegenden Variable-Element im aufrufenden Code die gleiche Weise ändern kann, die können der aufrufende Code selbst.  
  
 `ParamArray`  
 Dies ist optional. Gibt an, dass der letzte Parameter in der Parameterliste ein optionales Array von Elementen des Typs angegebenen Daten. Dadurch wird den aufrufenden Code eine beliebige Anzahl von Argumenten an die Prozedur übergeben.  
  
 `parametername`  
 Erforderlich. Der Name der lokalen Variablen, die Parameter darstellt.  
  
 `parametertype`  
 Erforderlich, wenn `Option Strict` ist `On`. Der Datentyp der lokalen Variablen, die Parameter darstellt.  
  
 `defaultvalue`  
 Erforderlich für `Optional` Parameter. Ein konstanter oder Konstante Ausdruck, der den Datentyp des Parameters ergibt. Wenn der Typ ist `Object`, oder eine Klasse, Schnittstelle, Array oder eine Struktur, der Standardwert kann nur `Nothing`.  
  
## <a name="remarks"></a>Hinweise  
 Parameter sind in Klammern gesetzt und durch Kommas getrennt. Ein Parameter kann mit allen Datentypen deklariert werden. Wenn Sie keinen angeben `parametertype`, wird standardmäßig `Object`.  
  
 Wenn der aufrufende Code die Prozedur aufruft, übergibt ein *Argument* an jeden erforderlichen Parameter. Weitere Informationen finden Sie unter [Unterschiede zwischen Parametern und Argumenten](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).  
  
 Das Argument, das der aufrufende Code auf jeden Parameter übergibt, ist ein Zeiger auf eine zugrunde liegende Element im aufrufenden Code. Wenn dieses Element ist *nicht variables* (eine Konstante, Literal, Enumeration oder Ausdruck), es ist nicht möglich, für jeden Code, um ihn zu ändern. Ist dies ein *Variable* Element (eine deklarierte Variable, Feld, Eigenschaft, Arrayelement oder Structure-Element), der aufrufende Code ändern kann. Weitere Informationen finden Sie unter [Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).  
  
 Wenn ein Variable-Element übergeben wird `ByRef`, das Verfahren können sie auch ändern. Weitere Informationen finden Sie unter [Unterschiede zwischen Argumentübergabe nach Wert "und" By Reference](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
## <a name="rules"></a>Regeln  
  
-   **Klammern.** Wenn Sie eine Parameterliste angeben, müssen Sie ihn in Klammern setzen. Wenn keine Parameter vorhanden sind, können Sie weiterhin umschließendes Klammerpaar eine leere Liste. Dies verbessert die Lesbarkeit des Codes befassen, dass das Element eine Prozedur ist.  
  
-   **Optionale Parameter.** Bei Verwendung der `Optional` Modifizierer für Parameter, alle nachfolgenden Parameter in der Liste muss ebenfalls optional und werden deklariert, indem die `Optional` Modifizierer.  
  
     Jeder Deklaration optionale Parameter muss angeben, die `defaultvalue` Klausel.  
  
     Weitere Informationen finden Sie unter [optionale Parameter](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).  
  
-   **Parameterarrays.** Sie müssen angeben, `ByVal` für eine `ParamArray` Parameter.  
  
     Sie können nicht beide verwenden `Optional` und `ParamArray` in derselben Parameterliste.  
  
     Weitere Informationen finden Sie unter [Parameterarrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).  
  
-   **Übergabemechanismus.** Ist der Standardmechanismus für jedes Argument `ByVal`, was bedeutet, dass die Prozedur kann nicht geändert werden die zugrunde liegende Variable-Element. Allerdings ist das Element einen Verweistyp handelt, kann die Prozedur den Inhalt oder die Member des zugrunde liegenden Objekts ändern, obwohl sie nicht ersetzen oder das Objekt selbst zuweisen.  
  
-   **Parameternamen.** Wenn der Datentyp des Parameters ein Array ist, führen Sie die `parametername` sofort mit Klammern. Weitere Informationen zu Parameternamen finden Sie unter [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine `Function` Prozedur, die zwei Parameter definiert.  
  
 [!code-vb[VbVbalrStatements#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)
- [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md)
- [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Übersicht über Attribute](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [Vorgehensweise: Umbrechen und Zusammenfassen von Anweisungen in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
