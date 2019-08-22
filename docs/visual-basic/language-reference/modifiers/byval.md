---
title: ByVal (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ByVal
- ByVal
helpviewer_keywords:
- ByVal keyword [Visual Basic], contexts
- ByVal keyword [Visual Basic]
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
ms.openlocfilehash: 1fa4c1fa0a2def02dd56fa3728a8df4b5ff16b7f
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666849"
---
# <a name="byval-visual-basic"></a>ByVal (Visual Basic)
Gibt an, dass ein Argument als [Wert](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)übermittelt wird, sodass die aufgerufene Prozedur oder Eigenschaft den Wert einer Variablen, die dem Argument im aufrufenden Code zugrunde liegt, nicht ändern kann. Wenn kein Modifizierer angegeben wird, ist ByVal der Standardwert.

> [!NOTE]
> Da es sich hierbei um den Standardwert handelt, müssen Sie das- `ByVal` Schlüsselwort nicht explizit in den Methoden Signaturen angeben. Sie erzeugt in der Regel einen lärmenden Code und führt häufig dazu, `ByRef` dass das nicht Standard Schlüsselwort übersehen wird.

## <a name="remarks"></a>Hinweise
 Der `ByVal`-Modifizierer kann in folgenden Kontexten verwendet werden:

 [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)

 [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)
  
 [Operator-Anweisung](../../../visual-basic/language-reference/statements/operator-statement.md)
  
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)
  
 [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="example"></a>Beispiel
 Im folgenden Beispiel wird die Verwendung des `ByVal` Parameters Übergabe Mechanismus mit einem Verweistyp Argument veranschaulicht. Im Beispiel ist `c1`das-Argument, eine Instanz der-Klasse `Class1`. `ByVal`verhindert, dass der Code in den Prozeduren den zugrunde liegenden Wert des Verweis `c1`Arguments () ändert, nicht jedoch die zugänglichen Felder und `c1`Eigenschaften von.

 [!code-vb[VbVbalrKeywords#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class5.vb#10)]

## <a name="see-also"></a>Siehe auch

- [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)
- [Übergeben von Argumenten als Wert und als Verweis](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
