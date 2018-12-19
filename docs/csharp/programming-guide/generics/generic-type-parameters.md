---
title: Generische Typparameter – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], type parameters
- type parameters [C#]
ms.assetid: a03b0ab2-0606-4b41-b7bf-e64d5bb4d18f
ms.openlocfilehash: 8b9e040beea0590320a34d35ca323374f357bf2f
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53238194"
---
# <a name="generic-type-parameters-c-programming-guide"></a><span data-ttu-id="3c82d-102">Generische Typparameter (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="3c82d-102">Generic Type Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="3c82d-103">Bei der Definition eines generischen Typs oder einer Methode ist ein Typparameter ein Platzhalter für einen bestimmten Typ, den ein Client angibt, wenn eine Variable des generischen Typs instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="3c82d-103">In a generic type or method definition, a type parameters is a placeholder for a specific type that a client specifies when they instantiate a variable of the generic type.</span></span> <span data-ttu-id="3c82d-104">Eine generische Klasse, z.B. die unter [Einführung in Generika](../../../csharp/programming-guide/generics/introduction-to-generics.md) aufgelistete Klasse `GenericList<T>`, kann nicht ohne Anpassung verwendet werden, denn sie ist nicht wirklich ein Typ, sondern mehr wie die Kopie eines Typs.</span><span class="sxs-lookup"><span data-stu-id="3c82d-104">A generic class, such as `GenericList<T>` listed in [Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md), cannot be used as-is because it is not really a type; it is more like a blueprint for a type.</span></span> <span data-ttu-id="3c82d-105">Um `GenericList<T>` verwenden zu können, muss der Clientcode einen konstruierten Typ deklarieren und instanziieren, indem er ein Typargument in spitzen Klammern angibt.</span><span class="sxs-lookup"><span data-stu-id="3c82d-105">To use `GenericList<T>`, client code must declare and instantiate a constructed type by specifying a type argument inside the angle brackets.</span></span> <span data-ttu-id="3c82d-106">Das Typargument für diese spezielle Klasse kann jeder Typ sein, der vom Compiler erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="3c82d-106">The type argument for this particular class can be any type recognized by the compiler.</span></span> <span data-ttu-id="3c82d-107">Instanzen von konstruierten Typen können in beliebiger Zahl erstellt werden, wobei jede Instanz ein anderes Typargument verwendet, z.B.:</span><span class="sxs-lookup"><span data-stu-id="3c82d-107">Any number of constructed type instances can be created, each one using a different type argument, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#7](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_1.cs)]  
  
 <span data-ttu-id="3c82d-108">Bei jeder dieser Instanzen von `GenericList<T>` wird jedes Vorkommen von `T` in der Klasse zur Laufzeit durch das Typargument ersetzt.</span><span class="sxs-lookup"><span data-stu-id="3c82d-108">In each of these instances of `GenericList<T>`, every occurrence of `T` in the class will be substituted at run time with the type argument.</span></span> <span data-ttu-id="3c82d-109">Aufgrund dieser Ersetzung werden drei separate typsichere und effiziente Objekte mithilfe einer einzigen Klassendefinition erstellt.</span><span class="sxs-lookup"><span data-stu-id="3c82d-109">By means of this substitution, we have created three separate type-safe and efficient objects using a single class definition.</span></span> <span data-ttu-id="3c82d-110">Weitere Informationen dazu, wie diese Ersetzung von der CLR ausgeführt wird, finden Sie unter [Generika zur Laufzeit](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).</span><span class="sxs-lookup"><span data-stu-id="3c82d-110">For more information on how this substitution is performed by the CLR, see [Generics in the Run Time](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).</span></span>  
  
## <a name="type-parameter-naming-guidelines"></a><span data-ttu-id="3c82d-111">Richtlinien für die Benennung von Typparametern</span><span class="sxs-lookup"><span data-stu-id="3c82d-111">Type Parameter Naming Guidelines</span></span>  
  
-   <span data-ttu-id="3c82d-112">**Verwenden** Sie zur Benennung von generischen Typparametern beschreibende Namen, es sei denn, ein Name aus einem einzelnen Buchstaben reicht als Erklärung völlig aus, und ein beschreibender Name würde das Verständnis für den Namen nicht wirklich erhöhen.</span><span class="sxs-lookup"><span data-stu-id="3c82d-112">**Do** name generic type parameters with descriptive names, unless a single letter name is completely self explanatory and a descriptive name would not add value.</span></span>  
  
     [!code-csharp[csProgGuideGenerics#8](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_2.cs)]  
  
-   <span data-ttu-id="3c82d-113">**Verwenden** Sie T als Typparametername für Typen, die einen einzelnen Buchstaben als Typparameter haben.</span><span class="sxs-lookup"><span data-stu-id="3c82d-113">**Consider** using T as the type parameter name for types with one single letter type parameter.</span></span>  
  
     [!code-csharp[csProgGuideGenerics#9](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_3.cs)]  
  
-   <span data-ttu-id="3c82d-114">**Verwenden** Sie das Präfix „T“ für beschreibende Typparameternamen.</span><span class="sxs-lookup"><span data-stu-id="3c82d-114">**Do** prefix descriptive type parameter names with "T".</span></span>  
  
     [!code-csharp[csProgGuideGenerics#10](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_4.cs)]  
  
-   <span data-ttu-id="3c82d-115">**Überlegen** Sie, ob Sie Einschränkungen, die für einen Typparameter gelten, im Namen des Parameters angeben möchten.</span><span class="sxs-lookup"><span data-stu-id="3c82d-115">**Consider** indicating constraints placed on a type parameter in the name of parameter.</span></span> <span data-ttu-id="3c82d-116">Ein auf `ISession` eingeschränkter Parameter könnte z.B. `TSession` genannt werden.</span><span class="sxs-lookup"><span data-stu-id="3c82d-116">For example, a parameter constrained to `ISession` may be called `TSession`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c82d-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c82d-117">See Also</span></span>

- <xref:System.Collections.Generic>  
- [<span data-ttu-id="3c82d-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="3c82d-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="3c82d-119">Generika</span><span class="sxs-lookup"><span data-stu-id="3c82d-119">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)  
- [<span data-ttu-id="3c82d-120">Unterschiede zwischen C++-Vorlagen und C#-Generika</span><span class="sxs-lookup"><span data-stu-id="3c82d-120">Differences Between C++ Templates and C# Generics</span></span>](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)
