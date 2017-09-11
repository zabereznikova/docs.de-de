---
title: Zugriffsebenen (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- access modifiers [C#], accessibility levels
- accessibility levels
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
caps.latest.revision: 19
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
ms.openlocfilehash: 796802a407c486c1df5332d5b4920467f3a1171b
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="accessibility-levels-c-reference"></a><span data-ttu-id="1ce92-102">Zugriffsebenen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="1ce92-102">Accessibility Levels (C# Reference)</span></span>
<span data-ttu-id="1ce92-103">Verwenden Sie die Zugriffsmodifizierer [öffentlich](../../../csharp/language-reference/keywords/public.md), [geschützt](../../../csharp/language-reference/keywords/protected.md), [intern](../../../csharp/language-reference/keywords/internal.md) oder [privat](../../../csharp/language-reference/keywords/private.md), um eine der folgenden deklarierten Zugriffsebenen für Member anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1ce92-103">Use the access modifiers, [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), or [private](../../../csharp/language-reference/keywords/private.md), to specify one of the following declared accessibility levels for members.</span></span>  
  
|<span data-ttu-id="1ce92-104">Deklarierter Zugriff</span><span class="sxs-lookup"><span data-stu-id="1ce92-104">Declared accessibility</span></span>|<span data-ttu-id="1ce92-105">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="1ce92-105">Meaning</span></span>|  
|----------------------------|-------------|  
|`public`|<span data-ttu-id="1ce92-106">Der Zugriff ist nicht beschränkt.</span><span class="sxs-lookup"><span data-stu-id="1ce92-106">Access is not restricted.</span></span>|  
|`protected`|<span data-ttu-id="1ce92-107">Der Zugriff ist auf die enthaltende Klasse oder auf Typen beschränkt, die von der enthaltenden Klasse abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="1ce92-107">Access is limited to the containing class or types derived from the containing class.</span></span>|  
|`internal`|<span data-ttu-id="1ce92-108">Der Zugriff ist auf die aktuelle Assembly beschränkt.</span><span class="sxs-lookup"><span data-stu-id="1ce92-108">Access is limited to the current assembly.</span></span>|  
|`protected internal`|<span data-ttu-id="1ce92-109">Der Zugriff ist auf die aktuelle Assembly oder auf Typen beschränkt, die von der enthaltenden Klasse abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="1ce92-109">Access is limited to the current assembly or types derived from the containing class.</span></span>|  
|`private`|<span data-ttu-id="1ce92-110">Der Zugriff ist auf die enthaltende Klasse beschränkt.</span><span class="sxs-lookup"><span data-stu-id="1ce92-110">Access is limited to the containing type.</span></span>|  
  
 <span data-ttu-id="1ce92-111">Es ist nur ein Zugriffsmodifizierer für einen Member oder Typ zulässig, außer wenn Sie die `protected internal`-Kombination verwenden.</span><span class="sxs-lookup"><span data-stu-id="1ce92-111">Only one access modifier is allowed for a member or type, except when you use the `protected internal` combination.</span></span>  
  
 <span data-ttu-id="1ce92-112">Zugriffsmodifizierer sind bei Namespaces nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="1ce92-112">Access modifiers are not allowed on namespaces.</span></span> <span data-ttu-id="1ce92-113">Namespaces haben uneingeschränkten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="1ce92-113">Namespaces have no access restrictions.</span></span>  
  
 <span data-ttu-id="1ce92-114">Abhängig vom Kontext einer Memberdeklaration sind nur bestimmte deklarierte Zugriffe zulässig.</span><span class="sxs-lookup"><span data-stu-id="1ce92-114">Depending on the context in which a member declaration occurs, only certain declared accessibilities are permitted.</span></span> <span data-ttu-id="1ce92-115">Wenn in einer Memberdeklaration kein Zugriffsmodifizierer angegeben ist, wird ein Standardzugriff verwendet.</span><span class="sxs-lookup"><span data-stu-id="1ce92-115">If no access modifier is specified in a member declaration, a default accessibility is used.</span></span>  
  
 <span data-ttu-id="1ce92-116">Typen der obersten Ebene, die nicht in anderen Typen geschachtelt sind, können nur Zugriff der Art `internal` oder `public` haben.</span><span class="sxs-lookup"><span data-stu-id="1ce92-116">Top-level types, which are not nested in other types, can only have `internal` or `public` accessibility.</span></span> <span data-ttu-id="1ce92-117">Der Standardzugriff für diese Typen ist `internal`.</span><span class="sxs-lookup"><span data-stu-id="1ce92-117">The default accessibility for these types is `internal`.</span></span>  
  
 <span data-ttu-id="1ce92-118">Geschachtelte Typen, die Member von anderen Typen sind, können deklarierte Zugriffe haben, wie in der folgenden Tabelle angegeben.</span><span class="sxs-lookup"><span data-stu-id="1ce92-118">Nested types, which are members of other types, can have declared accessibilities as indicated in the following table.</span></span>  
  
|<span data-ttu-id="1ce92-119">Member von</span><span class="sxs-lookup"><span data-stu-id="1ce92-119">Members of</span></span>|<span data-ttu-id="1ce92-120">Standard-Memberzugriff</span><span class="sxs-lookup"><span data-stu-id="1ce92-120">Default member accessibility</span></span>|<span data-ttu-id="1ce92-121">Zulässiger deklarierter Zugriffstyp des Members</span><span class="sxs-lookup"><span data-stu-id="1ce92-121">Allowed declared accessibility of the member</span></span>|  
|----------------|----------------------------------|--------------------------------------------------|  
|`enum`|`public`|<span data-ttu-id="1ce92-122">Keine</span><span class="sxs-lookup"><span data-stu-id="1ce92-122">None</span></span>|  
|`class`|`private`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`<br /><br /> `protected internal`|  
|`interface`|`public`|<span data-ttu-id="1ce92-123">Keine</span><span class="sxs-lookup"><span data-stu-id="1ce92-123">None</span></span>|  
|`struct`|`private`|`public`<br /><br /> `internal`<br /><br /> `private`|  
  
 <span data-ttu-id="1ce92-124">Der Zugriff auf einen geschachtelten Typ hängt von seiner [Zugriffsdomäne](../../../csharp/language-reference/keywords/accessibility-domain.md) ab, die sowohl durch den deklarierten Zugriffstyp des Members als auch durch die Zugriffsdomäne des direkt enthaltenden Typs bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="1ce92-124">The accessibility of a nested type depends on its [accessibility domain](../../../csharp/language-reference/keywords/accessibility-domain.md), which is determined by both the declared accessibility of the member and the accessibility domain of the immediately containing type.</span></span> <span data-ttu-id="1ce92-125">Die Zugriffsdomäne eines geschachtelten Typs kann jedoch nicht über die des enthaltenden Typs hinausgehen.</span><span class="sxs-lookup"><span data-stu-id="1ce92-125">However, the accessibility domain of a nested type cannot exceed that of the containing type.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="1ce92-126">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="1ce92-126">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1ce92-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ce92-127">See Also</span></span>  
 <span data-ttu-id="1ce92-128">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="1ce92-128">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="1ce92-129">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="1ce92-129">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="1ce92-130">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="1ce92-130">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="1ce92-131">[Access Modifiers (Zugriffsmodifizierer)](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="1ce92-131">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="1ce92-132">[Zugriffsdomäne](../../../csharp/language-reference/keywords/accessibility-domain.md) </span><span class="sxs-lookup"><span data-stu-id="1ce92-132">[Accessibility Domain](../../../csharp/language-reference/keywords/accessibility-domain.md) </span></span>  
 <span data-ttu-id="1ce92-133">[Einschränkungen bei der Verwendung von Zugriffsebenen](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="1ce92-133">[Restrictions on Using Accessibility Levels](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md) </span></span>  
 <span data-ttu-id="1ce92-134">[Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="1ce92-134">[Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span></span>  
 <span data-ttu-id="1ce92-135">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="1ce92-135">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="1ce92-136">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="1ce92-136">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="1ce92-137">[protected](../../../csharp/language-reference/keywords/protected.md) </span><span class="sxs-lookup"><span data-stu-id="1ce92-137">[protected](../../../csharp/language-reference/keywords/protected.md) </span></span>  
 [<span data-ttu-id="1ce92-138">internal</span><span class="sxs-lookup"><span data-stu-id="1ce92-138">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)

