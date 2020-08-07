---
title: Generische Methoden – C#-Programmierhandbuch
description: Lernen Sie Methoden kennen, die mit Typparametern deklariert und als generische Methoden bezeichnet werden. Hier finden Sie Codebeispiele und zusätzliche verfügbare Ressourcen.
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], methods
ms.assetid: 673eeea2-4b48-4faa-9c4e-2e89449221b9
ms.openlocfilehash: 77b81de26961a8b59644643bf043ed723dbf374f
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301878"
---
# <a name="generic-methods-c-programming-guide"></a><span data-ttu-id="ed754-104">Generische Methoden (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="ed754-104">Generic Methods (C# Programming Guide)</span></span>
<span data-ttu-id="ed754-105">Bei einer generischen Methode handelt es sich um eine mit Typparametern deklarierte Methode, wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ed754-105">A generic method is a method that is declared with type parameters, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#22)]  
  
 <span data-ttu-id="ed754-106">Im folgenden Codebeispiel wird eine Möglichkeit gezeigt, die Methode mit `int` für das Typargument aufzurufen:</span><span class="sxs-lookup"><span data-stu-id="ed754-106">The following code example shows one way to call the method by using `int` for the type argument:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#23)]  
  
 <span data-ttu-id="ed754-107">Sie können das Typargument auch weglassen, dann wird es vom Compiler abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="ed754-107">You can also omit the type argument and the compiler will infer it.</span></span> <span data-ttu-id="ed754-108">Der folgende Aufruf von `Swap` bewirkt das gleiche wie der vorherige Aufruf:</span><span class="sxs-lookup"><span data-stu-id="ed754-108">The following call to `Swap` is equivalent to the previous call:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#24)]  
  
 <span data-ttu-id="ed754-109">Für statische Methoden und Instanzmethoden gelten die gleichen Typrückschlussregeln.</span><span class="sxs-lookup"><span data-stu-id="ed754-109">The same rules for type inference apply to static methods and instance methods.</span></span> <span data-ttu-id="ed754-110">Der Compiler kann Typparameter auf der Grundlage der übergebenen Methodenargumente ableiten. Eine Einschränkung oder ein Rückgabewert genügen ihm zur Ableitung des Typparameters nicht.</span><span class="sxs-lookup"><span data-stu-id="ed754-110">The compiler can infer the type parameters based on the method arguments you pass in; it cannot infer the type parameters only from a constraint or return value.</span></span> <span data-ttu-id="ed754-111">Infolgedessen ist ein Typrückschluss bei Methoden ohne Parameter nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="ed754-111">Therefore type inference does not work with methods that have no parameters.</span></span> <span data-ttu-id="ed754-112">Der Typrückschluss tritt beim Kompilieren auf, bevor der Compiler versucht, die Signaturen von überladenen Methoden aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="ed754-112">Type inference occurs at compile time before the compiler tries to resolve overloaded method signatures.</span></span> <span data-ttu-id="ed754-113">Der Compiler wendet Typrückschlusslogik auf alle generischen Methoden gleichen Namens an.</span><span class="sxs-lookup"><span data-stu-id="ed754-113">The compiler applies type inference logic to all generic methods that share the same name.</span></span> <span data-ttu-id="ed754-114">Im Schritt zur Überladungsauflösung schließt der Compiler nur die generischen Methoden ein, bei denen der Typrückschluss erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="ed754-114">In the overload resolution step, the compiler includes only those generic methods on which type inference succeeded.</span></span>  
  
 <span data-ttu-id="ed754-115">Innerhalb einer generischen Klasse können nicht generische Methoden die Typparameter auf Klassenebene folgendermaßen zugreifen:</span><span class="sxs-lookup"><span data-stu-id="ed754-115">Within a generic class, non-generic methods can access the class-level type parameters, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#25)]  
  
 <span data-ttu-id="ed754-116">Wenn eine generische Methode definiert wird, die die gleichen Typparameter wie die übergeordnete Klasse akzeptiert, gibt der Compiler die Warnung [CS0693](../../misc/cs0693.md) aus, weil innerhalb des Gültigkeitsbereichs der Methode das Argument für das innere `T` das Argument für das innere `T` verdeckt.</span><span class="sxs-lookup"><span data-stu-id="ed754-116">If you define a generic method that takes the same type parameters as the containing class, the compiler generates warning [CS0693](../../misc/cs0693.md) because within the method scope, the argument supplied for the inner `T` hides the argument supplied for the outer `T`.</span></span> <span data-ttu-id="ed754-117">Falls Sie die Flexibilität benötigen, eine generische Klassenmethode mit anderen als den bei der Instanziierung der Klasse bereitgestellten Typargumenten aufrufen zu können, sollten Sie einen anderen Bezeichner für den Typparameter der Methode erwägen, wie in `GenericList2<T>` im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ed754-117">If you require the flexibility of calling a generic class method with type arguments other than the ones provided when the class was instantiated, consider providing another identifier for the type parameter of the method, as shown in `GenericList2<T>` in the following example.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#26)]  
  
 <span data-ttu-id="ed754-118">Verwenden Sie Einschränkungen, um spezialisiertere Operationen bei Typparametern in Methoden zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="ed754-118">Use constraints to enable more specialized operations on type parameters in methods.</span></span> <span data-ttu-id="ed754-119">Die Version von `Swap<T>`, jetzt `SwapIfGreater<T>` genannt, kann nur mit Typargumenten verwendet werden, die <xref:System.IComparable%601> implementieren.</span><span class="sxs-lookup"><span data-stu-id="ed754-119">This version of `Swap<T>`, now named `SwapIfGreater<T>`, can only be used with type arguments that implement <xref:System.IComparable%601>.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#27)]  
  
 <span data-ttu-id="ed754-120">Generische Methoden können auf mehrere Typparameter überladen werden.</span><span class="sxs-lookup"><span data-stu-id="ed754-120">Generic methods can be overloaded on several type parameters.</span></span> <span data-ttu-id="ed754-121">Beispielsweise können sich folgende Methoden alle in derselben Klasse befinden:</span><span class="sxs-lookup"><span data-stu-id="ed754-121">For example, the following methods can all be located in the same class:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#28)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="ed754-122">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="ed754-122">C# Language Specification</span></span>  
 <span data-ttu-id="ed754-123">Weitere Informationen erhalten Sie unter [C#-Sprachspezifikation](~/_csharplang/spec/classes.md#methods).</span><span class="sxs-lookup"><span data-stu-id="ed754-123">For more information, see the [C# Language Specification](~/_csharplang/spec/classes.md#methods).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed754-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed754-124">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="ed754-125">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ed754-125">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ed754-126">Einführung in Generics</span><span class="sxs-lookup"><span data-stu-id="ed754-126">Introduction to Generics</span></span>](./index.md)
- [<span data-ttu-id="ed754-127">Methoden</span><span class="sxs-lookup"><span data-stu-id="ed754-127">Methods</span></span>](../classes-and-structs/methods.md)
