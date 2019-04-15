---
title: Zugriffsebenen – C#-Referenz
ms.custom: seodec18
ms.date: 12/06/2017
helpviewer_keywords:
- access modifiers [C#], accessibility levels
- accessibility levels
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
ms.openlocfilehash: da49c6f0b44ab0eefbd338963a744a11502f75da
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59130467"
---
# <a name="accessibility-levels-c-reference"></a><span data-ttu-id="7a2ad-102">Zugriffsebenen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="7a2ad-102">Accessibility Levels (C# Reference)</span></span>

<span data-ttu-id="7a2ad-103">Verwenden Sie die Zugriffsmodifizierer `public`, `protected`, `internal` oder `private`, um eine der folgenden deklarierten Zugriffsebenen für Member anzugeben.</span><span class="sxs-lookup"><span data-stu-id="7a2ad-103">Use the access modifiers, `public`, `protected`, `internal`, or `private`, to specify one of the following declared accessibility levels for members.</span></span>  
  
|<span data-ttu-id="7a2ad-104">Deklarierter Zugriff</span><span class="sxs-lookup"><span data-stu-id="7a2ad-104">Declared accessibility</span></span>|<span data-ttu-id="7a2ad-105">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="7a2ad-105">Meaning</span></span>|  
|----------------------------|-------------|  
|[`public`](public.md)|<span data-ttu-id="7a2ad-106">Der Zugriff ist nicht beschränkt.</span><span class="sxs-lookup"><span data-stu-id="7a2ad-106">Access is not restricted.</span></span>|  
|[`protected`](protected.md)|<span data-ttu-id="7a2ad-107">Der Zugriff ist auf die enthaltende Klasse oder auf Typen beschränkt, die von der enthaltenden Klasse abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="7a2ad-107">Access is limited to the containing class or types derived from the containing class.</span></span>|  
|[`internal`](internal.md)|<span data-ttu-id="7a2ad-108">Der Zugriff ist auf die aktuelle Assembly beschränkt.</span><span class="sxs-lookup"><span data-stu-id="7a2ad-108">Access is limited to the current assembly.</span></span>|  
|[`protected internal`](protected-internal.md)|<span data-ttu-id="7a2ad-109">Der Zugriff ist auf die aktuelle Assembly oder auf Typen beschränkt, die von der enthaltenden Klasse abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="7a2ad-109">Access is limited to the current assembly or types derived from the containing class.</span></span>|  
|[`private`](private.md)|<span data-ttu-id="7a2ad-110">Der Zugriff ist auf die enthaltende Klasse beschränkt.</span><span class="sxs-lookup"><span data-stu-id="7a2ad-110">Access is limited to the containing type.</span></span>|  
|[`private protected`](private-protected.md)|<span data-ttu-id="7a2ad-111">Der Zugriff ist auf die enthaltende Klasse oder auf Typen beschränkt, die von der enthaltenden Klasse innerhalb der aktuellen Assembly abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="7a2ad-111">Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span> <span data-ttu-id="7a2ad-112">Verfügbar seit C# 7.2.</span><span class="sxs-lookup"><span data-stu-id="7a2ad-112">Available since C# 7.2.</span></span> |  
  
 <span data-ttu-id="7a2ad-113">Es ist nur ein Zugriffsmodifizierer für einen Member oder Typ zulässig, außer wenn Sie die `protected internal`- oder `private protected`-Kombination verwenden.</span><span class="sxs-lookup"><span data-stu-id="7a2ad-113">Only one access modifier is allowed for a member or type, except when you use the `protected internal` or `private protected` combinations.</span></span>  
  
 <span data-ttu-id="7a2ad-114">Zugriffsmodifizierer sind bei Namespaces nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="7a2ad-114">Access modifiers are not allowed on namespaces.</span></span> <span data-ttu-id="7a2ad-115">Namespaces haben uneingeschränkten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="7a2ad-115">Namespaces have no access restrictions.</span></span>  
  
 <span data-ttu-id="7a2ad-116">Abhängig vom Kontext einer Memberdeklaration sind nur bestimmte deklarierte Zugriffe zulässig.</span><span class="sxs-lookup"><span data-stu-id="7a2ad-116">Depending on the context in which a member declaration occurs, only certain declared accessibilities are permitted.</span></span> <span data-ttu-id="7a2ad-117">Wenn in einer Memberdeklaration kein Zugriffsmodifizierer angegeben ist, wird ein Standardzugriff verwendet.</span><span class="sxs-lookup"><span data-stu-id="7a2ad-117">If no access modifier is specified in a member declaration, a default accessibility is used.</span></span>  
  
 <span data-ttu-id="7a2ad-118">Typen der obersten Ebene, die nicht in anderen Typen geschachtelt sind, können nur Zugriff der Art `internal` oder `public` haben.</span><span class="sxs-lookup"><span data-stu-id="7a2ad-118">Top-level types, which are not nested in other types, can only have `internal` or `public` accessibility.</span></span> <span data-ttu-id="7a2ad-119">Der Standardzugriff für diese Typen ist `internal`.</span><span class="sxs-lookup"><span data-stu-id="7a2ad-119">The default accessibility for these types is `internal`.</span></span>  
  
 <span data-ttu-id="7a2ad-120">Geschachtelte Typen, die Member von anderen Typen sind, können deklarierte Zugriffe haben, wie in der folgenden Tabelle angegeben.</span><span class="sxs-lookup"><span data-stu-id="7a2ad-120">Nested types, which are members of other types, can have declared accessibilities as indicated in the following table.</span></span>  
  
|<span data-ttu-id="7a2ad-121">Member von</span><span class="sxs-lookup"><span data-stu-id="7a2ad-121">Members of</span></span>|<span data-ttu-id="7a2ad-122">Standard-Memberzugriff</span><span class="sxs-lookup"><span data-stu-id="7a2ad-122">Default member accessibility</span></span>|<span data-ttu-id="7a2ad-123">Zulässiger deklarierter Zugriffstyp des Members</span><span class="sxs-lookup"><span data-stu-id="7a2ad-123">Allowed declared accessibility of the member</span></span>|  
|----------------|----------------------------------|--------------------------------------------------|  
|`enum`|`public`|<span data-ttu-id="7a2ad-124">Keiner</span><span class="sxs-lookup"><span data-stu-id="7a2ad-124">None</span></span>|  
|`class`|`private`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`<br /><br /> `protected internal` <br /><br />`private protected`|  
|`interface`|`public`|<span data-ttu-id="7a2ad-125">Keiner</span><span class="sxs-lookup"><span data-stu-id="7a2ad-125">None</span></span>|  
|`struct`|`private`|`public`<br /><br /> `internal`<br /><br /> `private`|  
  
 <span data-ttu-id="7a2ad-126">Der Zugriff auf einen geschachtelten Typ hängt von seiner [Zugriffsdomäne](../../../csharp/language-reference/keywords/accessibility-domain.md) ab, die sowohl durch den deklarierten Zugriffstyp des Members als auch durch die Zugriffsdomäne des direkt enthaltenden Typs bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="7a2ad-126">The accessibility of a nested type depends on its [accessibility domain](../../../csharp/language-reference/keywords/accessibility-domain.md), which is determined by both the declared accessibility of the member and the accessibility domain of the immediately containing type.</span></span> <span data-ttu-id="7a2ad-127">Die Zugriffsdomäne eines geschachtelten Typs kann jedoch nicht über die des enthaltenden Typs hinausgehen.</span><span class="sxs-lookup"><span data-stu-id="7a2ad-127">However, the accessibility domain of a nested type cannot exceed that of the containing type.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="7a2ad-128">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="7a2ad-128">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7a2ad-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7a2ad-129">See also</span></span>

- [<span data-ttu-id="7a2ad-130">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="7a2ad-130">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="7a2ad-131">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="7a2ad-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="7a2ad-132">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="7a2ad-132">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="7a2ad-133">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="7a2ad-133">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)
- [<span data-ttu-id="7a2ad-134">Zugriffsdomäne</span><span class="sxs-lookup"><span data-stu-id="7a2ad-134">Accessibility Domain</span></span>](../../../csharp/language-reference/keywords/accessibility-domain.md)
- [<span data-ttu-id="7a2ad-135">Einschränkungen bei der Verwendung von Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="7a2ad-135">Restrictions on Using Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)
- [<span data-ttu-id="7a2ad-136">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="7a2ad-136">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="7a2ad-137">public</span><span class="sxs-lookup"><span data-stu-id="7a2ad-137">public</span></span>](../../../csharp/language-reference/keywords/public.md)
- [<span data-ttu-id="7a2ad-138">private</span><span class="sxs-lookup"><span data-stu-id="7a2ad-138">private</span></span>](../../../csharp/language-reference/keywords/private.md)
- [<span data-ttu-id="7a2ad-139">protected</span><span class="sxs-lookup"><span data-stu-id="7a2ad-139">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)
- [<span data-ttu-id="7a2ad-140">internal</span><span class="sxs-lookup"><span data-stu-id="7a2ad-140">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)
