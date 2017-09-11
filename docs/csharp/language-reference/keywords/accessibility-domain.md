---
title: "Zugriffsdomäne (C#-Referenz)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- accessibility domain [C#]
ms.assetid: 8af779c1-275b-44be-a864-9edfbca71bcc
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 90faf22d8a7d515ae8bd062f0b95f4be5e051f79
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="accessibility-domain-c-reference"></a><span data-ttu-id="7b67b-102">Zugriffsdomäne (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="7b67b-102">Accessibility Domain (C# Reference)</span></span>
<span data-ttu-id="7b67b-103">Die Zugriffsdomäne eines Members gibt an, in welche Teile des Programms ein Member verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="7b67b-103">The accessibility domain of a member specifies in which program sections a member can be referenced.</span></span> <span data-ttu-id="7b67b-104">Wenn der Member in einem anderen Typ geschachtelt ist, wird seine Zugriffsdomäne sowohl durch das [Zugriffslevel](../../../csharp/language-reference/keywords/accessibility-levels.md) des Members als auch durch die Zugriffsdomäne des direkt enthaltenden Typs bestimmt.</span><span class="sxs-lookup"><span data-stu-id="7b67b-104">If the member is nested within another type, its accessibility domain is determined by both the [accessibility level](../../../csharp/language-reference/keywords/accessibility-levels.md) of the member and the accessibility domain of the immediately containing type.</span></span>  
  
 <span data-ttu-id="7b67b-105">Die Zugriffsdomäne eines Typs der obersten Ebene ist mindestens der Programmtext des Projekts, in dem er deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="7b67b-105">The accessibility domain of a top-level type is at least the program text of the project that it is declared in.</span></span> <span data-ttu-id="7b67b-106">Das bedeutet, dass die Domäne alle Quelldateien des Projekts enthält.</span><span class="sxs-lookup"><span data-stu-id="7b67b-106">That is, the domain includes all of the source files of this project.</span></span> <span data-ttu-id="7b67b-107">Die Zugriffsdomäne eines geschachtelten Typs ist mindestens der Programmtext des Typs, in dem er deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="7b67b-107">The accessibility domain of a nested type is at least the program text of the type in which it is declared.</span></span> <span data-ttu-id="7b67b-108">Das bedeutet, dass die Domäne der Typkörper ist, der alle geschachtelten Typen enthält.</span><span class="sxs-lookup"><span data-stu-id="7b67b-108">That is, the domain is the type body, which includes all nested types.</span></span> <span data-ttu-id="7b67b-109">Die Zugriffsdomäne eines geschachtelten Typs geht nie über die des enthaltenden Typs hinaus.</span><span class="sxs-lookup"><span data-stu-id="7b67b-109">The accessibility domain of a nested type never exceeds that of the containing type.</span></span> <span data-ttu-id="7b67b-110">Diese Konzepte werden im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="7b67b-110">These concepts are demonstrated in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b67b-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7b67b-111">Example</span></span>  
 <span data-ttu-id="7b67b-112">Dieses Beispiel enthält einen Typ der obersten Ebene `T1`, und zwei geschachtelte Klassen `M1` und `M2`.</span><span class="sxs-lookup"><span data-stu-id="7b67b-112">This example contains a top-level type, `T1`, and two nested classes, `M1` and `M2`.</span></span> <span data-ttu-id="7b67b-113">Die Klassen enthalten Felder mit unterschiedlichen deklarierten Zugriffen.</span><span class="sxs-lookup"><span data-stu-id="7b67b-113">The classes contain fields that have different declared accessibilities.</span></span> <span data-ttu-id="7b67b-114">In der `Main`-Methode folgt jeder Anweisung ein Kommentar, der die Zugriffsdomäne jedes Members angibt.</span><span class="sxs-lookup"><span data-stu-id="7b67b-114">In the `Main` method, a comment follows each statement to indicate the accessibility domain of each member.</span></span> <span data-ttu-id="7b67b-115">Beachten Sie, dass die Anweisungen, die versuchen, auf die Member zu verweisen, auf die nicht zugegriffen werden kann, auskommentiert werden.</span><span class="sxs-lookup"><span data-stu-id="7b67b-115">Notice that the statements that try to reference the inaccessible members are commented out.</span></span> <span data-ttu-id="7b67b-116">Wenn Sie die Compilerfehler anzeigen möchten, die durch Verweisen auf einen Member verursacht werden, auf den nicht zugegriffen werden kann, entfernen Sie die Kommentare nacheinander.</span><span class="sxs-lookup"><span data-stu-id="7b67b-116">If you want to see the compiler errors caused by referencing an inaccessible member, remove the comments one at a time.</span></span>  
  
 <span data-ttu-id="7b67b-117">[!code-cs[csrefKeywordsModifiers#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/accessibility-domain_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="7b67b-117">[!code-cs[csrefKeywordsModifiers#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/accessibility-domain_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="7b67b-118">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="7b67b-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7b67b-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b67b-119">See Also</span></span>  
 <span data-ttu-id="7b67b-120">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="7b67b-120">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="7b67b-121">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="7b67b-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="7b67b-122">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="7b67b-122">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="7b67b-123">[Zugriffsmodifizierer](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="7b67b-123">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="7b67b-124">[Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="7b67b-124">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) </span></span>  
 <span data-ttu-id="7b67b-125">[Einschränkungen bei der Verwendung von Zugriffsebenen](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="7b67b-125">[Restrictions on Using Accessibility Levels](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md) </span></span>  
 <span data-ttu-id="7b67b-126">[Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="7b67b-126">[Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span></span>  
 <span data-ttu-id="7b67b-127">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="7b67b-127">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="7b67b-128">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="7b67b-128">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="7b67b-129">[protected](../../../csharp/language-reference/keywords/protected.md) </span><span class="sxs-lookup"><span data-stu-id="7b67b-129">[protected](../../../csharp/language-reference/keywords/protected.md) </span></span>  
 [<span data-ttu-id="7b67b-130">internal</span><span class="sxs-lookup"><span data-stu-id="7b67b-130">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)

