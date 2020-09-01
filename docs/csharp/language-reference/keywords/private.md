---
description: private-Schlüsselwort – C#-Referenz
title: private-Schlüsselwort – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- private_CSharpKeyword
- private
helpviewer_keywords:
- private keyword [C#]
ms.assetid: 654c0bb8-e6ac-4086-bf96-7474fa6aa1c8
ms.openlocfilehash: e6f40712fd2cca6d7b1f64760f1c6c5dd5c71370
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89139397"
---
# <a name="private-c-reference"></a><span data-ttu-id="bba42-103">private (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="bba42-103">private (C# Reference)</span></span>

<span data-ttu-id="bba42-104">Das `private`-Schlüsselwort ist ein Zugriffsmodifizierer für Member.</span><span class="sxs-lookup"><span data-stu-id="bba42-104">The `private` keyword is a member access modifier.</span></span>

> <span data-ttu-id="bba42-105">Auf dieser Seite wird der Zugriff auf `private` behandelt.</span><span class="sxs-lookup"><span data-stu-id="bba42-105">This page covers `private` access.</span></span> <span data-ttu-id="bba42-106">Das Schlüsselwort `private` ist auch Teil des Zugriffsmodifizierers [`private protected`](./private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="bba42-106">The `private` keyword is also part of the [`private protected`](./private-protected.md) access modifier.</span></span>

<span data-ttu-id="bba42-107">Privater-Zugriff ist die am wenigsten eingeschränkte Zugriffsebene.</span><span class="sxs-lookup"><span data-stu-id="bba42-107">Private access is the least permissive access level.</span></span> <span data-ttu-id="bba42-108">Private Member sind nur innerhalb der Klasse oder Struktur, in der sie, wie im folgenden Beispiel, deklariert werden:</span><span class="sxs-lookup"><span data-stu-id="bba42-108">Private members are accessible only within the body of the class or the struct in which they are declared, as in this example:</span></span>

```csharp
class Employee
{
    private int i;
    double d;   // private access by default
}
```

<span data-ttu-id="bba42-109">Geschachtelte Typen im gleichen Text können auch auf diese privaten Member zugreifen.</span><span class="sxs-lookup"><span data-stu-id="bba42-109">Nested types in the same body can also access those private members.</span></span>

<span data-ttu-id="bba42-110">Es ist ein Kompilierzeitfehler auf einen privaten Member außerhalb der Klasse oder Struktur, in der sie deklariert ist, zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="bba42-110">It is a compile-time error to reference a private member outside the class or the struct in which it is declared.</span></span>

<span data-ttu-id="bba42-111">Einen Vergleich von `private` mit den anderen Zugriffsmodifizierern finden Sie unter [Zugriffsebenen](accessibility-levels.md) und [Zugriffsmodifizierer](../../programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="bba42-111">For a comparison of `private` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md) and [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md).</span></span>

## <a name="example"></a><span data-ttu-id="bba42-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bba42-112">Example</span></span>

<span data-ttu-id="bba42-113">In diesem Beispiel enthält die `Employee`-Klasse zwei private Datenmember, `name` und `salary`.</span><span class="sxs-lookup"><span data-stu-id="bba42-113">In this example, the `Employee` class contains two private data members, `name` and `salary`.</span></span> <span data-ttu-id="bba42-114">Als private Member können nur Membermethoden auf sie zugreifen.</span><span class="sxs-lookup"><span data-stu-id="bba42-114">As private members, they cannot be accessed except by member methods.</span></span> <span data-ttu-id="bba42-115">Die öffentlichen Methoden `GetName` und `Salary` werden hinzugefügt, um gesteuerten Zugriff auf die privaten Member zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="bba42-115">Public methods named `GetName` and `Salary` are added to allow controlled access to the private members.</span></span> <span data-ttu-id="bba42-116">Auf den `name`-Member wird über eine öffentliche Methode zugegriffen, und auf den `salary`-Member wird über eine öffentliche schreibgeschützte Eigenschaft zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="bba42-116">The `name` member is accessed by way of a public method, and the `salary` member is accessed by way of a public read-only property.</span></span> <span data-ttu-id="bba42-117">(Weitere Informationen finden Sie unter [Eigenschaften](../../programming-guide/classes-and-structs/properties.md).)</span><span class="sxs-lookup"><span data-stu-id="bba42-117">(See [Properties](../../programming-guide/classes-and-structs/properties.md) for more information.)</span></span>

[!code-csharp[csrefKeywordsModifiers#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#10)]

## <a name="c-language-specification"></a><span data-ttu-id="bba42-118">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="bba42-118">C# language specification</span></span>  

<span data-ttu-id="bba42-119">Weitere Informationen finden Sie unter [Deklarierte Barrierefreiheit](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="bba42-119">For more information, see [Declared accessibility](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="bba42-120">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="bba42-120">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="bba42-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bba42-121">See also</span></span>

- [<span data-ttu-id="bba42-122">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="bba42-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="bba42-123">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="bba42-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="bba42-124">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="bba42-124">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="bba42-125">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="bba42-125">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="bba42-126">Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="bba42-126">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="bba42-127">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="bba42-127">Modifiers</span></span>](index.md)
- [<span data-ttu-id="bba42-128">public</span><span class="sxs-lookup"><span data-stu-id="bba42-128">public</span></span>](public.md)
- [<span data-ttu-id="bba42-129">protected</span><span class="sxs-lookup"><span data-stu-id="bba42-129">protected</span></span>](protected.md)
- [<span data-ttu-id="bba42-130">internal</span><span class="sxs-lookup"><span data-stu-id="bba42-130">internal</span></span>](internal.md)
