---
title: Operator *=
ms.date: 07/20/2015
f1_keywords:
- vb.*=
helpviewer_keywords:
- operator *=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '*= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 96c86509-6eb8-4682-8226-3852e049376f
ms.openlocfilehash: 4e2f18fb2b8110d97390390b3934d3c1761baa35
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866731"
---
# <a name="-operator-visual-basic"></a>*=-Operator (Visual Basic)

Multipliziert den Wert einer Variablen oder Eigenschaft mit dem Wert eines Ausdrucks und weist das Ergebnis der Variablen oder Eigenschaft zu.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
variableorproperty *= expression  
```  
  
## <a name="parts"></a>Bestandteile  

 `variableorproperty`  
 Erforderlich. Eine beliebige numerische Variable oder Eigenschaft.  
  
 `expression`  
 Erforderlich. Ein beliebiger numerischer Ausdruck.  
  
## <a name="remarks"></a>Bemerkungen  

 Das Element auf der linken Seite des `*=` Operators kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein. Die Variable oder [Eigenschaft darf nicht schreibgeschützt sein.](../modifiers/readonly.md)  
  
 Der `*=` Operator multipliziert zuerst den Wert des Ausdrucks (auf der rechten Seite des Operators) mit dem Wert der Variablen oder der Eigenschaft (auf der linken Seite des Operators). Der-Operator weist dann das Ergebnis dieses Vorgangs der Variablen oder der Eigenschaft zu.  
  
## <a name="overloading"></a>Überladen  

 Der [Operator *](multiplication-operator.md) kann *überladen*werden. das bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Das Überladen des- `*` Operators wirkt sich auf das Verhalten des- `*=` Operators aus. Wenn Ihr Code `*=` für eine Klasse oder Struktur verwendet, die überlastet `*` ist, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird der `*=` -Operator verwendet, um eine `Integer` Variable mit einer Sekunde zu multiplizieren und das Ergebnis der ersten Variablen zuzuweisen.  
  
 [!code-vb[VbVbalrOperators#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#5)]  
  
## <a name="see-also"></a>Weitere Informationen

- [*-Operator](multiplication-operator.md)
- [Zuweisungsoperatoren](assignment-operators.md)
- [Arithmetic Operators (Arithmetische Operatoren)](arithmetic-operators.md)
- [Operatorrangfolge in Visual Basic](operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](operators-listed-by-functionality.md)
- [Anweisungen](../../programming-guide/language-features/statements.md)
