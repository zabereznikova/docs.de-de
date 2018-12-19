---
title: '* *-Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 04/04/2018
f1_keywords:
- '*_CSharpKeyword'
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
ms.openlocfilehash: 24ac4a99c48f1e8204b821bfbf5f7fbc0a2b2f1d
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237349"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="a2cc9-102">\*-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="a2cc9-102">\* Operator (C# Reference)</span></span>
<span data-ttu-id="a2cc9-103">Der Multiplikationsoperator (`*`) berechnet das Produkt seiner Operanden.</span><span class="sxs-lookup"><span data-stu-id="a2cc9-103">The multiplication operator (`*`) computes the product of its operands.</span></span> <span data-ttu-id="a2cc9-104">Alle numerischen Typen besitzen vordefinierte Multiplikationsoperatoren.</span><span class="sxs-lookup"><span data-stu-id="a2cc9-104">All numeric types have predefined multiplication operators.</span></span>  

<span data-ttu-id="a2cc9-105">`*` dient auch als Dereferenzierungsoperator, der das Lesen und Schreiben in einen Zeiger ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="a2cc9-105">`*` also serves as the dereference operator, which allows reading and writing to a pointer.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="a2cc9-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a2cc9-106">Remarks</span></span>  
 <span data-ttu-id="a2cc9-107">Der `*`-Operator wird auch verwendet, um Zeigertypen zu deklarieren und Zeiger zu dereferenzieren.</span><span class="sxs-lookup"><span data-stu-id="a2cc9-107">The `*` operator is also used to declare pointer types and to dereference pointers.</span></span> <span data-ttu-id="a2cc9-108">Dieser Operator kann nur in nicht sicheren Kontexten verwendet werden, gekennzeichnet durch die Verwendung des [unsafe](../../../csharp/language-reference/keywords/unsafe.md)-Schlüsselworts und erfordert die Compileroption [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="a2cc9-108">This operator can only be used in unsafe contexts, denoted by the use of the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword, and requiring the [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>  <span data-ttu-id="a2cc9-109">Die englischen Begriffe „dereference operator“ und „indirection operator“ bezeichnen beide den Dereferenzierungsoperator.</span><span class="sxs-lookup"><span data-stu-id="a2cc9-109">The dereference operator is also known as the indirection operator.</span></span>  
  
 <span data-ttu-id="a2cc9-110">Benutzerdefinierte Typen können den binären `*`-Operator überladen (weitere Informationen finden Sie unter [Operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="a2cc9-110">User-defined types can overload the binary `*` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="a2cc9-111">Wenn ein binärer Operator überladen ist, wird der zugehörige Zuweisungsoperator, sofern er vorhanden ist, auch implizit überladen.</span><span class="sxs-lookup"><span data-stu-id="a2cc9-111">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2cc9-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a2cc9-112">Example</span></span>  
 [!code-csharp-interactive[csRefOperators#50](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="a2cc9-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a2cc9-113">Example</span></span>  
 [!code-csharp[csRefOperators#51](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="a2cc9-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2cc9-114">See Also</span></span>

- [<span data-ttu-id="a2cc9-115">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="a2cc9-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="a2cc9-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a2cc9-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="a2cc9-117">Unsicherer Code und Zeiger</span><span class="sxs-lookup"><span data-stu-id="a2cc9-117">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
- [<span data-ttu-id="a2cc9-118">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="a2cc9-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
