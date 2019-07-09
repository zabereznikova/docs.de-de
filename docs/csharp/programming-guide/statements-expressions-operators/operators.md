---
title: Operatoren – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 04/30/2019
helpviewer_keywords:
- operators [C#]
- C# language, operators
- operators [C#], about operators
ms.assetid: 214e7b83-1a41-4f7c-9867-64e9c0bab39f
ms.openlocfilehash: 551d4cd8bf26a1c1caf3cbf611d9f338ae2581be
ms.sourcegitcommit: eaa6d5cd0f4e7189dbe0bd756e9f53508b01989e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2019
ms.locfileid: "67609506"
---
# <a name="operators-c-programming-guide"></a>Operatoren (C#-Programmierhandbuch)

In C# ist ein *Operator* ein Programmelement, das auf einen oder mehrere *Operanden* in einem Ausdruck oder einer Anweisung angewendet wird. Operatoren mit einem Operanden, z. B. der Inkrementoperator (`++`) oder `new`, werden als *unäre* Operatoren bezeichnet. Operatoren mit zwei Operanden, z. B. arithmetische Operatoren (`+`,`-`,`*`,`/`), werden als *binäre* Operatoren bezeichnet. Der bedingte Operator (`?:`) verfügt über drei Operanden. Er ist der einzige ternäre Operator in C#.  
  
 Die folgende C#-Anweisung enthält einen einzelnen unären Operator und einen einzigen Operanden. Der Inkrementoperator `++`ändert den Wert des Operanden `y`.  
  
 [!code-csharp[csProgGuideStatements#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#5)]  
  
 Die folgende C#-Anweisung enthält zwei binäre Operatoren mit jeweils zwei Operanden. Die Operanden des Zuweisungsoperators `=`sind die ganzzahlige Variable `y` und der Ausdruck `2 + 3` . Der Ausdruck `2 + 3` selbst besteht aus dem Additionsoperator und zwei Operanden: `2` und `3`.  
  
 [!code-csharp[csProgGuideStatements#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#6)]  
  
Ein Operand kann ein gültiger Ausdruck sein, der aus beliebig langem Code zusammengesetzt ist, und kann eine beliebige Anzahl von Unterausdrücken enthalten. In einem Ausdruck mit mehreren Operatoren wird die Reihenfolge, in der die Operatoren angewendet werden, von der *Operatorrangfolge*, der *Assoziativität*und von Klammern bestimmt.  

## <a name="operator-precedence"></a>Operatorrangfolge
  
Jeder Operator verfügt über einen definierten Vorrang. In einem Ausdruck, der mehrere Operatoren mit verschiedenen Rangfolgenebenen enthält, bestimmt die Rangfolge der Operatoren die Reihenfolge, in der die Operatoren ausgewertet werden. Beispielsweise weist die folgende Anweisung `n1` 3 zu:

```csharp
n1 = 11 - 2 * 4;
```

Die Multiplikation wird zuerst ausgeführt, da Multiplikation Vorrang vor Subtraktion enthält.

Die vollständige Liste der nach Rangfolgenebene sortierten C#-Operatoren finden Sie unter [C#-Operatoren](../../language-reference/operators/index.md).
  
## <a name="associativity"></a>Assoziativität

 Wenn ein Ausdruck zwei oder mehr Operatoren mit demselben Rang enthält, wird die Auswertungsreihenfolge anhand des Assoziativitätsgesetzes festgelegt. Linksassoziative Operatoren werden von links nach rechts ausgewertet. `x * y / z` wird beispielsweise als `(x * y) / z`ausgewertet. Rechtsassoziative Operatoren werden von rechts nach links ausgewertet. Beispielsweise ist der Zuweisungsoperator rechtsassoziativ. Falls nicht, würde der folgende Code zu einem Fehler führen.  
  
```csharp  
int a, b, c;  
c = 1;  
// The following two lines are equivalent.  
a = b = c;  
a = (b = c);  
  
// The following line, which forces left associativity, causes an error.  
//(a = b) = c;  
```  
  
 Ein weiteres Beispiel für einen rechtsassoziativen Operator ist der ternäre Operator ([?:](../../../csharp/language-reference/operators/conditional-operator.md)). Die meisten binäre Operatoren sind linksassoziativ.  
  
 Unabhängig davon, ob Operatoren in einem Ausdruck linksassoziativ oder rechtsassoziativ sind, werden zuerst die Operanden aller Ausdrücke von links nach rechts ausgewertet. Die folgenden Beispiele veranschaulichen die Auswertungsreihenfolge von Operatoren und Operanden.  
  
|Anweisung|Reihenfolge der Auswertung|  
|---------------|-------------------------|  
|`a = b`|a, b, =|  
|`a = b + c`|a, b, c, +, =|  
|`a = b + c * d`|a, b, c, d, *, +, =|  
|`a = b * c + d`|a, b, c, *, d, +, =|  
|`a = b - c + d`|a, b, c, -, d, +, =|  
|`a += b -= c`|a, b, c, -=, +=|  
  
## <a name="adding-parentheses"></a>Hinzufügen von Klammern

 Sie können die Reihenfolge ändern, die von Operatorenrangfolge und Assoziativität festgelegt wird, indem Sie Klammern verwenden. Beispielsweise wird `2 + 3 * 2` gewöhnlich als 8 ausgewertet, da Multiplikationsoperatoren Vorrang gegenüber additiven Operatoren besitzen. Wenn Sie jedoch den Ausdruck als `(2 + 3) * 2`schreiben, wird die Addition vor der Multiplikation ausgewertet, und das Ergebnis ist 10. Die folgenden Beispiele veranschaulichen die Auswertungsreihenfolge der in Klammern gesetzten Ausdrücke. Wie in den vorherigen Beispielen werden die Operanden ausgewertet, bevor der Operator angewendet wird.  
  
|Anweisung|Reihenfolge der Auswertung|  
|---------------|-------------------------|  
|`a = (b + c) * d`|a, b, c, +, d, *, =|  
|`a = b - (c + d)`|a, b, c, d, +, -, =|  
|`a = (b + c) * (d - e)`|a, b, c, +, d, e, -, *, =|  
  
## <a name="operator-overloading"></a>Überladen von Operatoren

Sie können das Verhalten bestimmter Operatoren für benutzerdefinierte Klassen und Strukturen definieren. Dieser Prozess wird als *Operatorüberladung*bezeichnet. Weitere Informationen finden Sie unter [Operatorüberladung](../../language-reference/operators/operator-overloading.md).
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Anweisungen, Ausdrücke und Operatoren](index.md)
- [C#-Operatoren](../../language-reference/operators/index.md)
