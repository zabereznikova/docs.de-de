---
description: 'Operator „=>“: C#-Referenz'
title: 'Operator „=>“: C#-Referenz'
ms.date: 01/22/2019
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.openlocfilehash: 6a4df3a4bd358b87f98ff1bd5a3f624b1029a73b
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128360"
---
# <a name="-operator-c-reference"></a>Operator „=>-“ (C#-Referenz)

Das Token `=>` wird auf zwei Weisen unterstützt: als [Lambdaoperator](#lambda-operator) und als Trennzeichen eines Membernamens und der Memberimplementierung in der [Definition eines Ausdruckskörpers](#expression-body-definition).

## <a name="lambda-operator"></a>Lambdaoperator

In [Lambdaausdrücken](lambda-expressions.md) trennt der Lambdaoperator `=>` die Eingabeparameter auf der linken Seite vom Lambdakörper auf der rechten Seite.

Im folgenden Beispiel wird das [LINQ](../../programming-guide/concepts/linq/index.md)-Feature mit der Methodensyntax verwendet, um die Verwendung von Lambdaausdrücken zu veranschaulichen:

[!code-csharp-interactive[infer types of input variables](snippets/shared/LambdaOperator.cs#InferredTypes)]

Eingabeparameter eines Lambdaausdrucks sind zur Kompilierzeit stark typisiert. Wenn der Compiler die Typen von Eingabeparametern wie im obigen Beispiel ableiten kann, können Sie die Typdeklarationen weglassen. Wenn Sie den Typ von Eingabeparametern festlegen müssen, müssen Sie ihn wie im folgenden Beispiel gezeigt für jeden Parameter festlegen:

[!code-csharp-interactive[specify types of input variables](snippets/shared/LambdaOperator.cs#ExplicitTypes)]

Im folgenden Beispiel wird gezeigt, wie ein Lambdaausdruck ohne Eingabeparameter definiert wird:

[!code-csharp-interactive[without input variables](snippets/shared/LambdaOperator.cs#WithoutInput)]

Weitere Informationen finden Sie unter [Lambdaausdrücke](lambda-expressions.md).

## <a name="expression-body-definition"></a>Ausdruckskörperdefinition

Eine Ausdruckstextdefinition hat die folgende allgemeine Syntax:

```csharp
member => expression;
```

Dabei ist `expression` ein gültiger Ausdruck. Der Rückgabetyp von `expression` muss implizit in den Rückgabetyp des Members konvertiert werden können. Wenn der Rückgabetyp des Members `void` ist oder der Member ein Konstruktor, Finalizer oder ein Eigenschaften- oder Indexer-`set`-Accessor ist, muss `expression` ein [*Anweisungsausdruck*](~/_csharplang/spec/statements.md#expression-statements) sein. Da das Ergebnis des Ausdrucks verworfen wird, kann der Rückgabetyp dieses Ausdrucks ein beliebiger Typ sein.

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

Ausdruckskörperdefinitionen für Methoden, Operatoren und schreibgeschützte Eigenschaften werden ab C# 6 unterstützt. Ausdruckskörperdefinitionen für Konstruktoren, Finalizer sowie Eigenschaften- und Indexeraccessors werden ab C# 7.0 unterstützt.

Weitere Informationen finden Sie unter [Ausdruckskörpermember](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Operator `=>` kann nicht überladen werden.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen zum Lambdaoperator finden Sie im Abschnitt [Anonyme Funktionsausdrücke](~/_csharplang/spec/expressions.md#anonymous-function-expressions) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Operatoren und -Ausdrücke](index.md)
