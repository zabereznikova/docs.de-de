---
title: '>>Operator ='
ms.date: 07/20/2015
f1_keywords:
- vb.>>=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator >>= [Visual Basic]
- compound assignment statements [Visual Basic]
- '>>= operator [Visual Basic]'
ms.assetid: 2bcd9abb-7a8c-4229-b75d-8816ff1dc700
ms.openlocfilehash: a1c2331791644155504183d3cf5767470a3bf17b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873356"
---
# <a name="-operator-visual-basic"></a>>>=-Operator (Visual Basic)

Führt eine arithmetische Rechtsverschiebung für den Wert einer Variablen oder Eigenschaft durch und weist das Ergebnis der Variablen oder der Eigenschaft zurück.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
variableorproperty >>= amount  
```  
  
## <a name="parts"></a>Bestandteile  

 `variableorproperty`  
 Erforderlich. Variable oder Eigenschaft eines ganzzahligen Typs ( `SByte` , `Byte` , `Short` , `UShort` , `Integer` , `UInteger` , `Long` oder `ULong` ).  
  
 `amount`  
 Erforderlich. Numerischer Ausdruck eines Datentyps, der zu erweitert wird `Integer` .  
  
## <a name="remarks"></a>Bemerkungen  

 Das Element auf der linken Seite des `>>=` Operators kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein. Die Variable oder [Eigenschaft darf nicht schreibgeschützt sein.](../modifiers/readonly.md)  
  
 Der `>>=` Operator führt zuerst eine arithmetische Rechtsverschiebung für den Wert der Variablen oder der Eigenschaft aus. Der Operator weist dann das Ergebnis dieses Vorgangs der Variablen oder der Eigenschaft zurück.  
  
 Arithmetische Verschiebungen sind nicht zirkulär, d. h., dass die Bits, die von einem Ende des Ergebnisses entfernt wurden, nicht erneut am anderen Ende eingefügt werden. In einer arithmetischen rechten Schicht werden die Bits, die über die bitmost-Bitposition hinaus verschoben werden, verworfen, und das äußteste linke Bit wird an die auf der linken Seite freigegebenen Bitpositionen weitergegeben. Dies bedeutet, dass bei `variableorproperty` einem negativen Wert die frei gewordenen Positionen auf einen Wert festgelegt werden. Wenn `variableorproperty` positiv ist oder wenn der Datentyp ein nicht signierter Typ ist, werden die frei gewordenen Positionen auf 0 (null) festgelegt.  
  
## <a name="overloading"></a>Überladen  

 Der [>> -Operator](right-shift-operator.md) kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Das Überladen des- `>>` Operators wirkt sich auf das Verhalten des- `>>=` Operators aus. Wenn Ihr Code `>>=` für eine Klasse oder Struktur verwendet, die überlastet `>>` ist, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird der `>>=` -Operator verwendet, um das Bitmuster einer `Integer` Variablen rechts um den angegebenen Betrag zu verschieben und das Ergebnis der Variablen zuzuweisen.  
  
 [!code-vb[VbVbalrOperators#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#15)]  
  
## <a name="see-also"></a>Weitere Informationen

- [>> -Operator](right-shift-operator.md)
- [Zuweisungsoperatoren](assignment-operators.md)
- [Bitschiebeoperatoren](bit-shift-operators.md)
- [Operatorrangfolge in Visual Basic](operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](operators-listed-by-functionality.md)
- [Anweisungen](../../programming-guide/language-features/statements.md)
