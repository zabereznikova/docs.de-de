---
title: "Operator [] (C#-Referenz)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '[]_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- subscript operator [C#]
- square brackets [ ] operator [C#]
- '[] operator [C#]'
- indexing operator [C#]
ms.assetid: 5c16bb45-88f7-45ff-b42c-1af1972b042c
caps.latest.revision: 20
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
ms.openlocfilehash: b49d41af0dd4dc34b1b74c62ce8779aa31d69f77
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="2e768-102">Operator [] (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="2e768-102">[] Operator (C# Reference)</span></span>
<span data-ttu-id="2e768-103">Eckige Klammern (`[]`) werden für Arrays, Indexer und Attribute verwendet.</span><span class="sxs-lookup"><span data-stu-id="2e768-103">Square brackets (`[]`) are used for arrays, indexers, and attributes.</span></span> <span data-ttu-id="2e768-104">Sie können auch mit Zeigern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2e768-104">They can also be used with pointers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e768-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2e768-105">Remarks</span></span>  
 <span data-ttu-id="2e768-106">Auf einen Arraytyp folgt `[]`:</span><span class="sxs-lookup"><span data-stu-id="2e768-106">An array type is a type followed by `[]`:</span></span>  
  
 <span data-ttu-id="2e768-107">[!code-cs[csRefOperators#43](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="2e768-107">[!code-cs[csRefOperators#43](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_1.cs)]</span></span>  
  
 <span data-ttu-id="2e768-108">Um auf ein Element eines Arrays zuzugreifen, wird der Index des gewünschten Elements in Klammern eingeschlossen:</span><span class="sxs-lookup"><span data-stu-id="2e768-108">To access an element of an array, the index of the desired element is enclosed in brackets:</span></span>  
  
 <span data-ttu-id="2e768-109">[!code-cs[csRefOperators#44](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="2e768-109">[!code-cs[csRefOperators#44](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_2.cs)]</span></span>  
  
 <span data-ttu-id="2e768-110">Eine Ausnahme wird ausgelöst, wenn ein Arrayindex außerhalb des gültigen Bereichs liegt.</span><span class="sxs-lookup"><span data-stu-id="2e768-110">An exception is thrown if an array index is out of range.</span></span>  
  
 <span data-ttu-id="2e768-111">Der Arrayindizierungsoperator kann nicht überladen werden. Allerdings können Typen Indexer definieren sowie Eigenschaften, die einen oder mehrere Parameter annehmen.</span><span class="sxs-lookup"><span data-stu-id="2e768-111">The array indexing operator cannot be overloaded; however, types can define indexers, and properties that take one or more parameters.</span></span> <span data-ttu-id="2e768-112">Indexerparameter werden wie Arrayindizes in rechteckige Klammern eingeschlossen, können aber als beliebiger Typ deklariert werden, während Arrayindizes ganzzahlig sein müssen.</span><span class="sxs-lookup"><span data-stu-id="2e768-112">Indexer parameters are enclosed in square brackets, just like array indexes, but indexer parameters can be declared to be of any type, unlike array indexes, which must be integral.</span></span>  
  
 <span data-ttu-id="2e768-113">.NET Framework definiert z.B. einen `Hashtable`-Typ, der Schlüssel und Werte beliebigen Typs verknüpft:</span><span class="sxs-lookup"><span data-stu-id="2e768-113">For example, the .NET Framework defines a `Hashtable` type that associates keys and values of arbitrary type:</span></span>  
  
 <span data-ttu-id="2e768-114">[!code-cs[csRefOperators#45](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="2e768-114">[!code-cs[csRefOperators#45](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_3.cs)]</span></span>  
  
 <span data-ttu-id="2e768-115">Rechteckigen Klammern werden auch zum Angeben von [Attributen](../../../csharp/programming-guide/concepts/attributes/index.md) verwendet:</span><span class="sxs-lookup"><span data-stu-id="2e768-115">Square brackets are also used to specify [Attributes](../../../csharp/programming-guide/concepts/attributes/index.md):</span></span>  
  
 <span data-ttu-id="2e768-116">[!code-cs[csRefOperators#46](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="2e768-116">[!code-cs[csRefOperators#46](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_4.cs)]</span></span>  
  
 <span data-ttu-id="2e768-117">Sie können rechteckige Klammern verwenden, um einen Zeiger zu referenzieren:</span><span class="sxs-lookup"><span data-stu-id="2e768-117">You can use square brackets to index off a pointer:</span></span>  
  
 <span data-ttu-id="2e768-118">[!code-cs[csRefOperators#47](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="2e768-118">[!code-cs[csRefOperators#47](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_5.cs)]</span></span>  
  
 <span data-ttu-id="2e768-119">Es wird keine Überprüfung der Begrenzungen durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="2e768-119">No bounds checking is performed.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="2e768-120">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="2e768-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2e768-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e768-121">See Also</span></span>  
 <span data-ttu-id="2e768-122">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="2e768-122">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="2e768-123">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="2e768-123">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="2e768-124">[C#-Operatoren](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="2e768-124">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 <span data-ttu-id="2e768-125">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="2e768-125">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 <span data-ttu-id="2e768-126">[Indexer](../../../csharp/programming-guide/indexers/index.md) </span><span class="sxs-lookup"><span data-stu-id="2e768-126">[Indexers](../../../csharp/programming-guide/indexers/index.md) </span></span>  
 <span data-ttu-id="2e768-127">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="2e768-127">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 [<span data-ttu-id="2e768-128">fixed-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2e768-128">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)

