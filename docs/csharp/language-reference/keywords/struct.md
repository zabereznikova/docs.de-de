---
title: struct (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- struct_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- struct keyword [C#]
- structs [C#], struct keyword
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
caps.latest.revision: 23
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
ms.openlocfilehash: 309e68a57e1ee869850d960ffaac6cf35eb6e260
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="struct-c-reference"></a><span data-ttu-id="541da-102">struct (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="541da-102">struct (C# Reference)</span></span>
<span data-ttu-id="541da-103">Ein `struct`-Typ ist ein ein Werttyp, der in der Regeln verwendet wird, um eine kleine Gruppe verwandter Variablen zusammenzufassen, z. B. Koordinaten eines Rechtecks oder die Merkmale eines Lagerartikels.</span><span class="sxs-lookup"><span data-stu-id="541da-103">A `struct` type is a value type that is typically used to encapsulate small groups of related variables, such as the coordinates of a rectangle or the characteristics of an item in an inventory.</span></span> <span data-ttu-id="541da-104">Im folgenden Beispiel wird eine einfache Strukturdeklaration veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="541da-104">The following example shows a simple struct declaration:</span></span>  
  
```  
public struct Book  
{  
    public decimal price;  
    public string title;  
    public string author;  
}  
```  
  
## <a name="remarks"></a><span data-ttu-id="541da-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="541da-105">Remarks</span></span>  
 <span data-ttu-id="541da-106">Strukturen können auch [Konstruktoren](../../../csharp/programming-guide/classes-and-structs/constructors.md), [Konstanten](../../../csharp/programming-guide/classes-and-structs/constants.md), [Felder](../../../csharp/programming-guide/classes-and-structs/fields.md), [Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md), [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md), [Indexer](../../../csharp/programming-guide/indexers/index.md), [Operatoren](../../../csharp/programming-guide/statements-expressions-operators/operators.md), [Ereignisse](../../../csharp/programming-guide/events/index.md) und [geschachtelte Typen](../../../csharp/programming-guide/classes-and-structs/nested-types.md) enthalten. Wenn jedoch mehrere solche Member erforderlich sind, sollten Sie sich überlegen, den Typ in eine Klasse umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="541da-106">Structs can also contain [constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md), [constants](../../../csharp/programming-guide/classes-and-structs/constants.md), [fields](../../../csharp/programming-guide/classes-and-structs/fields.md), [methods](../../../csharp/programming-guide/classes-and-structs/methods.md), [properties](../../../csharp/programming-guide/classes-and-structs/properties.md), [indexers](../../../csharp/programming-guide/indexers/index.md), [operators](../../../csharp/programming-guide/statements-expressions-operators/operators.md), [events](../../../csharp/programming-guide/events/index.md), and [nested types](../../../csharp/programming-guide/classes-and-structs/nested-types.md), although if several such members are required, you should consider making your type a class instead.</span></span>  
  
 <span data-ttu-id="541da-107">Beispiele finden Sie unter [Verwenden von Strukturen](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="541da-107">For examples, see [Using Structs](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span></span>  
  
 <span data-ttu-id="541da-108">Strukturen können eine Schnittstelle implementieren, aber nicht von einer anderen Struktur erben.</span><span class="sxs-lookup"><span data-stu-id="541da-108">Structs can implement an interface but they cannot inherit from another struct.</span></span> <span data-ttu-id="541da-109">Aus diesem Grund können Strukturmember nicht als `protected` deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="541da-109">For that reason, struct members cannot be declared as `protected`.</span></span>  
  
 <span data-ttu-id="541da-110">Weitere Informationen finden Sie unter [Strukturen](../../../csharp/programming-guide/classes-and-structs/structs.md).</span><span class="sxs-lookup"><span data-stu-id="541da-110">For more information, see [Structs](../../../csharp/programming-guide/classes-and-structs/structs.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="541da-111">Beispiele</span><span class="sxs-lookup"><span data-stu-id="541da-111">Examples</span></span>  
 <span data-ttu-id="541da-112">Weitere Beispiele und Informationen finden Sie unter [Verwenden von Strukturen](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="541da-112">For examples and more information, see [Using Structs](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="541da-113">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="541da-113">C# Language Specification</span></span>  
 <span data-ttu-id="541da-114">Beispiele finden Sie unter [Verwenden von Strukturen](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="541da-114">For examples, see [Using Structs](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="541da-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="541da-115">See Also</span></span>  
 <span data-ttu-id="541da-116">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="541da-116">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="541da-117">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="541da-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="541da-118">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="541da-118">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="541da-119">[Tabelle für Standardwerte](../../../csharp/language-reference/keywords/default-values-table.md) </span><span class="sxs-lookup"><span data-stu-id="541da-119">[Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md) </span></span>  
 <span data-ttu-id="541da-120">[Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="541da-120">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="541da-121">[Typen](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="541da-121">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="541da-122">[Werttypen](../../../csharp/language-reference/keywords/value-types.md) </span><span class="sxs-lookup"><span data-stu-id="541da-122">[Value Types](../../../csharp/language-reference/keywords/value-types.md) </span></span>  
 <span data-ttu-id="541da-123">[Klasse](../../../csharp/language-reference/keywords/class.md) </span><span class="sxs-lookup"><span data-stu-id="541da-123">[class](../../../csharp/language-reference/keywords/class.md) </span></span>  
 <span data-ttu-id="541da-124">[Schnittstelle](../../../csharp/language-reference/keywords/interface.md) </span><span class="sxs-lookup"><span data-stu-id="541da-124">[interface](../../../csharp/language-reference/keywords/interface.md) </span></span>  
 [<span data-ttu-id="541da-125">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="541da-125">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)

