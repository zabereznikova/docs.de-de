---
title: Implizit typisierte Arrays – C#-Programmierhandbuch
description: Der Typ eines implizit typisierten Arrays in C# wird von den Elementen im Arrayinitialisierer abgeleitet. Verwenden Sie implizit typisierte Arrays in Abfrageausdrücken.
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], implicitly-typed
- implicitly-typed arrays [C#]
- C# language, implicitly typed arrays
ms.assetid: e05be95c-6732-403d-ae42-b35f057cbbea
ms.openlocfilehash: 1f14f68207dfb79c92eaa01ac2a8ffaa08facc03
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474708"
---
# <a name="implicitly-typed-arrays-c-programming-guide"></a><span data-ttu-id="7f1e0-104">Implizit typisierte Arrays (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="7f1e0-104">Implicitly Typed Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="7f1e0-105">Sie können ein implizit typisiertes Array erstellen, in dem der Typ der Arrayinstanz von den im Arrayinitialisierer angegebenen Elementen abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="7f1e0-105">You can create an implicitly-typed array in which the type of the array instance is inferred from the elements specified in the array initializer.</span></span> <span data-ttu-id="7f1e0-106">Die Regeln für implizit typisierte Variablen gelten auch für implizit typisierte Arrays.</span><span class="sxs-lookup"><span data-stu-id="7f1e0-106">The rules for any implicitly-typed variable also apply to implicitly-typed arrays.</span></span> <span data-ttu-id="7f1e0-107">Weitere Informationen zu finden Sie unter [Implizit typisierte lokale Variablen](../classes-and-structs/implicitly-typed-local-variables.md).</span><span class="sxs-lookup"><span data-stu-id="7f1e0-107">For more information, see [Implicitly Typed Local Variables](../classes-and-structs/implicitly-typed-local-variables.md).</span></span>

<span data-ttu-id="7f1e0-108">Implizit typisierte Arrays werden in der Regel in Abfrageausdrücken zusammen mit anonymen Typen sowie Objekt- und Auflistungsinitialisierern verwendet.</span><span class="sxs-lookup"><span data-stu-id="7f1e0-108">Implicitly-typed arrays are usually used in query expressions together with anonymous types and object and collection initializers.</span></span>

<span data-ttu-id="7f1e0-109">Die folgenden Beispiele zeigen, wie ein implizit typisiertes Array erstellt wird:</span><span class="sxs-lookup"><span data-stu-id="7f1e0-109">The following examples show how to create an implicitly-typed array:</span></span>

[!code-csharp[csProgGuideLINQ#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#37)]

<span data-ttu-id="7f1e0-110">Beachten Sie im vorherigen Beispiel, dass bei implizit typisierten Arrays auf der linken Seite der Initialisierungsanweisung keine eckigen Klammern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7f1e0-110">In the previous example, notice that with implicitly-typed arrays, no square brackets are used on the left side of the initialization statement.</span></span> <span data-ttu-id="7f1e0-111">Beachten Sie auch, dass verzweigte Arrays ebenso wie eindimensionale Arrays mithilfe von `new []` initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="7f1e0-111">Note also that jagged arrays are initialized by using `new []` just like single-dimension arrays.</span></span>

## <a name="implicitly-typed-arrays-in-object-initializers"></a><span data-ttu-id="7f1e0-112">Implizit typisierte Arrays in Objektinitialisierern</span><span class="sxs-lookup"><span data-stu-id="7f1e0-112">Implicitly-typed Arrays in Object Initializers</span></span>

<span data-ttu-id="7f1e0-113">Beim Erstellen eines anonymen Typs, der ein Array enthält, muss das Array im Objektinitialisierer des Typs implizit typisiert werden.</span><span class="sxs-lookup"><span data-stu-id="7f1e0-113">When you create an anonymous type that contains an array, the array must be implicitly typed in the type's object initializer.</span></span> <span data-ttu-id="7f1e0-114">Im folgenden Beispiel ist `contacts` ein implizit typisiertes Array aus anonymen Typen, von denen jeder ein Array mit dem Namen `PhoneNumbers` enthält.</span><span class="sxs-lookup"><span data-stu-id="7f1e0-114">In the following example, `contacts` is an implicitly-typed array of anonymous types, each of which contains an array named `PhoneNumbers`.</span></span> <span data-ttu-id="7f1e0-115">Beachten Sie, dass das Schlüsselwort `var` nicht in den Objektinitialisierern verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7f1e0-115">Note that the `var` keyword is not used inside the object initializers.</span></span>

[!code-csharp[csProgGuideLINQ#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#38)]

## <a name="see-also"></a><span data-ttu-id="7f1e0-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7f1e0-116">See also</span></span>

- [<span data-ttu-id="7f1e0-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="7f1e0-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="7f1e0-118">Implizit typisierte lokale Variablen</span><span class="sxs-lookup"><span data-stu-id="7f1e0-118">Implicitly Typed Local Variables</span></span>](../classes-and-structs/implicitly-typed-local-variables.md)
- [<span data-ttu-id="7f1e0-119">Arrays</span><span class="sxs-lookup"><span data-stu-id="7f1e0-119">Arrays</span></span>](./index.md)
- [<span data-ttu-id="7f1e0-120">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="7f1e0-120">Anonymous Types</span></span>](../classes-and-structs/anonymous-types.md)
- [<span data-ttu-id="7f1e0-121">Objekt- und Auflistungsinitialisierer</span><span class="sxs-lookup"><span data-stu-id="7f1e0-121">Object and Collection Initializers</span></span>](../classes-and-structs/object-and-collection-initializers.md)
- [<span data-ttu-id="7f1e0-122">var</span><span class="sxs-lookup"><span data-stu-id="7f1e0-122">var</span></span>](../../language-reference/keywords/var.md)
- [<span data-ttu-id="7f1e0-123">LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="7f1e0-123">LINQ in C#</span></span>](../../linq/index.md)
