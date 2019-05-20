---
title: private-Schlüsselwort – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- private_CSharpKeyword
- private
helpviewer_keywords:
- private keyword [C#]
ms.assetid: 654c0bb8-e6ac-4086-bf96-7474fa6aa1c8
ms.openlocfilehash: 67b2621d382651abc27cee2eadad91a6253895c1
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633330"
---
# <a name="private-c-reference"></a><span data-ttu-id="313a9-102">private (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="313a9-102">private (C# Reference)</span></span>

<span data-ttu-id="313a9-103">Das `private`-Schlüsselwort ist ein Zugriffsmodifizierer für Member.</span><span class="sxs-lookup"><span data-stu-id="313a9-103">The `private` keyword is a member access modifier.</span></span>

> <span data-ttu-id="313a9-104">Auf dieser Seite wird der Zugriff auf `private` behandelt.</span><span class="sxs-lookup"><span data-stu-id="313a9-104">This page covers `private` access.</span></span> <span data-ttu-id="313a9-105">Das Schlüsselwort `private` ist auch Teil des Zugriffsmodifizierers [`private protected`](./private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="313a9-105">The `private` keyword is also part of the [`private protected`](./private-protected.md) access modifier.</span></span>

<span data-ttu-id="313a9-106">Privater-Zugriff ist die am wenigsten eingeschränkte Zugriffsebene.</span><span class="sxs-lookup"><span data-stu-id="313a9-106">Private access is the least permissive access level.</span></span> <span data-ttu-id="313a9-107">Private Member sind nur innerhalb der Klasse oder Struktur, in der sie, wie im folgenden Beispiel, deklariert werden:</span><span class="sxs-lookup"><span data-stu-id="313a9-107">Private members are accessible only within the body of the class or the struct in which they are declared, as in this example:</span></span>

```csharp
class Employee
{
    private int i;
    double d;   // private access by default
}
```

<span data-ttu-id="313a9-108">Geschachtelte Typen im gleichen Text können auch auf diese privaten Member zugreifen.</span><span class="sxs-lookup"><span data-stu-id="313a9-108">Nested types in the same body can also access those private members.</span></span>

<span data-ttu-id="313a9-109">Es ist ein Kompilierzeitfehler auf einen privaten Member außerhalb der Klasse oder Struktur, in der sie deklariert ist, zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="313a9-109">It is a compile-time error to reference a private member outside the class or the struct in which it is declared.</span></span>

<span data-ttu-id="313a9-110">Einen Vergleich von `private` mit den anderen Zugriffsmodifizierern finden Sie unter [Zugriffsebenen](accessibility-levels.md) und [Zugriffsmodifizierer](../../programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="313a9-110">For a comparison of `private` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md) and [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md).</span></span>

## <a name="example"></a><span data-ttu-id="313a9-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="313a9-111">Example</span></span>

<span data-ttu-id="313a9-112">In diesem Beispiel enthält die `Employee`-Klasse zwei private Datenmember, `name` und `salary`.</span><span class="sxs-lookup"><span data-stu-id="313a9-112">In this example, the `Employee` class contains two private data members, `name` and `salary`.</span></span> <span data-ttu-id="313a9-113">Als private Member können nur Membermethoden auf sie zugreifen.</span><span class="sxs-lookup"><span data-stu-id="313a9-113">As private members, they cannot be accessed except by member methods.</span></span> <span data-ttu-id="313a9-114">Die öffentlichen Methoden `GetName` und `Salary` werden hinzugefügt, um gesteuerten Zugriff auf die privaten Member zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="313a9-114">Public methods named `GetName` and `Salary` are added to allow controlled access to the private members.</span></span> <span data-ttu-id="313a9-115">Auf den `name`-Member wird über eine öffentliche Methode zugegriffen, und auf den `salary`-Member wird über eine öffentliche schreibgeschützte Eigenschaft zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="313a9-115">The `name` member is accessed by way of a public method, and the `salary` member is accessed by way of a public read-only property.</span></span> <span data-ttu-id="313a9-116">(Weitere Informationen finden Sie unter [Eigenschaften](../../programming-guide/classes-and-structs/properties.md).)</span><span class="sxs-lookup"><span data-stu-id="313a9-116">(See [Properties](../../programming-guide/classes-and-structs/properties.md) for more information.)</span></span>

[!code-csharp[csrefKeywordsModifiers#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#10)]

## <a name="c-language-specification"></a><span data-ttu-id="313a9-117">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="313a9-117">C# language specification</span></span>  

<span data-ttu-id="313a9-118">Weitere Informationen finden Sie unter [Deklarierte Barrierefreiheit](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="313a9-118">For more information, see [Declared accessibility](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="313a9-119">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="313a9-119">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="313a9-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="313a9-120">See also</span></span>

- [<span data-ttu-id="313a9-121">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="313a9-121">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="313a9-122">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="313a9-122">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="313a9-123">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="313a9-123">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="313a9-124">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="313a9-124">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="313a9-125">Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="313a9-125">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="313a9-126">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="313a9-126">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="313a9-127">public</span><span class="sxs-lookup"><span data-stu-id="313a9-127">public</span></span>](public.md)
- [<span data-ttu-id="313a9-128">protected</span><span class="sxs-lookup"><span data-stu-id="313a9-128">protected</span></span>](protected.md)
- [<span data-ttu-id="313a9-129">internal</span><span class="sxs-lookup"><span data-stu-id="313a9-129">internal</span></span>](internal.md)
