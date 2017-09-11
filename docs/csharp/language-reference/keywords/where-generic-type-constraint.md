---
title: "where (Einschränkung des generischen Typs) (C#-Referenz)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- whereconstraint
- whereconstraint_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- where (generic type constraint) [C#]
ms.assetid: d7aa871b-0714-416a-bab2-96f87ada4310
caps.latest.revision: 10
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
ms.openlocfilehash: 8e81640ee56ed672bb09242a070fdf167740874b
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="where-generic-type-constraint-c-reference"></a><span data-ttu-id="d182c-102">where (Einschränkung des generischen Typs) (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="d182c-102">where (generic type constraint) (C# Reference)</span></span>
<span data-ttu-id="d182c-103">In einer generischen Typdefinition wird die `where`-Klausel verwendet, um Einschränkungen für Typen anzugeben, die als Argumente für einen Typenparameter verwendet werden können, der in einer generischen Deklaration definiert ist.</span><span class="sxs-lookup"><span data-stu-id="d182c-103">In a generic type definition, the `where` clause is used to specify constraints on the types that can be used as arguments for a type parameter defined in a generic declaration.</span></span> <span data-ttu-id="d182c-104">So können Sie beispielsweise eine generische Klasse erstellen, `MyGenericClass`, deren Typparameter `T` die Schnittstelle <xref:System.IComparable%601> implementiert:</span><span class="sxs-lookup"><span data-stu-id="d182c-104">For example, you can declare a generic class, `MyGenericClass`, such that the type parameter `T` implements the <xref:System.IComparable%601> interface:</span></span>  
  
```csharp  
public class MyGenericClass<T> where T:IComparable { }  
```  
  
> [!NOTE]
>  <span data-ttu-id="d182c-105">Weitere Informationen über die where-Klausel in einem Abfrageausdruck finden Sie unter [where-Klausel](../../../csharp/language-reference/keywords/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="d182c-105">For more information on the where clause in a query expression, see [where clause](../../../csharp/language-reference/keywords/where-clause.md).</span></span>  
  
 <span data-ttu-id="d182c-106">Zusätzlich zu Schnittstelleneinschränkungen kann eine `where`-Klausel eine Basisklasseneinschränkung enthalten, die angibt, dass ein Typ über die angegebene Klasse als Basisklasse verfügen muss (oder diese Klasse selbst sein muss), um als Typargument für diesen generischen Typ verwendet werden zu können.</span><span class="sxs-lookup"><span data-stu-id="d182c-106">In addition to interface constraints, a `where` clause can include a base class constraint, which states that a type must have the specified class as a base class (or be that class itself) in order to be used as a type argument for that generic type.</span></span> <span data-ttu-id="d182c-107">Wenn eine solche Einschränkung verwendet wird, muss sie vor jeder anderen Einschränkung für den Typparameter angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d182c-107">If such a constraint is used, it must appear before any other constraints on that type parameter.</span></span>  
  
 <span data-ttu-id="d182c-108">[!code-cs[csrefKeywordsContextual#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d182c-108">[!code-cs[csrefKeywordsContextual#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_1.cs)]</span></span>  
  
 <span data-ttu-id="d182c-109">Die `where`-Klausel kann auch eine Konstruktoreinschränkung einschließen.</span><span class="sxs-lookup"><span data-stu-id="d182c-109">The `where` clause may also include a constructor constraint.</span></span> <span data-ttu-id="d182c-110">Es ist möglich, eine Instanz eines Typparameters mithilfe des neuen Operators zu erstellen. Allerdings muss zu diesem Zweck der Typparameter durch die Konstruktoreinschränkung `new()` eingeschränkt werden.</span><span class="sxs-lookup"><span data-stu-id="d182c-110">It is possible to create an instance of a type parameter using the new operator; however, in order to do so the type parameter must be constrained by the constructor constraint, `new()`.</span></span> <span data-ttu-id="d182c-111">Die [new()-Einschränkung](../../../csharp/language-reference/keywords/new-constraint.md) informiert den Compiler, dass jedes angegebene Typargument über einen zugänglichen parameterlosen oder Standardkonstruktor verfügen muss.</span><span class="sxs-lookup"><span data-stu-id="d182c-111">The [new() Constraint](../../../csharp/language-reference/keywords/new-constraint.md) lets the compiler know that any type argument supplied must have an accessible parameterless--or default-- constructor.</span></span> <span data-ttu-id="d182c-112">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d182c-112">For example:</span></span>  
  
 <span data-ttu-id="d182c-113">[!code-cs[csrefKeywordsContextual#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="d182c-113">[!code-cs[csrefKeywordsContextual#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_2.cs)]</span></span>  
  
 <span data-ttu-id="d182c-114">Die `new()`-Einschränkung wird in der `where`-Klausel als Letztes angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d182c-114">The `new()` constraint appears last in the `where` clause.</span></span>  
  
 <span data-ttu-id="d182c-115">Bei mehreren Typparametern müssen Sie für jeden davon eine eigene `where`-Klausel verwenden, z.B.:</span><span class="sxs-lookup"><span data-stu-id="d182c-115">With multiple type parameters, use one `where` clause for each type parameter, for example:</span></span>  
  
 <span data-ttu-id="d182c-116">[!code-cs[csrefKeywordsContextual#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="d182c-116">[!code-cs[csrefKeywordsContextual#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_3.cs)]</span></span>  
  
 <span data-ttu-id="d182c-117">Sie können auch Einschränkungen wie folgt an Typparameter generischer Methoden anfügen:</span><span class="sxs-lookup"><span data-stu-id="d182c-117">You can also attach constraints to type parameters of generic methods, like this:</span></span>  
  
```csharp  
public bool MyMethod<T>(T t) where T : IMyInterface { }  
```  
  
 <span data-ttu-id="d182c-118">Beachten Sie, dass die Syntax zum Beschreiben der Parametereinschränkungen für Delegaten mit der Syntax von Methoden identisch ist:</span><span class="sxs-lookup"><span data-stu-id="d182c-118">Notice that the syntax to describe type parameter constraints on delegates is the same as that of methods:</span></span>  
  
```csharp  
delegate T MyDelegate<T>() where T : new()  
```  
  
 <span data-ttu-id="d182c-119">Informationen zu generischen Delegaten finden Sie unter [Generic Delegates (Generische Delegaten)](../../../csharp/programming-guide/generics/generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="d182c-119">For information on generic delegates, see [Generic Delegates](../../../csharp/programming-guide/generics/generic-delegates.md).</span></span>  
  
 <span data-ttu-id="d182c-120">Weitere Informationen zur Syntax und der Verwendung von Einschränkungen finden Sie unter [Einschränkungen für Typparameter](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="d182c-120">For details on the syntax and use of constraints, see [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="d182c-121">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="d182c-121">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d182c-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d182c-122">See Also</span></span>  
 <span data-ttu-id="d182c-123">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="d182c-123">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="d182c-124">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d182c-124">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d182c-125">[Einführung in Generika](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span><span class="sxs-lookup"><span data-stu-id="d182c-125">[Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span></span>  
 <span data-ttu-id="d182c-126">[new-Einschränkung](../../../csharp/language-reference/keywords/new-constraint.md) </span><span class="sxs-lookup"><span data-stu-id="d182c-126">[new Constraint](../../../csharp/language-reference/keywords/new-constraint.md) </span></span>  
 [<span data-ttu-id="d182c-127">Einschränkungen für Typparameter</span><span class="sxs-lookup"><span data-stu-id="d182c-127">Constraints on Type Parameters</span></span>](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)

