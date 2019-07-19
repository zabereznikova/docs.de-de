---
title: =-Operator – C#-Referenz
ms.custom: seodec18
ms.date: 06/21/2019
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: 1277b35723777760deebb6606ddc90bd21e654ec
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744116"
---
# <a name="-operator-c-reference"></a>=-Operator (C#-Referenz)

Der Zuweisungsoperator `=` weist den Wert seines rechtsseitigen Operanden einer Variablen, einer [Eigenschaft](../../programming-guide/classes-and-structs/properties.md) oder einem, durch seinen linksseitigen Operanden angegebenen [Indexer](../../../csharp/programming-guide/indexers/index.md)-Element zu. Das Ergebnis eines Zuweisungsausdrucks ist der Wert, der dem linksseitigen Operanden zugewiesen wird. Der Typ des rechtsseitigen Operanden muss mit dem Typ des linksseitigen Operanden übereinstimmen oder implizit in ihn konvertierbar sein.

Der Zuweisungsoperator rechtsassoziativ, d.h. ein Ausdruck der Form

```csharp
a = b = c
```

wird als ausgewertet,

```csharp
a = (b = c)
```

Das folgende Beispiel zeigt die Verwendung des Zuweisungsoperators mit einer lokalen Variablen, einer Eigenschaft und einem Indexerelement als linksseitigem Operanden:

[!code-csharp-interactive[simple assignment](~/samples/csharp/language-reference/operators/AssignmentOperator.cs#Simple)]

## <a name="ref-assignment-operator"></a>ref-Zuweisungsoperator

Ab C# 7.3 können Sie mit dem ref-Zuweisungsoperator `= ref` eine [ref local](../keywords/ref.md#ref-locals)- oder [ref readonly local](../keywords/ref.md#ref-readonly-locals)-Variable neu zuweisen. Im folgenden Beispiel wird die Verwendung des ref-Zuweisungsoperators veranschaulicht:

[!code-csharp[ref assignment operator](~/samples/csharp/language-reference/operators/AssignmentOperator.cs#RefAssignment)]

Im Fall des ref-Zuweisungsoperators muss der Typ beider Operanden identisch sein.

Weitere Informationen finden Sie unter [Hinweis zum Featurevorschlag](~/_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).

## <a name="compound-assignment"></a>Verbundzuweisung

Bei einem binären Operator `op` entspricht ein Verbundzuweisungsausdruck der Form

```csharp
x op= y
```

für die folgende Syntax:

```csharp
x = x op y
```

außer dass `x` nur einmal überprüft wird.

Verbundzuweisungen werden von [arithmetischen](arithmetic-operators.md#compound-assignment), [logischen booleschen](boolean-logical-operators.md#compound-assignment) und [bitweisen logischen und Verschiebungs-](bitwise-and-shift-operators.md#compound-assignment)-Operatoren unterstützt.

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Ein benutzerdefinierter Typ kann den Zuweisungsoperator nicht überladen. Ein benutzerdefinierter Typ kann jedoch eine implizite Konvertierung in einen anderen Typ definieren. Auf diese Weise kann der Wert eines benutzerdefinierten Typs einer Variablen, einer Eigenschaft oder einem Indexerelement eines anderen Typs zugewiesen werden. Weitere Informationen finden Sie unter [Benutzerdefinierte Konvertierungsoperatoren](user-defined-conversion-operators.md).

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Zuweisungsoperatoren](~/_csharplang/spec/expressions.md#assignment-operators) der [C#-Sprachspezifikation](../language-specification/index.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Operatoren](index.md)
- [ref (C#-Referenz)](../keywords/ref.md)
