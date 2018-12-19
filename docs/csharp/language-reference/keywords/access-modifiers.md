---
title: Zugriffsmodifizierer – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- access modifiers [C#]
ms.assetid: 61c3fa51-c00f-48cb-9b49-c805dedd62d7
ms.openlocfilehash: 0fb435a35b928cb78511d8969f1dfce9f94869eb
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53242021"
---
# <a name="access-modifiers-c-reference"></a><span data-ttu-id="eabcd-102">Zugriffsmodifizierer (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="eabcd-102">Access Modifiers (C# Reference)</span></span>
<span data-ttu-id="eabcd-103">Zugriffsmodifizierer sind Schlüsselwörter, die verwendet werden, um die deklarierte Zugriffsart eines Members oder Typs anzugeben.</span><span class="sxs-lookup"><span data-stu-id="eabcd-103">Access modifiers are keywords used to specify the declared accessibility of a member or a type.</span></span> <span data-ttu-id="eabcd-104">In diesem Abschnitt werden die vier Zugriffsmodifizierer beschrieben:</span><span class="sxs-lookup"><span data-stu-id="eabcd-104">This section introduces the four access modifiers:</span></span>  
  
-   `public`
-   `protected`
-   `internal`
-   `private`
  
 <span data-ttu-id="eabcd-105">Die folgenden sechs Zugriffsebenen können mit den Zugriffsmodifizierern angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="eabcd-105">The following six accessibility levels can be specified using the access modifiers:</span></span>  
  
- <span data-ttu-id="eabcd-106">[`public`](public.md): Der Zugriff ist nicht beschränkt.</span><span class="sxs-lookup"><span data-stu-id="eabcd-106">[`public`](public.md): Access is not restricted.</span></span>  
  
- <span data-ttu-id="eabcd-107">[`protected`](protected.md): Der Zugriff ist auf die enthaltende Klasse oder auf Typen beschränkt, die von der enthaltenden Klasse abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="eabcd-107">[`protected`](protected.md): Access is limited to the containing class or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="eabcd-108">[`internal`](internal.md): Der Zugriff ist auf die aktuelle Assembly beschränkt.</span><span class="sxs-lookup"><span data-stu-id="eabcd-108">[`internal`](internal.md): Access is limited to the current assembly.</span></span>  
  
- <span data-ttu-id="eabcd-109">[`protected internal`](protected-internal.md): Der Zugriff ist auf die aktuelle Assembly oder auf Typen beschränkt, die von der enthaltenden Klasse abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="eabcd-109">[`protected internal`](protected-internal.md): Access is limited to the current assembly or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="eabcd-110">[`private`](private.md): Der Zugriff ist auf die enthaltende Klasse beschränkt.</span><span class="sxs-lookup"><span data-stu-id="eabcd-110">[`private`](private.md): Access is limited to the containing type.</span></span>  

- <span data-ttu-id="eabcd-111">[`private protected`](private-protected.md): Der Zugriff ist auf die enthaltende Klasse oder auf Typen beschränkt, die von der enthaltenden Klasse innerhalb der aktuellen Assembly abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="eabcd-111">[`private protected`](private-protected.md): Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span>  
  
 <span data-ttu-id="eabcd-112">In diesem Abschnitt wird Folgendes beschrieben:</span><span class="sxs-lookup"><span data-stu-id="eabcd-112">This section also introduces the following:</span></span>  
  
-   <span data-ttu-id="eabcd-113">[Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md): Deklarieren von sechs Zugriffsebenen mithilfe der vier Zugriffsmodifizierer.</span><span class="sxs-lookup"><span data-stu-id="eabcd-113">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md): Using the four access modifiers to declare six levels of accessibility.</span></span>  
  
-   <span data-ttu-id="eabcd-114">[Zugriffsdomäne](../../../csharp/language-reference/keywords/accessibility-domain.md): Gibt an, in welchen Teilen des Programms auf ein Member verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="eabcd-114">[Accessibility Domain](../../../csharp/language-reference/keywords/accessibility-domain.md): Specifies where, in the program sections, a member can be referenced.</span></span>  
  
-   <span data-ttu-id="eabcd-115">[Einschränkungen bei der Verwendung von Zugriffsebenen](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): Ein Überblick über die Einschränkungen bei der Verwendung deklarierter Zugriffsebenen.</span><span class="sxs-lookup"><span data-stu-id="eabcd-115">[Restrictions on Using Accessibility Levels](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): A summary of the restrictions on using declared accessibility levels.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eabcd-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eabcd-116">See Also</span></span>  
- [<span data-ttu-id="eabcd-117">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="eabcd-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="eabcd-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="eabcd-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="eabcd-119">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="eabcd-119">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="eabcd-120">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="eabcd-120">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
- [<span data-ttu-id="eabcd-121">Zugriffsschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="eabcd-121">Access Keywords</span></span>](../../../csharp/language-reference/keywords/access-keywords.md)  
- [<span data-ttu-id="eabcd-122">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="eabcd-122">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
