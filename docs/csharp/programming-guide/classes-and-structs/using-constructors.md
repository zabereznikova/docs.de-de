---
title: Verwenden von Konstruktoren – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], about constructors
ms.assetid: 464253b2-fd5d-469a-836d-df0fdf2a43f7
ms.openlocfilehash: faab6ac57629db11c60ee5b563ea95ebb90016dd
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964363"
---
# <a name="using-constructors-c-programming-guide"></a><span data-ttu-id="f42b4-102">Verwenden von Konstruktoren (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="f42b4-102">Using Constructors (C# Programming Guide)</span></span>

<span data-ttu-id="f42b4-103">Wenn eine [Klasse](../../language-reference/keywords/class.md) oder [Struktur](../../language-reference/keywords/struct.md) erstellt wird, wird deren Konstruktor aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="f42b4-103">When a [class](../../language-reference/keywords/class.md) or [struct](../../language-reference/keywords/struct.md) is created, its constructor is called.</span></span> <span data-ttu-id="f42b4-104">Konstruktoren haben den gleichen Namen wie die Klasse oder Struktur, und sie initialisieren normalerweise die Datenmember des neuen Objekts.</span><span class="sxs-lookup"><span data-stu-id="f42b4-104">Constructors have the same name as the class or struct, and they usually initialize the data members of the new object.</span></span>  
  
 <span data-ttu-id="f42b4-105">Im folgenden Beispiel wird eine Klasse mit dem Namen `Taxi` durch Verwendung eines einfachen Konstruktors definiert.</span><span class="sxs-lookup"><span data-stu-id="f42b4-105">In the following example, a class named `Taxi` is defined by using a simple constructor.</span></span> <span data-ttu-id="f42b4-106">Die Klasse wird dann mit dem [new](../../language-reference/operators/new-operator.md)-Operator instanziiert.</span><span class="sxs-lookup"><span data-stu-id="f42b4-106">This class is then instantiated with the [new](../../language-reference/operators/new-operator.md) operator.</span></span> <span data-ttu-id="f42b4-107">Der `Taxi`-Konstruktor wird sofort durch den `new`-Operator aufgerufen, nachdem Speicher für das neue Objekt zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="f42b4-107">The `Taxi` constructor is invoked by the `new` operator immediately after memory is allocated for the new object.</span></span>  
  
 [!code-csharp[csProgGuideObjects#53](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#53)]  
  
 <span data-ttu-id="f42b4-108">Ein Konstruktor, der keine Parameter akzeptiert, wird *parameterloser Konstruktor* genannt.</span><span class="sxs-lookup"><span data-stu-id="f42b4-108">A constructor that takes no parameters is called a *parameterless constructor*.</span></span> <span data-ttu-id="f42b4-109">Parameterlose Konstruktoren werden aufgerufen, wenn ein Objekt durch Verwendung des Operators `new` instanziiert wird und keine Argumente für `new` bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="f42b4-109">Parameterless constructors are invoked whenever an object is instantiated by using the `new` operator and no arguments are provided to `new`.</span></span> <span data-ttu-id="f42b4-110">Weitere Informationen finden Sie unter [Instanzkonstruktoren](./instance-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="f42b4-110">For more information, see [Instance Constructors](./instance-constructors.md).</span></span>  
  
 <span data-ttu-id="f42b4-111">Klassen ohne Konstruktoren erhalten vom C#-Compiler einen öffentlichen parameterlosen Konstruktor, um die Instanziierung der Klasse zuzulassen, außer die Klasse ist [static](../../language-reference/keywords/static.md).</span><span class="sxs-lookup"><span data-stu-id="f42b4-111">Unless the class is [static](../../language-reference/keywords/static.md), classes without constructors are given a public parameterless constructor by the C# compiler in order to enable class instantiation.</span></span> <span data-ttu-id="f42b4-112">Weitere Informationen finden Sie unter [Statische Klassen und statische Klassenmember](./static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="f42b4-112">For more information, see [Static Classes and Static Class Members](./static-classes-and-static-class-members.md).</span></span>  
  
 <span data-ttu-id="f42b4-113">Sie können verhindern, dass eine Klasse instanziiert wird, indem Sie den Konstruktor auf „privat“ einstellen; dazu müssen Sie wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="f42b4-113">You can prevent a class from being instantiated by making the constructor private, as follows:</span></span>  
  
 [!code-csharp[csProgGuideObjects#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#11)]  
  
 <span data-ttu-id="f42b4-114">Weitere Informationen finden Sie unter [Private Konstruktoren](./private-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="f42b4-114">For more information, see [Private Constructors](./private-constructors.md).</span></span>  
  
 <span data-ttu-id="f42b4-115">Konstruktoren für [struct](../../language-reference/keywords/struct.md)-Typen ähneln Klassenkonstruktoren, `structs` können aber keinen expliziten parameterlosen Konstruktor enthalten, da er automatisch vom Compiler bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="f42b4-115">Constructors for [struct](../../language-reference/keywords/struct.md) types resemble class constructors, but `structs` cannot contain an explicit parameterless constructor because one is provided automatically by the compiler.</span></span> <span data-ttu-id="f42b4-116">Dieser Konstruktor initialisiert alle Felder in `struct` auf die [Standardwerte](../../language-reference/builtin-types/default-values.md).</span><span class="sxs-lookup"><span data-stu-id="f42b4-116">This constructor initializes each field in the `struct` to the [default value](../../language-reference/builtin-types/default-values.md).</span></span> <span data-ttu-id="f42b4-117">Dieser parameterlose Konstruktor wird jedoch nur aufgerufen, wenn `struct` mit `new` instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="f42b4-117">However, this parameterless constructor is only invoked if the `struct` is instantiated with `new`.</span></span> <span data-ttu-id="f42b4-118">Dieser Code verwendet den parameterlosen Konstruktor z.B. für <xref:System.Int32>, damit sichergestellt ist, dass der ganzzahlige Typ initialisiert wird:</span><span class="sxs-lookup"><span data-stu-id="f42b4-118">For example, this code uses the parameterless constructor for <xref:System.Int32>, so that you are assured that the integer is initialized:</span></span>  
  
```csharp  
int i = new int();  
Console.WriteLine(i);  
```  
  
 <span data-ttu-id="f42b4-119">Der folgende Code verursacht jedoch einen Compilerfehler, da nicht `new` verwendet wird, und da versucht wird, ein Objekt zu verwenden, das nicht initialisiert wurde:</span><span class="sxs-lookup"><span data-stu-id="f42b4-119">The following code, however, causes a compiler error because it does not use `new`, and because it tries to use an object that has not been initialized:</span></span>  
  
```csharp  
int i;  
Console.WriteLine(i);  
```  
  
 <span data-ttu-id="f42b4-120">Alternativ können auch Objekte, die auf `structs` basieren, – einschließlich aller integrierten numerischen Typen – initialisiert oder zugewiesen und anschließend verwendet werden, so wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f42b4-120">Alternatively, objects based on `structs` (including all built-in numeric types) can be initialized or assigned and then used as in the following example:</span></span>  
  
```csharp  
int a = 44;  // Initialize the value type...  
int b;  
b = 33;      // Or assign it before using it.  
Console.WriteLine("{0}, {1}", a, b);  
```  
  
 <span data-ttu-id="f42b4-121">Es ist also nicht erforderlich, einen parameterlosen Konstruktor für einen Werttyp aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="f42b4-121">So calling the parameterless constructor for a value type is not required.</span></span>  
  
 <span data-ttu-id="f42b4-122">Sowohl Klassen als auch `structs` können Konstruktoren definieren, die Parameter annehmen.</span><span class="sxs-lookup"><span data-stu-id="f42b4-122">Both classes and `structs` can define constructors that take parameters.</span></span> <span data-ttu-id="f42b4-123">Konstruktoren, die Parameter annehmen, müssen über eine `new`- oder [base](../../language-reference/keywords/base.md)-Anweisung aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f42b4-123">Constructors that take parameters must be called through a `new` statement or a [base](../../language-reference/keywords/base.md) statement.</span></span> <span data-ttu-id="f42b4-124">Klassen und `structs` können also mehrere Konstruktoren definieren, und keine von beiden wird zum Definieren eines parameterlosen Konstruktors benötigt.</span><span class="sxs-lookup"><span data-stu-id="f42b4-124">Classes and `structs` can also define multiple constructors, and neither is required to define a parameterless constructor.</span></span> <span data-ttu-id="f42b4-125">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f42b4-125">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#54](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#54)]  
  
 <span data-ttu-id="f42b4-126">Diese Klasse kann mithilfe aller folgenden Anweisungen erstellt werden:</span><span class="sxs-lookup"><span data-stu-id="f42b4-126">This class can be created by using either of the following statements:</span></span>  
  
 [!code-csharp[csProgGuideObjects#55](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#55)]  
  
 <span data-ttu-id="f42b4-127">Ein Konstruktor kann das Schlüsselwort `base` verwenden, um den Konstruktor einer Basisklasse aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="f42b4-127">A constructor can use the `base` keyword to call the constructor of a base class.</span></span> <span data-ttu-id="f42b4-128">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f42b4-128">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#56](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#56)]  
  
 <span data-ttu-id="f42b4-129">In diesem Beispiel wird der Konstruktor der Basisklasse aufgerufen, bevor der Block eines Konstruktors ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f42b4-129">In this example, the constructor for the base class is called before the block for the constructor is executed.</span></span> <span data-ttu-id="f42b4-130">Das Schlüsselwort `base` kann mit oder ohne Parameter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f42b4-130">The `base` keyword can be used with or without parameters.</span></span> <span data-ttu-id="f42b4-131">Alle Parameter des Konstruktors können als Parameter für `base` oder als Teil eines Ausdrucks verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f42b4-131">Any parameters to the constructor can be used as parameters to `base`, or as part of an expression.</span></span> <span data-ttu-id="f42b4-132">Weitere Informationen finden Sie unter [base](../../language-reference/keywords/base.md).</span><span class="sxs-lookup"><span data-stu-id="f42b4-132">For more information, see [base](../../language-reference/keywords/base.md).</span></span>  
  
 <span data-ttu-id="f42b4-133">Wenn ein Konstruktor der Basisklasse in einer abgeleiteten Klasse nicht explizit durch das Schlüsselwort `base` aufgerufen wird, wird der parameterlose Konstruktor (falls vorhanden) implizit aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="f42b4-133">In a derived class, if a base-class constructor is not called explicitly by using the `base` keyword, the parameterless constructor, if there is one, is called implicitly.</span></span> <span data-ttu-id="f42b4-134">Dies bedeutet, dass die folgenden Deklarationen identisch sind:</span><span class="sxs-lookup"><span data-stu-id="f42b4-134">This means that the following constructor declarations are effectively the same:</span></span>  
  
 [!code-csharp[csProgGuideObjects#58](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#58)]  
  
 [!code-csharp[csProgGuideObjects#57](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#57)]  
  
 <span data-ttu-id="f42b4-135">Wenn eine Basisklasse keinen parameterlosen Konstruktor bereitstellt, muss die abgeleitete Klasse einen expliziten Aufruf an den Basiskonstruktor mithilfe von `base` durchführen.</span><span class="sxs-lookup"><span data-stu-id="f42b4-135">If a base class does not offer a parameterless constructor, the derived class must make an explicit call to a base constructor by using `base`.</span></span>  
  
 <span data-ttu-id="f42b4-136">Ein Konstruktor kann einen anderen Konstruktor in demselben Objekt über das Schlüsselwort [this](../../language-reference/keywords/this.md) aufrufen.</span><span class="sxs-lookup"><span data-stu-id="f42b4-136">A constructor can invoke another constructor in the same object by using the [this](../../language-reference/keywords/this.md) keyword.</span></span> <span data-ttu-id="f42b4-137">Genau wie `base` kann `this` mit oder ohne Parameter verwendet werden, und alle Parameter im Konstruktor sind als Parameter für `this` oder als Teil eines Ausdrucks verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f42b4-137">Like `base`, `this` can be used with or without parameters, and any parameters in the constructor are available as parameters to `this`, or as part of an expression.</span></span> <span data-ttu-id="f42b4-138">Der zweite Konstruktor im vorherigen Beispiel kann z.B. über `this` neu geschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="f42b4-138">For example, the second constructor in the previous example can be rewritten using `this`:</span></span>  
  
 [!code-csharp[csProgGuideObjects#59](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#59)]  
  
 <span data-ttu-id="f42b4-139">Die Verwendung des Schlüsselworts `this` im vorherigen Beispiel bewirkt, dass dieser Konstruktor aufgerufen wird:</span><span class="sxs-lookup"><span data-stu-id="f42b4-139">The use of the `this` keyword in the previous example causes this constructor to be called:</span></span>  
  
 [!code-csharp[csProgGuideObjects#60](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#60)]  
  
 <span data-ttu-id="f42b4-140">Konstruktoren können als [public](../../language-reference/keywords/public.md), [private](../../language-reference/keywords/private.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md) oder [private protected](../../language-reference/keywords/private-protected.md) markiert werden.</span><span class="sxs-lookup"><span data-stu-id="f42b4-140">Constructors can be marked as [public](../../language-reference/keywords/public.md), [private](../../language-reference/keywords/private.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md) or [private protected](../../language-reference/keywords/private-protected.md).</span></span> <span data-ttu-id="f42b4-141">Diese Zugriffsmodifizierer definieren, wie Benutzer der Klasse die Klasse konstruieren können.</span><span class="sxs-lookup"><span data-stu-id="f42b4-141">These access modifiers define how users of the class can construct the class.</span></span> <span data-ttu-id="f42b4-142">Weitere Informationen finden Sie unter [Zugriffsmodifizierer](./access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="f42b4-142">For more information, see [Access Modifiers](./access-modifiers.md).</span></span>  
  
 <span data-ttu-id="f42b4-143">Ein Konstruktor kann mithilfe des Schlüsselworts [static](../../language-reference/keywords/static.md) als statisch deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="f42b4-143">A constructor can be declared static by using the [static](../../language-reference/keywords/static.md) keyword.</span></span> <span data-ttu-id="f42b4-144">Statische Konstruktoren werden automatisch aufgerufen, unmittelbar bevor auf ein statisches Feld zugegriffen wird, und werden generell zum Initialisieren statischer Klassenmember verwendet.</span><span class="sxs-lookup"><span data-stu-id="f42b4-144">Static constructors are called automatically, immediately before any static fields are accessed, and are generally used to initialize static class members.</span></span> <span data-ttu-id="f42b4-145">Weitere Informationen finden Sie unter [Statische Konstruktoren](./static-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="f42b4-145">For more information, see [Static Constructors](./static-constructors.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="f42b4-146">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="f42b4-146">C# Language Specification</span></span>  

<span data-ttu-id="f42b4-147">Weitere Informationen erhalten Sie unter [Instanzkonstruktoren](~/_csharplang/spec/classes.md#instance-constructors) und [Statische Konstruktoren](~/_csharplang/spec/classes.md#static-constructors) in der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="f42b4-147">For more information, see [Instance constructors](~/_csharplang/spec/classes.md#instance-constructors) and [Static constructors](~/_csharplang/spec/classes.md#static-constructors) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="f42b4-148">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="f42b4-148">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f42b4-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f42b4-149">See also</span></span>

- [<span data-ttu-id="f42b4-150">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="f42b4-150">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="f42b4-151">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="f42b4-151">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="f42b4-152">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="f42b4-152">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="f42b4-153">Finalizer</span><span class="sxs-lookup"><span data-stu-id="f42b4-153">Finalizers</span></span>](./destructors.md)
