---
title: Zugriffsdomäne – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- accessibility domain [C#]
ms.assetid: 8af779c1-275b-44be-a864-9edfbca71bcc
ms.openlocfilehash: 529d256a553c4000c77bcd5096db1a4d943874ff
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59141751"
---
# <a name="accessibility-domain-c-reference"></a><span data-ttu-id="cf732-102">Zugriffsdomäne (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="cf732-102">Accessibility Domain (C# Reference)</span></span>
<span data-ttu-id="cf732-103">Die Zugriffsdomäne eines Members gibt an, in welche Teile des Programms ein Member verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="cf732-103">The accessibility domain of a member specifies in which program sections a member can be referenced.</span></span> <span data-ttu-id="cf732-104">Wenn der Member in einem anderen Typ geschachtelt ist, wird seine Zugriffsdomäne sowohl durch das [Zugriffslevel](../../../csharp/language-reference/keywords/accessibility-levels.md) des Members als auch durch die Zugriffsdomäne des direkt enthaltenden Typs bestimmt.</span><span class="sxs-lookup"><span data-stu-id="cf732-104">If the member is nested within another type, its accessibility domain is determined by both the [accessibility level](../../../csharp/language-reference/keywords/accessibility-levels.md) of the member and the accessibility domain of the immediately containing type.</span></span>  
  
 <span data-ttu-id="cf732-105">Die Zugriffsdomäne eines Typs der obersten Ebene ist mindestens der Programmtext des Projekts, in dem er deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="cf732-105">The accessibility domain of a top-level type is at least the program text of the project that it is declared in.</span></span> <span data-ttu-id="cf732-106">Das bedeutet, dass die Domäne alle Quelldateien des Projekts enthält.</span><span class="sxs-lookup"><span data-stu-id="cf732-106">That is, the domain includes all of the source files of this project.</span></span> <span data-ttu-id="cf732-107">Die Zugriffsdomäne eines geschachtelten Typs ist mindestens der Programmtext des Typs, in dem er deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="cf732-107">The accessibility domain of a nested type is at least the program text of the type in which it is declared.</span></span> <span data-ttu-id="cf732-108">Das bedeutet, dass die Domäne der Typkörper ist, der alle geschachtelten Typen enthält.</span><span class="sxs-lookup"><span data-stu-id="cf732-108">That is, the domain is the type body, which includes all nested types.</span></span> <span data-ttu-id="cf732-109">Die Zugriffsdomäne eines geschachtelten Typs geht nie über die des enthaltenden Typs hinaus.</span><span class="sxs-lookup"><span data-stu-id="cf732-109">The accessibility domain of a nested type never exceeds that of the containing type.</span></span> <span data-ttu-id="cf732-110">Diese Konzepte werden im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="cf732-110">These concepts are demonstrated in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf732-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cf732-111">Example</span></span>  
 <span data-ttu-id="cf732-112">Dieses Beispiel enthält einen Typ der obersten Ebene `T1`, und zwei geschachtelte Klassen `M1` und `M2`.</span><span class="sxs-lookup"><span data-stu-id="cf732-112">This example contains a top-level type, `T1`, and two nested classes, `M1` and `M2`.</span></span> <span data-ttu-id="cf732-113">Die Klassen enthalten Felder mit unterschiedlichen deklarierten Zugriffen.</span><span class="sxs-lookup"><span data-stu-id="cf732-113">The classes contain fields that have different declared accessibilities.</span></span> <span data-ttu-id="cf732-114">In der `Main`-Methode folgt jeder Anweisung ein Kommentar, der die Zugriffsdomäne jedes Members angibt.</span><span class="sxs-lookup"><span data-stu-id="cf732-114">In the `Main` method, a comment follows each statement to indicate the accessibility domain of each member.</span></span> <span data-ttu-id="cf732-115">Beachten Sie, dass die Anweisungen, die versuchen, auf die Member zu verweisen, auf die nicht zugegriffen werden kann, auskommentiert werden. Wenn Sie die Compilerfehler anzeigen möchten, die durch Verweisen auf einen Member verursacht werden, auf den nicht zugegriffen werden kann, entfernen Sie die Kommentare nacheinander.</span><span class="sxs-lookup"><span data-stu-id="cf732-115">Notice that the statements that try to reference the inaccessible members are commented out. If you want to see the compiler errors caused by referencing an inaccessible member, remove the comments one at a time.</span></span>  
  
[!code-csharp[csrefKeywordsModifiers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#4)]
  
## <a name="c-language-specification"></a><span data-ttu-id="cf732-116">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="cf732-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cf732-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf732-117">See also</span></span>

- [<span data-ttu-id="cf732-118">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="cf732-118">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="cf732-119">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="cf732-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="cf732-120">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="cf732-120">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="cf732-121">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="cf732-121">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)
- [<span data-ttu-id="cf732-122">Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="cf732-122">Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/accessibility-levels.md)
- [<span data-ttu-id="cf732-123">Einschränkungen bei der Verwendung von Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="cf732-123">Restrictions on Using Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)
- [<span data-ttu-id="cf732-124">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="cf732-124">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="cf732-125">public</span><span class="sxs-lookup"><span data-stu-id="cf732-125">public</span></span>](../../../csharp/language-reference/keywords/public.md)
- [<span data-ttu-id="cf732-126">private</span><span class="sxs-lookup"><span data-stu-id="cf732-126">private</span></span>](../../../csharp/language-reference/keywords/private.md)
- [<span data-ttu-id="cf732-127">protected</span><span class="sxs-lookup"><span data-stu-id="cf732-127">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)
- [<span data-ttu-id="cf732-128">internal</span><span class="sxs-lookup"><span data-stu-id="cf732-128">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)
