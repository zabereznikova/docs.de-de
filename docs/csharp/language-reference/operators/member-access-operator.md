---
title: . Operator – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ._CSharpKeyword
helpviewer_keywords:
- member access operator (.) [C#]
- . operator [C#]
- dot operator (.) [C#]
ms.assetid: a1f54b52-b686-4ae5-a48e-a2a9ebd0eb7b
ms.openlocfilehash: f5048761973e10bec9650469383e2f52cee74da4
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53235045"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="d05ea-103">.</span><span class="sxs-lookup"><span data-stu-id="d05ea-103">.</span></span> <span data-ttu-id="d05ea-104">Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="d05ea-104">Operator (C# Reference)</span></span>
<span data-ttu-id="d05ea-105">Der Punktoperator (`.`) wird für den Memberzugriff verwendet.</span><span class="sxs-lookup"><span data-stu-id="d05ea-105">The dot operator (`.`) is used for member access.</span></span> <span data-ttu-id="d05ea-106">Der Punktoperator gibt einen Member eines Typs oder Namespaces an.</span><span class="sxs-lookup"><span data-stu-id="d05ea-106">The dot operator specifies a member of a type or namespace.</span></span> <span data-ttu-id="d05ea-107">Der Punktoperator wird z.B. verwendet, um auf bestimmte Methoden innerhalb der .NET Framework-Klassenbibliotheken zuzugreifen:</span><span class="sxs-lookup"><span data-stu-id="d05ea-107">For example, the dot operator is used to access specific methods within the .NET Framework class libraries:</span></span>  
  
 [!code-csharp[csRefOperators#16](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_1.cs)]  
  
 <span data-ttu-id="d05ea-108">Betrachten Sie beispielsweise die folgende Klasse:</span><span class="sxs-lookup"><span data-stu-id="d05ea-108">For example, consider the following class:</span></span>  
  
 [!code-csharp[csRefOperators#17](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_2.cs)]  
  
 [!code-csharp[csRefOperators#18](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_3.cs)]  
  
 <span data-ttu-id="d05ea-109">Die Variable `s` verfügt über zwei Member (`a` und `b`); verwenden Sie den Punktoperator, um auf beide zuzugreifen:</span><span class="sxs-lookup"><span data-stu-id="d05ea-109">The variable `s` has two members, `a` and `b`; to access them, use the dot operator:</span></span>  
  
 [!code-csharp[csRefOperators#19](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_4.cs)]  
  
 <span data-ttu-id="d05ea-110">Der Punkt wird auch verwendet, um qualifizierte Namen zu erzeugen, die z.B. den Namespace oder die Schnittstelle angeben, zu der Sie gehören.</span><span class="sxs-lookup"><span data-stu-id="d05ea-110">The dot is also used to form qualified names, which are names that specify the namespace or interface, for example, to which they belong.</span></span>  
  
 [!code-csharp[csRefOperators#20](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_5.cs)]  
  
 <span data-ttu-id="d05ea-111">Die using-Direktive macht manche Namensqualifikationen optional:</span><span class="sxs-lookup"><span data-stu-id="d05ea-111">The using directive makes some name qualification optional:</span></span>  
  
 [!code-csharp[csRefOperators#21](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_6.cs)]  
  
 <span data-ttu-id="d05ea-112">Wenn ein Bezeichner jedoch nicht eindeutig ist, muss er qualifiziert werden:</span><span class="sxs-lookup"><span data-stu-id="d05ea-112">But when an identifier is ambiguous, it must be qualified:</span></span>  
  
 [!code-csharp[csRefOperators#22](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_7.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="d05ea-113">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="d05ea-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d05ea-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d05ea-114">See Also</span></span>

- [<span data-ttu-id="d05ea-115">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="d05ea-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="d05ea-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="d05ea-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="d05ea-117">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="d05ea-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
