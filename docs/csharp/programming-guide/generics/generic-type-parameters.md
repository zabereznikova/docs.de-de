---
title: Generische Typparameter (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], type parameters
- type parameters [C#]
ms.assetid: a03b0ab2-0606-4b41-b7bf-e64d5bb4d18f
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
ms.openlocfilehash: ce1024215a381afb3a7b42f2127fe5e8c212d378
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="generic-type-parameters-c-programming-guide"></a><span data-ttu-id="09f70-102">Generische Typparameter (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="09f70-102">Generic Type Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="09f70-103">Bei der Definition eines generischen Typs oder einer Methode ist ein Typparameter ein Platzhalter für einen bestimmten Typ, den ein Client angibt, wenn eine Variable des generischen Typs instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="09f70-103">In a generic type or method definition, a type parameters is a placeholder for a specific type that a client specifies when they instantiate a variable of the generic type.</span></span> <span data-ttu-id="09f70-104">Eine generische Klasse, z.B. die unter [Einführung in Generika](../../../csharp/programming-guide/generics/introduction-to-generics.md) aufgelistete Klasse `GenericList<T>`, kann nicht ohne Anpassung verwendet werden, denn sie ist nicht wirklich ein Typ, sondern mehr wie die Kopie eines Typs.</span><span class="sxs-lookup"><span data-stu-id="09f70-104">A generic class, such as `GenericList<T>` listed in [Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md), cannot be used as-is because it is not really a type; it is more like a blueprint for a type.</span></span> <span data-ttu-id="09f70-105">Um `GenericList<T>` verwenden zu können, muss der Clientcode einen konstruierten Typ deklarieren und instanziieren, indem er ein Typargument in spitzen Klammern angibt.</span><span class="sxs-lookup"><span data-stu-id="09f70-105">To use `GenericList<T>`, client code must declare and instantiate a constructed type by specifying a type argument inside the angle brackets.</span></span> <span data-ttu-id="09f70-106">Das Typargument für diese spezielle Klasse kann jeder Typ sein, der vom Compiler erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="09f70-106">The type argument for this particular class can be any type recognized by the compiler.</span></span> <span data-ttu-id="09f70-107">Instanzen von konstruierten Typen können in beliebiger Zahl erstellt werden, wobei jede Instanz ein anderes Typargument verwendet, z.B.:</span><span class="sxs-lookup"><span data-stu-id="09f70-107">Any number of constructed type instances can be created, each one using a different type argument, as follows:</span></span>  
  
 <span data-ttu-id="09f70-108">[!code-cs[csProgGuideGenerics#7](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="09f70-108">[!code-cs[csProgGuideGenerics#7](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_1.cs)]</span></span>  
  
 <span data-ttu-id="09f70-109">Bei jeder dieser Instanzen von `GenericList<T>` wird jedes Vorkommen von `T` in der Klasse zur Laufzeit durch das Typargument ersetzt.</span><span class="sxs-lookup"><span data-stu-id="09f70-109">In each of these instances of `GenericList<T>`, every occurrence of `T` in the class will be substituted at run time with the type argument.</span></span> <span data-ttu-id="09f70-110">Aufgrund dieser Ersetzung werden drei separate typsichere und effiziente Objekte mithilfe einer einzigen Klassendefinition erstellt.</span><span class="sxs-lookup"><span data-stu-id="09f70-110">By means of this substitution, we have created three separate type-safe and efficient objects using a single class definition.</span></span> <span data-ttu-id="09f70-111">Weitere Informationen dazu, wie diese Ersetzung von der CLR ausgeführt wird, finden Sie unter [Generika zur Laufzeit](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).</span><span class="sxs-lookup"><span data-stu-id="09f70-111">For more information on how this substitution is performed by the CLR, see [Generics in the Run Time](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).</span></span>  
  
## <a name="type-parameter-naming-guidelines"></a><span data-ttu-id="09f70-112">Richtlinien für die Benennung von Typparametern</span><span class="sxs-lookup"><span data-stu-id="09f70-112">Type Parameter Naming Guidelines</span></span>  
  
-   <span data-ttu-id="09f70-113">**Verwenden** Sie zur Benennung von generischen Typparametern beschreibende Namen, es sei denn, ein Name aus einem einzelnen Buchstaben reicht als Erklärung völlig aus, und ein beschreibender Name würde das Verständnis für den Namen nicht wirklich erhöhen.</span><span class="sxs-lookup"><span data-stu-id="09f70-113">**Do** name generic type parameters with descriptive names, unless a single letter name is completely self explanatory and a descriptive name would not add value.</span></span>  
  
     <span data-ttu-id="09f70-114">[!code-cs[csProgGuideGenerics#8](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="09f70-114">[!code-cs[csProgGuideGenerics#8](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_2.cs)]</span></span>  
  
-   <span data-ttu-id="09f70-115">**Verwenden** Sie T als Typparametername für Typen, die einen einzelnen Buchstaben als Typparameter haben.</span><span class="sxs-lookup"><span data-stu-id="09f70-115">**Consider** using T as the type parameter name for types with one single letter type parameter.</span></span>  
  
     <span data-ttu-id="09f70-116">[!code-cs[csProgGuideGenerics#9](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="09f70-116">[!code-cs[csProgGuideGenerics#9](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_3.cs)]</span></span>  
  
-   <span data-ttu-id="09f70-117">**Verwenden** Sie das Präfix „T“ für beschreibende Typparameternamen.</span><span class="sxs-lookup"><span data-stu-id="09f70-117">**Do** prefix descriptive type parameter names with "T".</span></span>  
  
     <span data-ttu-id="09f70-118">[!code-cs[csProgGuideGenerics#10](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="09f70-118">[!code-cs[csProgGuideGenerics#10](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_4.cs)]</span></span>  
  
-   <span data-ttu-id="09f70-119">**Überlegen** Sie, ob Sie Einschränkungen, die für einen Typparameter gelten, im Namen des Parameters angeben möchten.</span><span class="sxs-lookup"><span data-stu-id="09f70-119">**Consider** indicating constraints placed on a type parameter in the name of parameter.</span></span> <span data-ttu-id="09f70-120">Ein auf `ISession` eingeschränkter Parameter könnte z.B. `TSession` genannt werden.</span><span class="sxs-lookup"><span data-stu-id="09f70-120">For example, a parameter constrained to `ISession` may be called `TSession`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09f70-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="09f70-121">See Also</span></span>  
 <span data-ttu-id="09f70-122"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="09f70-122"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="09f70-123">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="09f70-123">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="09f70-124">[Generika](../../../csharp/programming-guide/generics/index.md) </span><span class="sxs-lookup"><span data-stu-id="09f70-124">[Generics](../../../csharp/programming-guide/generics/index.md) </span></span>  
 [<span data-ttu-id="09f70-125">Unterschiede zwischen C++-Vorlagen und C#-Generika</span><span class="sxs-lookup"><span data-stu-id="09f70-125">Differences Between C++ Templates and C# Generics</span></span>](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)

