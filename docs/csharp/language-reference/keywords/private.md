---
title: private-Schlüsselwort – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- private_CSharpKeyword
- private
helpviewer_keywords:
- private keyword [C#]
ms.assetid: 654c0bb8-e6ac-4086-bf96-7474fa6aa1c8
ms.openlocfilehash: a13e9ef18b0f6452c3ff1497dc97110bc21c433d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75715201"
---
# <a name="private-c-reference"></a><span data-ttu-id="e5e3d-102">private (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="e5e3d-102">private (C# Reference)</span></span>

<span data-ttu-id="e5e3d-103">Das `private`-Schlüsselwort ist ein Zugriffsmodifizierer für Member.</span><span class="sxs-lookup"><span data-stu-id="e5e3d-103">The `private` keyword is a member access modifier.</span></span>

> <span data-ttu-id="e5e3d-104">Auf dieser Seite wird der Zugriff auf `private` behandelt.</span><span class="sxs-lookup"><span data-stu-id="e5e3d-104">This page covers `private` access.</span></span> <span data-ttu-id="e5e3d-105">Das Schlüsselwort `private` ist auch Teil des Zugriffsmodifizierers [`private protected`](./private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="e5e3d-105">The `private` keyword is also part of the [`private protected`](./private-protected.md) access modifier.</span></span>

<span data-ttu-id="e5e3d-106">Privater-Zugriff ist die am wenigsten eingeschränkte Zugriffsebene.</span><span class="sxs-lookup"><span data-stu-id="e5e3d-106">Private access is the least permissive access level.</span></span> <span data-ttu-id="e5e3d-107">Private Member sind nur innerhalb der Klasse oder Struktur, in der sie, wie im folgenden Beispiel, deklariert werden:</span><span class="sxs-lookup"><span data-stu-id="e5e3d-107">Private members are accessible only within the body of the class or the struct in which they are declared, as in this example:</span></span>

```csharp
class Employee
{
    private int i;
    double d;   // private access by default
}
```

<span data-ttu-id="e5e3d-108">Geschachtelte Typen im gleichen Text können auch auf diese privaten Member zugreifen.</span><span class="sxs-lookup"><span data-stu-id="e5e3d-108">Nested types in the same body can also access those private members.</span></span>

<span data-ttu-id="e5e3d-109">Es ist ein Kompilierzeitfehler auf einen privaten Member außerhalb der Klasse oder Struktur, in der sie deklariert ist, zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="e5e3d-109">It is a compile-time error to reference a private member outside the class or the struct in which it is declared.</span></span>

<span data-ttu-id="e5e3d-110">Einen Vergleich von `private` mit dem anderen Zugriffsmodifizierer finden Sie unter [Zugriffsebenen](accessibility-levels.md) und [Zugriffsmodifizierer](../../programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="e5e3d-110">For a comparison of `private` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md) and [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md).</span></span>

## <a name="example"></a><span data-ttu-id="e5e3d-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e5e3d-111">Example</span></span>

<span data-ttu-id="e5e3d-112">In diesem Beispiel enthält die `Employee`-Klasse zwei private Datenmember, `name` und `salary`.</span><span class="sxs-lookup"><span data-stu-id="e5e3d-112">In this example, the `Employee` class contains two private data members, `name` and `salary`.</span></span> <span data-ttu-id="e5e3d-113">Als private Member können nur Membermethoden auf sie zugreifen.</span><span class="sxs-lookup"><span data-stu-id="e5e3d-113">As private members, they cannot be accessed except by member methods.</span></span> <span data-ttu-id="e5e3d-114">Die öffentlichen Methoden `GetName` und `Salary` werden hinzugefügt, um gesteuerten Zugriff auf die privaten Member zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="e5e3d-114">Public methods named `GetName` and `Salary` are added to allow controlled access to the private members.</span></span> <span data-ttu-id="e5e3d-115">Auf den `name`-Member wird über eine öffentliche Methode zugegriffen, und auf den `salary`-Member wird über eine öffentliche schreibgeschützte Eigenschaft zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="e5e3d-115">The `name` member is accessed by way of a public method, and the `salary` member is accessed by way of a public read-only property.</span></span> <span data-ttu-id="e5e3d-116">(Weitere Informationen finden Sie unter [Eigenschaften](../../programming-guide/classes-and-structs/properties.md).)</span><span class="sxs-lookup"><span data-stu-id="e5e3d-116">(See [Properties](../../programming-guide/classes-and-structs/properties.md) for more information.)</span></span>

[!code-csharp[csrefKeywordsModifiers#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#10)]

## <a name="c-language-specification"></a><span data-ttu-id="e5e3d-117">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="e5e3d-117">C# language specification</span></span>  

<span data-ttu-id="e5e3d-118">Weitere Informationen finden Sie unter [Deklarierte Barrierefreiheit](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="e5e3d-118">For more information, see [Declared accessibility](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="e5e3d-119">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="e5e3d-119">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="e5e3d-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e5e3d-120">See also</span></span>

- [<span data-ttu-id="e5e3d-121">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="e5e3d-121">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e5e3d-122">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="e5e3d-122">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e5e3d-123">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="e5e3d-123">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="e5e3d-124">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="e5e3d-124">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="e5e3d-125">Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="e5e3d-125">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="e5e3d-126">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="e5e3d-126">Modifiers</span></span>](index.md)
- [<span data-ttu-id="e5e3d-127">public</span><span class="sxs-lookup"><span data-stu-id="e5e3d-127">public</span></span>](public.md)
- [<span data-ttu-id="e5e3d-128">protected</span><span class="sxs-lookup"><span data-stu-id="e5e3d-128">protected</span></span>](protected.md)
- [<span data-ttu-id="e5e3d-129">internal</span><span class="sxs-lookup"><span data-stu-id="e5e3d-129">internal</span></span>](internal.md)
