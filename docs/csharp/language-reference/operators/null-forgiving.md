---
title: '! NULL-toleranter Operator: C#-Referenz'
ms.date: 10/11/2019
f1_keywords:
- '!_CSharpKeyword'
helpviewer_keywords:
- null-forgiving operator [C#]
- '! operator [C#]'
ms.openlocfilehash: 2a8db2882968dbcbe6a8868ab6fe1c128c94a41f
ms.sourcegitcommit: e09dbff13f0b21b569a101f3b3c5efa174aec204
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/01/2020
ms.locfileid: "82624877"
---
# <a name="-null-forgiving-operator-c-reference"></a>! NULL-toleranter Operator (C#-Referenz)

Der unäre Postfix-Operator `!` (der NULL-tolerante Operator) ist in C# 8.0 und höher verfügbar. In einem aktivierten [Nullable-Anmerkungskontext](../../nullable-references.md#nullable-annotation-context) verwenden Sie den NULL-toleranten Operator, um zu deklarieren, dass der Ausdruck `x` eines Verweistyps nicht `null` ist: `x!`. Der unäre Präfixoperator `!` ist der [Operator für logische Negation](boolean-logical-operators.md#logical-negation-operator-).

Der NULL-tolerante Operator besitzt zur Laufzeit keine Auswirkungen. Er wirkt sich nur auf die statische Flussanalyse des Compilers aus, indem der NULL-Status des Ausdrucks geändert wird. Zur Laufzeit wird Ausdruck `x!` in das Ergebnis des zugrunde liegenden Ausdrucks `x` ausgewertet.

> [!NOTE]
> In C# 8 beendet der [NULL-tolerante Operator](member-access-operators.md#null-conditional-operators--and-) die Liste mit den vorangehenden NULL-bedingten Vorgängen. Der Ausdruck `x?.y!.z` wird beispielsweise als `(x?.y)!.z` analysiert. Aufgrund dieser Interpretation wird `z` ausgewertet, auch wenn `x` `null` ist, was zu <xref:System.NullReferenceException> führen kann.

Weitere Informationen zum Feature „Nullable-Verweistypen“ finden Sie unter [Nullable-Verweistypen](../builtin-types/nullable-reference-types.md).

## <a name="examples"></a>Beispiele

Einer der Anwendungsfälle des NULL-toleranten Operators besteht darin, die Argumentvalidierungslogik zu testen. Betrachten Sie beispielsweise die folgende Klasse:

[!code-csharp[Person class](snippets/NullForgivingOperator.cs#PersonClass)]

Mit dem [MSTest-Testframework](../../../core/testing/unit-testing-with-mstest.md) können Sie den folgenden Test für die Validierungslogik im Konstruktor erstellen:

[!code-csharp[Person test](snippets/NullForgivingOperator.cs#TestPerson)]

Ohne den NULL-toleranten Operator generiert der Compiler die folgende Warnung für den oben gezeigten Code: `Warning CS8625: Cannot convert null literal to non-nullable reference type`. Durch die Verwendung des NULL-toleranten Operators informieren Sie den Compiler darüber, dass die Übergabe von `null` erwartet wird und keine Warnung erfolgen sollte.

Sie können den NULL-toleranten Operator auch verwenden, wenn Sie definitiv wissen, dass ein Ausdruck nicht `null` sein kann, der Compiler aber nicht in der Lage ist, dies zu erkennen. Wenn die `IsValid`-Methode im folgenden Beispiel `true` zurückgibt, ist das Argument nicht `null`, und Sie können es sicher dereferenzieren:

[!code-csharp[Use null-forgiving operator](snippets/NullForgivingOperator.cs#UseNullForgiving)]

Ohne den NULL-toleranten Operator generiert der Compiler die folgende Warnung für den `p.Name`-Code: `Warning CS8602: Dereference of a possibly null reference`.

Wenn Sie die `IsValid`-Methode ändern können, können Sie das [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute)-Attribut verwenden, um den Compiler darüber zu informieren, dass ein Argument der `IsValid`-Methode nicht `null` sein kann, wenn die Methode `true` zurückgibt:

[!code-csharp[Use an attribute](snippets/NullForgivingOperator.cs#UseAttribute)]

Im vorherigen Beispiel müssen Sie den NULL-toleranten Operator nicht verwenden, da der Compiler über ausreichende Informationen verfügt, um zu ermitteln, dass `p` innerhalb der `if`-Anweisung nicht `null` sein kann. Weitere Informationen zu den Attributen, mit denen Sie zusätzliche Informationen zum NULL-Status einer Variablen bereitstellen können, finden Sie unter [Aktualisieren von APIs mit Attributen zum Definieren von NULL-Erwartungen](../attributes/nullable-analysis.md).

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Der NULL-tolerante Operator](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md#the-null-forgiving-operator) des [Entwurfs der Spezifikation von Nullable-Verweistypen](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Operatoren](index.md)
- [Tutorial: Entwerfen mit Nullable-Verweistypen](../../tutorials/nullable-reference-types.md)
