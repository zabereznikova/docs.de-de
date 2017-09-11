---
title: Zugriffsmodifizierer (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- access modifiers [C#]
ms.assetid: 61c3fa51-c00f-48cb-9b49-c805dedd62d7
caps.latest.revision: 15
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
ms.openlocfilehash: a3ad46580561500d9f011da4997007023a3bc844
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="access-modifiers-c-reference"></a><span data-ttu-id="f219d-102">Zugriffsmodifizierer (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="f219d-102">Access Modifiers (C# Reference)</span></span>
<span data-ttu-id="f219d-103">Zugriffsmodifizierer sind Schlüsselwörter, die verwendet werden, um die deklarierte Zugriffsart eines Members oder Typs anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f219d-103">Access modifiers are keywords used to specify the declared accessibility of a member or a type.</span></span> <span data-ttu-id="f219d-104">In diesem Abschnitt werden die vier Zugriffsmodifizierer beschrieben:</span><span class="sxs-lookup"><span data-stu-id="f219d-104">This section introduces the four access modifiers:</span></span>  
  
-   [<span data-ttu-id="f219d-105">public</span><span class="sxs-lookup"><span data-stu-id="f219d-105">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
  
-   [<span data-ttu-id="f219d-106">protected</span><span class="sxs-lookup"><span data-stu-id="f219d-106">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
  
-   [<span data-ttu-id="f219d-107">internal</span><span class="sxs-lookup"><span data-stu-id="f219d-107">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)  
  
-   [<span data-ttu-id="f219d-108">private</span><span class="sxs-lookup"><span data-stu-id="f219d-108">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
  
 <span data-ttu-id="f219d-109">Die folgenden fünf Zugriffsebenen können mit den Zugriffsmodifizierern angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="f219d-109">The following five accessibility levels can be specified using the access modifiers:</span></span>  
  
 <span data-ttu-id="f219d-110">`public`: Der Zugriff ist nicht beschränkt.</span><span class="sxs-lookup"><span data-stu-id="f219d-110">`public`: Access is not restricted.</span></span>  
  
 <span data-ttu-id="f219d-111">`protected`: Der Zugriff ist auf die enthaltende Klasse oder auf Typen beschränkt, die von der enthaltenden Klasse abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="f219d-111">`protected`: Access is limited to the containing class or types derived from the containing class.</span></span>  
  
 <span data-ttu-id="f219d-112">`Internal`: Der Zugriff ist auf die aktuelle Assembly beschränkt.</span><span class="sxs-lookup"><span data-stu-id="f219d-112">`Internal`: Access is limited to the current assembly.</span></span>  
  
 <span data-ttu-id="f219d-113">[protected internal](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md): Der Zugriff ist auf die aktuelle Assembly oder auf Typen beschränkt, die von der enthaltenden Klasse abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="f219d-113">[protected internal](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md): Access is limited to the current assembly or types derived from the containing class.</span></span>  
  
 <span data-ttu-id="f219d-114">`private`: Der Zugriff ist auf die enthaltende Klasse beschränkt.</span><span class="sxs-lookup"><span data-stu-id="f219d-114">`private`: Access is limited to the containing type.</span></span>  
  
 <span data-ttu-id="f219d-115">In diesem Abschnitt wird Folgendes beschrieben:</span><span class="sxs-lookup"><span data-stu-id="f219d-115">This section also introduces the following:</span></span>  
  
-   <span data-ttu-id="f219d-116">[Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md): Deklarieren von fünf Zugriffsebenen mithilfe der vier Zugriffsmodifizierer.</span><span class="sxs-lookup"><span data-stu-id="f219d-116">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md): Using the four access modifiers to declare five levels of accessibility.</span></span>  
  
-   <span data-ttu-id="f219d-117">[Zugriffsdomäne](../../../csharp/language-reference/keywords/accessibility-domain.md): Gibt an, in welche Teile des Programms ein Member verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="f219d-117">[Accessibility Domain](../../../csharp/language-reference/keywords/accessibility-domain.md): Specifies where, in the program sections, a member can be referenced.</span></span>  
  
-   <span data-ttu-id="f219d-118">[Einschränkungen bei der Verwendung von Zugriffsebenen](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): Ein Überblick über die Einschränkungen bei der Verwendung deklarierter Zugriffsebenen.</span><span class="sxs-lookup"><span data-stu-id="f219d-118">[Restrictions on Using Accessibility Levels](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): A summary of the restrictions on using declared accessibility levels.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f219d-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f219d-119">See Also</span></span>  
 <span data-ttu-id="f219d-120">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="f219d-120">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="f219d-121">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f219d-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="f219d-122">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="f219d-122">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="f219d-123">[Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="f219d-123">[Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span></span>  
 <span data-ttu-id="f219d-124">[Zugriffsschlüsselwörter](../../../csharp/language-reference/keywords/access-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="f219d-124">[Access Keywords](../../../csharp/language-reference/keywords/access-keywords.md) </span></span>  
 [<span data-ttu-id="f219d-125">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="f219d-125">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)

