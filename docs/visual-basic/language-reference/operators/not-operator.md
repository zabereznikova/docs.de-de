---
title: Not-Operator
ms.date: 07/20/2015
f1_keywords:
- vb.Not
helpviewer_keywords:
- Boolean expressions, negating
- operators [Visual Basic], bitwise
- negation operator [Visual Basic]
- inverse bit values in variables [Visual Basic]
- bitwise operators [Visual Basic], NOT operator
- bitwise comparison [Visual Basic]
- Not operator [Visual Basic]
- logical negation
- operators [Visual Basic], negation
ms.assetid: 8f2ea83c-d2ed-480a-a474-3042a1cad9b5
ms.openlocfilehash: 56cdeb80a217dbce15921eddd6a43d8d1b049376
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401458"
---
# <a name="not-operator-visual-basic"></a>Not-Operator (Visual Basic)
Führt eine logische Negation für einen- `Boolean` Ausdruck oder eine bitweise Negation eines numerischen Ausdrucks aus.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
result = Not expression  
```  
  
## <a name="parts"></a>Bestandteile  
 `result`  
 Erforderlich. Ein beliebiger `Boolean`-Ausdruck oder numerischer Ausdruck.  
  
 `expression`  
 Erforderlich. Ein beliebiger `Boolean`-Ausdruck oder numerischer Ausdruck.  
  
## <a name="remarks"></a>Bemerkungen  
 In `Boolean` der folgenden Tabelle wird für Ausdrücke veranschaulicht, wie `result` bestimmt wird.  
  
|Wenn `expression` gleich |Der Wert von `result` ist|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 Bei numerischen Ausdrücken kehrt der `Not` Operator die Bitwerte eines beliebigen numerischen Ausdrucks um und legt das entsprechende Bit in `result` entsprechend der folgenden Tabelle fest.  
  
|Wenn `expression` Bit in|Das Bit in `result` ist|  
|-------------------------------|----------------------------|  
|1|0|  
|0|1|  
  
> [!NOTE]
> Da die logischen und bitweisen Operatoren Vorrang vor anderen arithmetischen und relationalen Operatoren sind, sollten alle bitweisen Vorgänge in Klammern eingeschlossen werden, um eine exakte Ausführung sicherzustellen.  
  
## <a name="data-types"></a>Datentypen  
 Bei einer booleschen Negation ist der Datentyp des Ergebnisses `Boolean` . Bei einer bitweisen Negation ist der Ergebnis Datentyp mit dem von identisch `expression` . Wenn Expression jedoch ist `Decimal` , ist das Ergebnis `Long` .  
  
## <a name="overloading"></a>Überladen  
 Der `Not` Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn der Operand den Typ dieser Klasse oder Struktur aufweist. Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der- `Not` Operator verwendet, um eine logische Negation für einen- `Boolean` Ausdruck auszuführen. Das Ergebnis ist ein `Boolean` Wert, der das Gegenteil des Werts des Ausdrucks darstellt.  
  
 [!code-vb[VbVbalrOperators#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#33)]  
  
 Das vorherige Beispiel erzeugt die Ergebnisse von `False` und `True` .  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der- `Not` Operator verwendet, um eine logische Negation der einzelnen Bits eines numerischen Ausdrucks auszuführen. Das Bit im Ergebnis Muster wird auf das Gegenteil des entsprechenden Bits im Operanden Muster festgelegt, einschließlich des Signier Bits.  
  
 [!code-vb[VbVbalrOperators#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#34)]  
  
 Im vorherigen Beispiel werden die Ergebnisse von – 11, – 9 bzw. – 7 erzeugt.  
  
## <a name="see-also"></a>Weitere Informationen

- [Logische/bitweise Operatoren (Visual Basic)](logical-bitwise-operators.md)
- [Operatorrangfolge in Visual Basic](operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](operators-listed-by-functionality.md)
- [Logische und bitweise Operatoren in Visual Basic](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
