---
title: '?? Operator „-“: C#-Referenz'
ms.custom: seodec18
ms.date: 06/07/2019
f1_keywords:
- ??_CSharpKeyword
helpviewer_keywords:
- null-coalescing operator [C#]
- ?? operator [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
ms.openlocfilehash: a19b5558da36ffb11dabd1b9bec419a3623a0f17
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/12/2019
ms.locfileid: "67024987"
---
# <a name="-operator-c-reference"></a>?? Operator (C#-Referenz)

Der NULL-Zusammenfügungsoperator `??` gibt den Wert des linken Operanden zurück, wenn dieser nicht `null` ist. Andernfalls wertet der Operator den rechten Operanden aus und gibt dessen Ergebnis zurück. Der `??`-Operator wertet seinen rechten Operanden nicht aus, wenn der linke Operand auf einen Wert ungleich NULL ausgewertet wird.

Der NULL-Zusammenfügungsoperator ist rechtsassoziativ, d.h. ein Ausdruck der Form

```csharp
a ?? b ?? c
```

wird als ausgewertet,

```csharp
a ?? (b ?? c)
```

Der `??`-Operator kann in den folgenden Szenarien nützlich sein:

- In Ausdrücken mit den [NULL-bedingten Operatoren „?.“ und „?[]“](member-access-operators.md#null-conditional-operators--and-) können Sie den NULL-Zusammenfügungsoperator verwenden, um einen alternativen Ausdruck zum Auswerten für den Fall bereitzustellen, dass das Ergebnis des NULL-bedingten Vorgangs `null` ist:

  [!code-csharp-interactive[with null-conditional](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullConditional)]

- Wenn Sie mit [Nullable-Werttypen](../../programming-guide/nullable-types/index.md) arbeiten und den Wert eines zugrunde liegenden Werttyps bereitstellen müssen, verwenden Sie den NULL-Zusammenfügungsoperator, um den Wert für den Fall anzugeben, dass der Wert eines Nullable-Typs `null` ist:

  [!code-csharp-interactive[with nullable types](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullableTypes)]

  Verwenden Sie die <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType>-Methode, wenn der Wert, der verwenden werden soll, falls der Wert des Nullable-Typs `null` lautet, der Standardwert des zugrunde liegenden Werttyps sein soll.

- Ab C# 7.0 können Sie einen [`throw`Ausdruck](../keywords/throw.md#the-throw-expression) als rechten Operanden des NULL-Zusammenfügungsoperators verwenden, um den Code für die Überprüfung der Argumente präziser zu fassen:

  [!code-csharp[with throw expression](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithThrowExpression)]

  Das oben stehende Beispiel veranschaulicht auch, wie Sie [Ausdruckskörpermember](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) verwenden, um eine Eigenschaft zu definieren.

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Der NULL-Zusammenfügungsoperator kann nicht überladen werden.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie unter [NULL-Zusammenfügungsoperator](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) in der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Operatoren](index.md)
- [?.- und ?[]-Operatoren](member-access-operators.md#null-conditional-operators--and-)
- [?:-Operator](conditional-operator.md)
