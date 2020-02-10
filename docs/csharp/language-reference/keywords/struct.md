---
title: struct – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- structs [C#], struct keyword
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
ms.openlocfilehash: 77d5c83dd4c81b96bc62ace6e609db8bc411dc41
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2020
ms.locfileid: "77093161"
---
# <a name="struct-c-reference"></a><span data-ttu-id="9244d-102">struct (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="9244d-102">struct (C# Reference)</span></span>

<span data-ttu-id="9244d-103">Ein `struct`-Typ ist ein ein Werttyp, der in der Regel verwendet wird, um eine kleine Gruppe verwandter Variablen zusammenzufassen, z. B. Koordinaten eines Rechtecks oder die Merkmale eines Lagerartikels.</span><span class="sxs-lookup"><span data-stu-id="9244d-103">A `struct` type is a value type that is typically used to encapsulate small groups of related variables, such as the coordinates of a rectangle or the characteristics of an item in an inventory.</span></span> <span data-ttu-id="9244d-104">Im folgenden Beispiel wird eine einfache Strukturdeklaration veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="9244d-104">The following example shows a simple struct declaration:</span></span>

```csharp
public struct Book
{
    public decimal price;
    public string title;
    public string author;
}
```

## <a name="remarks"></a><span data-ttu-id="9244d-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9244d-105">Remarks</span></span>

<span data-ttu-id="9244d-106">Strukturen können auch [Konstruktoren](../../programming-guide/classes-and-structs/constructors.md), [Konstanten](../../programming-guide/classes-and-structs/constants.md), [Felder](../../programming-guide/classes-and-structs/fields.md), [Methoden](../../programming-guide/classes-and-structs/methods.md), [Eigenschaften](../../programming-guide/classes-and-structs/properties.md), [Indexer](../../programming-guide/indexers/index.md), [Operatoren](../operators/index.md), [Ereignisse](../../programming-guide/events/index.md) und [geschachtelte Typen](../../programming-guide/classes-and-structs/nested-types.md) enthalten. Wenn jedoch mehrere solche Member erforderlich sind, sollten Sie sich überlegen, den Typ in eine Klasse umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="9244d-106">Structs can also contain [constructors](../../programming-guide/classes-and-structs/constructors.md), [constants](../../programming-guide/classes-and-structs/constants.md), [fields](../../programming-guide/classes-and-structs/fields.md), [methods](../../programming-guide/classes-and-structs/methods.md), [properties](../../programming-guide/classes-and-structs/properties.md), [indexers](../../programming-guide/indexers/index.md), [operators](../operators/index.md), [events](../../programming-guide/events/index.md), and [nested types](../../programming-guide/classes-and-structs/nested-types.md), although if several such members are required, you should consider making your type a class instead.</span></span>

<span data-ttu-id="9244d-107">Beispiele finden Sie unter [Verwenden von Strukturen](../../programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="9244d-107">For examples, see [Using Structs](../../programming-guide/classes-and-structs/using-structs.md).</span></span>

<span data-ttu-id="9244d-108">Strukturen können eine Schnittstelle implementieren, aber nicht von einer anderen Struktur erben.</span><span class="sxs-lookup"><span data-stu-id="9244d-108">Structs can implement an interface but they cannot inherit from another struct.</span></span> <span data-ttu-id="9244d-109">Aus diesem Grund können Strukturmember nicht als `protected` deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="9244d-109">For that reason, struct members cannot be declared as `protected`.</span></span>

<span data-ttu-id="9244d-110">Weitere Informationen finden Sie unter [Strukturen](../../programming-guide/classes-and-structs/structs.md).</span><span class="sxs-lookup"><span data-stu-id="9244d-110">For more information, see [Structs](../../programming-guide/classes-and-structs/structs.md).</span></span>

## <a name="examples"></a><span data-ttu-id="9244d-111">Beispiele</span><span class="sxs-lookup"><span data-stu-id="9244d-111">Examples</span></span>

<span data-ttu-id="9244d-112">Weitere Beispiele und Informationen finden Sie unter [Verwenden von Strukturen](../../programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="9244d-112">For examples and more information, see [Using Structs](../../programming-guide/classes-and-structs/using-structs.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="9244d-113">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="9244d-113">C# language specification</span></span>

<span data-ttu-id="9244d-114">Beispiele finden Sie unter [Verwenden von Strukturen](../../programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="9244d-114">For examples, see [Using Structs](../../programming-guide/classes-and-structs/using-structs.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9244d-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9244d-115">See also</span></span>

- [<span data-ttu-id="9244d-116">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="9244d-116">C# reference</span></span>](../index.md)
- [<span data-ttu-id="9244d-117">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="9244d-117">C# keywords</span></span>](index.md)
- [<span data-ttu-id="9244d-118">Werttypen</span><span class="sxs-lookup"><span data-stu-id="9244d-118">Value types</span></span>](../builtin-types/value-types.md)
- [<span data-ttu-id="9244d-119">class</span><span class="sxs-lookup"><span data-stu-id="9244d-119">class</span></span>](class.md)
- [<span data-ttu-id="9244d-120">interface</span><span class="sxs-lookup"><span data-stu-id="9244d-120">interface</span></span>](interface.md)
- [<span data-ttu-id="9244d-121">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="9244d-121">Classes and structs</span></span>](../../programming-guide/classes-and-structs/index.md)
