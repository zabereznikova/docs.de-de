---
title: Operator +=
ms.date: 07/20/2015
f1_keywords:
- vb.+=
helpviewer_keywords:
- += operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- += operator [Visual Basic], appending strings
- compound assignment statements [Visual Basic]
ms.assetid: d3e959f4-85d4-4e47-87c4-77b62335a5b3
ms.openlocfilehash: a3a37798a3ddb480ac5322c4b2d3e9396e739aa6
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873478"
---
# <a name="-operator-visual-basic"></a>+=-Operator (Visual Basic)

Fügt den Wert eines numerischen Ausdrucks zum Wert einer numerischen Variablen oder Eigenschaft hinzu und weist das Ergebnis der Variablen oder Eigenschaft zu. Kann auch verwendet werden, um einen `String` -Ausdruck zu einer `String` Variablen oder Eigenschaft zu verketten und das Ergebnis der Variablen oder der Eigenschaft zuzuweisen.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
variableorproperty += expression  
```  
  
## <a name="parts"></a>Bestandteile  

 `variableorproperty`  
 Erforderlich. Eine beliebige numerische oder `String` Variable oder Eigenschaft.  
  
 `expression`  
 Erforderlich. Beliebiger numerischer or- `String` Ausdruck.  
  
## <a name="remarks"></a>Bemerkungen  

 Das Element auf der linken Seite des `+=` Operators kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein. Die Variable oder [Eigenschaft darf nicht schreibgeschützt sein.](../modifiers/readonly.md)  
  
 Der `+=` Operator Fügt der Variablen oder der Eigenschaft auf der linken Seite den Wert auf der rechten Seite hinzu und weist das Ergebnis der Variablen oder der Eigenschaft auf der linken Seite zu. Der `+=` Operator kann auch verwendet werden, um den `String` Ausdruck rechts von der `String` Variablen oder der Eigenschaft auf der linken Seite zu verketten und das Ergebnis der Variablen oder der Eigenschaft auf der linken Seite zuzuweisen.  
  
> [!NOTE]
> Wenn Sie den- `+=` Operator verwenden, sind Sie möglicherweise nicht in der Lage, zu bestimmen, ob Addition oder Zeichen folgen Verkettung auftreten. Verwenden `&=` Sie den Operator für die Verkettung, um Mehrdeutigkeit zu vermeiden und selbst dokumentierenden Code bereitzustellen.  
  
 Dieser Zuweisungs Operator führt implizit erweiternde, aber keine einschränkenden Konvertierungen durch, wenn die Kompilierungs Umgebung strikte Semantik erzwingt. Weitere Informationen zu diesen Konvertierungen finden Sie unter [erweiternde und einschränkende Konvertierungen](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md). Weitere Informationen zu Strict-und einschränkend sein Semantik finden Sie unter [Option Strict-Anweisung](../statements/option-strict-statement.md).  
  
 Wenn eine einschränkend sein Semantik zulässig ist, `+=` führt der Operator implizit eine Vielzahl von Zeichen folgen-und numerischen Konvertierungen aus, die mit denen des Operators identisch sind `+` . Ausführliche Informationen zu diesen Konvertierungen finden Sie unter [+-Operator](addition-operator.md).  
  
## <a name="overloading"></a>Überladen  

 Der `+` Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Das Überladen des- `+` Operators wirkt sich auf das Verhalten des- `+=` Operators aus. Wenn Ihr Code `+=` für eine Klasse oder Struktur verwendet, die überlastet `+` ist, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird der- `+=` Operator verwendet, um den Wert einer Variablen mit einem anderen zu kombinieren. Der erste Teil verwendet `+=` mit numerischen Variablen, um einen Wert zu einem anderen hinzuzufügen. Im zweiten Teil wird `+=` mit `String` Variablen verwendet, um einen Wert mit einem anderen zu verketten. In beiden Fällen wird das Ergebnis der ersten Variablen zugewiesen.  
  
 [!code-vb[VbVbalrOperators#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#7)]  
  
 [!code-vb[VbVbalrOperators#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#8)]  
  
 Der Wert von `num1` ist jetzt 13, und der Wert von `str1` ist jetzt "103".  
  
## <a name="see-also"></a>Weitere Informationen

- [+-Operator](addition-operator.md)
- [Zuweisungsoperatoren](assignment-operators.md)
- [Arithmetic Operators (Arithmetische Operatoren)](arithmetic-operators.md)
- [Verkettungsoperatoren](concatenation-operators.md)
- [Operatorrangfolge in Visual Basic](operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](operators-listed-by-functionality.md)
- [Anweisungen](../../programming-guide/language-features/statements.md)
