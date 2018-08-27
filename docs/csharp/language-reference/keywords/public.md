---
title: public (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- public
- public_CSharpKeyword
helpviewer_keywords:
- public keyword [C#]
ms.assetid: 0ae45d16-a551-4b74-9845-57208de1328e
ms.openlocfilehash: 853f9c9ebe36345a897337d4e793d3c88059e068
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2018
ms.locfileid: "42998726"
---
# <a name="public-c-reference"></a><span data-ttu-id="18f5b-102">public (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="18f5b-102">public (C# Reference)</span></span>
<span data-ttu-id="18f5b-103">Das Schlüsselwort `public` ist ein Zugriffsmodifizierer für Typen und Typmember.</span><span class="sxs-lookup"><span data-stu-id="18f5b-103">The `public` keyword is an access modifier for types and type members.</span></span> <span data-ttu-id="18f5b-104">Der öffentlicher Zugriff ist die eingeschränkteste Zugriffsebene.</span><span class="sxs-lookup"><span data-stu-id="18f5b-104">Public access is the most permissive access level.</span></span> <span data-ttu-id="18f5b-105">Es gibt keine Einschränkungen für den Zugriff auf öffentliche Member, wie im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="18f5b-105">There are no restrictions on accessing public members, as in this example:</span></span>  
  
```csharp  
class SampleClass  
{  
    public int x; // No access restrictions.  
}  
```  
  
 <span data-ttu-id="18f5b-106">Unter [Access Modifiers (Zugriffsmodifizierer)](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) und [Accessibility Levels (Zugriffsebenen)](../../../csharp/language-reference/keywords/accessibility-levels.md) finden Sie weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="18f5b-106">See [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) and [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) for more information.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18f5b-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="18f5b-107">Example</span></span>  
 <span data-ttu-id="18f5b-108">Im folgenden Beispiel werden zwei Klassen deklariert, `PointTest` und `MainClass`.</span><span class="sxs-lookup"><span data-stu-id="18f5b-108">In the following example, two classes are declared, `PointTest` and `MainClass`.</span></span> <span data-ttu-id="18f5b-109">Auf die öffentlichen Member `x` und `y` von `PointTest` wird direkt von `MainClass` zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="18f5b-109">The public members `x` and `y` of `PointTest` are accessed directly from `MainClass`.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/public_1.cs)]  
  
 <span data-ttu-id="18f5b-110">Wenn Sie die Zugriffsebene `public` auf [private](../../../csharp/language-reference/keywords/private.md) (privat) oder [protected](../../../csharp/language-reference/keywords/protected.md) (geschützt) festlegen, wird die folgende Fehlermeldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="18f5b-110">If you change the `public` access level to [private](../../../csharp/language-reference/keywords/private.md) or [protected](../../../csharp/language-reference/keywords/protected.md), you will get the error message:</span></span>  
  
 <span data-ttu-id="18f5b-111">'PointTest.y' is inaccessible due to its protection level (Der Zugriff auf ‚PointTest.y‘ ist aufgrund der Sicherheitsebene nicht möglich).</span><span class="sxs-lookup"><span data-stu-id="18f5b-111">'PointTest.y' is inaccessible due to its protection level.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="18f5b-112">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="18f5b-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="18f5b-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18f5b-113">See Also</span></span>

- [<span data-ttu-id="18f5b-114">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="18f5b-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="18f5b-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="18f5b-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="18f5b-116">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="18f5b-116">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
- [<span data-ttu-id="18f5b-117">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="18f5b-117">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="18f5b-118">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="18f5b-118">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
- [<span data-ttu-id="18f5b-119">Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="18f5b-119">Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/accessibility-levels.md)  
- [<span data-ttu-id="18f5b-120">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="18f5b-120">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
- [<span data-ttu-id="18f5b-121">private</span><span class="sxs-lookup"><span data-stu-id="18f5b-121">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
- [<span data-ttu-id="18f5b-122">protected</span><span class="sxs-lookup"><span data-stu-id="18f5b-122">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
- [<span data-ttu-id="18f5b-123">internal</span><span class="sxs-lookup"><span data-stu-id="18f5b-123">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)
