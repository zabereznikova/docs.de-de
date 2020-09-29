---
description: Zugriffsdomäne – C#-Referenz
title: Zugriffsdomäne – C#-Referenz
ms.date: 07/20/2015
helpviewer_keywords:
- accessibility domain [C#]
ms.assetid: 8af779c1-275b-44be-a864-9edfbca71bcc
ms.openlocfilehash: 35fc619dd284ff9915662ba48fa06dd295cbbf42
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168841"
---
# <a name="accessibility-domain-c-reference"></a><span data-ttu-id="d6d18-103">Zugriffsdomäne (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="d6d18-103">Accessibility Domain (C# Reference)</span></span>

<span data-ttu-id="d6d18-104">Die Zugriffsdomäne eines Members gibt an, in welche Teile des Programms ein Member verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="d6d18-104">The accessibility domain of a member specifies in which program sections a member can be referenced.</span></span> <span data-ttu-id="d6d18-105">Wenn der Member in einem anderen Typ geschachtelt ist, wird seine Zugriffsdomäne sowohl durch das [Zugriffslevel](./accessibility-levels.md) des Members als auch durch die Zugriffsdomäne des direkt enthaltenden Typs bestimmt.</span><span class="sxs-lookup"><span data-stu-id="d6d18-105">If the member is nested within another type, its accessibility domain is determined by both the [accessibility level](./accessibility-levels.md) of the member and the accessibility domain of the immediately containing type.</span></span>  
  
 <span data-ttu-id="d6d18-106">Die Zugriffsdomäne eines Typs der obersten Ebene ist mindestens der Programmtext des Projekts, in dem er deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="d6d18-106">The accessibility domain of a top-level type is at least the program text of the project that it is declared in.</span></span> <span data-ttu-id="d6d18-107">Das bedeutet, dass die Domäne alle Quelldateien des Projekts enthält.</span><span class="sxs-lookup"><span data-stu-id="d6d18-107">That is, the domain includes all of the source files of this project.</span></span> <span data-ttu-id="d6d18-108">Die Zugriffsdomäne eines geschachtelten Typs ist mindestens der Programmtext des Typs, in dem er deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="d6d18-108">The accessibility domain of a nested type is at least the program text of the type in which it is declared.</span></span> <span data-ttu-id="d6d18-109">Das bedeutet, dass die Domäne der Typkörper ist, der alle geschachtelten Typen enthält.</span><span class="sxs-lookup"><span data-stu-id="d6d18-109">That is, the domain is the type body, which includes all nested types.</span></span> <span data-ttu-id="d6d18-110">Die Zugriffsdomäne eines geschachtelten Typs geht nie über die des enthaltenden Typs hinaus.</span><span class="sxs-lookup"><span data-stu-id="d6d18-110">The accessibility domain of a nested type never exceeds that of the containing type.</span></span> <span data-ttu-id="d6d18-111">Diese Konzepte werden im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d6d18-111">These concepts are demonstrated in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6d18-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d6d18-112">Example</span></span>  

 <span data-ttu-id="d6d18-113">Dieses Beispiel enthält einen Typ der obersten Ebene `T1`, und zwei geschachtelte Klassen `M1` und `M2`.</span><span class="sxs-lookup"><span data-stu-id="d6d18-113">This example contains a top-level type, `T1`, and two nested classes, `M1` and `M2`.</span></span> <span data-ttu-id="d6d18-114">Die Klassen enthalten Felder mit unterschiedlichen deklarierten Zugriffen.</span><span class="sxs-lookup"><span data-stu-id="d6d18-114">The classes contain fields that have different declared accessibilities.</span></span> <span data-ttu-id="d6d18-115">In der `Main`-Methode folgt jeder Anweisung ein Kommentar, der die Zugriffsdomäne jedes Members angibt.</span><span class="sxs-lookup"><span data-stu-id="d6d18-115">In the `Main` method, a comment follows each statement to indicate the accessibility domain of each member.</span></span> <span data-ttu-id="d6d18-116">Beachten Sie, dass die Anweisungen, die versuchen, auf die Member zu verweisen, auf die nicht zugegriffen werden kann, auskommentiert werden. Wenn Sie die Compilerfehler anzeigen möchten, die durch Verweisen auf einen Member verursacht werden, auf den nicht zugegriffen werden kann, entfernen Sie die Kommentare nacheinander.</span><span class="sxs-lookup"><span data-stu-id="d6d18-116">Notice that the statements that try to reference the inaccessible members are commented out. If you want to see the compiler errors caused by referencing an inaccessible member, remove the comments one at a time.</span></span>  
  
[!code-csharp[csrefKeywordsModifiers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#4)]
  
## <a name="c-language-specification"></a><span data-ttu-id="d6d18-117">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="d6d18-117">C# Language Specification</span></span>  

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d6d18-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d6d18-118">See also</span></span>

- [<span data-ttu-id="d6d18-119">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="d6d18-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d6d18-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="d6d18-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d6d18-121">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d6d18-121">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="d6d18-122">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="d6d18-122">Access Modifiers</span></span>](./access-modifiers.md)
- [<span data-ttu-id="d6d18-123">Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="d6d18-123">Accessibility Levels</span></span>](./accessibility-levels.md)
- [<span data-ttu-id="d6d18-124">Einschränkungen bei der Verwendung von Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="d6d18-124">Restrictions on Using Accessibility Levels</span></span>](./restrictions-on-using-accessibility-levels.md)
- [<span data-ttu-id="d6d18-125">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="d6d18-125">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="d6d18-126">public</span><span class="sxs-lookup"><span data-stu-id="d6d18-126">public</span></span>](./public.md)
- [<span data-ttu-id="d6d18-127">private</span><span class="sxs-lookup"><span data-stu-id="d6d18-127">private</span></span>](./private.md)
- [<span data-ttu-id="d6d18-128">protected</span><span class="sxs-lookup"><span data-stu-id="d6d18-128">protected</span></span>](./protected.md)
- [<span data-ttu-id="d6d18-129">internal</span><span class="sxs-lookup"><span data-stu-id="d6d18-129">internal</span></span>](./internal.md)
