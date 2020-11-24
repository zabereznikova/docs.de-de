---
title: Lambdaausdrücke in PLINQ und TPL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Func delegate, creating with lambda expression
- Action delegate, creating with lambda expression
- lambda expressions, with Action and Func
ms.assetid: 645b2c17-29d0-4ffa-8684-430743cc2f2d
ms.openlocfilehash: 9d884bbcb248effa41b24788d530151783280a53
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94817119"
---
# <a name="lambda-expressions-in-plinq-and-tpl"></a>Lambdaausdrücke in PLINQ und TPL

Die Task Parallel Library (TPL) enthält viele Methoden, die eine der <xref:System.Func%601?displayProperty=nameWithType>- oder <xref:System.Action?displayProperty=nameWithType>-Delegatenfamilien als Eingabeparameter annehmen. Sie verwenden diese Delegaten zur Übergabe der benutzerdefinierten Programmlogik an die parallele Schleife, Aufgabe oder Abfrage. In den Codebeispielen für TPL und PLINQ werden Lambdaausdrücke verwendet, um Instanzen dieser Delegaten als Inlinecodeblöcke zu erstellen. Dieses Thema bietet eine kurze Einführung in Func und Action und zeigt, wie Sie Lambdaausdrücke in der Task Parallel Library und in PLINQ verwenden.

> [!NOTE]
> Weitere allgemeine Informationen zu Delegaten finden Sie unter [Delegaten (C#-Programmierhandbuch)](../../csharp/programming-guide/delegates/index.md) und [Delegaten (Visual Basic)](../../visual-basic/programming-guide/language-features/delegates/index.md). Weitere Informationen zu Lambdaausdrücken in C# und Visual Basic finden Sie unter [Lambdaausdrücke (C#-Programmierhandbuch)](../../csharp/language-reference/operators/lambda-expressions.md) und [Lambdaausdrücke (Visual Basic)](../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).

## <a name="func-delegate"></a>Func-Delegat

Ein `Func`-Delegat kapselt eine Methode, die einen Wert zurückgibt. In einer `Func`-Signatur gibt der letzte bzw. der am weitesten rechts stehende Typparameter immer den Rückgabetyp an. Eine häufige Ursache von Compilerfehlern ist der Versuch, zwei Eingabeparameter an eine <xref:System.Func%602?displayProperty=nameWithType> zu übergeben. Dieser Typ akzeptiert jedoch nur einen Eingabeparameter. .NET definiert 17 Versionen von `Func`: <xref:System.Func%601?displayProperty=nameWithType>, <xref:System.Func%602?displayProperty=nameWithType>, <xref:System.Func%603?displayProperty=nameWithType> usw. bis <xref:System.Func%6017?displayProperty=nameWithType>.

## <a name="action-delegate"></a>Action-Delegat

Ein <xref:System.Action?displayProperty=nameWithType>-Delegat kapselt eine Methode (Sub in Visual Basic), die keinen Wert zurückgibt. In einer Signatur des Typs `Action` stellen die Typparameter nur Eingabeparameter dar. Wie `Func` definiert .NET 17 Versionen von `Action`, und zwar von einer Version ohne Typparameter bis zu einer mit 16 Typparametern.

## <a name="example"></a>Beispiel

Das folgende Beispiel für die <xref:System.Threading.Tasks.Parallel.ForEach%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%601%7D%2CSystem.Func%7B%60%600%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%601%2C%60%601%7D%2CSystem.Action%7B%60%601%7D%29?displayProperty=nameWithType>-Methode veranschaulicht, wie Func- und Action-Delegaten mithilfe von Lambdaausdrücken ausgedrückt werden.

[!code-csharp[System.Threading.Tasks.Parallel#02](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.threading.tasks.parallel/cs/parallelforeach.cs#02)]
[!code-vb[System.Threading.Tasks.Parallel#02](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.threading.tasks.parallel/vb/parallelforeach.vb#02)]

## <a name="see-also"></a>Weitere Informationen

- [Parallele Programmierung](index.md)
