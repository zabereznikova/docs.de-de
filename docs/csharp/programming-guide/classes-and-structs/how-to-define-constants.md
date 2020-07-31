---
title: Definieren von Konstanten in C#
description: Hier erfahren Sie, wie Sie Konstanten in C# definieren. Dies sind Felder, deren Werte zur Kompilierzeit festgelegt werden. Verwenden Sie Konstanten, um aussagekräftige Namen für spezielle Werte bereitzustellen.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.assetid: 43f511be-346c-4b8a-995e-aded94542ece
ms.openlocfilehash: afa2799cf76f976e332f91b631dc90e2799a0aa0
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864643"
---
# <a name="how-to-define-constants-in-c"></a><span data-ttu-id="bca23-104">Definieren von Konstanten in C\#</span><span class="sxs-lookup"><span data-stu-id="bca23-104">How to define constants in C\#</span></span>
<span data-ttu-id="bca23-105">Konstanten sind Felder, deren Wert bei der Kompilierung festgelegt wird und nie geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="bca23-105">Constants are fields whose values are set at compile time and can never be changed.</span></span> <span data-ttu-id="bca23-106">Verwenden Sie Konstanten, um aussagekräftige Namen anstelle numerischer Literale („magische Zahlen“) für spezielle Werte bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="bca23-106">Use constants to provide meaningful names instead of numeric literals ("magic numbers") for special values.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bca23-107">In C# kann die Präprozessoranweisung [#define](../../language-reference/preprocessor-directives/preprocessor-define.md) nicht verwendet werden, um Konstanten zu definieren, so wie Sie es normalerweise in C und C++ tun würden.</span><span class="sxs-lookup"><span data-stu-id="bca23-107">In C# the [#define](../../language-reference/preprocessor-directives/preprocessor-define.md) preprocessor directive cannot be used to define constants in the way that is typically used in C and C++.</span></span>  
  
 <span data-ttu-id="bca23-108">Verwenden Sie zum Definieren von konstanten Werten integraler Typen (`int`, `byte` usw.) einen enumerierten Typ.</span><span class="sxs-lookup"><span data-stu-id="bca23-108">To define constant values of integral types (`int`, `byte`, and so on) use an enumerated type.</span></span> <span data-ttu-id="bca23-109">Weitere Informationen finden Sie unter [enum](../../language-reference/builtin-types/enum.md).</span><span class="sxs-lookup"><span data-stu-id="bca23-109">For more information, see [enum](../../language-reference/builtin-types/enum.md).</span></span>  
  
 <span data-ttu-id="bca23-110">Zum Definieren nicht-integraler Konstanten ist eine Methode, diese in einer einzelnen statischen Klasse namens `Constants` zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="bca23-110">To define non-integral constants, one approach is to group them in a single static class named `Constants`.</span></span> <span data-ttu-id="bca23-111">Dies erfordert, dass allen Verweise auf die Konstanten, so wie im folgenden Beispiel gezeigt, der Klassenname vorangestellt wird.</span><span class="sxs-lookup"><span data-stu-id="bca23-111">This will require that all references to the constants be prefaced with the class name, as shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bca23-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bca23-112">Example</span></span>  
 [!code-csharp[csProgGuideObjects#89](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#89)]  
  
 <span data-ttu-id="bca23-113">Die Verwendung des Klassennamenqualifizierers hilft Ihnen sicherzustellen, dass Sie und andere Benutzer der Konstante verstehen, dass diese konstant ist und nicht verändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="bca23-113">The use of the class name qualifier helps ensure that you and others who use the constant understand that it is constant and cannot be modified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bca23-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bca23-114">See also</span></span>

- [<span data-ttu-id="bca23-115">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="bca23-115">Classes and Structs</span></span>](./index.md)
