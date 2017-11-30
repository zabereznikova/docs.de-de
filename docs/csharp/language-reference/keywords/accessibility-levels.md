---
title: Zugriffsebenen (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- access modifiers [C#], accessibility levels
- accessibility levels
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 77124554d7a0b38414e154e024aceddbfffcfbd4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="accessibility-levels-c-reference"></a><span data-ttu-id="864ed-102">Zugriffsebenen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="864ed-102">Accessibility Levels (C# Reference)</span></span>
<span data-ttu-id="864ed-103">Verwenden Sie die Zugriffsmodifizierer [öffentlich](../../../csharp/language-reference/keywords/public.md), [geschützt](../../../csharp/language-reference/keywords/protected.md), [intern](../../../csharp/language-reference/keywords/internal.md) oder [privat](../../../csharp/language-reference/keywords/private.md), um eine der folgenden deklarierten Zugriffsebenen für Member anzugeben.</span><span class="sxs-lookup"><span data-stu-id="864ed-103">Use the access modifiers, [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), or [private](../../../csharp/language-reference/keywords/private.md), to specify one of the following declared accessibility levels for members.</span></span>  
  
|<span data-ttu-id="864ed-104">Deklarierter Zugriff</span><span class="sxs-lookup"><span data-stu-id="864ed-104">Declared accessibility</span></span>|<span data-ttu-id="864ed-105">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="864ed-105">Meaning</span></span>|  
|----------------------------|-------------|  
|`public`|<span data-ttu-id="864ed-106">Der Zugriff ist nicht beschränkt.</span><span class="sxs-lookup"><span data-stu-id="864ed-106">Access is not restricted.</span></span>|  
|`protected`|<span data-ttu-id="864ed-107">Der Zugriff ist auf die enthaltende Klasse oder auf Typen beschränkt, die von der enthaltenden Klasse abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="864ed-107">Access is limited to the containing class or types derived from the containing class.</span></span>|  
|`internal`|<span data-ttu-id="864ed-108">Der Zugriff ist auf die aktuelle Assembly beschränkt.</span><span class="sxs-lookup"><span data-stu-id="864ed-108">Access is limited to the current assembly.</span></span>|  
|`protected internal`|<span data-ttu-id="864ed-109">Der Zugriff ist auf die aktuelle Assembly oder auf Typen beschränkt, die von der enthaltenden Klasse abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="864ed-109">Access is limited to the current assembly or types derived from the containing class.</span></span>|  
|`private`|<span data-ttu-id="864ed-110">Der Zugriff ist auf die enthaltende Klasse beschränkt.</span><span class="sxs-lookup"><span data-stu-id="864ed-110">Access is limited to the containing type.</span></span>|  
|`private protected`|<span data-ttu-id="864ed-111">Zugriff ist auf die enthaltende Klasse oder von der enthaltenden Klasse innerhalb der aktuellen Assembly abgeleitete Typen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="864ed-111">Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span>|  
  
 <span data-ttu-id="864ed-112">Nur ein Zugriffsmodifizierer ist zulässig, für die ein Member oder Typ, außer bei der Verwendung der `protected internal` oder `private protected` Kombinationen.</span><span class="sxs-lookup"><span data-stu-id="864ed-112">Only one access modifier is allowed for a member or type, except when you use the `protected internal` or `private protected` combinations.</span></span>  
  
 <span data-ttu-id="864ed-113">Zugriffsmodifizierer sind bei Namespaces nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="864ed-113">Access modifiers are not allowed on namespaces.</span></span> <span data-ttu-id="864ed-114">Namespaces haben uneingeschränkten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="864ed-114">Namespaces have no access restrictions.</span></span>  
  
 <span data-ttu-id="864ed-115">Abhängig vom Kontext einer Memberdeklaration sind nur bestimmte deklarierte Zugriffe zulässig.</span><span class="sxs-lookup"><span data-stu-id="864ed-115">Depending on the context in which a member declaration occurs, only certain declared accessibilities are permitted.</span></span> <span data-ttu-id="864ed-116">Wenn in einer Memberdeklaration kein Zugriffsmodifizierer angegeben ist, wird ein Standardzugriff verwendet.</span><span class="sxs-lookup"><span data-stu-id="864ed-116">If no access modifier is specified in a member declaration, a default accessibility is used.</span></span>  
  
 <span data-ttu-id="864ed-117">Typen der obersten Ebene, die nicht in anderen Typen geschachtelt sind, können nur Zugriff der Art `internal` oder `public` haben.</span><span class="sxs-lookup"><span data-stu-id="864ed-117">Top-level types, which are not nested in other types, can only have `internal` or `public` accessibility.</span></span> <span data-ttu-id="864ed-118">Der Standardzugriff für diese Typen ist `internal`.</span><span class="sxs-lookup"><span data-stu-id="864ed-118">The default accessibility for these types is `internal`.</span></span>  
  
 <span data-ttu-id="864ed-119">Geschachtelte Typen, die Member von anderen Typen sind, können deklarierte Zugriffe haben, wie in der folgenden Tabelle angegeben.</span><span class="sxs-lookup"><span data-stu-id="864ed-119">Nested types, which are members of other types, can have declared accessibilities as indicated in the following table.</span></span>  
  
|<span data-ttu-id="864ed-120">Member von</span><span class="sxs-lookup"><span data-stu-id="864ed-120">Members of</span></span>|<span data-ttu-id="864ed-121">Standard-Memberzugriff</span><span class="sxs-lookup"><span data-stu-id="864ed-121">Default member accessibility</span></span>|<span data-ttu-id="864ed-122">Zulässiger deklarierter Zugriffstyp des Members</span><span class="sxs-lookup"><span data-stu-id="864ed-122">Allowed declared accessibility of the member</span></span>|  
|----------------|----------------------------------|--------------------------------------------------|  
|`enum`|`public`|<span data-ttu-id="864ed-123">Keine</span><span class="sxs-lookup"><span data-stu-id="864ed-123">None</span></span>|  
|`class`|`private`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`<br /><br /> `protected internal` <br /><br />`private protected`|  
|`interface`|`public`|<span data-ttu-id="864ed-124">Keine</span><span class="sxs-lookup"><span data-stu-id="864ed-124">None</span></span>|  
|`struct`|`private`|`public`<br /><br /> `internal`<br /><br /> `private`|  
  
 <span data-ttu-id="864ed-125">Der Zugriff auf einen geschachtelten Typ hängt von seiner [Zugriffsdomäne](../../../csharp/language-reference/keywords/accessibility-domain.md) ab, die sowohl durch den deklarierten Zugriffstyp des Members als auch durch die Zugriffsdomäne des direkt enthaltenden Typs bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="864ed-125">The accessibility of a nested type depends on its [accessibility domain](../../../csharp/language-reference/keywords/accessibility-domain.md), which is determined by both the declared accessibility of the member and the accessibility domain of the immediately containing type.</span></span> <span data-ttu-id="864ed-126">Die Zugriffsdomäne eines geschachtelten Typs kann jedoch nicht über die des enthaltenden Typs hinausgehen.</span><span class="sxs-lookup"><span data-stu-id="864ed-126">However, the accessibility domain of a nested type cannot exceed that of the containing type.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="864ed-127">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="864ed-127">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="864ed-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="864ed-128">See Also</span></span>  
 [<span data-ttu-id="864ed-129">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="864ed-129">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="864ed-130">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="864ed-130">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="864ed-131">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="864ed-131">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="864ed-132">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="864ed-132">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [<span data-ttu-id="864ed-133">Zugriffsdomäne</span><span class="sxs-lookup"><span data-stu-id="864ed-133">Accessibility Domain</span></span>](../../../csharp/language-reference/keywords/accessibility-domain.md)  
 [<span data-ttu-id="864ed-134">Einschränkungen bei der Verwendung von Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="864ed-134">Restrictions on Using Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)  
 [<span data-ttu-id="864ed-135">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="864ed-135">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="864ed-136">public</span><span class="sxs-lookup"><span data-stu-id="864ed-136">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 [<span data-ttu-id="864ed-137">private</span><span class="sxs-lookup"><span data-stu-id="864ed-137">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
 [<span data-ttu-id="864ed-138">protected</span><span class="sxs-lookup"><span data-stu-id="864ed-138">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
 [<span data-ttu-id="864ed-139">internal</span><span class="sxs-lookup"><span data-stu-id="864ed-139">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)
