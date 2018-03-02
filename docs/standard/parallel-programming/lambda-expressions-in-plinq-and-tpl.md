---
title: "Lambdaausdrücke in PLINQ und TPL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Func delegate, creating with lambda expression
- Action delegate, creating with lambda expression
- lambda expressions, with Action and Func
ms.assetid: 645b2c17-29d0-4ffa-8684-430743cc2f2d
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 364d23db41aac4733226189f7c8ae85d281b9887
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="lambda-expressions-in-plinq-and-tpl"></a><span data-ttu-id="558fe-102">Lambdaausdrücke in PLINQ und TPL</span><span class="sxs-lookup"><span data-stu-id="558fe-102">Lambda Expressions in PLINQ and TPL</span></span>
<span data-ttu-id="558fe-103">Die Task Parallel Library (TPL) enthält viele Methoden, die eine der <xref:System.Func%601?displayProperty=nameWithType>- oder <xref:System.Action?displayProperty=nameWithType>-Delegatenfamilien als Eingabeparameter annehmen.</span><span class="sxs-lookup"><span data-stu-id="558fe-103">The Task Parallel Library (TPL) contains many methods that take one of the <xref:System.Func%601?displayProperty=nameWithType> or <xref:System.Action?displayProperty=nameWithType> family of delegates as input parameters.</span></span> <span data-ttu-id="558fe-104">Sie verwenden diese Delegaten zur Übergabe der benutzerdefinierten Programmlogik an die parallele Schleife, Aufgabe oder Abfrage.</span><span class="sxs-lookup"><span data-stu-id="558fe-104">You use these delegates to pass in your custom program logic to the parallel loop, task or query.</span></span> <span data-ttu-id="558fe-105">In den Codebeispielen für TPL und PLINQ werden Lambdaausdrücke verwendet, um Instanzen dieser Delegaten als Inlinecodeblöcke zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="558fe-105">The code examples for TPL as well as PLINQ use lambda expressions to create instances of those delegates as inline code blocks.</span></span> <span data-ttu-id="558fe-106">Dieses Thema bietet eine kurze Einführung in Func und Action und zeigt, wie Sie Lambdaausdrücke in der Task Parallel Library und in PLINQ verwenden.</span><span class="sxs-lookup"><span data-stu-id="558fe-106">This topic provides a brief introduction to Func and Action and shows you how to use lambda expressions in the Task Parallel Library and PLINQ.</span></span>  
  
 <span data-ttu-id="558fe-107">**Hinweis** Weitere Informationen zu Delegaten im Allgemeinen finden Sie unter [Delegaten (C#-Programmierhandbuch)](../../csharp/programming-guide/delegates/index.md) und [Delegaten (Visual Basic)](../../visual-basic/programming-guide/language-features/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="558fe-107">**Note** For more information about delegates in general, see [Delegates](../../csharp/programming-guide/delegates/index.md) and [Delegates](../../visual-basic/programming-guide/language-features/delegates/index.md).</span></span> <span data-ttu-id="558fe-108">Weitere Informationen zu Lambdaausdrücken in C# und [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] finden Sie unter [Lambda-Ausdrücke (C#-Programmierhandbuch)](~/docs/csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) und [Lambda-Ausdrücke (Visual Basic)](~/docs/visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="558fe-108">For more information about lambda expressions in C# and [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)], see [Lambda Expressions](~/docs/csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) and [Lambda Expressions](~/docs/visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
## <a name="func-delegate"></a><span data-ttu-id="558fe-109">Func-Delegat</span><span class="sxs-lookup"><span data-stu-id="558fe-109">Func Delegate</span></span>  
 <span data-ttu-id="558fe-110">Ein `Func`-Delegat kapselt eine Methode, die einen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="558fe-110">A `Func` delegate encapsulates a method that returns a value.</span></span> <span data-ttu-id="558fe-111">In einer Func-Signatur gibt der letzte bzw. der am weitesten rechts stehende Typparameter immer den Rückgabetyp an.</span><span class="sxs-lookup"><span data-stu-id="558fe-111">In a Func signature, the last or rightmost type parameter always specifies the return type.</span></span> <span data-ttu-id="558fe-112">Eine häufige Ursache von Compilerfehlern ist der Versuch, zwei Eingabeparameter an eine <xref:System.Func%602?displayProperty=nameWithType> zu übergeben. Dieser Typ akzeptiert jedoch nur einen Eingabeparameter.</span><span class="sxs-lookup"><span data-stu-id="558fe-112">One common cause of compiler errors is to attempt to pass in two input parameters to a <xref:System.Func%602?displayProperty=nameWithType>; in fact this type takes only one input parameter.</span></span> <span data-ttu-id="558fe-113">Die Framework-Klassenbibliothek definiert 17 Versionen von `Func`: <xref:System.Func%601?displayProperty=nameWithType>, <xref:System.Func%602?displayProperty=nameWithType>, <xref:System.Func%603?displayProperty=nameWithType> usw. bis <xref:System.Func%6017?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="558fe-113">The Framework Class Library defines 17 versions of `Func`: <xref:System.Func%601?displayProperty=nameWithType>, <xref:System.Func%602?displayProperty=nameWithType>, <xref:System.Func%603?displayProperty=nameWithType>, and so on up through <xref:System.Func%6017?displayProperty=nameWithType>.</span></span>  
  
## <a name="action-delegate"></a><span data-ttu-id="558fe-114">Action-Delegat</span><span class="sxs-lookup"><span data-stu-id="558fe-114">Action Delegate</span></span>  
 <span data-ttu-id="558fe-115">Ein <xref:System.Action?displayProperty=nameWithType>-Delegat kapselt eine Methode (Untermethode in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), die keinen Wert oder [void](~/docs/csharp/language-reference/keywords/void.md) zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="558fe-115">A <xref:System.Action?displayProperty=nameWithType> delegate encapsulates a method (Sub in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) that does not return a value, or returns [void](~/docs/csharp/language-reference/keywords/void.md).</span></span> <span data-ttu-id="558fe-116">In einer Signatur vom Typ „Action“ stellen die Typparameter nur Eingabeparameter dar.</span><span class="sxs-lookup"><span data-stu-id="558fe-116">In an Action type signature, the type parameters represent only input parameters.</span></span> <span data-ttu-id="558fe-117">Die .NET Framework-Klassenbibliothek definiert wie bei Func 17 Versionen von Action, von einer Version ohne Typparameter bis zu einer Version mit 16 Typparametern.</span><span class="sxs-lookup"><span data-stu-id="558fe-117">Like Func, the Framework Class Library defines 17 versions of Action, from a version that has no type parameters up through a version that has 16 type parameters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="558fe-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="558fe-118">Example</span></span>  
 <span data-ttu-id="558fe-119">Das folgende Beispiel für die <xref:System.Threading.Tasks.Parallel.ForEach%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%601%7D%2CSystem.Func%7B%60%600%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%601%2C%60%601%7D%2CSystem.Action%7B%60%601%7D%29?displayProperty=nameWithType>-Methode veranschaulicht, wie Func- und Action-Delegaten mithilfe von Lambdaausdrücken ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="558fe-119">The following example for the <xref:System.Threading.Tasks.Parallel.ForEach%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%601%7D%2CSystem.Func%7B%60%600%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%601%2C%60%601%7D%2CSystem.Action%7B%60%601%7D%29?displayProperty=nameWithType> method shows how to express both Func and Action delegates by using lambda expressions.</span></span>  
  
 [!code-csharp[System.Threading.Tasks.Parallel#02](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.threading.tasks.parallel/cs/parallelforeach.cs#02)]
 [!code-vb[System.Threading.Tasks.Parallel#02](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.threading.tasks.parallel/vb/parallelforeach.vb#02)]  
  
## <a name="see-also"></a><span data-ttu-id="558fe-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="558fe-120">See Also</span></span>  
 [<span data-ttu-id="558fe-121">Parallele Programmierung</span><span class="sxs-lookup"><span data-stu-id="558fe-121">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)
