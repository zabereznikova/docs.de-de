---
title: '* Operator (C#-Referenz)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '*_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
caps.latest.revision: 14
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
ms.openlocfilehash: 165ca8f797eb8d03ae1dec8c0ec5e1f4b31cb050
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="af923-102">Operator * (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="af923-102">* Operator (C# Reference)</span></span>
<span data-ttu-id="af923-103">Der Multiplikationsoperator (`*`) berechnet das Produkt seiner Operanden.</span><span class="sxs-lookup"><span data-stu-id="af923-103">The multiplication operator (`*`), which computes the product of its operands.</span></span>  <span data-ttu-id="af923-104">Darüber hinaus ermöglicht der Dereferenzierungsoperator das Lesen und Schreiben in einen Zeiger.</span><span class="sxs-lookup"><span data-stu-id="af923-104">Also, the dereference operator, which allows reading and writing to a pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af923-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="af923-105">Remarks</span></span>  
 <span data-ttu-id="af923-106">Alle numerischen Typen besitzen vordefinierte Multiplikationsoperatoren.</span><span class="sxs-lookup"><span data-stu-id="af923-106">All numeric types have predefined multiplication operators.</span></span>  
  
 <span data-ttu-id="af923-107">Der `*`-Operator wird auch verwendet, um Zeigertypen zu deklarieren und Zeiger zu dereferenzieren.</span><span class="sxs-lookup"><span data-stu-id="af923-107">The `*` operator is also used to declare pointer types and to dereference pointers.</span></span> <span data-ttu-id="af923-108">Dieser Operator kann nur in nicht sicheren Kontexten verwendet werden, gekennzeichnet durch die Verwendung des [unsafe](../../../csharp/language-reference/keywords/unsafe.md)-Schlüsselworts und erfordert die Compileroption [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="af923-108">This operator can only be used in unsafe contexts, denoted by the use of the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword, and requiring the [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>  <span data-ttu-id="af923-109">Die englischen Begriffe „dereference operator“ und „indirection operator“ bezeichnen beide den Dereferenzierungsoperator.</span><span class="sxs-lookup"><span data-stu-id="af923-109">The dereference operator is also known as the indirection operator.</span></span>  
  
 <span data-ttu-id="af923-110">Benutzerdefinierte Typen können den binären `*`-Operator überladen (weitere Informationen finden Sie unter [Operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="af923-110">User-defined types can overload the binary `*` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="af923-111">Wenn ein binärer Operator überladen ist, wird der zugehörige Zuweisungsoperator, sofern er vorhanden ist, auch implizit überladen.</span><span class="sxs-lookup"><span data-stu-id="af923-111">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af923-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="af923-112">Example</span></span>  
 <span data-ttu-id="af923-113">[!code-cs[csRefOperators#50](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="af923-113">[!code-cs[csRefOperators#50](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="af923-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="af923-114">Example</span></span>  
 <span data-ttu-id="af923-115">[!code-cs[csRefOperators#51](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="af923-115">[!code-cs[csRefOperators#51](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af923-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af923-116">See Also</span></span>  
 <span data-ttu-id="af923-117">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="af923-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="af923-118">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="af923-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="af923-119">[Unsicherer Code und Zeiger](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span><span class="sxs-lookup"><span data-stu-id="af923-119">[Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span></span>  
 [<span data-ttu-id="af923-120">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="af923-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

