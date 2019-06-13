---
title: ?? -Operator – C#-Referenz
ms.custom: seodec18
ms.date: 06/07/2019
f1_keywords:
- ??_CSharpKeyword
helpviewer_keywords:
- null-coalescing operator [C#]
- ?? operator [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
ms.openlocfilehash: 8ca97261b348b7813ab179abbc1f2c5f535966a1
ms.sourcegitcommit: 5ae6affa0b171be3bb5f4729fb68ea4fe799f959
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2019
ms.locfileid: "66816012"
---
# <a name="-operator-c-reference"></a>?? operator (C#-Referenz)

Der Null-Sammeloperator `??` Wert des linken Operanden zurückgegeben, falls dies nicht der Fall `null`ist, andernfalls es der Rechte Operand ausgewertet wird und das Ergebnis zurückgibt. Die `??` Operator nicht seines rechtsseitigen Operanden ausgewertet, wenn der linke Operand ungleich Null ergibt.

Der Null-Sammeloperator ist rechtsassoziativ, d. h. ein Ausdruck der Form

```csharp
a ?? b ?? c
```

wird als ausgewertet,

```csharp
a ?? (b ?? c)
```

Die `??` Operator kann in den folgenden Szenarien nützlich sein:

- In Ausdrücken, mit der [nullbedingten Operatoren?. und?] ](member-access-operators.md#null-conditional-operators--and-), können Sie die Null-Sammeloperator, geben Sie einen alternativen Ausdruck zum Auswerten der Fall, dass das Ergebnis des Ausdrucks mit Null-bedingten Vorgängen `null`:

  [!code-csharp-interactive[with null-conditional](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullConditional)]

- Beim Arbeiten mit [auf NULL festlegbare Werttypen](../../programming-guide/nullable-types/index.md) und müssen einen Wert, der eine zugrunde liegende Werttyp Geben Sie mithilfe der Null-Sammeloperator Geben Sie den Wert aus, um anzugeben, falls ein nullable-Typ-Wert ist `null`:

  [!code-csharp-interactive[with nullable types](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullableTypes)]

  Verwenden der <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> Methode Wenn der Wert, der verwendet werden, wenn ein nullable-Typ-Wert ist `null` sollte der Standardwert der zugrunde liegende Werttyp sein.

- Beginnend mit C# 7.0 können Sie eine [ `throw` Ausdruck](../keywords/throw.md#the-throw-expression) als der Rechte Operand des Operators, der die Argument-Überprüfen von Code präziser werden, Null-Sammeloperator:

  [!code-csharp[with throw expression](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithThrowExpression)]

  Im vorherigen Beispiel wird auch veranschaulicht, wie [ausdruckskörpermember](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) eine Eigenschaft definieren.

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Der Null-Sammeloperator werden nicht überladen.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie unter [der null-Sammeloperator](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) Teil der [ C# Sprachspezifikation](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)
- [?.- und ?[]-Operatoren](member-access-operators.md#null-conditional-operators--and-)
- [?:-Operator](conditional-operator.md)
