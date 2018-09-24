---
title: true-Operator (C#-Referenz)
ms.date: 07/20/2015
helpviewer_keywords:
- true operator [C#]
ms.assetid: acaba817-5da5-4364-b3b2-2e5c75ec1839
ms.openlocfilehash: 54b8d764dc673598474d6adbbee82e0223a16b93
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "45994584"
---
# <a name="true-operator-c-reference"></a>true-Operator (C#-Referenz)
Gibt den [bool](../../../csharp/language-reference/keywords/bool.md)-Wert `true` zurück, um anzugeben, dass ein Operand TRUE ist, und gibt ansonsten `false` zurück.  
  
 Vor C#-2.0 wurden die Operatoren `true` und `false` verwendet, um benutzerdefinierte Werttypen, die NULL-Werte zulassen, zu erstellen, die mit Typen, wie z.B. `SqlBool`, kompatibel waren. Jedoch bietet die Sprache jetzt integrierte Unterstützung für Werttypen, die NULL-Werte zulassen, und diese sollten Sie nach Möglichkeit verwendet, anstatt die Operatoren `true` und `false` zu überladen. Weitere Informationen finden Sie unter [Typen, die NULL-Werte zulassen](../../../csharp/programming-guide/nullable-types/index.md).  
  
 Bei booleschen Werten, die NULL-Werte zulassen, ist der Ausdruck `a != b` nicht unbedingt gleich `!(a == b)`, da ein oder beide Werte möglicherweise NULL sind. Sie müssen sowohl den Operator `true` als auch den Operator `false` separat überladen, um die NULL-Werte im Ausdruck ordnungsgemäß zu identifizieren. Im folgenden Beispiel wird die Überladung und Verwendung der Operatoren `true` und `false` gezeigt.  
  
 [!code-csharp[csrefKeywordsOperator#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/true-operator_1.cs)]  
  
 Ein Typ, der die Operatoren `true` und `false` überlädt, kann für den Kontrollausdruck in den Anweisungen [if](../../../csharp/language-reference/keywords/if-else.md), [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md) und [for](../../../csharp/language-reference/keywords/for.md) sowie in [bedingten Ausdrücken](../../../csharp/language-reference/operators/conditional-operator.md) verwendet werden.  
  
 Wenn ein Typ Operator `true` definiert, muss er auch Operator [false](../../../csharp/language-reference/keywords/false.md) definieren.  
  
 Ein Typ kann nicht direkt die bedingten logischen Operatoren ([&&](../../../csharp/language-reference/operators/conditional-and-operator.md) und [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md)) überladen. Jedoch kann ein ähnlicher Effekt erzielt werden, indem die regulären logischen Operatoren sowie die Operatoren `true` und `false` überladen werden.  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)  
- [C#-Operatoren](../../../csharp/language-reference/operators/index.md)  
- [false](../../../csharp/language-reference/keywords/false.md)
