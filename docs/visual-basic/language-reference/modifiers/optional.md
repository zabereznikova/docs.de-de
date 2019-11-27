---
title: Optional
ms.date: 07/20/2015
f1_keywords:
- vb.Optional
- vb.optional
helpviewer_keywords:
- Optional keyword [Visual Basic], contexts
- Optional keyword [Visual Basic]
ms.assetid: 4571ce88-a539-4115-b230-54eb277c6aa7
ms.openlocfilehash: a16dae35bf4bc84d95501624c4f023f390a8dda8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351437"
---
# <a name="optional-visual-basic"></a>Optional (Visual Basic)

Gibt an, dass ein Prozedur Argument beim Aufrufen der Prozedur ausgelassen werden kann.

## <a name="remarks"></a>Hinweise

Für jeden optionalen Parameter muss ein konstanter Ausdruck als Standardwert dieses Parameters angegeben werden. Wenn der Ausdruck als " [Nothing](../../../visual-basic/language-reference/nothing.md)" ausgewertet wird, wird der Standardwert des Value-Datentyps als Standardwert des-Parameters verwendet.

Wenn die Parameterliste einen optionalen Parameter enthält, muss jeder Parameter, der darauf folgt, ebenfalls optional sein.

Der `Optional`-Modifizierer kann in folgenden Kontexten verwendet werden:

- [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)

- [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)

- [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)

- [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)

> [!NOTE]
> Wenn Sie eine Prozedur mit oder ohne optionale Parameter aufrufen, können Sie Argumente anhand der Position oder des Namens übergeben. Weitere Informationen finden Sie unter [übergeben von Argumenten nach Position und Name](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).

> [!NOTE]
> Sie können auch eine Prozedur mit optionalen Parametern definieren, indem Sie überladen verwenden. Wenn Sie über einen optionalen Parameter verfügen, können Sie zwei überladene Versionen der Prozedur definieren, eine, die den-Parameter annimmt, und eine, die nicht ist. Weitere Informationen finden Sie unter [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine Prozedur definiert, die über einen optionalen Parameter verfügt.

```vb
Public Function FindMatches(ByRef values As List(Of String),
                            ByVal searchString As String,
                            Optional ByVal matchCase As Boolean = False) As List(Of String)

    Dim results As IEnumerable(Of String)

    If matchCase Then
        results = From v In values
                  Where v.Contains(searchString)
    Else
        results = From v In values
                  Where UCase(v).Contains(UCase(searchString))
    End If

    Return results.ToList()
End Function
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie eine Prozedur mit Argumenten, die über die Position und mit den über den Namen übermittelt werden, aufgerufen wird. Die Prozedur verfügt über zwei optionale Parameter.

[!code-vb[VbVbalrKeywords#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class8.vb#21)]

## <a name="see-also"></a>Siehe auch

- [Parameterliste](../../../visual-basic/language-reference/statements/parameter-list.md)
- [Optionale Parameter](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
- [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)
