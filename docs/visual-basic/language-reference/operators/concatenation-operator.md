---
title: '&amp;-Operator'
ms.date: 07/20/2015
f1_keywords:
- vb.&
helpviewer_keywords:
- And (&) operator
- ampersand operator (&)
- '& operator'
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
ms.assetid: fefc3d00-cbf1-475c-8c5e-6fb213b3f85a
ms.openlocfilehash: 20c2e2088691e68221872cc1dfc5486413515a4d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867155"
---
# <a name="amp-operator-visual-basic"></a>&amp; Operator (Visual Basic)

Generiert eine Zeichen folgen Verkettung von zwei Ausdrücken.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
result = expression1 & expression2  
```  
  
## <a name="parts"></a>Bestandteile  

 `result`  
 Erforderlich. Beliebige- `String` oder- `Object` Variable.  
  
 `expression1`  
 Erforderlich. Jeder Ausdruck mit einem Datentyp, der zu erweitert wird `String` .  
  
 `expression2`  
 Erforderlich. Jeder Ausdruck mit einem Datentyp, der zu erweitert wird `String` .  
  
## <a name="remarks"></a>Bemerkungen  

 Wenn der Datentyp von `expression1` oder `expression2` nicht ist `String` `String` , wird er in konvertiert `String` . Wenn einer der Datentypen nicht in erweitert `String` wird, generiert der Compiler einen Fehler.  
  
 Der Datentyp von `result` ist `String` . Wenn ein oder beide Ausdrücke als " [Nothing](../nothing.md) " ausgewertet werden oder den Wert aufweisen <xref:System.DBNull.Value?displayProperty=nameWithType> , werden Sie als Zeichenfolge mit dem Wert "" behandelt.  
  
> [!NOTE]
> Der `&` Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
> [!NOTE]
> Das kaufmännische und-Zeichen (&) kann auch verwendet werden, um Variablen als Typ zu identifizieren `Long` . Weitere Informationen finden Sie unter [Typzeichen](../../programming-guide/language-features/data-types/type-characters.md).  
  
## <a name="example"></a>Beispiel  

 In diesem Beispiel wird der- `&` Operator verwendet, um die Zeichen folgen Verkettung zu erzwingen. Das Ergebnis ist ein Zeichen folgen Wert, der die Verkettung der beiden Zeichen folgen Operanden darstellt.  
  
 [!code-vb[VbVbalrOperators#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>Weitere Informationen

- [&=-Operator](and-assignment-operator.md)
- [Verkettungsoperatoren](concatenation-operators.md)
- [Operatorrangfolge in Visual Basic](operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](operators-listed-by-functionality.md)
- [Verkettungsoperatoren in Visual Basic](../../programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
