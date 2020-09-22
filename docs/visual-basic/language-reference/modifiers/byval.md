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
ms.openlocfilehash: 8daf6600f59cea343e0d02b99632b92ce4bf3183
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875469"
---
# <a name="byval-visual-basic"></a>ByVal (Visual Basic)

Gibt an, dass ein Argument als [Wert](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)übermittelt wird, sodass die aufgerufene Prozedur oder Eigenschaft den Wert einer Variablen, die dem Argument im aufrufenden Code zugrunde liegt, nicht ändern kann. Wenn kein Modifizierer angegeben wird, ist ByVal der Standardwert.

> [!NOTE]
> Da es sich hierbei um den Standardwert handelt, müssen Sie das- `ByVal` Schlüsselwort nicht explizit in den Methoden Signaturen angeben. Sie erzeugt in der Regel einen lärmenden Code und führt häufig dazu, dass das nicht Standard `ByRef` Schlüsselwort übersehen wird.

## <a name="remarks"></a>Bemerkungen

 Der `ByVal`-Modifizierer kann in folgenden Kontexten verwendet werden:

 [Declare Statement](../statements/declare-statement.md)

 [Function-Anweisung](../statements/function-statement.md)
  
 [Operator Statement](../statements/operator-statement.md)
  
 [Property Statement](../statements/property-statement.md)
  
 [Sub-Anweisung](../statements/sub-statement.md)

## <a name="example"></a>Beispiel

 Im folgenden Beispiel wird die Verwendung des `ByVal` Parameters Übergabe Mechanismus mit einem Verweistyp Argument veranschaulicht. Im Beispiel ist das-Argument `c1` , eine Instanz der-Klasse `Class1` . `ByVal` verhindert, dass der Code in den Prozeduren den zugrunde liegenden Wert des Verweis Arguments () ändert, `c1` nicht jedoch die zugänglichen Felder und Eigenschaften von `c1` .

 [!code-vb[VbVbalrKeywords#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class5.vb#10)]

## <a name="see-also"></a>Weitere Informationen

- [Schlüsselwörter](../keywords/index.md)
- [Übergeben von Argumenten als Wert und als Verweis](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
