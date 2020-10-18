---
title: Der erste Operand in einem binären If-Ausdruck muss ein Typ, der NULL-Werte zulässt, oder ein Referenztyp sein
ms.date: 07/20/2015
f1_keywords:
- bc33107
- vbc33107
helpviewer_keywords:
- BC33107
ms.assetid: 493c8899-3f6b-4471-8eb6-9284e8492768
ms.openlocfilehash: bca9b74a68815b4e5a3bb2dc114b9031cdf24099
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162738"
---
# <a name="bc33107-first-operand-in-a-binary-if-expression-must-be-nullable-or-a-reference-type"></a>BC33107: der erste Operand in einem binären If-Ausdruck muss NULL-Werte zulassen oder ein Verweistyp sein.

Ein `If` Ausdruck kann entweder zwei oder drei Argumente annehmen. Wenn Sie nur zwei Argumente senden, muss das erste Argument ein Referenztyp oder ein Werte zulässt-Werttyp sein. Wenn das erste Argument etwas anderes als ausgewertet wird `Nothing` , wird der Wert zurückgegeben. Wenn das erste Argument ergibt `Nothing` , wird das zweite Argument ausgewertet und zurückgegeben.

 Der folgende Code enthält z. b `If` . zwei Ausdrücke, eine mit drei Argumenten und eine mit zwei Argumenten. Die Ausdrücke berechnen und geben denselben Wert zurück.

```vb
' firstChoice is a nullable value type.
Dim firstChoice? As Integer = Nothing
Dim secondChoice As Integer = 1128
' If expression with three arguments.
Console.WriteLine(If(firstChoice IsNot Nothing, firstChoice, secondChoice))
' If expression with two arguments.
Console.WriteLine(If(firstChoice, secondChoice))
```

 Dieser Fehler wird durch die folgenden Ausdrücke verursacht:

```vb
Dim choice1 = 4
Dim choice2 = 5
Dim booleanVar = True

' Not valid.
'Console.WriteLine(If(choice1 < choice2, 1))
' Not valid.
'Console.WriteLine(If(booleanVar, "Test returns True."))
```

 **Fehler-ID:** BC33107

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Wenn Sie den Code nicht ändern können, sodass das erste Argument ein Werte zulässt-Werttyp oder Verweistyp ist, sollten Sie in Erwägung gezogen werden, einen Ausdruck mit drei Argumenten oder eine- `If` Anweisung zu ändern `If...Then...Else` .

```vb
Console.WriteLine(If(choice1 < choice2, 1, 2))
Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))
```

## <a name="see-also"></a>Siehe auch

- [If-Operator](../operators/if-operator.md)
- [If...Then...Else-Anweisung](../statements/if-then-else-statement.md)
- [Auf NULL festlegbare Werttypen](../../programming-guide/language-features/data-types/nullable-value-types.md)
