---
title: sein. -Operator – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ._CSharpKeyword
helpviewer_keywords:
- member access operator (.) [C#]
- . operator [C#]
- dot operator (.) [C#]
ms.assetid: a1f54b52-b686-4ae5-a48e-a2a9ebd0eb7b
ms.openlocfilehash: a59f69d0349a054c8c2a5b701b8f63df113a6580
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333719"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="06f1a-103">sein.</span><span class="sxs-lookup"><span data-stu-id="06f1a-103">.</span></span> <span data-ttu-id="06f1a-104">operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="06f1a-104">operator (C# Reference)</span></span>

<span data-ttu-id="06f1a-105">Der Punktoperator (`.`) wird für den Memberzugriff verwendet.</span><span class="sxs-lookup"><span data-stu-id="06f1a-105">The dot operator (`.`) is used for member access.</span></span> <span data-ttu-id="06f1a-106">Der Punktoperator gibt einen Member eines Typs oder Namespaces an.</span><span class="sxs-lookup"><span data-stu-id="06f1a-106">The dot operator specifies a member of a type or namespace.</span></span> <span data-ttu-id="06f1a-107">Der Punktoperator wird z.B. verwendet, um auf bestimmte Methoden innerhalb der .NET Framework-Klassenbibliotheken zuzugreifen:</span><span class="sxs-lookup"><span data-stu-id="06f1a-107">For example, the dot operator is used to access specific methods within the .NET Framework class libraries:</span></span>

[!code-csharp[csRefOperators#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#16)]

<span data-ttu-id="06f1a-108">Betrachten Sie beispielsweise die folgende Klasse:</span><span class="sxs-lookup"><span data-stu-id="06f1a-108">For example, consider the following class:</span></span>

[!code-csharp[csRefOperators#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#17)]

[!code-csharp[csRefOperators#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#18)]

<span data-ttu-id="06f1a-109">Die Variable `s` verfügt über zwei Member (`a` und `b`); verwenden Sie den Punktoperator, um auf beide zuzugreifen:</span><span class="sxs-lookup"><span data-stu-id="06f1a-109">The variable `s` has two members, `a` and `b`; to access them, use the dot operator:</span></span>

[!code-csharp[csRefOperators#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#19)]

<span data-ttu-id="06f1a-110">Der Punkt wird auch verwendet, um qualifizierte Namen zu erzeugen, die z.B. den Namespace oder die Schnittstelle angeben, zu der Sie gehören.</span><span class="sxs-lookup"><span data-stu-id="06f1a-110">The dot is also used to form qualified names, which are names that specify the namespace or interface, for example, to which they belong.</span></span>

[!code-csharp[csRefOperators#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#20)]

<span data-ttu-id="06f1a-111">Die using-Direktive macht manche Namensqualifikationen optional:</span><span class="sxs-lookup"><span data-stu-id="06f1a-111">The using directive makes some name qualification optional:</span></span>

[!code-csharp[csRefOperators#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#21)]

<span data-ttu-id="06f1a-112">Wenn ein Bezeichner jedoch nicht eindeutig ist, muss er qualifiziert werden:</span><span class="sxs-lookup"><span data-stu-id="06f1a-112">But when an identifier is ambiguous, it must be qualified:</span></span>

[!code-csharp[csRefOperators#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#22)]

## <a name="c-language-specification"></a><span data-ttu-id="06f1a-113">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="06f1a-113">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="06f1a-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06f1a-114">See also</span></span>

- [<span data-ttu-id="06f1a-115">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="06f1a-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="06f1a-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="06f1a-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="06f1a-117">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="06f1a-117">C# Operators</span></span>](index.md)