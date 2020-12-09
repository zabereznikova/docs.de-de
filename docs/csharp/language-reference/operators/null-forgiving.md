---
description: '! NULL-toleranter Operator: C#-Referenz'
title: '! NULL-toleranter Operator: C#-Referenz'
ms.date: 11/13/2020
f1_keywords:
- nullForgiving_CSharpKeyword
helpviewer_keywords:
- null-forgiving operator [C#]
- '! operator [C#]'
ms.openlocfilehash: 7b8c634404cf2f214cc4bee5d754443e9302a723
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739515"
---
# <a name="-null-forgiving-operator-c-reference"></a>! NULL-toleranter Operator (C#-Referenz)

Der unäre Postfix-Operator `!` (der NULL-tolerante Operator) ist in C# 8.0 und höher verfügbar. In einem aktivierten [Nullable-Anmerkungskontext](../../nullable-references.md#nullable-annotation-context) verwenden Sie den NULL-toleranten Operator, um zu deklarieren, dass der Ausdruck `x` eines Verweistyps nicht `null` ist: `x!`. Der unäre Präfixoperator `!` ist der [Operator für logische Negation](boolean-logical-operators.md#logical-negation-operator-).

Der NULL-tolerante Operator besitzt zur Laufzeit keine Auswirkungen. Er wirkt sich nur auf die statische Flussanalyse des Compilers aus, indem der NULL-Status des Ausdrucks geändert wird. Zur Laufzeit wird Ausdruck `x!` in das Ergebnis des zugrunde liegenden Ausdrucks `x` ausgewertet.

Weitere Informationen zum Feature „Nullable-Verweistypen“ finden Sie unter [Nullable-Verweistypen](../builtin-types/nullable-reference-types.md).

## <a name="examples"></a>Beispiele

Einer der Anwendungsfälle des NULL-toleranten Operators besteht darin, die Argumentvalidierungslogik zu testen. Betrachten Sie beispielsweise die folgende Klasse:

[!code-csharp[Person class](snippets/shared/NullForgivingOperator.cs#PersonClass)]

Mit dem [MSTest-Testframework](../../../core/testing/unit-testing-with-mstest.md) können Sie den folgenden Test für die Validierungslogik im Konstruktor erstellen:

[!code-csharp[Person test](snippets/shared/NullForgivingOperator.cs#TestPerson)]

Ohne den NULL-toleranten Operator generiert der Compiler die folgende Warnung für den oben gezeigten Code: `Warning CS8625: Cannot convert null literal to non-nullable reference type`. Durch die Verwendung des NULL-toleranten Operators informieren Sie den Compiler darüber, dass die Übergabe von `null` erwartet wird und keine Warnung erfolgen sollte.

Sie können den NULL-toleranten Operator auch verwenden, wenn Sie definitiv wissen, dass ein Ausdruck nicht `null` sein kann, der Compiler aber nicht in der Lage ist, dies zu erkennen. Wenn die `IsValid`-Methode im folgenden Beispiel `true` zurückgibt, ist das Argument nicht `null`, und Sie können es sicher dereferenzieren:

[!code-csharp[Use null-forgiving operator](snippets/shared/NullForgivingOperator.cs#UseNullForgiving)]

Ohne den NULL-toleranten Operator generiert der Compiler die folgende Warnung für den `p.Name`-Code: `Warning CS8602: Dereference of a possibly null reference`.

Wenn Sie die `IsValid`-Methode ändern können, können Sie das [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute)-Attribut verwenden, um den Compiler darüber zu informieren, dass ein Argument der `IsValid`-Methode nicht `null` sein kann, wenn die Methode `true` zurückgibt:

[!code-csharp[Use an attribute](snippets/shared/NullForgivingOperator.cs#UseAttribute)]

Im vorherigen Beispiel müssen Sie den NULL-toleranten Operator nicht verwenden, da der Compiler über ausreichende Informationen verfügt, um zu ermitteln, dass `p` innerhalb der `if`-Anweisung nicht `null` sein kann. Weitere Informationen zu den Attributen, mit denen Sie zusätzliche Informationen zum NULL-Status einer Variablen bereitstellen können, finden Sie unter [Aktualisieren von APIs mit Attributen zum Definieren von NULL-Erwartungen](../attributes/nullable-analysis.md).

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Der NULL-tolerante Operator](~/_csharplang/proposals/csharp-9.0/nullable-reference-types-specification.md#the-null-forgiving-operator) des [Entwurfs der Spezifikation von Nullable-Verweistypen](~/_csharplang/proposals/csharp-9.0/nullable-reference-types-specification.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Operatoren und -Ausdrücke](index.md)
- [Tutorial: Entwerfen mit Nullable-Verweistypen](../../tutorials/nullable-reference-types.md)
