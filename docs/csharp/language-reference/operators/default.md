---
title: 'default-Operator: C#-Referenz'
description: Verwendung des Default-Operators zum Erzeigen des Standardwerts eines Typs
ms.date: 08/01/2019
helpviewer_keywords:
- default keyword [C#]
ms.openlocfilehash: 0d37fe952e71e74f014872231a2e58663dea9d18
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398184"
---
# <a name="default-operator-c-reference"></a>default-Operator (C#-Referenz)

Der `default`-Operator dient zum Erzeugen des [Standardwerts](../builtin-types/default-values.md) eines Typs. Das Argument für den `default`-Operator muss der Name eines Typs oder ein Typparameter sein.

Im folgenden Beispiel wird die Verwendung des `default`-Operators veranschaulicht:

[!code-csharp-interactive[default of T](snippets/DefaultOperator.cs#WithOperand)]

Außerdem verwenden Sie das Schlüsselwort `default` in einer [`switch`-Anweisung](../keywords/switch.md) als case-Standardbezeichnung.

## <a name="default-literal"></a>Standardliteral

Ab C# 7.1 können Sie das `default`-Literal verwenden, um den Standardwert eines Typs zu erzeugen, wenn der Compiler den Ausdruckstyp ableiten kann. Der `default`-Literalausdruck erzeugt den gleichen Wert wie der `default(T)`-Ausdruck, wobei `T` der abgeleitete Typ ist. Sie können das `default`-Literal in den folgenden Fälle verwenden:

- Bei der Zuweisung oder Initialisierung einer Variablen.
- Bei der Deklaration des Standardwerts eines [optionalen Methodenparameters](../../methods.md#optional-parameters-and-arguments)
- Bei einem Methodenaufruf zum Bereitstellen eines Argumentwerts.
- In einer [`return`-Anweisung](../keywords/return.md) oder als Ausdruck in einem [Ausdruckskörpermember](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)

Im folgenden Beispiel wird die Verwendung des `default`-Literals veranschaulicht:

[!code-csharp-interactive[default literal](snippets/DefaultOperator.cs#DefaultLiteral)]

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Ausdrücke mit Standardwert](~/_csharplang/spec/expressions.md#default-value-expressions) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

Weitere Informationen zum `default`-Literal finden Sie unter [Hinweis zum Featurevorschlag](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).

## <a name="see-also"></a>Weitere Informationen

- [C#-Referenz](../index.md)
- [C#-Operatoren](index.md)
- [Standardwerte der C#-Typen](../builtin-types/default-values.md)
- [Generics in .NET](../../../standard/generics/index.md)
