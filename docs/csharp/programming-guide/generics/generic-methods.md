---
title: Generische Methoden (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], methods
ms.assetid: 673eeea2-4b48-4faa-9c4e-2e89449221b9
caps.latest.revision: 27
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
ms.openlocfilehash: 14461773303bafc098f79c3686b1f76827f11005
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="generic-methods-c-programming-guide"></a><span data-ttu-id="ecfc8-102">Generische Methoden (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="ecfc8-102">Generic Methods (C# Programming Guide)</span></span>
<span data-ttu-id="ecfc8-103">Bei einer generischen Methode handelt es sich um eine mit Typparametern deklarierte Methode, wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ecfc8-103">A generic method is a method that is declared with type parameters, as follows:</span></span>  
  
 <span data-ttu-id="ecfc8-104">[!code-cs[csProgGuideGenerics#22](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ecfc8-104">[!code-cs[csProgGuideGenerics#22](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_1.cs)]</span></span>  
  
 <span data-ttu-id="ecfc8-105">Im folgenden Codebeispiel wird eine Möglichkeit gezeigt, die Methode mit `int` für das Typargument aufzurufen:</span><span class="sxs-lookup"><span data-stu-id="ecfc8-105">The following code example shows one way to call the method by using `int` for the type argument:</span></span>  
  
 <span data-ttu-id="ecfc8-106">[!code-cs[csProgGuideGenerics#23](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="ecfc8-106">[!code-cs[csProgGuideGenerics#23](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_2.cs)]</span></span>  
  
 <span data-ttu-id="ecfc8-107">Sie können das Typargument auch weglassen, dann wird es vom Compiler abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="ecfc8-107">You can also omit the type argument and the compiler will infer it.</span></span> <span data-ttu-id="ecfc8-108">Der folgende Aufruf von `Swap` bewirkt das gleiche wie der vorherige Aufruf:</span><span class="sxs-lookup"><span data-stu-id="ecfc8-108">The following call to `Swap` is equivalent to the previous call:</span></span>  
  
 <span data-ttu-id="ecfc8-109">[!code-cs[csProgGuideGenerics#24](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="ecfc8-109">[!code-cs[csProgGuideGenerics#24](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_3.cs)]</span></span>  
  
 <span data-ttu-id="ecfc8-110">Für statische Methoden und Instanzmethoden gelten die gleichen Typrückschlussregeln.</span><span class="sxs-lookup"><span data-stu-id="ecfc8-110">The same rules for type inference apply to static methods and instance methods.</span></span> <span data-ttu-id="ecfc8-111">Der Compiler kann Typparameter auf der Grundlage der übergebenen Methodenargumente ableiten. Eine Einschränkung oder ein Rückgabewert genügen ihm zur Ableitung des Typparameters nicht.</span><span class="sxs-lookup"><span data-stu-id="ecfc8-111">The compiler can infer the type parameters based on the method arguments you pass in; it cannot infer the type parameters only from a constraint or return value.</span></span> <span data-ttu-id="ecfc8-112">Infolgedessen ist ein Typrückschluss bei Methoden ohne Parameter nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="ecfc8-112">Therefore type inference does not work with methods that have no parameters.</span></span> <span data-ttu-id="ecfc8-113">Der Typrückschluss tritt beim Kompilieren auf, bevor der Compiler versucht, die Signaturen von überladenen Methoden aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="ecfc8-113">Type inference occurs at compile time before the compiler tries to resolve overloaded method signatures.</span></span> <span data-ttu-id="ecfc8-114">Der Compiler wendet Typrückschlusslogik auf alle generischen Methoden gleichen Namens an.</span><span class="sxs-lookup"><span data-stu-id="ecfc8-114">The compiler applies type inference logic to all generic methods that share the same name.</span></span> <span data-ttu-id="ecfc8-115">Im Schritt zur Überladungsauflösung schließt der Compiler nur die generischen Methoden ein, bei denen der Typrückschluss erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="ecfc8-115">In the overload resolution step, the compiler includes only those generic methods on which type inference succeeded.</span></span>  
  
 <span data-ttu-id="ecfc8-116">Innerhalb einer generischen Klasse können nicht generische Methoden die Typparameter auf Klassenebene folgendermaßen zugreifen:</span><span class="sxs-lookup"><span data-stu-id="ecfc8-116">Within a generic class, non-generic methods can access the class-level type parameters, as follows:</span></span>  
  
 <span data-ttu-id="ecfc8-117">[!code-cs[csProgGuideGenerics#25](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="ecfc8-117">[!code-cs[csProgGuideGenerics#25](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_4.cs)]</span></span>  
  
 <span data-ttu-id="ecfc8-118">Wenn eine generische Methode definiert wird, die die gleichen Typparameter wie die übergeordnete Klasse verwendet, gibt der Compiler die Warnung CS0693 aus, weil innerhalb des Gültigkeitsbereichs der Methode das Argument für das äußere `T` durch das Argument für das innere `T` ausgeblendet wird.</span><span class="sxs-lookup"><span data-stu-id="ecfc8-118">If you define a generic method that takes the same type parameters as the containing class, the compiler generates warning CS0693 because within the method scope, the argument supplied for the inner `T` hides the argument supplied for the outer `T`.</span></span> <span data-ttu-id="ecfc8-119">Falls Sie die Flexibilität benötigen, eine generische Klassenmethode mit anderen als den bei der Instanziierung der Klasse bereitgestellten Typargumenten aufrufen zu können, sollten Sie einen anderen Bezeichner für den Typparameter der Methode erwägen, wie in `GenericList2<T>` im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ecfc8-119">If you require the flexibility of calling a generic class method with type arguments other than the ones provided when the class was instantiated, consider providing another identifier for the type parameter of the method, as shown in `GenericList2<T>` in the following example.</span></span>  
  
 <span data-ttu-id="ecfc8-120">[!code-cs[csProgGuideGenerics#26](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="ecfc8-120">[!code-cs[csProgGuideGenerics#26](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_5.cs)]</span></span>  
  
 <span data-ttu-id="ecfc8-121">Verwenden Sie Einschränkungen, um spezialisiertere Operationen bei Typparametern in Methoden zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="ecfc8-121">Use constraints to enable more specialized operations on type parameters in methods.</span></span> <span data-ttu-id="ecfc8-122">Die Version von `Swap<T>`, jetzt `SwapIfGreater<T>` genannt, kann nur mit Typargumenten verwendet werden, die <xref:System.IComparable%601> implementieren.</span><span class="sxs-lookup"><span data-stu-id="ecfc8-122">This version of `Swap<T>`, now named `SwapIfGreater<T>`, can only be used with type arguments that implement <xref:System.IComparable%601>.</span></span>  
  
 <span data-ttu-id="ecfc8-123">[!code-cs[csProgGuideGenerics#27](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="ecfc8-123">[!code-cs[csProgGuideGenerics#27](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_6.cs)]</span></span>  
  
 <span data-ttu-id="ecfc8-124">Generische Methoden können auf mehrere Typparameter überladen werden.</span><span class="sxs-lookup"><span data-stu-id="ecfc8-124">Generic methods can be overloaded on several type parameters.</span></span> <span data-ttu-id="ecfc8-125">Beispielsweise können sich folgende Methoden alle in derselben Klasse befinden:</span><span class="sxs-lookup"><span data-stu-id="ecfc8-125">For example, the following methods can all be located in the same class:</span></span>  
  
 <span data-ttu-id="ecfc8-126">[!code-cs[csProgGuideGenerics#28](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="ecfc8-126">[!code-cs[csProgGuideGenerics#28](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_7.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="ecfc8-127">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="ecfc8-127">C# Language Specification</span></span>  
 <span data-ttu-id="ecfc8-128">Weitere Informationen erhalten Sie unter [C#-Sprachspezifikation](../../../csharp/language-reference/language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="ecfc8-128">For more information, see the [C# Language Specification](../../../csharp/language-reference/language-specification/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecfc8-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ecfc8-129">See Also</span></span>  
 <span data-ttu-id="ecfc8-130"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="ecfc8-130"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="ecfc8-131">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ecfc8-131">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="ecfc8-132">[Einführung in Generika](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span><span class="sxs-lookup"><span data-stu-id="ecfc8-132">[Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span></span>  
 [<span data-ttu-id="ecfc8-133">Methoden</span><span class="sxs-lookup"><span data-stu-id="ecfc8-133">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)

