---
description: Zugriffsebenen – C#-Referenz
title: Zugriffsebenen – C#-Referenz
ms.date: 12/06/2017
helpviewer_keywords:
- access modifiers [C#], accessibility levels
- accessibility levels
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
ms.openlocfilehash: 26b8f78595b1406deb371113cf491b80ad7c1474
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89127021"
---
# <a name="accessibility-levels-c-reference"></a><span data-ttu-id="a2e61-103">Zugriffsebenen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="a2e61-103">Accessibility Levels (C# Reference)</span></span>

<span data-ttu-id="a2e61-104">Verwenden Sie die Zugriffsmodifizierer `public`, `protected`, `internal` oder `private`, um eine der folgenden deklarierten Zugriffsebenen für Member anzugeben.</span><span class="sxs-lookup"><span data-stu-id="a2e61-104">Use the access modifiers, `public`, `protected`, `internal`, or `private`, to specify one of the following declared accessibility levels for members.</span></span>  
  
|<span data-ttu-id="a2e61-105">Deklarierter Zugriff</span><span class="sxs-lookup"><span data-stu-id="a2e61-105">Declared accessibility</span></span>|<span data-ttu-id="a2e61-106">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="a2e61-106">Meaning</span></span>|  
|----------------------------|-------------|  
|[`public`](public.md)|<span data-ttu-id="a2e61-107">Der Zugriff ist nicht beschränkt.</span><span class="sxs-lookup"><span data-stu-id="a2e61-107">Access is not restricted.</span></span>|  
|[`protected`](protected.md)|<span data-ttu-id="a2e61-108">Der Zugriff ist auf die enthaltende Klasse oder auf Typen beschränkt, die von der enthaltenden Klasse abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="a2e61-108">Access is limited to the containing class or types derived from the containing class.</span></span>|  
|[`internal`](internal.md)|<span data-ttu-id="a2e61-109">Der Zugriff ist auf die aktuelle Assembly beschränkt.</span><span class="sxs-lookup"><span data-stu-id="a2e61-109">Access is limited to the current assembly.</span></span>|  
|[`protected internal`](protected-internal.md)|<span data-ttu-id="a2e61-110">Der Zugriff ist auf die aktuelle Assembly oder auf Typen beschränkt, die von der enthaltenden Klasse abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="a2e61-110">Access is limited to the current assembly or types derived from the containing class.</span></span>|  
|[`private`](private.md)|<span data-ttu-id="a2e61-111">Der Zugriff ist auf die enthaltende Klasse beschränkt.</span><span class="sxs-lookup"><span data-stu-id="a2e61-111">Access is limited to the containing type.</span></span>|  
|[`private protected`](private-protected.md)|<span data-ttu-id="a2e61-112">Der Zugriff ist auf die enthaltende Klasse oder auf Typen beschränkt, die von der enthaltenden Klasse innerhalb der aktuellen Assembly abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="a2e61-112">Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span> <span data-ttu-id="a2e61-113">Verfügbar seit C# 7.2.</span><span class="sxs-lookup"><span data-stu-id="a2e61-113">Available since C# 7.2.</span></span> |  
  
 <span data-ttu-id="a2e61-114">Es ist nur ein Zugriffsmodifizierer für einen Member oder Typ zulässig, außer wenn Sie die `protected internal`- oder `private protected`-Kombination verwenden.</span><span class="sxs-lookup"><span data-stu-id="a2e61-114">Only one access modifier is allowed for a member or type, except when you use the `protected internal` or `private protected` combinations.</span></span>  
  
 <span data-ttu-id="a2e61-115">Zugriffsmodifizierer sind bei Namespaces nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="a2e61-115">Access modifiers are not allowed on namespaces.</span></span> <span data-ttu-id="a2e61-116">Namespaces haben uneingeschränkten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="a2e61-116">Namespaces have no access restrictions.</span></span>  
  
 <span data-ttu-id="a2e61-117">Abhängig vom Kontext einer Memberdeklaration sind nur bestimmte deklarierte Zugriffe zulässig.</span><span class="sxs-lookup"><span data-stu-id="a2e61-117">Depending on the context in which a member declaration occurs, only certain declared accessibilities are permitted.</span></span> <span data-ttu-id="a2e61-118">Wenn in einer Memberdeklaration kein Zugriffsmodifizierer angegeben ist, wird ein Standardzugriff verwendet.</span><span class="sxs-lookup"><span data-stu-id="a2e61-118">If no access modifier is specified in a member declaration, a default accessibility is used.</span></span>  
  
 <span data-ttu-id="a2e61-119">Typen der obersten Ebene, die nicht in anderen Typen geschachtelt sind, können nur Zugriff der Art `internal` oder `public` haben.</span><span class="sxs-lookup"><span data-stu-id="a2e61-119">Top-level types, which are not nested in other types, can only have `internal` or `public` accessibility.</span></span> <span data-ttu-id="a2e61-120">Der Standardzugriff für diese Typen ist `internal`.</span><span class="sxs-lookup"><span data-stu-id="a2e61-120">The default accessibility for these types is `internal`.</span></span>  
  
 <span data-ttu-id="a2e61-121">Geschachtelte Typen, die Member von anderen Typen sind, können deklarierte Zugriffe haben, wie in der folgenden Tabelle angegeben.</span><span class="sxs-lookup"><span data-stu-id="a2e61-121">Nested types, which are members of other types, can have declared accessibilities as indicated in the following table.</span></span>  
  
|<span data-ttu-id="a2e61-122">Member von</span><span class="sxs-lookup"><span data-stu-id="a2e61-122">Members of</span></span>|<span data-ttu-id="a2e61-123">Standard-Memberzugriff</span><span class="sxs-lookup"><span data-stu-id="a2e61-123">Default member accessibility</span></span>|<span data-ttu-id="a2e61-124">Zulässiger deklarierter Zugriffstyp des Members</span><span class="sxs-lookup"><span data-stu-id="a2e61-124">Allowed declared accessibility of the member</span></span>|  
|----------------|----------------------------------|--------------------------------------------------|  
|`enum`|`public`|<span data-ttu-id="a2e61-125">Keiner</span><span class="sxs-lookup"><span data-stu-id="a2e61-125">None</span></span>|  
|`class`|`private`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`<br /><br /> `protected internal` <br /><br />`private protected`|  
|`interface`|`public`|<span data-ttu-id="a2e61-126">Keine</span><span class="sxs-lookup"><span data-stu-id="a2e61-126">None</span></span>|  
|`struct`|`private`|`public`<br /><br /> `internal`<br /><br /> `private`|  
  
 <span data-ttu-id="a2e61-127">Der Zugriff auf einen geschachtelten Typ hängt von seiner [Zugriffsdomäne](./accessibility-domain.md) ab, die sowohl durch den deklarierten Zugriffstyp des Members als auch durch die Zugriffsdomäne des direkt enthaltenden Typs bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="a2e61-127">The accessibility of a nested type depends on its [accessibility domain](./accessibility-domain.md), which is determined by both the declared accessibility of the member and the accessibility domain of the immediately containing type.</span></span> <span data-ttu-id="a2e61-128">Die Zugriffsdomäne eines geschachtelten Typs kann jedoch nicht über die des enthaltenden Typs hinausgehen.</span><span class="sxs-lookup"><span data-stu-id="a2e61-128">However, the accessibility domain of a nested type cannot exceed that of the containing type.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="a2e61-129">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="a2e61-129">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a2e61-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2e61-130">See also</span></span>

- [<span data-ttu-id="a2e61-131">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="a2e61-131">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a2e61-132">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a2e61-132">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a2e61-133">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="a2e61-133">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="a2e61-134">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="a2e61-134">Access Modifiers</span></span>](./access-modifiers.md)
- [<span data-ttu-id="a2e61-135">Zugriffsdomäne</span><span class="sxs-lookup"><span data-stu-id="a2e61-135">Accessibility Domain</span></span>](./accessibility-domain.md)
- [<span data-ttu-id="a2e61-136">Einschränkungen bei der Verwendung von Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="a2e61-136">Restrictions on Using Accessibility Levels</span></span>](./restrictions-on-using-accessibility-levels.md)
- [<span data-ttu-id="a2e61-137">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="a2e61-137">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="a2e61-138">public</span><span class="sxs-lookup"><span data-stu-id="a2e61-138">public</span></span>](./public.md)
- [<span data-ttu-id="a2e61-139">private</span><span class="sxs-lookup"><span data-stu-id="a2e61-139">private</span></span>](./private.md)
- [<span data-ttu-id="a2e61-140">protected</span><span class="sxs-lookup"><span data-stu-id="a2e61-140">protected</span></span>](./protected.md)
- [<span data-ttu-id="a2e61-141">internal</span><span class="sxs-lookup"><span data-stu-id="a2e61-141">internal</span></span>](./internal.md)
