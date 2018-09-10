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
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44192014"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="440da-102">Operator != (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="440da-102">!= Operator (C# Reference)</span></span>
<span data-ttu-id="440da-103">Der Ungleichheitsoperator (`!=`) gibt FALSE zurück, wenn die Operanden gleich sind; andernfalls TRUE.</span><span class="sxs-lookup"><span data-stu-id="440da-103">The inequality operator (`!=`) returns false if its operands are equal, true otherwise.</span></span> <span data-ttu-id="440da-104">Vergleichsoperatoren sind für alle Typen, einschließlich Zeichenfolgen und Objekte vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="440da-104">Inequality operators are predefined for all types, including string and object.</span></span> <span data-ttu-id="440da-105">Benutzerdefinierte Typen können den Operator `!=` überladen.</span><span class="sxs-lookup"><span data-stu-id="440da-105">User-defined types can overload the `!=` operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="440da-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="440da-106">Remarks</span></span>  
 <span data-ttu-id="440da-107">Für vordefinierte Werttypen gibt der Ungleichheitsoperator (`!=`) TRUE zurück, wenn die Werte der Operanden verschieden sind; andernfalls FALSE.</span><span class="sxs-lookup"><span data-stu-id="440da-107">For predefined value types, the inequality operator (`!=`) returns true if the values of its operands are different, false otherwise.</span></span> <span data-ttu-id="440da-108">Für andere Verweistypen als `string`, `!=` wird TRUE zurückgegeben, wenn beide Operanden auf unterschiedliche Objekte verweisen.</span><span class="sxs-lookup"><span data-stu-id="440da-108">For reference types other than `string`, `!=` returns true if its two operands refer to different objects.</span></span> <span data-ttu-id="440da-109">Für den `string`-Typ vergleicht `!=` die Werte der Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="440da-109">For the `string` type, `!=` compares the values of the strings.</span></span>  
  
 <span data-ttu-id="440da-110">Benutzerdefinierte Werttypen können den Operator `!=` überladen (weitere Informationen finden Sie unter [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="440da-110">User-defined value types can overload the `!=` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="440da-111">Dies können auch benutzerdefinierte Verweistypen, obwohl `!=` sich standardmäßig für vordefinierte und benutzerdefinierte Verweistypen wie oben beschrieben verhält.</span><span class="sxs-lookup"><span data-stu-id="440da-111">So can user-defined reference types, although by default `!=` behaves as described above for both predefined and user-defined reference types.</span></span> <span data-ttu-id="440da-112">Wenn `!=` überladen ist, muss [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) auch überladen werden.</span><span class="sxs-lookup"><span data-stu-id="440da-112">If `!=` is overloaded, [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) must also be overloaded.</span></span> <span data-ttu-id="440da-113">Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen (enum) zulässig.</span><span class="sxs-lookup"><span data-stu-id="440da-113">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="440da-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="440da-114">Example</span></span>  
 [!code-csharp[csRefOperators#33](../../../csharp/language-reference/operators/codesnippet/CSharp/not-equal-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="440da-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="440da-115">See Also</span></span>

- [<span data-ttu-id="440da-116">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="440da-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="440da-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="440da-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="440da-118">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="440da-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
