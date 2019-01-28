---
title: as – C#-Referenz
ms.custom: seodec18
ms.date: 10/11/2018
f1_keywords:
- as_CSharpKeyword
- as
helpviewer_keywords:
- type conversion [C#], as keyword
- as keyword [C#]
ms.assetid: a9be126b-cbf4-4990-a70d-d0e1983cad0e
ms.openlocfilehash: 33f7971a95b8573168da11d2bd2abc80fa74370e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54736467"
---
# <a name="as-c-reference"></a>as (C#-Referenz)
Sie können den `as`-Operator verwenden, um bestimmte Arten von Konvertierungen zwischen kompatiblen Verweistypen oder [auf NULL festlegbaren Typen](../../../csharp/programming-guide/nullable-types/index.md) durchzuführen. Der folgende Code zeigt ein Beispiel.  
  
[!code-csharp[csrefKeywordsOperator#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#1)]

Wie das Beispiel zeigt, müssen Sie das Ergebnis des `as`-Ausdrucks mit `null` vergleichen, um zu überprüfen, ob eine Konvertierung erfolgreich war. Ab C# 7.0 können Sie den [is](is.md)-Ausdruck verwenden, um zu testen, ob eine Konvertierung erfolgreich war. Wenn die Konvertierung erfolgreich war, können Sie den Ausdruck auch verwenden, um bedingt eine Variable zuzuweisen. In vielen Szenarien ist dies präziser als die Verwendung des `as`-Operators. Weitere Informationen finden Sie im Abschnitt [Typmuster](is.md#type) des Artikels zum [`is`-Operator](is.md).
  
## <a name="remarks"></a>Hinweise  
 Der `as`-Operator kann mit einem Umwandlungsvorgang verglichen werden. Wenn die Konvertierung jedoch nicht möglich ist, gibt `as` `null` zurück, statt eine Ausnahme auszulösen. Betrachten Sie das folgende Beispiel:  
  
```csharp  
expression as type  
```  
  
 Der Code ist äquivalent zu folgendem Ausdruck, jedoch wird die `expression`-Variable nur einmal ausgewertet.  
  
```csharp  
expression is type ? (type)expression : (type)null  
```  
  
 Beachten Sie, dass der `as`-Operator nur Verweis- und Boxingkonvertierungen sowie Konvertierungen mit Nullwert durchführt. Der `as`-Operator kann keine anderen Konvertierungen wie z.B. benutzerdefinierte Konvertierungen durchführen, die stattdessen mithilfe der Cast-Ausdrücke ausgeführt werden sollten.  
  
## <a name="example"></a>Beispiel  

[!code-csharp[csrefKeywordsOperator#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#2)]
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  

Weitere Informationen finden Sie unter [Der as-Operator](~/_csharplang/spec/expressions.md#the-as-operator) in der [C#-Sprachspezifikation](../language-specification/index.md). Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.
 
## <a name="see-also"></a>Siehe auch
- [C#-Referenz](../../../csharp/language-reference/index.md)
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
- [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)
- [is](../../../csharp/language-reference/keywords/is.md)
- [?: Operator](../../../csharp/language-reference/operators/conditional-operator.md)
- [Operatorschlüsselwörter](../../../csharp/language-reference/keywords/operator-keywords.md)
