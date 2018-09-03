---
title: Operator != (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- '!=_CSharpKeyword'
helpviewer_keywords:
- inequality operator (!=) [C#]
- not equals operator (!=) [C#]
- '!= operator [C#]'
ms.assetid: eeff7a4e-ad6f-462d-9f8d-49e9b91c6c97
ms.openlocfilehash: e974ffb1b25944e24fca23864dc7e932ec1876d5
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43415380"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="7339a-102">Operator != (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="7339a-102">!= Operator (C# Reference)</span></span>
<span data-ttu-id="7339a-103">Der Ungleichheitsoperator (`!=`) gibt FALSE zurück, wenn die Operanden gleich sind; andernfalls TRUE.</span><span class="sxs-lookup"><span data-stu-id="7339a-103">The inequality operator (`!=`) returns false if its operands are equal, true otherwise.</span></span> <span data-ttu-id="7339a-104">Vergleichsoperatoren sind für alle Typen, einschließlich Zeichenfolgen und Objekte vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="7339a-104">Inequality operators are predefined for all types, including string and object.</span></span> <span data-ttu-id="7339a-105">Benutzerdefinierte Typen können den Operator `!=` überladen.</span><span class="sxs-lookup"><span data-stu-id="7339a-105">User-defined types can overload the `!=` operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7339a-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7339a-106">Remarks</span></span>  
 <span data-ttu-id="7339a-107">Für vordefinierte Werttypen gibt der Ungleichheitsoperator (`!=`) TRUE zurück, wenn die Werte der Operanden verschieden sind; andernfalls FALSE.</span><span class="sxs-lookup"><span data-stu-id="7339a-107">For predefined value types, the inequality operator (`!=`) returns true if the values of its operands are different, false otherwise.</span></span> <span data-ttu-id="7339a-108">Für andere Verweistypen als `string`, `!=` wird TRUE zurückgegeben, wenn beide Operanden auf unterschiedliche Objekte verweisen.</span><span class="sxs-lookup"><span data-stu-id="7339a-108">For reference types other than `string`, `!=` returns true if its two operands refer to different objects.</span></span> <span data-ttu-id="7339a-109">Für den `string`-Typ vergleicht `!=` die Werte der Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="7339a-109">For the `string` type, `!=` compares the values of the strings.</span></span>  
  
 <span data-ttu-id="7339a-110">Benutzerdefinierte Werttypen können den Operator `!=` überladen (weitere Informationen finden Sie unter [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="7339a-110">User-defined value types can overload the `!=` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="7339a-111">Dies können auch benutzerdefinierte Verweistypen, obwohl `!=` sich standardmäßig für vordefinierte und benutzerdefinierte Verweistypen wie oben beschrieben verhält.</span><span class="sxs-lookup"><span data-stu-id="7339a-111">So can user-defined reference types, although by default `!=` behaves as described above for both predefined and user-defined reference types.</span></span> <span data-ttu-id="7339a-112">Wenn `!=` überladen ist, muss [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) auch überladen werden.</span><span class="sxs-lookup"><span data-stu-id="7339a-112">If `!=` is overloaded, [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) must also be overloaded.</span></span> <span data-ttu-id="7339a-113">Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen (enum) zulässig.</span><span class="sxs-lookup"><span data-stu-id="7339a-113">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7339a-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7339a-114">Example</span></span>  
 [!code-csharp[csRefOperators#33](../../../csharp/language-reference/operators/codesnippet/CSharp/not-equal-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="7339a-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7339a-115">See Also</span></span>

- [<span data-ttu-id="7339a-116">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="7339a-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="7339a-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="7339a-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="7339a-118">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="7339a-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
