---
title: public (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- public
- public_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- public keyword [C#]
ms.assetid: 0ae45d16-a551-4b74-9845-57208de1328e
caps.latest.revision: 21
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
ms.openlocfilehash: ae19bf9a33a9860a8960cde5dd4402e10418a094
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="public-c-reference"></a><span data-ttu-id="0194e-102">public (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="0194e-102">public (C# Reference)</span></span>
<span data-ttu-id="0194e-103">Das Schlüsselwort `public` ist ein Zugriffsmodifizierer für Typen und Typmember.</span><span class="sxs-lookup"><span data-stu-id="0194e-103">The `public` keyword is an access modifier for types and type members.</span></span> <span data-ttu-id="0194e-104">Der öffentlicher Zugriff ist die eingeschränkteste Zugriffsebene.</span><span class="sxs-lookup"><span data-stu-id="0194e-104">Public access is the most permissive access level.</span></span> <span data-ttu-id="0194e-105">Es gibt keine Einschränkungen für den Zugriff auf öffentliche Member, wie im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="0194e-105">There are no restrictions on accessing public members, as in this example:</span></span>  
  
```  
class SampleClass  
{  
    public int x; // No access restrictions.  
}  
```  
  
 <span data-ttu-id="0194e-106">Unter [Access Modifiers (Zugriffsmodifizierer)](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) und [Accessibility Levels (Zugriffsebenen)](../../../csharp/language-reference/keywords/accessibility-levels.md) finden Sie weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="0194e-106">See [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) and [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) for more information.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0194e-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0194e-107">Example</span></span>  
 <span data-ttu-id="0194e-108">Im folgenden Beispiel werden zwei Klassen deklariert, `PointTest` und `MainClass`.</span><span class="sxs-lookup"><span data-stu-id="0194e-108">In the following example, two classes are declared, `PointTest` and `MainClass`.</span></span> <span data-ttu-id="0194e-109">Auf die öffentlichen Member `x` und `y` von `PointTest` wird direkt von `MainClass` zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="0194e-109">The public members `x` and `y` of `PointTest` are accessed directly from `MainClass`.</span></span>  
  
 <span data-ttu-id="0194e-110">[!code-cs[csrefKeywordsModifiers#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/public_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="0194e-110">[!code-cs[csrefKeywordsModifiers#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/public_1.cs)]</span></span>  
  
 <span data-ttu-id="0194e-111">Wenn Sie die Zugriffsebene `public` auf [private](../../../csharp/language-reference/keywords/private.md) (privat) oder [protected](../../../csharp/language-reference/keywords/protected.md) (geschützt) festlegen, wird die folgende Fehlermeldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="0194e-111">If you change the `public` access level to [private](../../../csharp/language-reference/keywords/private.md) or [protected](../../../csharp/language-reference/keywords/protected.md), you will get the error message:</span></span>  
  
 <span data-ttu-id="0194e-112">'PointTest.y' is inaccessible due to its protection level (Der Zugriff auf ‚PointTest.y‘ ist aufgrund der Sicherheitsebene nicht möglich).</span><span class="sxs-lookup"><span data-stu-id="0194e-112">'PointTest.y' is inaccessible due to its protection level.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="0194e-113">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="0194e-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0194e-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0194e-114">See Also</span></span>  
 <span data-ttu-id="0194e-115">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="0194e-115">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="0194e-116">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0194e-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="0194e-117">[Access Modifiers (Zugriffsmodifizierer)](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="0194e-117">[Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span></span>  
 <span data-ttu-id="0194e-118">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="0194e-118">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="0194e-119">[Zugriffsmodifizierer](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="0194e-119">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="0194e-120">[Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="0194e-120">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) </span></span>  
 <span data-ttu-id="0194e-121">[Modifizierer](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="0194e-121">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="0194e-122">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="0194e-122">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="0194e-123">[protected](../../../csharp/language-reference/keywords/protected.md) </span><span class="sxs-lookup"><span data-stu-id="0194e-123">[protected](../../../csharp/language-reference/keywords/protected.md) </span></span>  
 [<span data-ttu-id="0194e-124">internal</span><span class="sxs-lookup"><span data-stu-id="0194e-124">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)

