---
title: Parameterliste
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
ms.openlocfilehash: 706fc2414806db5608cce410bf4156839ec2d83e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404316"
---
# <a name="parameter-list-visual-basic"></a>Parameterliste (Visual Basic)

Gibt die Parameter an, die eine Prozedur beim Aufrufen erwartet. Mehrere Parameter werden durch Kommas getrennt. Im folgenden finden Sie die Syntax für einen Parameter.

## <a name="syntax"></a>Syntax

```vb
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]
parametername[( )] [ As parametertype ] [ = defaultvalue ]
```

## <a name="parts"></a>Bestandteile

`attributelist`  
Optional. Liste der Attribute, die auf diesen Parameter angewendet werden. Sie müssen die [Attribut Liste](attribute-list.md) in spitzen Klammern (" `<` " und " `>` ") einschließen.

`Optional`  
Optional. Gibt an, dass dieser Parameter nicht erforderlich ist, wenn die Prozedur aufgerufen wird.

`ByVal`  
Optional. Gibt an, dass die Prozedur das Variablen Element, das dem entsprechenden Argument im aufrufenden Code zugrunde liegt, nicht ersetzen oder neu zuweisen kann.

`ByRef`  
Optional. Gibt an, dass die Prozedur das zugrunde liegende Variablen Element im aufrufenden Code auf dieselbe Weise wie der Aufruf Code selbst ändern kann.

`ParamArray`  
Optional. Gibt an, dass der letzte Parameter in der Parameterliste ein optionales Array von Elementen des angegebenen Datentyps ist. Dadurch kann der aufrufende Code eine beliebige Anzahl von Argumenten an die Prozedur übergeben.

`parametername`  
Erforderlich. Der Name der lokalen Variablen, die den Parameter darstellt.

`parametertype`  
Erforderlich, wenn `Option Strict` ist `On` . Datentyp der lokalen Variablen, die den Parameter darstellt.

`defaultvalue`  
Erforderlich für `Optional` Parameter. Jeder Konstante oder konstanter Ausdruck, der den Datentyp des Parameters ergibt. Wenn der Typ `Object` oder eine Klasse, eine Schnittstelle, ein Array oder eine Struktur ist, kann der Standardwert nur sein `Nothing` .

## <a name="remarks"></a>Bemerkungen

Parameter werden in Klammern eingeschlossen und durch Kommas getrennt. Ein Parameter kann mit einem beliebigen Datentyp deklariert werden. Wenn Sie nicht angeben `parametertype` , wird als Standardwert verwendet `Object` .

Wenn der aufrufende Code die Prozedur aufruft, übergibt er ein *Argument* an jeden erforderlichen Parameter. Weitere Informationen finden Sie [unter Unterschiede zwischen Parametern und Argumenten](../../programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).

Das Argument, das der aufrufende Code an jeden Parameter übergibt, ist ein Zeiger auf ein zugrunde liegendes Element im aufrufenden Code. Wenn dieses Element *nicht variabel* ist (eine Konstante, ein Literalwert, eine Enumeration oder ein Ausdruck), ist es für Code nicht möglich, ihn zu ändern. Wenn es sich um ein *Variablen* Element (eine deklarierte Variable, ein Feld, eine Eigenschaft, ein Array Element oder ein Strukturelement) handelt, kann der Aufruf Code diese ändern. Weitere Informationen finden Sie [unter Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten](../../programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).

Wenn ein Variablen Element übermittelt wird `ByRef` , kann es auch durch die Prozedur geändert werden. Weitere Informationen finden Sie [unter Unterschiede zwischen dem übergeben von Argumenten als Wert und als Verweis](../../programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).

## <a name="rules"></a>Regeln

- **Klammern.** Wenn Sie eine Parameterliste angeben, müssen Sie Sie in Klammern einschließen. Wenn keine Parameter vorhanden sind, können Sie weiterhin Klammern verwenden, die eine leere Liste einschließen. Dies verbessert die Lesbarkeit des Codes, indem klargestellt wird, dass das Element eine Prozedur ist.

- **Optionale Parameter.** Wenn Sie den- `Optional` Modifizierer für einen Parameter verwenden, müssen alle nachfolgenden Parameter in der Liste ebenfalls optional sein und mit dem- `Optional` Modifizierer deklariert werden.

     Jede optionale Parameter Deklaration muss die-Klausel bereitstellen `defaultvalue` .

     Weitere Informationen finden Sie unter [optionale Parameter](../../programming-guide/language-features/procedures/optional-parameters.md).

- **Parameter Arrays.** Sie müssen `ByVal` für einen `ParamArray` Parameter angeben.

     Sie können nicht sowohl `Optional` als auch `ParamArray` in der gleichen Parameterliste verwenden.

     Weitere Informationen finden Sie unter [Parameter Arrays](../../programming-guide/language-features/procedures/parameter-arrays.md).

- **Übergabe Mechanismus.** Der Standardmechanismus für jedes Argument ist `ByVal` , was bedeutet, dass die Prozedur das zugrunde liegende Variablen Element nicht ändern kann. Wenn das Element jedoch ein Verweistyp ist, kann die Prozedur die Inhalte oder Member des zugrunde liegenden Objekts ändern, auch wenn das Objekt nicht ersetzt oder neu zugewiesen werden kann.

- **Parameter Namen.** Wenn der Datentyp des Parameters ein Array ist, folgen Sie `parametername` sofort den Klammern. Weitere Informationen zu Parameternamen finden Sie unter [deklarierte Element Namen](../../programming-guide/language-features/declared-elements/declared-element-names.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine `Function` Prozedur gezeigt, die zwei Parameter definiert.

[!code-vb[VbVbalrStatements#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#2)]

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [Function-Anweisung](function-statement.md)
- [Sub-Anweisung](sub-statement.md)
- [Declare Statement](declare-statement.md)
- [Structure Statement](structure-statement.md)
- [Option Strict-Anweisung](option-strict-statement.md)
- [Übersicht über Attribute](../../programming-guide/concepts/attributes/index.md)
- [Vorgehensweise: Umbrechen und Zusammenfassen von Anweisungen in Code](../../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
