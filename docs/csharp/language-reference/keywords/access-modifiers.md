---
title: Zugriffsmodifizierer – C#-Referenz
ms.date: 07/20/2015
helpviewer_keywords:
- access modifiers [C#]
ms.assetid: 61c3fa51-c00f-48cb-9b49-c805dedd62d7
ms.openlocfilehash: 754949e42771de30cc2dce7e4e610f70ada6dfd4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713841"
---
# <a name="access-modifiers-c-reference"></a><span data-ttu-id="3becc-102">Zugriffsmodifizierer (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="3becc-102">Access Modifiers (C# Reference)</span></span>
<span data-ttu-id="3becc-103">Zugriffsmodifizierer sind Schlüsselwörter, die verwendet werden, um die deklarierte Zugriffsart eines Members oder Typs anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3becc-103">Access modifiers are keywords used to specify the declared accessibility of a member or a type.</span></span> <span data-ttu-id="3becc-104">In diesem Abschnitt werden die vier Zugriffsmodifizierer beschrieben:</span><span class="sxs-lookup"><span data-stu-id="3becc-104">This section introduces the four access modifiers:</span></span>  
  
- `public`
- `protected`
- `internal`
- `private`
  
 <span data-ttu-id="3becc-105">Die folgenden sechs Zugriffsebenen können mit den Zugriffsmodifizierern angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="3becc-105">The following six accessibility levels can be specified using the access modifiers:</span></span>  
  
- <span data-ttu-id="3becc-106">[`public`](public.md): Der Zugriff ist nicht beschränkt.</span><span class="sxs-lookup"><span data-stu-id="3becc-106">[`public`](public.md): Access is not restricted.</span></span>  
  
- <span data-ttu-id="3becc-107">[`protected`](protected.md): Der Zugriff ist auf die enthaltende Klasse oder auf Typen beschränkt, die von der enthaltenden Klasse abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="3becc-107">[`protected`](protected.md): Access is limited to the containing class or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="3becc-108">[`internal`](internal.md): Der Zugriff ist auf die aktuelle Assembly beschränkt.</span><span class="sxs-lookup"><span data-stu-id="3becc-108">[`internal`](internal.md): Access is limited to the current assembly.</span></span>  
  
- <span data-ttu-id="3becc-109">[`protected internal`](protected-internal.md): Der Zugriff ist auf die aktuelle Assembly oder auf Typen beschränkt, die von der enthaltenden Klasse abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="3becc-109">[`protected internal`](protected-internal.md): Access is limited to the current assembly or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="3becc-110">[`private`](private.md): Der Zugriff ist auf den enthaltenden Typ beschränkt.</span><span class="sxs-lookup"><span data-stu-id="3becc-110">[`private`](private.md): Access is limited to the containing type.</span></span>  

- <span data-ttu-id="3becc-111">[`private protected`](private-protected.md): Der Zugriff ist auf die enthaltende Klasse oder auf Typen beschränkt, die von der enthaltenden Klasse innerhalb der aktuellen Assembly abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="3becc-111">[`private protected`](private-protected.md): Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span>  
  
 <span data-ttu-id="3becc-112">In diesem Abschnitt wird Folgendes beschrieben:</span><span class="sxs-lookup"><span data-stu-id="3becc-112">This section also introduces the following:</span></span>  
  
- <span data-ttu-id="3becc-113">[Zugriffsebenen](./accessibility-levels.md): Deklarieren von sechs Zugriffsebenen mithilfe der vier Zugriffsmodifizierer.</span><span class="sxs-lookup"><span data-stu-id="3becc-113">[Accessibility Levels](./accessibility-levels.md): Using the four access modifiers to declare six levels of accessibility.</span></span>  
  
- <span data-ttu-id="3becc-114">[Zugriffsdomäne](./accessibility-domain.md): Gibt an, in welche Teile des Programms ein Member verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="3becc-114">[Accessibility Domain](./accessibility-domain.md): Specifies where, in the program sections, a member can be referenced.</span></span>  
  
- <span data-ttu-id="3becc-115">[Einschränkungen bei der Verwendung von Zugriffsebenen](./restrictions-on-using-accessibility-levels.md): Ein Überblick über die Einschränkungen bei der Verwendung deklarierter Zugriffsebenen.</span><span class="sxs-lookup"><span data-stu-id="3becc-115">[Restrictions on Using Accessibility Levels](./restrictions-on-using-accessibility-levels.md): A summary of the restrictions on using declared accessibility levels.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3becc-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3becc-116">See also</span></span>

- [<span data-ttu-id="3becc-117">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="3becc-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="3becc-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="3becc-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="3becc-119">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="3becc-119">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="3becc-120">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="3becc-120">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="3becc-121">Zugriffsschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="3becc-121">Access Keywords</span></span>](base.md)
- [<span data-ttu-id="3becc-122">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="3becc-122">Modifiers</span></span>](index.md)
