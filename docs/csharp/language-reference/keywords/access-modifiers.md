---
title: Zugriffsmodifizierer (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- access modifiers [C#]
ms.assetid: 61c3fa51-c00f-48cb-9b49-c805dedd62d7
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d63cf724a2364059e5f3327254a9ec95f7493e5e
ms.sourcegitcommit: d2da0142247ef42a219a5d2907f153e62dc6ea0d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2018
---
# <a name="access-modifiers-c-reference"></a><span data-ttu-id="1728d-102">Zugriffsmodifizierer (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="1728d-102">Access Modifiers (C# Reference)</span></span>
<span data-ttu-id="1728d-103">Zugriffsmodifizierer sind Schlüsselwörter, die verwendet werden, um die deklarierte Zugriffsart eines Members oder Typs anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1728d-103">Access modifiers are keywords used to specify the declared accessibility of a member or a type.</span></span> <span data-ttu-id="1728d-104">In diesem Abschnitt werden die vier Zugriffsmodifizierer beschrieben:</span><span class="sxs-lookup"><span data-stu-id="1728d-104">This section introduces the four access modifiers:</span></span>  
  
-   `public`
-   `protected`
-   `internal`
-   `private`
  
 <span data-ttu-id="1728d-105">Die folgenden sechs Zugriffsebenen können mit den Zugriffsmodifizierern angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="1728d-105">The following six accessibility levels can be specified using the access modifiers:</span></span>  
  
- <span data-ttu-id="1728d-106">[`public`](public.md): Der Zugriff ist nicht beschränkt.</span><span class="sxs-lookup"><span data-stu-id="1728d-106">[`public`](public.md): Access is not restricted.</span></span>  
  
- <span data-ttu-id="1728d-107">[`protected`](protected.md): Der Zugriff ist auf die enthaltende Klasse oder auf Typen beschränkt, die von der enthaltenden Klasse abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="1728d-107">[`protected`](protected.md): Access is limited to the containing class or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="1728d-108">[`internal`](internal.md): Der Zugriff ist auf die aktuelle Assembly beschränkt.</span><span class="sxs-lookup"><span data-stu-id="1728d-108">[`internal`](internal.md): Access is limited to the current assembly.</span></span>  
  
- <span data-ttu-id="1728d-109">[`protected internal`](protected-internal.md): Der Zugriff ist auf die aktuelle Assembly oder auf Typen beschränkt, die von der enthaltenden Klasse abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="1728d-109">[`protected internal`](protected-internal.md): Access is limited to the current assembly or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="1728d-110">[`private`](private.md): Der Zugriff ist auf den enthaltenden Typ beschränkt.</span><span class="sxs-lookup"><span data-stu-id="1728d-110">[`private`](private.md): Access is limited to the containing type.</span></span>  

- <span data-ttu-id="1728d-111">[`private protected`](private-protected.md): Der Zugriff ist auf die enthaltende Klasse oder auf Typen beschränkt, die von der enthaltenden Klasse innerhalb der aktuellen Assembly abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="1728d-111">[`private protected`](private-protected.md): Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span>  
  
 <span data-ttu-id="1728d-112">In diesem Abschnitt wird Folgendes beschrieben:</span><span class="sxs-lookup"><span data-stu-id="1728d-112">This section also introduces the following:</span></span>  
  
-   <span data-ttu-id="1728d-113">[Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md): Deklarieren von sechs Zugriffsebenen mithilfe der vier Zugriffsmodifizierer.</span><span class="sxs-lookup"><span data-stu-id="1728d-113">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md): Using the four access modifiers to declare six levels of accessibility.</span></span>  
  
-   <span data-ttu-id="1728d-114">[Zugriffsdomäne](../../../csharp/language-reference/keywords/accessibility-domain.md): Gibt an, in welche Teile des Programms ein Member verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="1728d-114">[Accessibility Domain](../../../csharp/language-reference/keywords/accessibility-domain.md): Specifies where, in the program sections, a member can be referenced.</span></span>  
  
-   <span data-ttu-id="1728d-115">[Einschränkungen bei der Verwendung von Zugriffsebenen](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): Ein Überblick über die Einschränkungen bei der Verwendung deklarierter Zugriffsebenen.</span><span class="sxs-lookup"><span data-stu-id="1728d-115">[Restrictions on Using Accessibility Levels](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): A summary of the restrictions on using declared accessibility levels.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1728d-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1728d-116">See Also</span></span>  
 [<span data-ttu-id="1728d-117">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="1728d-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="1728d-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="1728d-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="1728d-119">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="1728d-119">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="1728d-120">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="1728d-120">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="1728d-121">Zugriffsschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="1728d-121">Access Keywords</span></span>](../../../csharp/language-reference/keywords/access-keywords.md)  
 [<span data-ttu-id="1728d-122">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="1728d-122">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
