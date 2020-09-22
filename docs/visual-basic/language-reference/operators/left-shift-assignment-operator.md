---
title: <<=-Operator
ms.date: 07/20/2015
f1_keywords:
- vb.<<=
helpviewer_keywords:
- operator <<=
- assignment statements [Visual Basic], compound
- <<= operator [Visual Basic]
- statements [Visual Basic], compound assignment
- operator<<=
- compound assignment statements [Visual Basic]
ms.assetid: 8ad26613-faff-4e2f-89ee-63feee33bfda
ms.openlocfilehash: 72fc842002586a4d5e48bc39b5c785fc6a9e9451
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866904"
---
# <a name="-operator-visual-basic"></a>\<\<Operator = (Visual Basic)

Führt eine arithmetische Verschiebung nach Links für den Wert einer Variablen oder Eigenschaft durch und weist das Ergebnis wieder der Variablen oder Eigenschaft zu.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
variableorproperty <<= amount  
```  
  
## <a name="parts"></a>Bestandteile  

 `variableorproperty`  
 Erforderlich. Variable oder Eigenschaft eines ganzzahligen Typs ( `SByte` , `Byte` , `Short` , `UShort` , `Integer` , `UInteger` , `Long` oder `ULong` ).  
  
 `amount`  
 Erforderlich. Numerischer Ausdruck eines Datentyps, der zu erweitert wird `Integer` .  
  
## <a name="remarks"></a>Bemerkungen  

 Das Element auf der linken Seite des `<<=` Operators kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein. Die Variable oder [Eigenschaft darf nicht schreibgeschützt sein.](../modifiers/readonly.md)  
  
 Der `<<=` Operator führt zuerst eine arithmetische linke Verschiebung des Werts der Variablen oder Eigenschaft durch. Der Operator weist dann das Ergebnis dieses Vorgangs wieder dieser Variablen oder Eigenschaft zu.  
  
 Arithmetische Verschiebungen sind nicht zirkulär, d. h., dass die Bits, die von einem Ende des Ergebnisses entfernt wurden, nicht erneut am anderen Ende eingefügt werden. In einer arithmetischen linken Schicht werden die Bits, die nach dem Bereich des Ergebnis Datentyps verschoben werden, verworfen, und die auf der rechten Seite frei gewordenen Bitpositionen werden auf 0 (null) festgelegt.  
  
## <a name="overloading"></a>Überladen  

 Der [<< -Operator](left-shift-operator.md) kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Das Überladen des- `<<` Operators wirkt sich auf das Verhalten des- `<<=` Operators aus. Wenn Ihr Code `<<=` für eine Klasse oder Struktur verwendet, die überlastet `<<` ist, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird der `<<=` -Operator verwendet, um das Bitmuster einer `Integer` Variablen um den angegebenen Betrag nach Links zu verschieben und das Ergebnis der Variablen zuzuweisen.  
  
 [!code-vb[VbVbalrOperators#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#13)]  
  
## <a name="see-also"></a>Weitere Informationen

- [<< -Operator](left-shift-operator.md)
- [Zuweisungsoperatoren](assignment-operators.md)
- [Bitschiebeoperatoren](bit-shift-operators.md)
- [Operatorrangfolge in Visual Basic](operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](operators-listed-by-functionality.md)
- [Anweisungen](../../programming-guide/language-features/statements.md)
