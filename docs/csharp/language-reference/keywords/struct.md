---
title: struct – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- structs [C#], struct keyword
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
ms.openlocfilehash: 8d9a23a0813423571c894758257b284ad67a72e2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744646"
---
# <a name="struct-c-reference"></a><span data-ttu-id="0ce31-102">struct (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="0ce31-102">struct (C# Reference)</span></span>

<span data-ttu-id="0ce31-103">Ein `struct`-Typ ist ein ein Werttyp, der in der Regel verwendet wird, um eine kleine Gruppe verwandter Variablen zusammenzufassen, z. B. Koordinaten eines Rechtecks oder die Merkmale eines Lagerartikels.</span><span class="sxs-lookup"><span data-stu-id="0ce31-103">A `struct` type is a value type that is typically used to encapsulate small groups of related variables, such as the coordinates of a rectangle or the characteristics of an item in an inventory.</span></span> <span data-ttu-id="0ce31-104">Im folgenden Beispiel wird eine einfache Strukturdeklaration veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="0ce31-104">The following example shows a simple struct declaration:</span></span>

```csharp
public struct Book
{
    public decimal price;
    public string title;
    public string author;
}
```

## <a name="remarks"></a><span data-ttu-id="0ce31-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0ce31-105">Remarks</span></span>

<span data-ttu-id="0ce31-106">Strukturen können auch [Konstruktoren](../../programming-guide/classes-and-structs/constructors.md), [Konstanten](../../programming-guide/classes-and-structs/constants.md), [Felder](../../programming-guide/classes-and-structs/fields.md), [Methoden](../../programming-guide/classes-and-structs/methods.md), [Eigenschaften](../../programming-guide/classes-and-structs/properties.md), [Indexer](../../programming-guide/indexers/index.md), [Operatoren](../operators/index.md), [Ereignisse](../../programming-guide/events/index.md) und [geschachtelte Typen](../../programming-guide/classes-and-structs/nested-types.md) enthalten. Wenn jedoch mehrere solche Member erforderlich sind, sollten Sie sich überlegen, den Typ in eine Klasse umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="0ce31-106">Structs can also contain [constructors](../../programming-guide/classes-and-structs/constructors.md), [constants](../../programming-guide/classes-and-structs/constants.md), [fields](../../programming-guide/classes-and-structs/fields.md), [methods](../../programming-guide/classes-and-structs/methods.md), [properties](../../programming-guide/classes-and-structs/properties.md), [indexers](../../programming-guide/indexers/index.md), [operators](../operators/index.md), [events](../../programming-guide/events/index.md), and [nested types](../../programming-guide/classes-and-structs/nested-types.md), although if several such members are required, you should consider making your type a class instead.</span></span>

<span data-ttu-id="0ce31-107">Beispiele finden Sie unter [Verwenden von Strukturen](../../programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="0ce31-107">For examples, see [Using Structs](../../programming-guide/classes-and-structs/using-structs.md).</span></span>

<span data-ttu-id="0ce31-108">Strukturen können eine Schnittstelle implementieren, aber nicht von einer anderen Struktur erben.</span><span class="sxs-lookup"><span data-stu-id="0ce31-108">Structs can implement an interface but they cannot inherit from another struct.</span></span> <span data-ttu-id="0ce31-109">Aus diesem Grund können Strukturmember nicht als `protected` deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="0ce31-109">For that reason, struct members cannot be declared as `protected`.</span></span>

<span data-ttu-id="0ce31-110">Weitere Informationen finden Sie unter [Strukturen](../../programming-guide/classes-and-structs/structs.md).</span><span class="sxs-lookup"><span data-stu-id="0ce31-110">For more information, see [Structs](../../programming-guide/classes-and-structs/structs.md).</span></span>

## <a name="examples"></a><span data-ttu-id="0ce31-111">Beispiele</span><span class="sxs-lookup"><span data-stu-id="0ce31-111">Examples</span></span>

<span data-ttu-id="0ce31-112">Weitere Beispiele und Informationen finden Sie unter [Verwenden von Strukturen](../../programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="0ce31-112">For examples and more information, see [Using Structs](../../programming-guide/classes-and-structs/using-structs.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="0ce31-113">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="0ce31-113">C# language specification</span></span>

<span data-ttu-id="0ce31-114">Beispiele finden Sie unter [Verwenden von Strukturen](../../programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="0ce31-114">For examples, see [Using Structs](../../programming-guide/classes-and-structs/using-structs.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0ce31-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0ce31-115">See also</span></span>

- [<span data-ttu-id="0ce31-116">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="0ce31-116">C# reference</span></span>](../index.md)
- [<span data-ttu-id="0ce31-117">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="0ce31-117">C# keywords</span></span>](index.md)
- [<span data-ttu-id="0ce31-118">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="0ce31-118">Built-in types table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="0ce31-119">Werttypen</span><span class="sxs-lookup"><span data-stu-id="0ce31-119">Value types</span></span>](../builtin-types/value-types.md)
- [<span data-ttu-id="0ce31-120">class</span><span class="sxs-lookup"><span data-stu-id="0ce31-120">class</span></span>](class.md)
- [<span data-ttu-id="0ce31-121">interface</span><span class="sxs-lookup"><span data-stu-id="0ce31-121">interface</span></span>](interface.md)
- [<span data-ttu-id="0ce31-122">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="0ce31-122">Classes and structs</span></span>](../../programming-guide/classes-and-structs/index.md)
