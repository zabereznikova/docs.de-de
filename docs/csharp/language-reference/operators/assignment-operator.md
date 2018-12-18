---
title: =-Operator – C#-Referenz
ms.custom: seodec18
ms.date: 11/26/2018
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: 2c999e76a9238e6401e89af0faa81967b13a3995
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244387"
---
# <a name="-operator-c-reference"></a>Operator = (C#-Referenz)

Der Zuweisungsoperator `=` weist den Wert seines rechtsseitigen Operanden einer Variablen, einer [Eigenschaft](../../programming-guide/classes-and-structs/properties.md) oder einem, durch seinen linksseitigen Operanden angegebenen [Indexer](../../../csharp/programming-guide/indexers/index.md)-Element zu. Das Ergebnis eines Zuweisungsausdrucks ist der Wert, der dem linksseitigen Operanden zugewiesen wird. Der Typ des rechtsseitigen Operanden muss mit dem Typ des linksseitigen Operanden übereinstimmen oder implizit in ihn konvertierbar sein.

Der Zuweisungsoperator rechtsassoziativ, d.h. ein Ausdruck der Form

```csharp
a = b = c
```

wird als ausgewertet,

```csharp
a = (b = c)
```

Das folgende Beispiel zeigt die Verwendung des Zuweisungsoperators, um einer lokalen Variablen, einer Eigenschaft und einem Indexerelement Werte zuzuweisen:

[!code-csharp-interactive[assignment operator](~/samples/snippets/csharp/language-reference/operators/AssignmentExamples.cs#Assignments)]

## <a name="ref-assignment-operator"></a>ref-Zuweisungsoperator

Ab C# 7.3 können Sie mit dem ref-Zuweisungsoperator `= ref` eine [ref local](../keywords/ref.md#ref-locals)- oder [ref readonly local](../keywords/ref.md#ref-readonly-locals)-Variable neu zuweisen. Im folgenden Beispiel wird die Verwendung des ref-Zuweisungsoperators veranschaulicht:

[!code-csharp[ref assignment operator](~/samples/snippets/csharp/language-reference/operators/AssignmentExamples.cs#RefAssignment)]

Im Fall des ref-Zuweisungsoperators der Typ des linken und des rechten Operanden identisch sein.

Weitere Informationen finden Sie unter [Hinweis zum Featurevorschlag](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.3/ref-local-reassignment.md).

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Ein benutzerdefinierter Typ kann den Zuweisungsoperator nicht überladen. Ein benutzerdefinierter Typ kann jedoch eine implizite Konvertierung in einen anderen Typ definieren. Auf diese Weise kann der Wert eines benutzerdefinierten Typs einer Variablen, einer Eigenschaft oder einem Indexerelement eines anderen Typs zugewiesen werden. Weitere Informationen finden Sie im Artikel [Schlüsselwort „implicit“](../keywords/implicit.md).

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Einfache Zuweisung](~/_csharplang/spec/expressions.md#simple-assignment) der [C#-Sprachspezifikation](../language-specification/index.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)
- [ref (C#-Referenz)](../keywords/ref.md)
