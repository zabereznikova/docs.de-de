---
title: . Operator (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ._CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- member access operator (.) [C#]
- . operator [C#]
- dot operator (.) [C#]
ms.assetid: a1f54b52-b686-4ae5-a48e-a2a9ebd0eb7b
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
ms.openlocfilehash: fdc7c1821548509f3a3750aef2836c034f7aa53b
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="bbadf-103">.</span><span class="sxs-lookup"><span data-stu-id="bbadf-103">.</span></span> <span data-ttu-id="bbadf-104">Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="bbadf-104">Operator (C# Reference)</span></span>
<span data-ttu-id="bbadf-105">Der Punktoperator (`.`) wird für den Memberzugriff verwendet.</span><span class="sxs-lookup"><span data-stu-id="bbadf-105">The dot operator (`.`) is used for member access.</span></span> <span data-ttu-id="bbadf-106">Der Punktoperator gibt einen Member eines Typs oder Namespaces an.</span><span class="sxs-lookup"><span data-stu-id="bbadf-106">The dot operator specifies a member of a type or namespace.</span></span> <span data-ttu-id="bbadf-107">Der Punktoperator wird z.B. verwendet, um auf bestimmte Methoden innerhalb der .NET Framework-Klassenbibliotheken zuzugreifen:</span><span class="sxs-lookup"><span data-stu-id="bbadf-107">For example, the dot operator is used to access specific methods within the .NET Framework class libraries:</span></span>  
  
 <span data-ttu-id="bbadf-108">[!code-cs[csRefOperators#16](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="bbadf-108">[!code-cs[csRefOperators#16](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_1.cs)]</span></span>  
  
 <span data-ttu-id="bbadf-109">Betrachten Sie beispielsweise die folgende Klasse:</span><span class="sxs-lookup"><span data-stu-id="bbadf-109">For example, consider the following class:</span></span>  
  
 <span data-ttu-id="bbadf-110">[!code-cs[csRefOperators#17](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="bbadf-110">[!code-cs[csRefOperators#17](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_2.cs)]</span></span>  
  
 <span data-ttu-id="bbadf-111">[!code-cs[csRefOperators#18](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="bbadf-111">[!code-cs[csRefOperators#18](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_3.cs)]</span></span>  
  
 <span data-ttu-id="bbadf-112">Die Variable `s` verfügt über zwei Member (`a` und `b`); verwenden Sie den Punktoperator, um auf beide zuzugreifen:</span><span class="sxs-lookup"><span data-stu-id="bbadf-112">The variable `s` has two members, `a` and `b`; to access them, use the dot operator:</span></span>  
  
 <span data-ttu-id="bbadf-113">[!code-cs[csRefOperators#19](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="bbadf-113">[!code-cs[csRefOperators#19](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_4.cs)]</span></span>  
  
 <span data-ttu-id="bbadf-114">Der Punkt wird auch verwendet, um qualifizierte Namen zu erzeugen, die z.B. den Namespace oder die Schnittstelle angeben, zu der Sie gehören.</span><span class="sxs-lookup"><span data-stu-id="bbadf-114">The dot is also used to form qualified names, which are names that specify the namespace or interface, for example, to which they belong.</span></span>  
  
 <span data-ttu-id="bbadf-115">[!code-cs[csRefOperators#20](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="bbadf-115">[!code-cs[csRefOperators#20](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_5.cs)]</span></span>  
  
 <span data-ttu-id="bbadf-116">Die using-Direktive macht manche Namensqualifikationen optional:</span><span class="sxs-lookup"><span data-stu-id="bbadf-116">The using directive makes some name qualification optional:</span></span>  
  
 <span data-ttu-id="bbadf-117">[!code-cs[csRefOperators#21](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="bbadf-117">[!code-cs[csRefOperators#21](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_6.cs)]</span></span>  
  
 <span data-ttu-id="bbadf-118">Wenn ein Bezeichner jedoch nicht eindeutig ist, muss er qualifiziert werden:</span><span class="sxs-lookup"><span data-stu-id="bbadf-118">But when an identifier is ambiguous, it must be qualified:</span></span>  
  
 <span data-ttu-id="bbadf-119">[!code-cs[csRefOperators#22](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="bbadf-119">[!code-cs[csRefOperators#22](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_7.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="bbadf-120">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="bbadf-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bbadf-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bbadf-121">See Also</span></span>  
 <span data-ttu-id="bbadf-122">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="bbadf-122">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="bbadf-123">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="bbadf-123">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="bbadf-124">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="bbadf-124">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

