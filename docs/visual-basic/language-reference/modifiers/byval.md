---
title: ByVal
ms.date: 07/20/2015
f1_keywords:
- vb.ByVal
- ByVal
helpviewer_keywords:
- ByVal keyword [Visual Basic], contexts
- ByVal keyword [Visual Basic]
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
ms.openlocfilehash: a96f871c6ce119f65ebbec54fdb1471ae105d504
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351588"
---
# <a name="byval-visual-basic"></a>ByVal (Visual Basic)
Gibt an, dass ein Argument als [Wert](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)übermittelt wird, sodass die aufgerufene Prozedur oder Eigenschaft den Wert einer Variablen, die dem Argument im aufrufenden Code zugrunde liegt, nicht ändern kann. Wenn kein Modifizierer angegeben wird, ist ByVal der Standardwert.

> [!NOTE]
> Da es sich hierbei um den Standardwert handelt, müssen Sie das `ByVal`-Schlüsselwort nicht explizit in den Methoden Signaturen angeben. Sie erzeugt in der Regel einen lärmenden Code und führt häufig dazu, dass das nicht standardmäßige `ByRef`-Schlüsselwort übersehen wird.

## <a name="remarks"></a>Hinweise
 Der `ByVal`-Modifizierer kann in folgenden Kontexten verwendet werden:

 [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)

 [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)
  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)
  
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)
  
 [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="example"></a>Beispiel
 Im folgenden Beispiel wird die Verwendung des `ByVal` Parameter Übergabe Mechanismus mit einem Verweistyp Argument veranschaulicht. Im Beispiel ist das-Argument `c1`, eine Instanz der-Klasse `Class1`. `ByVal` hindert den Code in den Prozeduren daran, den zugrunde liegenden Wert des Verweis Arguments `c1`zu ändern, aber nicht die zugänglichen Felder und Eigenschaften von `c1`zu schützen.

 [!code-vb[VbVbalrKeywords#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class5.vb#10)]

## <a name="see-also"></a>Siehe auch

- [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)
- [Übergeben von Argumenten als Wert und als Verweis](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
