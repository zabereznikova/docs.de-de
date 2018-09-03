---
title: Zugriffsebenen (C#-Referenz)
ms.date: 12/06/2017
helpviewer_keywords:
- access modifiers [C#], accessibility levels
- accessibility levels
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
ms.openlocfilehash: 4679fd2564454e7f1ade5cb4813729b65f433012
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43484550"
---
# <a name="accessibility-levels-c-reference"></a><span data-ttu-id="58942-102">Zugriffsebenen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="58942-102">Accessibility Levels (C# Reference)</span></span>

<span data-ttu-id="58942-103">Verwenden Sie die Zugriffsmodifizierer `public`, `protected`, `internal` oder `private`, um eine der folgenden deklarierten Zugriffsebenen für Member anzugeben.</span><span class="sxs-lookup"><span data-stu-id="58942-103">Use the access modifiers, `public`, `protected`, `internal`, or `private`, to specify one of the following declared accessibility levels for members.</span></span>  
  
|<span data-ttu-id="58942-104">Deklarierter Zugriff</span><span class="sxs-lookup"><span data-stu-id="58942-104">Declared accessibility</span></span>|<span data-ttu-id="58942-105">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="58942-105">Meaning</span></span>|  
|----------------------------|-------------|  
|[`public`](public.md)|<span data-ttu-id="58942-106">Der Zugriff ist nicht beschränkt.</span><span class="sxs-lookup"><span data-stu-id="58942-106">Access is not restricted.</span></span>|  
|[`protected`](protected.md)|<span data-ttu-id="58942-107">Der Zugriff ist auf die enthaltende Klasse oder auf Typen beschränkt, die von der enthaltenden Klasse abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="58942-107">Access is limited to the containing class or types derived from the containing class.</span></span>|  
|[`internal`](internal.md)|<span data-ttu-id="58942-108">Der Zugriff ist auf die aktuelle Assembly beschränkt.</span><span class="sxs-lookup"><span data-stu-id="58942-108">Access is limited to the current assembly.</span></span>|  
|[`protected internal`](protected-internal.md)|<span data-ttu-id="58942-109">Der Zugriff ist auf die aktuelle Assembly oder auf Typen beschränkt, die von der enthaltenden Klasse abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="58942-109">Access is limited to the current assembly or types derived from the containing class.</span></span>|  
|[`private`](private.md)|<span data-ttu-id="58942-110">Der Zugriff ist auf die enthaltende Klasse beschränkt.</span><span class="sxs-lookup"><span data-stu-id="58942-110">Access is limited to the containing type.</span></span>|  
|[`private protected`](private-protected.md)|<span data-ttu-id="58942-111">Der Zugriff ist auf die enthaltende Klasse oder auf Typen beschränkt, die von der enthaltenden Klasse innerhalb der aktuellen Assembly abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="58942-111">Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span> <span data-ttu-id="58942-112">Verfügbar seit C# 7.2.</span><span class="sxs-lookup"><span data-stu-id="58942-112">Available since C# 7.2.</span></span> |  
  
 <span data-ttu-id="58942-113">Es ist nur ein Zugriffsmodifizierer für einen Member oder Typ zulässig, außer wenn Sie die `protected internal`- oder `private protected`-Kombination verwenden.</span><span class="sxs-lookup"><span data-stu-id="58942-113">Only one access modifier is allowed for a member or type, except when you use the `protected internal` or `private protected` combinations.</span></span>  
  
 <span data-ttu-id="58942-114">Zugriffsmodifizierer sind bei Namespaces nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="58942-114">Access modifiers are not allowed on namespaces.</span></span> <span data-ttu-id="58942-115">Namespaces haben uneingeschränkten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="58942-115">Namespaces have no access restrictions.</span></span>  
  
 <span data-ttu-id="58942-116">Abhängig vom Kontext einer Memberdeklaration sind nur bestimmte deklarierte Zugriffe zulässig.</span><span class="sxs-lookup"><span data-stu-id="58942-116">Depending on the context in which a member declaration occurs, only certain declared accessibilities are permitted.</span></span> <span data-ttu-id="58942-117">Wenn in einer Memberdeklaration kein Zugriffsmodifizierer angegeben ist, wird ein Standardzugriff verwendet.</span><span class="sxs-lookup"><span data-stu-id="58942-117">If no access modifier is specified in a member declaration, a default accessibility is used.</span></span>  
  
 <span data-ttu-id="58942-118">Typen der obersten Ebene, die nicht in anderen Typen geschachtelt sind, können nur Zugriff der Art `internal` oder `public` haben.</span><span class="sxs-lookup"><span data-stu-id="58942-118">Top-level types, which are not nested in other types, can only have `internal` or `public` accessibility.</span></span> <span data-ttu-id="58942-119">Der Standardzugriff für diese Typen ist `internal`.</span><span class="sxs-lookup"><span data-stu-id="58942-119">The default accessibility for these types is `internal`.</span></span>  
  
 <span data-ttu-id="58942-120">Geschachtelte Typen, die Member von anderen Typen sind, können deklarierte Zugriffe haben, wie in der folgenden Tabelle angegeben.</span><span class="sxs-lookup"><span data-stu-id="58942-120">Nested types, which are members of other types, can have declared accessibilities as indicated in the following table.</span></span>  
  
|<span data-ttu-id="58942-121">Member von</span><span class="sxs-lookup"><span data-stu-id="58942-121">Members of</span></span>|<span data-ttu-id="58942-122">Standard-Memberzugriff</span><span class="sxs-lookup"><span data-stu-id="58942-122">Default member accessibility</span></span>|<span data-ttu-id="58942-123">Zulässiger deklarierter Zugriffstyp des Members</span><span class="sxs-lookup"><span data-stu-id="58942-123">Allowed declared accessibility of the member</span></span>|  
|----------------|----------------------------------|--------------------------------------------------|  
|`enum`|`public`|<span data-ttu-id="58942-124">Keiner</span><span class="sxs-lookup"><span data-stu-id="58942-124">None</span></span>|  
|`class`|`private`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`<br /><br /> `protected internal` <br /><br />`private protected`|  
|`interface`|`public`|<span data-ttu-id="58942-125">Keiner</span><span class="sxs-lookup"><span data-stu-id="58942-125">None</span></span>|  
|`struct`|`private`|`public`<br /><br /> `internal`<br /><br /> `private`|  
  
 <span data-ttu-id="58942-126">Der Zugriff auf einen geschachtelten Typ hängt von seiner [Zugriffsdomäne](../../../csharp/language-reference/keywords/accessibility-domain.md) ab, die sowohl durch den deklarierten Zugriffstyp des Members als auch durch die Zugriffsdomäne des direkt enthaltenden Typs bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="58942-126">The accessibility of a nested type depends on its [accessibility domain](../../../csharp/language-reference/keywords/accessibility-domain.md), which is determined by both the declared accessibility of the member and the accessibility domain of the immediately containing type.</span></span> <span data-ttu-id="58942-127">Die Zugriffsdomäne eines geschachtelten Typs kann jedoch nicht über die des enthaltenden Typs hinausgehen.</span><span class="sxs-lookup"><span data-stu-id="58942-127">However, the accessibility domain of a nested type cannot exceed that of the containing type.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="58942-128">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="58942-128">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="58942-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58942-129">See Also</span></span>  
- [<span data-ttu-id="58942-130">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="58942-130">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="58942-131">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="58942-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="58942-132">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="58942-132">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="58942-133">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="58942-133">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
- [<span data-ttu-id="58942-134">Zugriffsdomäne</span><span class="sxs-lookup"><span data-stu-id="58942-134">Accessibility Domain</span></span>](../../../csharp/language-reference/keywords/accessibility-domain.md)  
- [<span data-ttu-id="58942-135">Einschränkungen bei der Verwendung von Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="58942-135">Restrictions on Using Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)  
- [<span data-ttu-id="58942-136">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="58942-136">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
- [<span data-ttu-id="58942-137">public</span><span class="sxs-lookup"><span data-stu-id="58942-137">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
- [<span data-ttu-id="58942-138">private</span><span class="sxs-lookup"><span data-stu-id="58942-138">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
- [<span data-ttu-id="58942-139">protected</span><span class="sxs-lookup"><span data-stu-id="58942-139">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
- [<span data-ttu-id="58942-140">internal</span><span class="sxs-lookup"><span data-stu-id="58942-140">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)
