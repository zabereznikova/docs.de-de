---
title: Standardwertausdrücke – C#-Referenz
description: Verwenden Sie Standardwertausdrücke, um den Standardwert eines Typs abzurufen.
ms.date: 03/13/2020
f1_keywords:
- default_CSharpKeyword
- default
helpviewer_keywords:
- default keyword [C#]
ms.openlocfilehash: f03971efa87bf03967c79512e44d22134dd80c17
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916862"
---
# <a name="default-value-expressions-c-reference"></a>Standardwertausdrücke (C#-Referenz)

Ein Standardwertausdruck erzeugt den [Standardwert](../builtin-types/default-values.md) für einen Typ. Es gibt zwei Arten von Standardwertausdrücken: den Aufruf des [default-Operators](#default-operator) und ein [default-Literal](#default-literal).

Außerdem verwenden Sie das Schlüsselwort `default` in einer [`switch`-Anweisung](../keywords/switch.md) als case-Standardbezeichnung.

## <a name="default-operator"></a>default-Operator

Das Argument für den `default`-Operator muss der Name eines Typs oder Typparameters sein, wie das folgende Beispiel zeigt:

[!code-csharp-interactive[default of T](snippets/shared/DefaultOperator.cs#WithOperand)]

## <a name="default-literal"></a>default-Literal

Ab C# 7.1 können Sie das `default`-Literal verwenden, um den Standardwert eines Typs zu erzeugen, wenn der Compiler den Ausdruckstyp ableiten kann. Der `default`-Literalausdruck erzeugt den gleichen Wert wie der `default(T)`-Ausdruck, wobei `T` der abgeleitete Typ ist. Sie können das `default`-Literal in den folgenden Fälle verwenden:

- Bei der Zuweisung oder Initialisierung einer Variablen.
- Bei der Deklaration des Standardwerts eines [optionalen Methodenparameters](../../methods.md#optional-parameters-and-arguments)
- Bei einem Methodenaufruf zum Bereitstellen eines Argumentwerts.
- In einer [`return`-Anweisung](../keywords/return.md) oder als Ausdruck in einem [Ausdruckskörpermember](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)

Im folgenden Beispiel wird die Verwendung des `default`-Literals veranschaulicht:

[!code-csharp-interactive[default literal](snippets/shared/DefaultOperator.cs#DefaultLiteral)]

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Ausdrücke mit Standardwert](~/_csharplang/spec/expressions.md#default-value-expressions) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

Weitere Informationen zum `default`-Literal finden Sie unter [Hinweis zum Featurevorschlag](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Operatoren und -Ausdrücke](index.md)
- [Standardwerte der C#-Typen](../builtin-types/default-values.md)
- [Generics in .NET](../../../standard/generics/index.md)
