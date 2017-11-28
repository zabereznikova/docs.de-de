---
title: . Operator (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: ._CSharpKeyword
helpviewer_keywords:
- member access operator (.) [C#]
- . operator [C#]
- dot operator (.) [C#]
ms.assetid: a1f54b52-b686-4ae5-a48e-a2a9ebd0eb7b
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2bb636bc110f57ace9a824a43afdd86246ed0a5c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="2cebd-103">.</span><span class="sxs-lookup"><span data-stu-id="2cebd-103">.</span></span> <span data-ttu-id="2cebd-104">Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="2cebd-104">Operator (C# Reference)</span></span>
<span data-ttu-id="2cebd-105">Der Punktoperator (`.`) wird für den Memberzugriff verwendet.</span><span class="sxs-lookup"><span data-stu-id="2cebd-105">The dot operator (`.`) is used for member access.</span></span> <span data-ttu-id="2cebd-106">Der Punktoperator gibt einen Member eines Typs oder Namespaces an.</span><span class="sxs-lookup"><span data-stu-id="2cebd-106">The dot operator specifies a member of a type or namespace.</span></span> <span data-ttu-id="2cebd-107">Der Punktoperator wird z.B. verwendet, um auf bestimmte Methoden innerhalb der .NET Framework-Klassenbibliotheken zuzugreifen:</span><span class="sxs-lookup"><span data-stu-id="2cebd-107">For example, the dot operator is used to access specific methods within the .NET Framework class libraries:</span></span>  
  
 [!code-csharp[csRefOperators#16](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_1.cs)]  
  
 <span data-ttu-id="2cebd-108">Betrachten Sie beispielsweise die folgende Klasse:</span><span class="sxs-lookup"><span data-stu-id="2cebd-108">For example, consider the following class:</span></span>  
  
 [!code-csharp[csRefOperators#17](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_2.cs)]  
  
 [!code-csharp[csRefOperators#18](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_3.cs)]  
  
 <span data-ttu-id="2cebd-109">Die Variable `s` verfügt über zwei Member (`a` und `b`); verwenden Sie den Punktoperator, um auf beide zuzugreifen:</span><span class="sxs-lookup"><span data-stu-id="2cebd-109">The variable `s` has two members, `a` and `b`; to access them, use the dot operator:</span></span>  
  
 [!code-csharp[csRefOperators#19](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_4.cs)]  
  
 <span data-ttu-id="2cebd-110">Der Punkt wird auch verwendet, um qualifizierte Namen zu erzeugen, die z.B. den Namespace oder die Schnittstelle angeben, zu der Sie gehören.</span><span class="sxs-lookup"><span data-stu-id="2cebd-110">The dot is also used to form qualified names, which are names that specify the namespace or interface, for example, to which they belong.</span></span>  
  
 [!code-csharp[csRefOperators#20](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_5.cs)]  
  
 <span data-ttu-id="2cebd-111">Die using-Direktive macht manche Namensqualifikationen optional:</span><span class="sxs-lookup"><span data-stu-id="2cebd-111">The using directive makes some name qualification optional:</span></span>  
  
 [!code-csharp[csRefOperators#21](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_6.cs)]  
  
 <span data-ttu-id="2cebd-112">Wenn ein Bezeichner jedoch nicht eindeutig ist, muss er qualifiziert werden:</span><span class="sxs-lookup"><span data-stu-id="2cebd-112">But when an identifier is ambiguous, it must be qualified:</span></span>  
  
 [!code-csharp[csRefOperators#22](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_7.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="2cebd-113">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="2cebd-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2cebd-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2cebd-114">See Also</span></span>  
 [<span data-ttu-id="2cebd-115">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="2cebd-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="2cebd-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="2cebd-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="2cebd-117">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="2cebd-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
