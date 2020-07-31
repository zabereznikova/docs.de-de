---
title: Konstruktoren – C#-Programmierhandbuch
description: In C# wird bei Erstellung einer Klasse oder einer Struktur ein Konstruktor erstellt. Verwenden Sie Konstruktoren, um Standardwerte festzulegen, Instanziierungen zu begrenzen und flexiblen, einfach lesbaren Code zu schreiben.
ms.date: 05/05/2017
helpviewer_keywords:
- constructors [C#]
- classes [C#], constructors
- C# language, constructors
ms.assetid: df2e2e9d-7998-418b-8e7d-890c17ff6c95
ms.openlocfilehash: 4a731e648143f5e0ecf8860625962d8baa29fe26
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474903"
---
# <a name="constructors-c-programming-guide"></a><span data-ttu-id="6a30a-104">Konstruktoren (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="6a30a-104">Constructors (C# Programming Guide)</span></span>

<span data-ttu-id="6a30a-105">Wenn eine [class](../../language-reference/keywords/class.md) oder [struct](../../language-reference/builtin-types/struct.md) erstellt wird, wird deren Konstruktor aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="6a30a-105">Whenever a [class](../../language-reference/keywords/class.md) or [struct](../../language-reference/builtin-types/struct.md) is created, its constructor is called.</span></span> <span data-ttu-id="6a30a-106">Eine Klasse oder Struktur verfügt möglicherweise über mehrere Konstruktoren, die andere Argumente verwenden.</span><span class="sxs-lookup"><span data-stu-id="6a30a-106">A class or struct may have multiple constructors that take different arguments.</span></span> <span data-ttu-id="6a30a-107">Mit Konstruktoren können Programmierer Standardwerte festlegen, Instanziierungen einschränken und Code schreiben, der flexibel und leicht zu lesen ist.</span><span class="sxs-lookup"><span data-stu-id="6a30a-107">Constructors enable the programmer to set default values, limit instantiation, and write code that is flexible and easy to read.</span></span> <span data-ttu-id="6a30a-108">Weitere Informationen und Beispiele finden Sie unter [Verwenden von Konstruktoren](./using-constructors.md) und [Instanzkonstruktoren](./instance-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="6a30a-108">For more information and examples, see [Using Constructors](./using-constructors.md) and [Instance Constructors](./instance-constructors.md).</span></span>  

## <a name="parameterless-constructors"></a><span data-ttu-id="6a30a-109">Parameterlose Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="6a30a-109">Parameterless constructors</span></span>
  
<span data-ttu-id="6a30a-110">Wenn Sie keinen Konstruktor für die Klasse angeben, erstellt C# standardmäßig einen, der das Objekt instanziiert und Membervariablen auf die Standardwerte festlegt, wie in den [Standardwerten der C#-Typen](../../language-reference/builtin-types/default-values.md) aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="6a30a-110">If you don't provide a constructor for your class, C# creates one by default that instantiates the object and sets member variables to the default values as listed in the [Default values of C# types](../../language-reference/builtin-types/default-values.md) article.</span></span> <span data-ttu-id="6a30a-111">Wenn Sie keinen Konstruktor für die Struktur angeben, stützt sich C# auf einen *impliziten parameterlosen Konstruktor*, um automatisch jedes Feld auf seinen Standardwert zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="6a30a-111">If you don't provide a constructor for your struct, C# relies on an *implicit parameterless constructor* to automatically initialize each field to its default value.</span></span> <span data-ttu-id="6a30a-112">Weitere Informationen und Beispiele finden Sie unter [Instanzkonstruktoren](instance-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="6a30a-112">For more information and examples, see [Instance constructors](instance-constructors.md).</span></span>  

## <a name="constructor-syntax"></a><span data-ttu-id="6a30a-113">Konstruktorsyntax</span><span class="sxs-lookup"><span data-stu-id="6a30a-113">Constructor syntax</span></span>

<span data-ttu-id="6a30a-114">Ein Konstruktor ist eine Methode, dessen Name derselbe ist wie der seines Typs.</span><span class="sxs-lookup"><span data-stu-id="6a30a-114">A constructor is a method whose name is the same as the name of its type.</span></span> <span data-ttu-id="6a30a-115">Die Methodensignatur enthält nur den Methodennamen und die Parameterliste; ein Rückgabetyp ist nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="6a30a-115">Its method signature includes only the method name and its parameter list; it does not include a return type.</span></span> <span data-ttu-id="6a30a-116">Im folgenden Beispiel wird der Konstruktor für eine Klasse mit dem Namen `Person` gezeigt.</span><span class="sxs-lookup"><span data-stu-id="6a30a-116">The following example shows the constructor for a class named `Person`.</span></span>

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#1)]  

<span data-ttu-id="6a30a-117">Wenn ein Konstruktor als einzelne Anweisung implementiert werden kann, können Sie eine [expression body definition (Ausdruckstextdefinition)](../statements-expressions-operators/expression-bodied-members.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="6a30a-117">If a constructor can be implemented as a single statement, you can use an [expression body definition](../statements-expressions-operators/expression-bodied-members.md).</span></span> <span data-ttu-id="6a30a-118">Im folgenden Beispiel wird eine `Location`-Klasse definiert, deren Klassenkonstruktor einen einzelnen Zeichenfolgenparameter namens *name* enthält.</span><span class="sxs-lookup"><span data-stu-id="6a30a-118">The following example defines a `Location` class whose constructor has a single string parameter named *name*.</span></span> <span data-ttu-id="6a30a-119">Die Ausdruckstextdefinition weist das Argument dem Feld `locationName` zu.</span><span class="sxs-lookup"><span data-stu-id="6a30a-119">The expression body definition assigns the argument to the `locationName` field.</span></span>

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

## <a name="static-constructors"></a><span data-ttu-id="6a30a-120">Statische Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="6a30a-120">Static constructors</span></span>

<span data-ttu-id="6a30a-121">Die vorherigen Beispiele haben alle Instanzkonstruktoren gezeigt, die ein neues Objekt erstellen.</span><span class="sxs-lookup"><span data-stu-id="6a30a-121">The previous examples have all shown instance constructors, which create a new object.</span></span> <span data-ttu-id="6a30a-122">Eine Klasse oder Struktur kann auch einen statischen Konstruktor haben, der statische Member dieses Typs initialisiert.</span><span class="sxs-lookup"><span data-stu-id="6a30a-122">A class or struct can also have a static constructor, which initializes static members of the type.</span></span>  <span data-ttu-id="6a30a-123">Statische Konstruktoren sind parameterlos.</span><span class="sxs-lookup"><span data-stu-id="6a30a-123">Static constructors are parameterless.</span></span> <span data-ttu-id="6a30a-124">Wenn Sie keinen statischen Konstruktor zum Initialisieren von statischen Feldern angeben, initialisiert der C#-Compiler statische Felder mit ihrem Standardwert, wie unter [Standardwerte der C#-Typen](../../language-reference/builtin-types/default-values.md) aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="6a30a-124">If you don't provide a static constructor to initialize static fields, the C# compiler initializes static fields to their default value as listed in the [Default values of C# types](../../language-reference/builtin-types/default-values.md) article.</span></span>

<span data-ttu-id="6a30a-125">Im folgenden Beispiel wird ein statischer Konstruktor verwendet, um ein statisches Feld zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="6a30a-125">The following example uses a static constructor to initialize a static field.</span></span>

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#2)]  

<span data-ttu-id="6a30a-126">Sie können einen statischen Konstruktor auch mit einer Ausdruckstextdefinition definieren, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="6a30a-126">You can also define a static constructor with an expression body definition, as the following example shows.</span></span>

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#3)]  

<span data-ttu-id="6a30a-127">Weitere Informationen und Beispiele finden Sie unter [Statische Konstruktoren](./static-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="6a30a-127">For more information and examples, see [Static Constructors](./static-constructors.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6a30a-128">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="6a30a-128">In This Section</span></span>  
 [<span data-ttu-id="6a30a-129">Verwenden von Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="6a30a-129">Using Constructors</span></span>](./using-constructors.md)  
  
 [<span data-ttu-id="6a30a-130">Instanzkonstruktoren</span><span class="sxs-lookup"><span data-stu-id="6a30a-130">Instance Constructors</span></span>](./instance-constructors.md)  
  
 [<span data-ttu-id="6a30a-131">Private Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="6a30a-131">Private Constructors</span></span>](./private-constructors.md)  
  
 [<span data-ttu-id="6a30a-132">Statische Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="6a30a-132">Static Constructors</span></span>](./static-constructors.md)  
  
 [<span data-ttu-id="6a30a-133">Schreiben eines Kopierkonstruktors</span><span class="sxs-lookup"><span data-stu-id="6a30a-133">How to write a copy constructor</span></span>](./how-to-write-a-copy-constructor.md)  
  
## <a name="see-also"></a><span data-ttu-id="6a30a-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6a30a-134">See also</span></span>

- [<span data-ttu-id="6a30a-135">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="6a30a-135">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="6a30a-136">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="6a30a-136">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="6a30a-137">Finalizer</span><span class="sxs-lookup"><span data-stu-id="6a30a-137">Finalizers</span></span>](./destructors.md)
- [<span data-ttu-id="6a30a-138">static</span><span class="sxs-lookup"><span data-stu-id="6a30a-138">static</span></span>](../../language-reference/keywords/static.md)
- [<span data-ttu-id="6a30a-139">Why Do Initializers Run In The Opposite Order As Constructors? Part One (Warum werden Initialisierer In der entgegengesetzten Reihenfolge ausgeführt wie Konstruktoren? Teil Eins)</span><span class="sxs-lookup"><span data-stu-id="6a30a-139">Why Do Initializers Run In The Opposite Order As Constructors? Part One</span></span>](https://docs.microsoft.com/archive/blogs/ericlippert/why-do-initializers-run-in-the-opposite-order-as-constructors-part-one)
