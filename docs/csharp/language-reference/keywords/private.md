---
title: private (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- private_CSharpKeyword
- private
dev_langs:
- CSharp
helpviewer_keywords:
- private keyword [C#]
ms.assetid: 654c0bb8-e6ac-4086-bf96-7474fa6aa1c8
caps.latest.revision: 17
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
ms.openlocfilehash: c18fd87b12bf3f7f1a1d1ef0dfded8643308169c
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="private-c-reference"></a><span data-ttu-id="d850f-102">private (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="d850f-102">private (C# Reference)</span></span>
<span data-ttu-id="d850f-103">Das `private`-Schlüsselwort ist ein Zugriffsmodifizierer für Member.</span><span class="sxs-lookup"><span data-stu-id="d850f-103">The `private` keyword is a member access modifier.</span></span> <span data-ttu-id="d850f-104">Privater-Zugriff ist die am wenigsten eingeschränkte Zugriffsebene.</span><span class="sxs-lookup"><span data-stu-id="d850f-104">Private access is the least permissive access level.</span></span> <span data-ttu-id="d850f-105">Private Member sind nur innerhalb der Klasse oder Struktur, in der sie, wie im folgenden Beispiel, deklariert werden:</span><span class="sxs-lookup"><span data-stu-id="d850f-105">Private members are accessible only within the body of the class or the struct in which they are declared, as in this example:</span></span>  
  
```  
class Employee  
{  
    private int i;  
    double d;   // private access by default  
}  
```  
  
 <span data-ttu-id="d850f-106">Geschachtelte Typen im gleichen Text können auch auf diese privaten Member zugreifen.</span><span class="sxs-lookup"><span data-stu-id="d850f-106">Nested types in the same body can also access those private members.</span></span>  
  
 <span data-ttu-id="d850f-107">Es ist ein Kompilierzeitfehler auf einen privaten Member außerhalb der Klasse oder Struktur, in der sie deklariert ist, zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="d850f-107">It is a compile-time error to reference a private member outside the class or the struct in which it is declared.</span></span>  
  
 <span data-ttu-id="d850f-108">Einen Vergleich von `private` mit den anderen Zugriffsmodifizierern finden Sie unter [Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md) und [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="d850f-108">For a comparison of `private` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) and [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d850f-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d850f-109">Example</span></span>  
 <span data-ttu-id="d850f-110">In diesem Beispiel enthält die `Employee`-Klasse zwei private Datenmember, `name` und `salary`.</span><span class="sxs-lookup"><span data-stu-id="d850f-110">In this example, the `Employee` class contains two private data members, `name` and `salary`.</span></span> <span data-ttu-id="d850f-111">Als private Member können nur Membermethoden auf sie zugreifen.</span><span class="sxs-lookup"><span data-stu-id="d850f-111">As private members, they cannot be accessed except by member methods.</span></span> <span data-ttu-id="d850f-112">Die öffentlichen Methoden `GetName` und `Salary` werden hinzugefügt, um gesteuerten Zugriff auf die privaten Member zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="d850f-112">Public methods named `GetName` and `Salary` are added to allow controlled access to the private members.</span></span> <span data-ttu-id="d850f-113">Auf den `name`-Member wird über eine öffentliche Methode zugegriffen, und auf den `salary`-Member wird über eine öffentliche schreibgeschützte Eigenschaft zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="d850f-113">The `name` member is accessed by way of a public method, and the `salary` member is accessed by way of a public read-only property.</span></span> <span data-ttu-id="d850f-114">(Weitere Informationen finden Sie unter [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md).)</span><span class="sxs-lookup"><span data-stu-id="d850f-114">(See [Properties](../../../csharp/programming-guide/classes-and-structs/properties.md) for more information.)</span></span>  
  
 <span data-ttu-id="d850f-115">[!code-cs[csrefKeywordsModifiers#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/private_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d850f-115">[!code-cs[csrefKeywordsModifiers#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/private_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="d850f-116">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="d850f-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d850f-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d850f-117">See Also</span></span>  
 <span data-ttu-id="d850f-118">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="d850f-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="d850f-119">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d850f-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d850f-120">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="d850f-120">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="d850f-121">[Zugriffsmodifizierer](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="d850f-121">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="d850f-122">[Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="d850f-122">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) </span></span>  
 <span data-ttu-id="d850f-123">[Modifizierer](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="d850f-123">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="d850f-124">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="d850f-124">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="d850f-125">[protected](../../../csharp/language-reference/keywords/protected.md) </span><span class="sxs-lookup"><span data-stu-id="d850f-125">[protected](../../../csharp/language-reference/keywords/protected.md) </span></span>  
 [<span data-ttu-id="d850f-126">internal</span><span class="sxs-lookup"><span data-stu-id="d850f-126">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)

