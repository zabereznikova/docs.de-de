---
title: Operator [] (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- '[]_CSharpKeyword'
helpviewer_keywords:
- subscript operator [C#]
- square brackets [ ] operator [C#]
- '[] operator [C#]'
- indexing operator [C#]
ms.assetid: 5c16bb45-88f7-45ff-b42c-1af1972b042c
ms.openlocfilehash: 19283a795f8cfc444dfcb186dcecc0ea86eb27fd
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43467431"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="1ea78-102">Operator [] (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="1ea78-102">[] Operator (C# Reference)</span></span>
<span data-ttu-id="1ea78-103">Eckige Klammern (`[]`) werden für Arrays, Indexer und Attribute verwendet.</span><span class="sxs-lookup"><span data-stu-id="1ea78-103">Square brackets (`[]`) are used for arrays, indexers, and attributes.</span></span> <span data-ttu-id="1ea78-104">Sie können auch mit Zeigern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1ea78-104">They can also be used with pointers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ea78-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1ea78-105">Remarks</span></span>  
 <span data-ttu-id="1ea78-106">Auf einen Arraytyp folgt `[]`:</span><span class="sxs-lookup"><span data-stu-id="1ea78-106">An array type is a type followed by `[]`:</span></span>  
  
 [!code-csharp[csRefOperators#43](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_1.cs)]  
  
 <span data-ttu-id="1ea78-107">Um auf ein Element eines Arrays zuzugreifen, wird der Index des gewünschten Elements in Klammern eingeschlossen:</span><span class="sxs-lookup"><span data-stu-id="1ea78-107">To access an element of an array, the index of the desired element is enclosed in brackets:</span></span>  
  
 [!code-csharp[csRefOperators#44](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_2.cs)]  
  
 <span data-ttu-id="1ea78-108">Eine Ausnahme wird ausgelöst, wenn ein Arrayindex außerhalb des gültigen Bereichs liegt.</span><span class="sxs-lookup"><span data-stu-id="1ea78-108">An exception is thrown if an array index is out of range.</span></span>  
  
 <span data-ttu-id="1ea78-109">Der Arrayindizierungsoperator kann nicht überladen werden. Allerdings können Typen Indexer definieren, die einen oder mehrere Parameter annehmen.</span><span class="sxs-lookup"><span data-stu-id="1ea78-109">The array indexing operator cannot be overloaded; however, types can define indexers that take one or more parameters.</span></span> <span data-ttu-id="1ea78-110">Indexerparameter werden wie Arrayindizes in rechteckige Klammern eingeschlossen, können aber als beliebiger Typ deklariert werden, während Arrayindizes ganzzahlig sein müssen.</span><span class="sxs-lookup"><span data-stu-id="1ea78-110">Indexer parameters are enclosed in square brackets, just like array indexes, but indexer parameters can be declared to be of any type, unlike array indexes, which must be integral.</span></span>  
  
 <span data-ttu-id="1ea78-111">.NET Framework definiert z.B. einen `Hashtable`-Typ, der Schlüssel und Werte beliebigen Typs verknüpft:</span><span class="sxs-lookup"><span data-stu-id="1ea78-111">For example, the .NET Framework defines a `Hashtable` type that associates keys and values of arbitrary type:</span></span>  
  
 [!code-csharp[csRefOperators#45](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_3.cs)]  
  
 <span data-ttu-id="1ea78-112">Rechteckigen Klammern werden auch zum Angeben von [Attributen](../../../csharp/programming-guide/concepts/attributes/index.md) verwendet:</span><span class="sxs-lookup"><span data-stu-id="1ea78-112">Square brackets are also used to specify [Attributes](../../../csharp/programming-guide/concepts/attributes/index.md):</span></span>  
  
 [!code-csharp[csRefOperators#46](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_4.cs)]  
  
 <span data-ttu-id="1ea78-113">Sie können rechteckige Klammern verwenden, um einen Zeiger zu referenzieren:</span><span class="sxs-lookup"><span data-stu-id="1ea78-113">You can use square brackets to index off a pointer:</span></span>  
  
 [!code-csharp[csRefOperators#47](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_5.cs)]  
  
 <span data-ttu-id="1ea78-114">Es wird keine Überprüfung der Begrenzungen durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="1ea78-114">No bounds checking is performed.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="1ea78-115">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="1ea78-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1ea78-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ea78-116">See Also</span></span>

- [<span data-ttu-id="1ea78-117">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="1ea78-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="1ea78-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="1ea78-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="1ea78-119">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="1ea78-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="1ea78-120">Arrays</span><span class="sxs-lookup"><span data-stu-id="1ea78-120">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
- [<span data-ttu-id="1ea78-121">Indexer</span><span class="sxs-lookup"><span data-stu-id="1ea78-121">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)  
- [<span data-ttu-id="1ea78-122">unsafe</span><span class="sxs-lookup"><span data-stu-id="1ea78-122">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
- [<span data-ttu-id="1ea78-123">fixed-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1ea78-123">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
