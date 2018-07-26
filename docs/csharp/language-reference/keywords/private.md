---
title: private (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- private_CSharpKeyword
- private
helpviewer_keywords:
- private keyword [C#]
ms.assetid: 654c0bb8-e6ac-4086-bf96-7474fa6aa1c8
ms.openlocfilehash: 89bc23e91bf693f0a95b75dffe2399cb7e865b50
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37960806"
---
# <a name="private-c-reference"></a><span data-ttu-id="5a815-102">private (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="5a815-102">private (C# Reference)</span></span>
<span data-ttu-id="5a815-103">Das `private`-Schlüsselwort ist ein Zugriffsmodifizierer für Member.</span><span class="sxs-lookup"><span data-stu-id="5a815-103">The `private` keyword is a member access modifier.</span></span> 
   
 > <span data-ttu-id="5a815-104">Auf dieser Seite wird der Zugriff auf `private` behandelt.</span><span class="sxs-lookup"><span data-stu-id="5a815-104">This page covers `private` access.</span></span> <span data-ttu-id="5a815-105">Das Schlüsselwort `private` ist auch Teil des Zugriffsmodifizierers [`private protected`](./private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="5a815-105">The `private` keyword is also part of the [`private protected`](./private-protected.md) access modifier.</span></span>
  
<span data-ttu-id="5a815-106">Privater-Zugriff ist die am wenigsten eingeschränkte Zugriffsebene.</span><span class="sxs-lookup"><span data-stu-id="5a815-106">Private access is the least permissive access level.</span></span> <span data-ttu-id="5a815-107">Private Member sind nur innerhalb der Klasse oder Struktur, in der sie, wie im folgenden Beispiel, deklariert werden:</span><span class="sxs-lookup"><span data-stu-id="5a815-107">Private members are accessible only within the body of the class or the struct in which they are declared, as in this example:</span></span>  
  
```csharp  
class Employee  
{  
    private int i;  
    double d;   // private access by default  
}  
```  

 <span data-ttu-id="5a815-108">Geschachtelte Typen im gleichen Text können auch auf diese privaten Member zugreifen.</span><span class="sxs-lookup"><span data-stu-id="5a815-108">Nested types in the same body can also access those private members.</span></span>  
  
 <span data-ttu-id="5a815-109">Es ist ein Kompilierzeitfehler auf einen privaten Member außerhalb der Klasse oder Struktur, in der sie deklariert ist, zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="5a815-109">It is a compile-time error to reference a private member outside the class or the struct in which it is declared.</span></span>  
  
 <span data-ttu-id="5a815-110">Einen Vergleich von `private` mit den anderen Zugriffsmodifizierern finden Sie unter [Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md) und [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="5a815-110">For a comparison of `private` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) and [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a815-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5a815-111">Example</span></span>  
 <span data-ttu-id="5a815-112">In diesem Beispiel enthält die `Employee`-Klasse zwei private Datenmember, `name` und `salary`.</span><span class="sxs-lookup"><span data-stu-id="5a815-112">In this example, the `Employee` class contains two private data members, `name` and `salary`.</span></span> <span data-ttu-id="5a815-113">Als private Member können nur Membermethoden auf sie zugreifen.</span><span class="sxs-lookup"><span data-stu-id="5a815-113">As private members, they cannot be accessed except by member methods.</span></span> <span data-ttu-id="5a815-114">Die öffentlichen Methoden `GetName` und `Salary` werden hinzugefügt, um gesteuerten Zugriff auf die privaten Member zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="5a815-114">Public methods named `GetName` and `Salary` are added to allow controlled access to the private members.</span></span> <span data-ttu-id="5a815-115">Auf den `name`-Member wird über eine öffentliche Methode zugegriffen, und auf den `salary`-Member wird über eine öffentliche schreibgeschützte Eigenschaft zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="5a815-115">The `name` member is accessed by way of a public method, and the `salary` member is accessed by way of a public read-only property.</span></span> <span data-ttu-id="5a815-116">(Weitere Informationen finden Sie unter [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md).)</span><span class="sxs-lookup"><span data-stu-id="5a815-116">(See [Properties](../../../csharp/programming-guide/classes-and-structs/properties.md) for more information.)</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/private_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="5a815-117">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="5a815-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5a815-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5a815-118">See Also</span></span>  
 [<span data-ttu-id="5a815-119">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="5a815-119">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="5a815-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="5a815-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="5a815-121">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="5a815-121">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="5a815-122">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="5a815-122">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [<span data-ttu-id="5a815-123">Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="5a815-123">Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/accessibility-levels.md)  
 [<span data-ttu-id="5a815-124">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="5a815-124">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="5a815-125">public</span><span class="sxs-lookup"><span data-stu-id="5a815-125">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 [<span data-ttu-id="5a815-126">protected</span><span class="sxs-lookup"><span data-stu-id="5a815-126">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
 [<span data-ttu-id="5a815-127">internal</span><span class="sxs-lookup"><span data-stu-id="5a815-127">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)
