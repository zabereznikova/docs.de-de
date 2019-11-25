---
title: Zuweisungsoperatoren (C#-Referenz)
ms.custom: seodec18
ms.date: 09/10/2019
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: 103bc823ab6a56d53a3f2ec05b8de9295f1de400
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039084"
---
# <a name="assignment-operators-c-reference"></a>Zuweisungsoperatoren (C#-Referenz)

Der Zuweisungsoperator `=` weist den Wert seines rechtsseitigen Operanden einer Variablen, einer [Eigenschaft](../../programming-guide/classes-and-structs/properties.md) oder einem, durch seinen linksseitigen Operanden angegebenen [Indexer](../../programming-guide/indexers/index.md)-Element zu. Das Ergebnis eines Zuweisungsausdrucks ist der Wert, der dem linksseitigen Operanden zugewiesen wird. Der Typ des rechtsseitigen Operanden muss mit dem Typ des linksseitigen Operanden übereinstimmen oder implizit in ihn konvertierbar sein.

Der Zuweisungsoperator `=` ist rechtsassoziativ, d. h. ein Ausdruck der Form

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

Im Fall des REF-Zuweisungsoperators müssen beide Operanden vom gleichen Typ sein.

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

## <a name="null-coalescing-assignment"></a>NULL-Coalescing-Zuweisung

Sie können ab C# 8.0 den NULL-Coalescing-Zuweisungsoperator `??=` verwenden, um den Wert des rechten Operanden dem linken Operanden nur dann zuzuweisen, wenn die Auswertung des linken Operanden `null` ergibt. Weitere Informationen finden Sie im Artikel zu den Operatoren [?? und ??=](null-coalescing-operator.md).

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Ein benutzerdefinierter Typ kann den Zuweisungsoperator [nicht überladen](operator-overloading.md). Ein benutzerdefinierter Typ kann jedoch eine implizite Konvertierung in einen anderen Typ definieren. Auf diese Weise kann der Wert eines benutzerdefinierten Typs einer Variablen, einer Eigenschaft oder einem Indexerelement eines anderen Typs zugewiesen werden. Weitere Informationen finden Sie unter [Benutzerdefinierte Konvertierungsoperatoren](user-defined-conversion-operators.md).

Ein benutzerdefinierter Typ kann einen Verbundzuweisungsoperator nicht explizit überladen. Wenn jedoch ein benutzerdefinierter Typ einen binären `op`-Operator überlädt, wird der `op=`-Operator, sofern vorhanden, ebenfalls implizit überladen.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Zuweisungsoperatoren](~/_csharplang/spec/expressions.md#assignment-operators) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

Weitere Informationen zum REF-Zuweiseungsoperator `= ref` finden Sie unter [Hinweis zum Featurevorschlag](~/_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Operatoren](index.md)
- [ref (C#-Referenz)](../keywords/ref.md)
