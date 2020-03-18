---
title: Lambdaausdrücke in PLINQ und TPL
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Func delegate, creating with lambda expression
- Action delegate, creating with lambda expression
- lambda expressions, with Action and Func
ms.assetid: 645b2c17-29d0-4ffa-8684-430743cc2f2d
ms.openlocfilehash: 4e5be295a52edc1a7f0a0a3aa98f55335ae3e31b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "77452999"
---
# <a name="lambda-expressions-in-plinq-and-tpl"></a><span data-ttu-id="c469a-102">Lambdaausdrücke in PLINQ und TPL</span><span class="sxs-lookup"><span data-stu-id="c469a-102">Lambda Expressions in PLINQ and TPL</span></span>

<span data-ttu-id="c469a-103">Die Task Parallel Library (TPL) enthält viele Methoden, die eine der <xref:System.Func%601?displayProperty=nameWithType>- oder <xref:System.Action?displayProperty=nameWithType>-Delegatenfamilien als Eingabeparameter annehmen.</span><span class="sxs-lookup"><span data-stu-id="c469a-103">The Task Parallel Library (TPL) contains many methods that take one of the <xref:System.Func%601?displayProperty=nameWithType> or <xref:System.Action?displayProperty=nameWithType> family of delegates as input parameters.</span></span> <span data-ttu-id="c469a-104">Sie verwenden diese Delegaten zur Übergabe der benutzerdefinierten Programmlogik an die parallele Schleife, Aufgabe oder Abfrage.</span><span class="sxs-lookup"><span data-stu-id="c469a-104">You use these delegates to pass in your custom program logic to the parallel loop, task or query.</span></span> <span data-ttu-id="c469a-105">In den Codebeispielen für TPL und PLINQ werden Lambdaausdrücke verwendet, um Instanzen dieser Delegaten als Inlinecodeblöcke zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c469a-105">The code examples for TPL as well as PLINQ use lambda expressions to create instances of those delegates as inline code blocks.</span></span> <span data-ttu-id="c469a-106">Dieses Thema bietet eine kurze Einführung in Func und Action und zeigt, wie Sie Lambdaausdrücke in der Task Parallel Library und in PLINQ verwenden.</span><span class="sxs-lookup"><span data-stu-id="c469a-106">This topic provides a brief introduction to Func and Action and shows you how to use lambda expressions in the Task Parallel Library and PLINQ.</span></span>

> [!NOTE]
> <span data-ttu-id="c469a-107">Weitere allgemeine Informationen zu Delegaten finden Sie unter [Delegaten (C#-Programmierhandbuch)](../../csharp/programming-guide/delegates/index.md) und [Delegaten (Visual Basic)](../../visual-basic/programming-guide/language-features/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="c469a-107">For more information about delegates in general, see [Delegates](../../csharp/programming-guide/delegates/index.md) and [Delegates](../../visual-basic/programming-guide/language-features/delegates/index.md).</span></span> <span data-ttu-id="c469a-108">Weitere Informationen zu Lambdaausdrücken in C# und Visual Basic finden Sie unter [Lambdaausdrücke (C#-Programmierhandbuch)](../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) und [Lambdaausdrücke (Visual Basic)](../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="c469a-108">For more information about lambda expressions in C# and Visual Basic, see [Lambda Expressions](../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) and [Lambda Expressions](../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>

## <a name="func-delegate"></a><span data-ttu-id="c469a-109">Func-Delegat</span><span class="sxs-lookup"><span data-stu-id="c469a-109">Func Delegate</span></span>

<span data-ttu-id="c469a-110">Ein `Func`-Delegat kapselt eine Methode, die einen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="c469a-110">A `Func` delegate encapsulates a method that returns a value.</span></span> <span data-ttu-id="c469a-111">In einer `Func`-Signatur gibt der letzte bzw. der am weitesten rechts stehende Typparameter immer den Rückgabetyp an.</span><span class="sxs-lookup"><span data-stu-id="c469a-111">In a `Func` signature, the last, or rightmost, type parameter always specifies the return type.</span></span> <span data-ttu-id="c469a-112">Eine häufige Ursache von Compilerfehlern ist der Versuch, zwei Eingabeparameter an eine <xref:System.Func%602?displayProperty=nameWithType> zu übergeben. Dieser Typ akzeptiert jedoch nur einen Eingabeparameter.</span><span class="sxs-lookup"><span data-stu-id="c469a-112">One common cause of compiler errors is to attempt to pass in two input parameters to a <xref:System.Func%602?displayProperty=nameWithType>; in fact this type takes only one input parameter.</span></span> <span data-ttu-id="c469a-113">.NET definiert 17 Versionen von `Func`: <xref:System.Func%601?displayProperty=nameWithType>, <xref:System.Func%602?displayProperty=nameWithType>, <xref:System.Func%603?displayProperty=nameWithType> usw. bis <xref:System.Func%6017?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c469a-113">.NET defines 17 versions of `Func`: <xref:System.Func%601?displayProperty=nameWithType>, <xref:System.Func%602?displayProperty=nameWithType>, <xref:System.Func%603?displayProperty=nameWithType>, and so on up through <xref:System.Func%6017?displayProperty=nameWithType>.</span></span>

## <a name="action-delegate"></a><span data-ttu-id="c469a-114">Action-Delegat</span><span class="sxs-lookup"><span data-stu-id="c469a-114">Action Delegate</span></span>

<span data-ttu-id="c469a-115">Ein <xref:System.Action?displayProperty=nameWithType>-Delegat kapselt eine Methode (Sub in Visual Basic), die keinen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="c469a-115">A <xref:System.Action?displayProperty=nameWithType> delegate encapsulates a method (Sub in Visual Basic) that does not return a value.</span></span> <span data-ttu-id="c469a-116">In einer Signatur des Typs `Action` stellen die Typparameter nur Eingabeparameter dar.</span><span class="sxs-lookup"><span data-stu-id="c469a-116">In an `Action` type signature, the type parameters represent only input parameters.</span></span> <span data-ttu-id="c469a-117">Wie `Func` definiert .NET 17 Versionen von `Action`, und zwar von einer Version ohne Typparameter bis zu einer mit 16 Typparametern.</span><span class="sxs-lookup"><span data-stu-id="c469a-117">Like `Func`, .NET defines 17 versions of `Action`, from a version that has no type parameters up through a version that has 16 type parameters.</span></span>

## <a name="example"></a><span data-ttu-id="c469a-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c469a-118">Example</span></span>

<span data-ttu-id="c469a-119">Das folgende Beispiel für die <xref:System.Threading.Tasks.Parallel.ForEach%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%601%7D%2CSystem.Func%7B%60%600%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%601%2C%60%601%7D%2CSystem.Action%7B%60%601%7D%29?displayProperty=nameWithType>-Methode veranschaulicht, wie Func- und Action-Delegaten mithilfe von Lambdaausdrücken ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="c469a-119">The following example for the <xref:System.Threading.Tasks.Parallel.ForEach%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%601%7D%2CSystem.Func%7B%60%600%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%601%2C%60%601%7D%2CSystem.Action%7B%60%601%7D%29?displayProperty=nameWithType> method shows how to express both Func and Action delegates by using lambda expressions.</span></span>

[!code-csharp[System.Threading.Tasks.Parallel#02](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.threading.tasks.parallel/cs/parallelforeach.cs#02)]
[!code-vb[System.Threading.Tasks.Parallel#02](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.threading.tasks.parallel/vb/parallelforeach.vb#02)]

## <a name="see-also"></a><span data-ttu-id="c469a-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c469a-120">See also</span></span>

- [<span data-ttu-id="c469a-121">Parallele Programmierung</span><span class="sxs-lookup"><span data-stu-id="c469a-121">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)
