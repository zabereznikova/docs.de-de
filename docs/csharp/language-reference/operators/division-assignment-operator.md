---
title: /=-Operator – C#-Referenz
ms.custom: seodec18
ms.date: 12/13/2018
f1_keywords:
- /=_CSharpKeyword
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
ms.openlocfilehash: ed4dd6c0c944b77543aae4de8d51534b4df4f4ef
ms.sourcegitcommit: d6e419f9d9cd7e8f21ebf5acde6d016c16332579
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2018
ms.locfileid: "53286519"
---
# <a name="-operator-c-reference"></a>Operator /= (C#-Referenz)

Der Divisionszuweisungsoperator

Ein Ausdruck mit dem Operator `/=`, z.B.

```csharp
x /= y
```

für die folgende Syntax:

```csharp
x = x / y
```

außer dass `x` nur einmal überprüft wird.

Der [Divisionsoperator](division-operator.md) `/` dividiert den ersten Operanden durch den zweiten Operanden. Er wird von allen numerischen Typen unterstützt.

Im folgenden Beispiel wird die Verwendung des `/=`-Operators veranschaulicht:

[!code-csharp-interactive[divide and assign](~/samples/snippets/csharp/language-reference/operators/DivisionExamples.cs#DivisionAssignment)]

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Wenn ein benutzerdefinierter Typ den [Divisionsoperator](division-operator.md) `/` [überlädt](../keywords/operator.md), wird auch der Divisionszuweisungsoperator `/=` implizit überladen. Ein benutzerdefinierter Typ kann den Divisionszuweisungsoperator nicht explizit überladen.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Verbundzuweisung](~/_csharplang/spec/expressions.md#compound-assignment) der [C#-Sprachspezifikation](../language-specification/index.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)
