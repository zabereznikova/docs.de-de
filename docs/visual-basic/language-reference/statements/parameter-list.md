---
title: Parameterliste (Visual Basic) | Microsoft-Dokumentation
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
- Visual Basic code, procedures
- parameters, Visual Basic
- parameters, lists
- parameter lists
- Visual Basic code, parameter lists
- arguments [Visual Basic], Visual Basic
- procedures, parameter lists
ms.assetid: 5d737319-0c34-4df9-a23d-188fc840becd
caps.latest.revision: 19
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: abadaa8e035bfa4c92acc30ab633d6a7e958676c
ms.lasthandoff: 03/13/2017

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
 Optional. Liste der Attribute, die für diesen Parameter gelten. Setzen Sie die [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md) in spitzen Klammern ("`<`"und"`>`").  
  
 `Optional`  
 Optional. Gibt an, dass dieser Parameter nicht erforderlich ist, wenn die Prozedur aufgerufen wird.  
  
 `ByVal`  
 Optional. Gibt an, dass die Prozedur nicht ersetzen oder zugrunde liegende das entsprechende Argument in den aufrufenden Code Variablenelement zuweisen.  
  
 `ByRef`  
 Optional. Gibt an, dass die Prozedur das zugrunde liegende Variablenelement im Aufrufcode genauso ändern kann wie der aufrufende Code selbst.  
  
 `ParamArray`  
 Optional. Gibt an, dass der letzte Parameter in der Parameterliste ein optionales Array von Elementen des angegebenen Datentyps. Dadurch wird den aufrufenden Code eine beliebige Anzahl von Argumenten an die Prozedur übergeben.  
  
 `parametername`  
 Erforderlich. Der Name der lokalen Variablen, die den Parameter darstellt.  
  
 `parametertype`  
 Erforderlich, wenn `Option Strict` ist `On`. Der Datentyp der lokalen Variablen, die den Parameter darstellt.  
  
 `defaultvalue`  
 Erforderlich für `Optional` Parameter. Jeder Konstante oder einen konstanten Ausdruck, der den Datentyp des Parameters ausgewertet wird. Wenn der Typ `Object`, oder eine Klasse, Schnittstelle, Array oder eine Struktur, der Standardwert kann nur `Nothing`.  
  
## <a name="remarks"></a>Hinweise  
 Parameter sind in Klammern gesetzt und durch Kommas getrennt. Ein Parameter kann mit jedem Datentyp deklariert werden. Wenn Sie keinen angeben `parametertype`, wird standardmäßig `Object`.  
  
 Wenn der aufrufende Code die Prozedur aufruft, übergibt er ein *Argument* an jeden erforderlichen Parameter. Weitere Informationen finden Sie unter [Unterschiede zwischen Parametern und Argumenten](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).  
  
 Das Argument, das der Aufrufcode an jeden Parameter übergibt, ist ein Zeiger auf ein zugrunde liegendes Element im Aufrufcode. Wenn dieses Element ist *nicht variables* (eine Konstante, Literal, Enumeration oder Ausdruck), es ist nicht möglich, für jeden Code, um ihn zu ändern. Ist dies ein *Variable* Element (eine deklarierte Variable, Feld, Eigenschaft, Arrayelement oder Strukturelement), der aufrufende Code ändern kann. Weitere Informationen finden Sie unter [Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).  
  
 Wenn ein Variable-Element übergeben wird `ByRef`, die Prozedur kann es auch ändern. Weitere Informationen finden Sie unter [Unterschiede zwischen übergeben von Argumenten nach Wert und als Verweis](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
## <a name="rules"></a>Regeln  
  
-   **Klammern.** Wenn Sie eine Parameterliste angeben, müssen Sie ihn in Klammern setzen. Wenn keine Parameter vorhanden sind, können Sie immer noch Klammern, die eine leere Liste einschließen. Dies verbessert die Lesbarkeit des Codes, weil dadurch deutlich, dass das Element eine Prozedur ist.  
  
-   **Optionale Parameter.** Bei Verwendung der `Optional` Modifizierer für einen Parameter, alle nachfolgenden Parameter in der Liste muss ebenfalls optional und werden deklariert, indem die `Optional` Modifizierer.  
  
     Jede optionale Parameterdeklaration angeben muss die `defaultvalue` Klausel.  
  
     Weitere Informationen finden Sie unter [optionale Parameter](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).  
  
-   **Parameter-Arrays.** Geben Sie `ByVal` für eine `ParamArray` Parameter.  
  
     Sie können nicht beides verwenden `Optional` und `ParamArray` in einer Parameterliste.  
  
     Weitere Informationen finden Sie unter [Parameterarrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).  
  
-   **Mechanismus übergeben.** Der Standardmechanismus für jedes Argument ist `ByVal`, was bedeutet, dass die Prozedur wird das zugrunde liegende Variablenelement nicht ändern. Jedoch, wenn das Element ein Verweistyp ist, kann die Prozedur den Inhalt oder die Member des zugrunde liegenden Objekts ändern, obwohl sie nicht ersetzen oder das Objekt selbst zuweisen.  
  
-   **Parameternamen.** Wenn der Datentyp des Parameters ein Array ist, führen Sie die `parametername` sofort durch Klammern. Weitere Informationen zu Parameternamen finden Sie unter [Elementnamen deklariert](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine `Function` Prozedur, die zwei Parameter definiert.  
  
 [!code-vb[VbVbalrStatements&#2;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/parameter-list_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.InteropServices.DllImportAttribute></xref:System.Runtime.InteropServices.DllImportAttribute>   
 [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Übersicht über Attribute](../../../visual-basic/programming-guide/concepts/attributes/index.md)   
 [Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
