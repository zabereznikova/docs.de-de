---
description: Zugriffsmodifizierer – C#-Referenz
title: Zugriffsmodifizierer – C#-Referenz
ms.date: 07/20/2015
helpviewer_keywords:
- access modifiers [C#]
ms.assetid: 61c3fa51-c00f-48cb-9b49-c805dedd62d7
ms.openlocfilehash: e941fc673c508f10863ee49b6544d6886bd594a3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168815"
---
# <a name="access-modifiers-c-reference"></a><span data-ttu-id="0a1b5-103">Zugriffsmodifizierer (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="0a1b5-103">Access Modifiers (C# Reference)</span></span>

<span data-ttu-id="0a1b5-104">Zugriffsmodifizierer sind Schlüsselwörter, die verwendet werden, um die deklarierte Zugriffsart eines Members oder Typs anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0a1b5-104">Access modifiers are keywords used to specify the declared accessibility of a member or a type.</span></span> <span data-ttu-id="0a1b5-105">In diesem Abschnitt werden die vier Zugriffsmodifizierer beschrieben:</span><span class="sxs-lookup"><span data-stu-id="0a1b5-105">This section introduces the four access modifiers:</span></span>  
  
- `public`
- `protected`
- `internal`
- `private`
  
 <span data-ttu-id="0a1b5-106">Die folgenden sechs Zugriffsebenen können mit den Zugriffsmodifizierern angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="0a1b5-106">The following six accessibility levels can be specified using the access modifiers:</span></span>  
  
- <span data-ttu-id="0a1b5-107">[`public`](public.md): Der Zugriff ist nicht beschränkt.</span><span class="sxs-lookup"><span data-stu-id="0a1b5-107">[`public`](public.md): Access is not restricted.</span></span>  
  
- <span data-ttu-id="0a1b5-108">[`protected`](protected.md): Der Zugriff ist auf die enthaltende Klasse oder auf Typen beschränkt, die von der enthaltenden Klasse abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="0a1b5-108">[`protected`](protected.md): Access is limited to the containing class or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="0a1b5-109">[`internal`](internal.md): Der Zugriff ist auf die aktuelle Assembly beschränkt.</span><span class="sxs-lookup"><span data-stu-id="0a1b5-109">[`internal`](internal.md): Access is limited to the current assembly.</span></span>  
  
- <span data-ttu-id="0a1b5-110">[`protected internal`](protected-internal.md): Der Zugriff ist auf die aktuelle Assembly oder auf Typen beschränkt, die von der enthaltenden Klasse abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="0a1b5-110">[`protected internal`](protected-internal.md): Access is limited to the current assembly or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="0a1b5-111">[`private`](private.md): Der Zugriff ist auf die enthaltende Klasse beschränkt.</span><span class="sxs-lookup"><span data-stu-id="0a1b5-111">[`private`](private.md): Access is limited to the containing type.</span></span>  

- <span data-ttu-id="0a1b5-112">[`private protected`](private-protected.md): Der Zugriff ist auf die enthaltende Klasse oder auf Typen beschränkt, die von der enthaltenden Klasse innerhalb der aktuellen Assembly abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="0a1b5-112">[`private protected`](private-protected.md): Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span>  
  
 <span data-ttu-id="0a1b5-113">In diesem Abschnitt wird Folgendes beschrieben:</span><span class="sxs-lookup"><span data-stu-id="0a1b5-113">This section also introduces the following:</span></span>  
  
- <span data-ttu-id="0a1b5-114">[Zugriffsebenen](./accessibility-levels.md): Deklarieren von sechs Zugriffsebenen mithilfe der vier Zugriffsmodifizierer.</span><span class="sxs-lookup"><span data-stu-id="0a1b5-114">[Accessibility Levels](./accessibility-levels.md): Using the four access modifiers to declare six levels of accessibility.</span></span>  
  
- <span data-ttu-id="0a1b5-115">[Zugriffsdomäne](./accessibility-domain.md): Gibt an, in welche Teile des Programms ein Member verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="0a1b5-115">[Accessibility Domain](./accessibility-domain.md): Specifies where, in the program sections, a member can be referenced.</span></span>  
  
- <span data-ttu-id="0a1b5-116">[Einschränkungen bei der Verwendung von Zugriffsebenen](./restrictions-on-using-accessibility-levels.md): Ein Überblick über die Einschränkungen bei der Verwendung deklarierter Zugriffsebenen.</span><span class="sxs-lookup"><span data-stu-id="0a1b5-116">[Restrictions on Using Accessibility Levels](./restrictions-on-using-accessibility-levels.md): A summary of the restrictions on using declared accessibility levels.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a1b5-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0a1b5-117">See also</span></span>

- [<span data-ttu-id="0a1b5-118">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="0a1b5-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0a1b5-119">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="0a1b5-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0a1b5-120">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="0a1b5-120">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="0a1b5-121">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="0a1b5-121">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="0a1b5-122">Zugriffsschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="0a1b5-122">Access Keywords</span></span>](base.md)
- [<span data-ttu-id="0a1b5-123">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="0a1b5-123">Modifiers</span></span>](index.md)
