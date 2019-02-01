---
title: =&gt;-Operator – C#-Referenz
ms.custom: seodec18
ms.date: 01/22/2019
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.openlocfilehash: fa2e149f5b19e80e3171d08519be3ae249d2a112
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54540805"
---
# <a name="gt-operator-c-reference"></a>=&gt;-Operator (C#-Referenz)

Das Token `=>` wird auf zwei Weisen unterstützt: als Lambdaoperator und als Trennzeichen eines Membernamens und der Memberimplementierung in der Definition eines Ausdruckskörpers.

## <a name="lambda-operator"></a>Lambdaoperator

In [Lambdaausdrücken](../../programming-guide/statements-expressions-operators/lambda-expressions.md) trennt der Lambdaoperator `=>` die Eingabevariablen auf der linken Seite vom Lambdakörper auf der rechten Seite.

Im folgenden Beispiel wird das [LINQ](../../programming-guide/concepts/linq/index.md)-Feature mit der Methodensyntax verwendet, um die Verwendung von Lambdaausdrücken zu veranschaulichen:

[!code-csharp-interactive[infer types of input variables](~/samples/snippets/csharp/language-reference/operators/LambdaOperatorExamples.cs#InferredTypes)]

Eingabevariablen von Lambdaausdrücken sind zur Kompilierzeit stark typisiert. Wenn der Compiler die Typen von Eingabevariablen wie im obigen Beispiel ableiten kann, können Sie die Typdeklarationen weglassen. Wenn Sie den Typ von Eingabevariablen festlegen müssen, müssen Sie ihn wie im folgenden Beispiel gezeigt für jede Variable festlegen:

[!code-csharp-interactive[specify types of input variables](~/samples/snippets/csharp/language-reference/operators/LambdaOperatorExamples.cs#ExplicitTypes)]

Im folgenden Beispiel wird gezeigt, wie ein Lambdaausdruck ohne Eingabevariablen definiert wird:

[!code-csharp-interactive[without input variables](~/samples/snippets/csharp/language-reference/operators/LambdaOperatorExamples.cs#WithoutInput)]

Weitere Informationen finden Sie unter [Lambdaausdrücke](../../programming-guide/statements-expressions-operators/lambda-expressions.md).

## <a name="expression-body-definition"></a>Ausdruckskörperdefinition

Eine Ausdruckstextdefinition hat die folgende allgemeine Syntax:

```csharp
member => expression;
```

wobei *expression* ein gültiger Ausdruck ist. Beachten Sie, dass *expression* nur dann ein *Anweisungsausdruck* sein kann, wenn der Rückgabetyp des Members `void` ist oder der Member ein Konstruktor, Finalizer oder ein `set`-Eigenschaftenaccessor ist.

Im folgenden Beispiel wird eine Ausdruckskörperdefinition für eine `Person.ToString`-Methode angegeben:

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

Diese ist eine kompakte Version der folgenden Methodendefinition:

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```

Ausdruckskörperdefinitionen für Methoden und schreibgeschützte Eigenschaften werden ab C# 6 unterstützt. Ausdruckskörperdefinitionen für Konstruktoren, Finalizer, Eigenschaftenaccessors und Indizes werden ab C# 7.0 unterstützt.

Weitere Informationen finden Sie unter [Ausdruckskörpermember](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Operator `=>` kann nicht überladen werden.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Anonyme Funktionsausdrücke](~/_csharplang/spec/expressions.md#anonymous-function-expressions) der [C#-Sprachspezifikation](../language-specification/index.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)
- [Lambda-Ausdrücke](../../programming-guide/statements-expressions-operators/lambda-expressions.md)
- [Ausdruckskörpermember](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)