---
description: partial-Methode – C#-Referenz
title: partial-Methode – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- partialmethod_CSharpKeyword
helpviewer_keywords:
- partial methods [C#]
ms.assetid: 43f40242-17e0-4452-8573-090503ad3137
ms.openlocfilehash: d6c433fd30f6ec51355bdefee90d815783487c1b
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134379"
---
# <a name="partial-method-c-reference"></a><span data-ttu-id="2e55c-103">partial-Methode (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="2e55c-103">partial method (C# Reference)</span></span>

<span data-ttu-id="2e55c-104">Bei partiellen Methoden wird die Signatur in einem Teil eines partiellen Typs definiert, und die Implementierung wird in einem anderen Teil des Typs definiert.</span><span class="sxs-lookup"><span data-stu-id="2e55c-104">A partial method has its signature defined in one part of a partial type, and its implementation defined in another part of the type.</span></span> <span data-ttu-id="2e55c-105">Mit partiellen Methoden können Klassen-Designer Methoden-Hooks bereitstellen, die Ereignis-Handlern ähneln und die Entwickler ggf. implementieren können.</span><span class="sxs-lookup"><span data-stu-id="2e55c-105">Partial methods enable class designers to provide method hooks, similar to event handlers, that developers may decide to implement or not.</span></span> <span data-ttu-id="2e55c-106">Wenn der Entwickler keine Implementierung angibt, entfernt der Compiler die Signatur bei der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="2e55c-106">If the developer does not supply an implementation, the compiler removes the signature at compile time.</span></span> <span data-ttu-id="2e55c-107">Die folgenden Bedingungen gelten für partielle Methoden:</span><span class="sxs-lookup"><span data-stu-id="2e55c-107">The following conditions apply to partial methods:</span></span>

- <span data-ttu-id="2e55c-108">Die Signaturen in beiden Teilen des partiellen Typs müssen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e55c-108">Signatures in both parts of the partial type must match.</span></span>

- <span data-ttu-id="2e55c-109">Die Methode muss "void" zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="2e55c-109">The method must return void.</span></span>

- <span data-ttu-id="2e55c-110">Es sind keine Zugriffsmodifizierer zulässig.</span><span class="sxs-lookup"><span data-stu-id="2e55c-110">No access modifiers are allowed.</span></span> <span data-ttu-id="2e55c-111">Partielle Methoden sind implizit privat.</span><span class="sxs-lookup"><span data-stu-id="2e55c-111">Partial methods are implicitly private.</span></span>

<span data-ttu-id="2e55c-112">Im folgenden Beispiel wird eine partielle Methode veranschaulicht, die in zwei Teilen einer partiellen Klasse definiert ist:</span><span class="sxs-lookup"><span data-stu-id="2e55c-112">The following example shows a partial method defined in two parts of a partial class:</span></span>

[!code-csharp[csrefKeywordsContextual#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#9)]

<span data-ttu-id="2e55c-113">Weitere Informationen finden Sie unter [Partielle Klassen und Methoden](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="2e55c-113">For more information, see [Partial Classes and Methods](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2e55c-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e55c-114">See also</span></span>

- [<span data-ttu-id="2e55c-115">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="2e55c-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="2e55c-116">partial-Typ</span><span class="sxs-lookup"><span data-stu-id="2e55c-116">partial type</span></span>](partial-type.md)
