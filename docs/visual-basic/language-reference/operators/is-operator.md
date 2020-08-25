---
title: Is-Operator
ms.date: 07/20/2015
f1_keywords:
- vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
ms.openlocfilehash: 1c2d87ef0a8202332c87af552f488d652c400213
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812262"
---
# <a name="is-operator-visual-basic"></a>Is-Operator (Visual Basic)

Vergleicht zwei Objekt Verweis Variablen.

## <a name="syntax"></a>Syntax

```vb
result = object1 Is object2
```

## <a name="parts"></a>Bestandteile

 `result`  
 Erforderlich. Ein beliebiger `Boolean` Wert.  
  
 `object1`  
 Erforderlich. Ein beliebiger `Object` Name.  
  
 `object2`  
 Erforderlich. Ein beliebiger `Object` Name.  
  
## <a name="remarks"></a>Hinweise

Der- `Is` Operator bestimmt, ob zwei Objekt Verweise auf das gleiche Objekt verweisen. Es werden jedoch keine Wert Vergleiche durchgeführt. Wenn `object1` und `object2` beide auf genau dieselbe Objektinstanz verweisen, ist `result` `True` . andernfalls ist der Wert `result` `False` .

> [!NOTE]
> Das `Is` Schlüsselwort wird auch im [SELECT... Case-Anweisung](../statements/select-case-statement.md).
  
## <a name="example"></a>Beispiel

Im folgenden Beispiel wird der- `Is` Operator verwendet, um Paare von Objekt verweisen zu vergleichen. Die Ergebnisse werden einem Wert zugewiesen, `Boolean` der angibt, ob die beiden-Objekte identisch sind.

[!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]

Wie das vorherige Beispiel zeigt, können Sie den- `Is` Operator verwenden, um früh gebundene und spät gebundene Objekte zu testen.

## <a name="use-typeof-operator-with-is-operator"></a>Typeof-Operator mit is-Operator verwenden

`Is` der-Operator kann auch mit dem-Schlüsselwort verwendet werden, `TypeOf` um einen `TypeOf` ...-Ausdruck zu erstellen `Is` , der testet, ob eine Objekt Variable mit einem-Datentyp kompatibel ist. Beispiel:

```vb
If TypeOf sender Is Button Then
```

## <a name="see-also"></a>Weitere Informationen

- [Typeof-Operator](typeof-operator.md)
- [IsNot-Operator](isnot-operator.md)
- [Comparison Operators in Visual Basic](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Operatorrangfolge in Visual Basic](operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](operators-listed-by-functionality.md)
- [Operatoren und Ausdrücke](../../programming-guide/language-features/operators-and-expressions/index.md)
