---
title: Generische Methoden – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], methods
ms.assetid: 673eeea2-4b48-4faa-9c4e-2e89449221b9
ms.openlocfilehash: 5f066ca39c97b70554886e423c37c4ee47d49158
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712194"
---
# <a name="generic-methods-c-programming-guide"></a><span data-ttu-id="358b5-102">Generische Methoden (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="358b5-102">Generic Methods (C# Programming Guide)</span></span>
<span data-ttu-id="358b5-103">Bei einer generischen Methode handelt es sich um eine mit Typparametern deklarierte Methode, wie folgt:</span><span class="sxs-lookup"><span data-stu-id="358b5-103">A generic method is a method that is declared with type parameters, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#22)]  
  
 <span data-ttu-id="358b5-104">Im folgenden Codebeispiel wird eine Möglichkeit gezeigt, die Methode mit `int` für das Typargument aufzurufen:</span><span class="sxs-lookup"><span data-stu-id="358b5-104">The following code example shows one way to call the method by using `int` for the type argument:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#23)]  
  
 <span data-ttu-id="358b5-105">Sie können das Typargument auch weglassen, dann wird es vom Compiler abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="358b5-105">You can also omit the type argument and the compiler will infer it.</span></span> <span data-ttu-id="358b5-106">Der folgende Aufruf von `Swap` bewirkt das gleiche wie der vorherige Aufruf:</span><span class="sxs-lookup"><span data-stu-id="358b5-106">The following call to `Swap` is equivalent to the previous call:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#24)]  
  
 <span data-ttu-id="358b5-107">Für statische Methoden und Instanzmethoden gelten die gleichen Typrückschlussregeln.</span><span class="sxs-lookup"><span data-stu-id="358b5-107">The same rules for type inference apply to static methods and instance methods.</span></span> <span data-ttu-id="358b5-108">Der Compiler kann Typparameter auf der Grundlage der übergebenen Methodenargumente ableiten. Eine Einschränkung oder ein Rückgabewert genügen ihm zur Ableitung des Typparameters nicht.</span><span class="sxs-lookup"><span data-stu-id="358b5-108">The compiler can infer the type parameters based on the method arguments you pass in; it cannot infer the type parameters only from a constraint or return value.</span></span> <span data-ttu-id="358b5-109">Infolgedessen ist ein Typrückschluss bei Methoden ohne Parameter nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="358b5-109">Therefore type inference does not work with methods that have no parameters.</span></span> <span data-ttu-id="358b5-110">Der Typrückschluss tritt beim Kompilieren auf, bevor der Compiler versucht, die Signaturen von überladenen Methoden aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="358b5-110">Type inference occurs at compile time before the compiler tries to resolve overloaded method signatures.</span></span> <span data-ttu-id="358b5-111">Der Compiler wendet Typrückschlusslogik auf alle generischen Methoden gleichen Namens an.</span><span class="sxs-lookup"><span data-stu-id="358b5-111">The compiler applies type inference logic to all generic methods that share the same name.</span></span> <span data-ttu-id="358b5-112">Im Schritt zur Überladungsauflösung schließt der Compiler nur die generischen Methoden ein, bei denen der Typrückschluss erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="358b5-112">In the overload resolution step, the compiler includes only those generic methods on which type inference succeeded.</span></span>  
  
 <span data-ttu-id="358b5-113">Innerhalb einer generischen Klasse können nicht generische Methoden die Typparameter auf Klassenebene folgendermaßen zugreifen:</span><span class="sxs-lookup"><span data-stu-id="358b5-113">Within a generic class, non-generic methods can access the class-level type parameters, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#25)]  
  
 <span data-ttu-id="358b5-114">Wenn eine generische Methode definiert wird, die die gleichen Typparameter wie die übergeordnete Klasse akzeptiert, gibt der Compiler die Warnung [CS0693](../../misc/cs0693.md) aus, weil innerhalb des Gültigkeitsbereichs der Methode das Argument für das innere `T` das Argument für das innere `T` verdeckt.</span><span class="sxs-lookup"><span data-stu-id="358b5-114">If you define a generic method that takes the same type parameters as the containing class, the compiler generates warning [CS0693](../../misc/cs0693.md) because within the method scope, the argument supplied for the inner `T` hides the argument supplied for the outer `T`.</span></span> <span data-ttu-id="358b5-115">Falls Sie die Flexibilität benötigen, eine generische Klassenmethode mit anderen als den bei der Instanziierung der Klasse bereitgestellten Typargumenten aufrufen zu können, sollten Sie einen anderen Bezeichner für den Typparameter der Methode erwägen, wie in `GenericList2<T>` im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="358b5-115">If you require the flexibility of calling a generic class method with type arguments other than the ones provided when the class was instantiated, consider providing another identifier for the type parameter of the method, as shown in `GenericList2<T>` in the following example.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#26)]  
  
 <span data-ttu-id="358b5-116">Verwenden Sie Einschränkungen, um spezialisiertere Operationen bei Typparametern in Methoden zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="358b5-116">Use constraints to enable more specialized operations on type parameters in methods.</span></span> <span data-ttu-id="358b5-117">Die Version von `Swap<T>`, jetzt `SwapIfGreater<T>` genannt, kann nur mit Typargumenten verwendet werden, die <xref:System.IComparable%601> implementieren.</span><span class="sxs-lookup"><span data-stu-id="358b5-117">This version of `Swap<T>`, now named `SwapIfGreater<T>`, can only be used with type arguments that implement <xref:System.IComparable%601>.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#27)]  
  
 <span data-ttu-id="358b5-118">Generische Methoden können auf mehrere Typparameter überladen werden.</span><span class="sxs-lookup"><span data-stu-id="358b5-118">Generic methods can be overloaded on several type parameters.</span></span> <span data-ttu-id="358b5-119">Beispielsweise können sich folgende Methoden alle in derselben Klasse befinden:</span><span class="sxs-lookup"><span data-stu-id="358b5-119">For example, the following methods can all be located in the same class:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#28)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="358b5-120">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="358b5-120">C# Language Specification</span></span>  
 <span data-ttu-id="358b5-121">Weitere Informationen erhalten Sie unter [C#-Sprachspezifikation](~/_csharplang/spec/classes.md#methods).</span><span class="sxs-lookup"><span data-stu-id="358b5-121">For more information, see the [C# Language Specification](~/_csharplang/spec/classes.md#methods).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="358b5-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="358b5-122">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="358b5-123">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="358b5-123">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="358b5-124">Einführung in Generics</span><span class="sxs-lookup"><span data-stu-id="358b5-124">Introduction to Generics</span></span>](./index.md)
- [<span data-ttu-id="358b5-125">Methoden</span><span class="sxs-lookup"><span data-stu-id="358b5-125">Methods</span></span>](../classes-and-structs/methods.md)
