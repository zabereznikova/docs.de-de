---
title: + Operator (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- +_CSharpKeyword
helpviewer_keywords:
- + operator [C#]
- concatenation operator [C#]
- addition operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
ms.openlocfilehash: b49694bc8937c58bd295f0f8e57c378802d0dfb9
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2018
ms.locfileid: "44227986"
---
# <a name="-operator-c-reference"></a>Operator + (C#-Referenz)
Der `+`-Operator kann entweder als unärer oder als binärer Operator funktionieren.  
  
## <a name="remarks"></a>Hinweise  
 Unäre `+`-Operatoren sind für alle numerischen Typen vordefiniert. Das Ergebnis einer unären `+`-Operation für einen numerischen Typ ist nur der Wert des Operanden.  
  
 Binäre `+`-Operatoren sind für numerische Typen und Zeichenfolgentypen vordefiniert. Für numerische Typen berechnet + die Summe der beiden Operanden. Wenn ein oder beide Operanden vom Typ „String“ sind, verkettet + die Zeichenfolgendarstellungen der Operanden.  
  
 Delegattypen bieten auch einen binären `+`-Operator, der Delegaten miteinander verkettet.  
  
 Benutzerdefinierte Typen können die unären `+`- und binären `+`-Operatoren überladen. Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen (enum) zulässig. Weitere Informationen finden Sie unter [Operator (C#-Referenz)](../../../csharp/language-reference/keywords/operator.md).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csRefOperators#28](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-operator_1.cs)]  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [C#-Operatoren](../../../csharp/language-reference/operators/index.md)  
- [Operator (C#-Referenz)](../../../csharp/language-reference/keywords/operator.md)
