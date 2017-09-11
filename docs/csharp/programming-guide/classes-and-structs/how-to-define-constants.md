---
title: 'Gewusst wie: Definieren von Konstanten in C#'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.assetid: 43f511be-346c-4b8a-995e-aded94542ece
caps.latest.revision: 7
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
ms.openlocfilehash: 6c5a6f63675893eb0700afab462bf237f5639d74
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-define-constants-in-c"></a><span data-ttu-id="7fb9e-102">Gewusst wie: Definieren von Konstanten in C#</span><span class="sxs-lookup"><span data-stu-id="7fb9e-102">How to: Define Constants in C#</span></span>
<span data-ttu-id="7fb9e-103">Konstanten sind Felder, deren Wert bei der Kompilierung festgelegt wird und nie geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="7fb9e-103">Constants are fields whose values are set at compile time and can never be changed.</span></span> <span data-ttu-id="7fb9e-104">Verwenden Sie Konstanten, um aussagekräftige Namen anstelle numerischer Literale („magische Zahlen“) für spezielle Werte bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="7fb9e-104">Use constants to provide meaningful names instead of numeric literals ("magic numbers") for special values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7fb9e-105">In C# kann die Präprozessoranweisung [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) nicht verwendet werden, um Konstanten zu definieren, so wie Sie es normalerweise in C und C++ tun würden.</span><span class="sxs-lookup"><span data-stu-id="7fb9e-105">In C# the [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) preprocessor directive cannot be used to define constants in the way that is typically used in C and C++.</span></span>  
  
 <span data-ttu-id="7fb9e-106">Verwenden Sie zum Definieren von konstanten Werten integraler Typen (`int`, `byte` usw.) einen enumerierten Typ.</span><span class="sxs-lookup"><span data-stu-id="7fb9e-106">To define constant values of integral types (`int`, `byte`, and so on) use an enumerated type.</span></span> <span data-ttu-id="7fb9e-107">Weitere Informationen finden Sie unter [enum](../../../csharp/language-reference/keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="7fb9e-107">For more information, see [enum](../../../csharp/language-reference/keywords/enum.md).</span></span>  
  
 <span data-ttu-id="7fb9e-108">Zum Definieren nicht-integraler Konstanten ist eine Methode, diese in einer einzelnen statischen Klasse namens `Constants` zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="7fb9e-108">To define non-integral constants, one approach is to group them in a single static class named `Constants`.</span></span> <span data-ttu-id="7fb9e-109">Dies erfordert, dass allen Verweise auf die Konstanten, so wie im folgenden Beispiel gezeigt, der Klassenname vorangestellt wird.</span><span class="sxs-lookup"><span data-stu-id="7fb9e-109">This will require that all references to the constants be prefaced with the class name, as shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7fb9e-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7fb9e-110">Example</span></span>  
 <span data-ttu-id="7fb9e-111">[!code-cs[csProgGuideObjects#89](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-constants_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="7fb9e-111">[!code-cs[csProgGuideObjects#89](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-constants_1.cs)]</span></span>  
  
 <span data-ttu-id="7fb9e-112">Die Verwendung des Klassennamenqualifizierers hilft Ihnen sicherzustellen, dass Sie und andere Benutzer der Konstante verstehen, dass diese konstant ist und nicht verändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="7fb9e-112">The use of the class name qualifier helps ensure that you and others who use the constant understand that it is constant and cannot be modified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fb9e-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7fb9e-113">See Also</span></span>  
 [<span data-ttu-id="7fb9e-114">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="7fb9e-114">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)

