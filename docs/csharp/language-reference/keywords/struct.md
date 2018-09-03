---
title: struct (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- structs [C#], struct keyword
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
ms.openlocfilehash: 7931da2e5f5c493b54eb1f33a1d6f57b38592f6e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43399017"
---
# <a name="struct-c-reference"></a><span data-ttu-id="603c8-102">struct (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="603c8-102">struct (C# Reference)</span></span>
<span data-ttu-id="603c8-103">Ein `struct`-Typ ist ein ein Werttyp, der in der Regel verwendet wird, um eine kleine Gruppe verwandter Variablen zusammenzufassen, z. B. Koordinaten eines Rechtecks oder die Merkmale eines Lagerartikels.</span><span class="sxs-lookup"><span data-stu-id="603c8-103">A `struct` type is a value type that is typically used to encapsulate small groups of related variables, such as the coordinates of a rectangle or the characteristics of an item in an inventory.</span></span> <span data-ttu-id="603c8-104">Im folgenden Beispiel wird eine einfache Strukturdeklaration veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="603c8-104">The following example shows a simple struct declaration:</span></span>  
  
```csharp  
public struct Book  
{  
    public decimal price;  
    public string title;  
    public string author;  
}  
```  
  
## <a name="remarks"></a><span data-ttu-id="603c8-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="603c8-105">Remarks</span></span>  
 <span data-ttu-id="603c8-106">Strukturen können auch [Konstruktoren](../../../csharp/programming-guide/classes-and-structs/constructors.md), [Konstanten](../../../csharp/programming-guide/classes-and-structs/constants.md), [Felder](../../../csharp/programming-guide/classes-and-structs/fields.md), [Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md), [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md), [Indexer](../../../csharp/programming-guide/indexers/index.md), [Operatoren](../../../csharp/programming-guide/statements-expressions-operators/operators.md), [Ereignisse](../../../csharp/programming-guide/events/index.md) und [geschachtelte Typen](../../../csharp/programming-guide/classes-and-structs/nested-types.md) enthalten. Wenn jedoch mehrere solche Member erforderlich sind, sollten Sie sich überlegen, den Typ in eine Klasse umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="603c8-106">Structs can also contain [constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md), [constants](../../../csharp/programming-guide/classes-and-structs/constants.md), [fields](../../../csharp/programming-guide/classes-and-structs/fields.md), [methods](../../../csharp/programming-guide/classes-and-structs/methods.md), [properties](../../../csharp/programming-guide/classes-and-structs/properties.md), [indexers](../../../csharp/programming-guide/indexers/index.md), [operators](../../../csharp/programming-guide/statements-expressions-operators/operators.md), [events](../../../csharp/programming-guide/events/index.md), and [nested types](../../../csharp/programming-guide/classes-and-structs/nested-types.md), although if several such members are required, you should consider making your type a class instead.</span></span>  
  
 <span data-ttu-id="603c8-107">Beispiele finden Sie unter [Verwenden von Strukturen](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="603c8-107">For examples, see [Using Structs](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span></span>  
  
 <span data-ttu-id="603c8-108">Strukturen können eine Schnittstelle implementieren, aber nicht von einer anderen Struktur erben.</span><span class="sxs-lookup"><span data-stu-id="603c8-108">Structs can implement an interface but they cannot inherit from another struct.</span></span> <span data-ttu-id="603c8-109">Aus diesem Grund können Strukturmember nicht als `protected` deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="603c8-109">For that reason, struct members cannot be declared as `protected`.</span></span>  
  
 <span data-ttu-id="603c8-110">Weitere Informationen finden Sie unter [Strukturen](../../../csharp/programming-guide/classes-and-structs/structs.md).</span><span class="sxs-lookup"><span data-stu-id="603c8-110">For more information, see [Structs](../../../csharp/programming-guide/classes-and-structs/structs.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="603c8-111">Beispiele</span><span class="sxs-lookup"><span data-stu-id="603c8-111">Examples</span></span>  
 <span data-ttu-id="603c8-112">Weitere Beispiele und Informationen finden Sie unter [Verwenden von Strukturen](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="603c8-112">For examples and more information, see [Using Structs](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="603c8-113">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="603c8-113">C# Language Specification</span></span>  
 <span data-ttu-id="603c8-114">Beispiele finden Sie unter [Verwenden von Strukturen](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="603c8-114">For examples, see [Using Structs](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="603c8-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="603c8-115">See Also</span></span>

- [<span data-ttu-id="603c8-116">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="603c8-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="603c8-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="603c8-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="603c8-118">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="603c8-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="603c8-119">Tabelle für Standardwerte</span><span class="sxs-lookup"><span data-stu-id="603c8-119">Default Values Table</span></span>](../../../csharp/language-reference/keywords/default-values-table.md)  
- [<span data-ttu-id="603c8-120">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="603c8-120">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [<span data-ttu-id="603c8-121">Typen</span><span class="sxs-lookup"><span data-stu-id="603c8-121">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
- [<span data-ttu-id="603c8-122">Werttypen</span><span class="sxs-lookup"><span data-stu-id="603c8-122">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
- [<span data-ttu-id="603c8-123">class</span><span class="sxs-lookup"><span data-stu-id="603c8-123">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
- [<span data-ttu-id="603c8-124">interface</span><span class="sxs-lookup"><span data-stu-id="603c8-124">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)  
- [<span data-ttu-id="603c8-125">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="603c8-125">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
