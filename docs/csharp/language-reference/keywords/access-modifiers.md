---
title: Zugriffsmodifizierer (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: access modifiers [C#]
ms.assetid: 61c3fa51-c00f-48cb-9b49-c805dedd62d7
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 23f99d0925aefde7ef43888d16e888a0943dfc21
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="access-modifiers-c-reference"></a><span data-ttu-id="26c07-102">Zugriffsmodifizierer (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="26c07-102">Access Modifiers (C# Reference)</span></span>
<span data-ttu-id="26c07-103">Zugriffsmodifizierer sind Schlüsselwörter, die verwendet werden, um die deklarierte Zugriffsart eines Members oder Typs anzugeben.</span><span class="sxs-lookup"><span data-stu-id="26c07-103">Access modifiers are keywords used to specify the declared accessibility of a member or a type.</span></span> <span data-ttu-id="26c07-104">In diesem Abschnitt werden die vier Zugriffsmodifizierer beschrieben:</span><span class="sxs-lookup"><span data-stu-id="26c07-104">This section introduces the four access modifiers:</span></span>  
  
-   [<span data-ttu-id="26c07-105">public</span><span class="sxs-lookup"><span data-stu-id="26c07-105">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
  
-   [<span data-ttu-id="26c07-106">protected</span><span class="sxs-lookup"><span data-stu-id="26c07-106">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
  
-   [<span data-ttu-id="26c07-107">internal</span><span class="sxs-lookup"><span data-stu-id="26c07-107">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)  
  
-   [<span data-ttu-id="26c07-108">private</span><span class="sxs-lookup"><span data-stu-id="26c07-108">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
  
 <span data-ttu-id="26c07-109">Die folgenden sechs Zugriffsebenen können mit den Zugriffsmodifizierern angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="26c07-109">The following six accessibility levels can be specified using the access modifiers:</span></span>  
  
 <span data-ttu-id="26c07-110">`public`: Der Zugriff ist nicht beschränkt.</span><span class="sxs-lookup"><span data-stu-id="26c07-110">`public`: Access is not restricted.</span></span>  
  
 <span data-ttu-id="26c07-111">`protected`: Der Zugriff ist auf die enthaltende Klasse oder auf Typen beschränkt, die von der enthaltenden Klasse abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="26c07-111">`protected`: Access is limited to the containing class or types derived from the containing class.</span></span>  
  
 <span data-ttu-id="26c07-112">`internal`: Der Zugriff ist auf die aktuelle Assembly beschränkt.</span><span class="sxs-lookup"><span data-stu-id="26c07-112">`internal`: Access is limited to the current assembly.</span></span>  
  
 <span data-ttu-id="26c07-113">[`protected internal`](../../../csharp/language-reference/keywords/protected-internal.md): Der Zugriff ist auf die aktuelle Assembly oder von der enthaltenden Klasse abgeleitete Typen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="26c07-113">[`protected internal`](../../../csharp/language-reference/keywords/protected-internal.md): Access is limited to the current assembly or types derived from the containing class.</span></span>  
  
 <span data-ttu-id="26c07-114">`private`: Der Zugriff ist auf die enthaltende Klasse beschränkt.</span><span class="sxs-lookup"><span data-stu-id="26c07-114">`private`: Access is limited to the containing type.</span></span>  

 <span data-ttu-id="26c07-115">[`private protected`](../../../csharp/language-reference/keywords/private-protected.md): Der Zugriff ist auf die enthaltende Klasse oder von der enthaltenden Klasse innerhalb der aktuellen Assembly abgeleitete Typen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="26c07-115">[`private protected`](../../../csharp/language-reference/keywords/private-protected.md): Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span>  
  
 <span data-ttu-id="26c07-116">In diesem Abschnitt wird Folgendes beschrieben:</span><span class="sxs-lookup"><span data-stu-id="26c07-116">This section also introduces the following:</span></span>  
  
-   <span data-ttu-id="26c07-117">[Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md): mithilfe der vier Zugriffsmodifizierer deklarieren sechs Zugriffsebenen.</span><span class="sxs-lookup"><span data-stu-id="26c07-117">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md): Using the four access modifiers to declare six levels of accessibility.</span></span>  
  
-   <span data-ttu-id="26c07-118">[Zugriffsdomäne](../../../csharp/language-reference/keywords/accessibility-domain.md): Gibt an, in welche Teile des Programms ein Member verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="26c07-118">[Accessibility Domain](../../../csharp/language-reference/keywords/accessibility-domain.md): Specifies where, in the program sections, a member can be referenced.</span></span>  
  
-   <span data-ttu-id="26c07-119">[Einschränkungen bei der Verwendung von Zugriffsebenen](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): Ein Überblick über die Einschränkungen bei der Verwendung deklarierter Zugriffsebenen.</span><span class="sxs-lookup"><span data-stu-id="26c07-119">[Restrictions on Using Accessibility Levels](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): A summary of the restrictions on using declared accessibility levels.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26c07-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="26c07-120">See Also</span></span>  
 [<span data-ttu-id="26c07-121">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="26c07-121">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="26c07-122">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="26c07-122">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="26c07-123">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="26c07-123">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="26c07-124">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="26c07-124">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="26c07-125">Zugriffsschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="26c07-125">Access Keywords</span></span>](../../../csharp/language-reference/keywords/access-keywords.md)  
 [<span data-ttu-id="26c07-126">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="26c07-126">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
