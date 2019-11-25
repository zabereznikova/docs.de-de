---
title: Konstruktoren – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 05/05/2017
helpviewer_keywords:
- constructors [C#]
- classes [C#], constructors
- C# language, constructors
ms.assetid: df2e2e9d-7998-418b-8e7d-890c17ff6c95
ms.openlocfilehash: 13597275460c075309b7457485a17655cf93f251
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971098"
---
# <a name="constructors-c-programming-guide"></a><span data-ttu-id="76cf5-102">Konstruktoren (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="76cf5-102">Constructors (C# Programming Guide)</span></span>

<span data-ttu-id="76cf5-103">Wenn eine [class](../../language-reference/keywords/class.md) oder [struct](../../language-reference/keywords/struct.md) erstellt wird, wird deren Konstruktor aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="76cf5-103">Whenever a [class](../../language-reference/keywords/class.md) or [struct](../../language-reference/keywords/struct.md) is created, its constructor is called.</span></span> <span data-ttu-id="76cf5-104">Eine Klasse oder Struktur verfügt möglicherweise über mehrere Konstruktoren, die andere Argumente verwenden.</span><span class="sxs-lookup"><span data-stu-id="76cf5-104">A class or struct may have multiple constructors that take different arguments.</span></span> <span data-ttu-id="76cf5-105">Mit Konstruktoren können Programmierer Standardwerte festlegen, Instanziierungen einschränken und Code schreiben, der flexibel und leicht zu lesen ist.</span><span class="sxs-lookup"><span data-stu-id="76cf5-105">Constructors enable the programmer to set default values, limit instantiation, and write code that is flexible and easy to read.</span></span> <span data-ttu-id="76cf5-106">Weitere Informationen und Beispiele finden Sie unter [Verwenden von Konstruktoren](./using-constructors.md) und [Instanzkonstruktoren](./instance-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="76cf5-106">For more information and examples, see [Using Constructors](./using-constructors.md) and [Instance Constructors](./instance-constructors.md).</span></span>  

## <a name="parameterless-constructors"></a><span data-ttu-id="76cf5-107">Parameterlose Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="76cf5-107">Parameterless constructors</span></span>
  
<span data-ttu-id="76cf5-108">Wenn Sie keinen Konstruktor für die Klasse angeben, erstellt C# standardmäßig einen, der das Objekt instanziiert und Membervariablen auf die Standardwerte festlegt, wie in der [Tabelle für Standardwerte](../../language-reference/keywords/default-values-table.md) aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="76cf5-108">If you don't provide a constructor for your class, C# creates one by default that instantiates the object and sets member variables to the default values as listed in the [Default Values Table](../../language-reference/keywords/default-values-table.md).</span></span> <span data-ttu-id="76cf5-109">Wenn Sie keinen Konstruktor für die Struktur angeben, stützt sich C# auf einen *impliziten parameterlosen Konstruktor*, um automatisch jedes Feld eines Werttyps auf seinen Standardwert zu initialisieren, wie in der [Tabelle für Standardwerte](../../language-reference/keywords/default-values-table.md) aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="76cf5-109">If you don't provide a constructor for your struct, C# relies on an *implicit parameterless constructor* to automatically initialize each field of a value type to its default value as listed in the [Default Values Table](../../language-reference/keywords/default-values-table.md).</span></span> <span data-ttu-id="76cf5-110">Weitere Informationen und Beispiele finden Sie unter [Instanzkonstruktoren](./instance-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="76cf5-110">For more information and examples, see [Instance Constructors](./instance-constructors.md).</span></span>  

## <a name="constructor-syntax"></a><span data-ttu-id="76cf5-111">Konstruktorsyntax</span><span class="sxs-lookup"><span data-stu-id="76cf5-111">Constructor syntax</span></span>

<span data-ttu-id="76cf5-112">Ein Konstruktor ist eine Methode, dessen Name derselbe ist wie der seines Typs.</span><span class="sxs-lookup"><span data-stu-id="76cf5-112">A constructor is a method whose name is the same as the name of its type.</span></span> <span data-ttu-id="76cf5-113">Die Methodensignatur enthält nur den Methodennamen und die Parameterliste; ein Rückgabetyp ist nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="76cf5-113">Its method signature includes only the method name and its parameter list; it does not include a return type.</span></span> <span data-ttu-id="76cf5-114">Im folgenden Beispiel wird der Konstruktor für eine Klasse mit dem Namen `Person` gezeigt.</span><span class="sxs-lookup"><span data-stu-id="76cf5-114">The following example shows the constructor for a class named `Person`.</span></span>

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#1)]  

<span data-ttu-id="76cf5-115">Wenn ein Konstruktor als einzelne Anweisung implementiert werden kann, können Sie eine [expression body definition (Ausdruckstextdefinition)](../statements-expressions-operators/expression-bodied-members.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="76cf5-115">If a constructor can be implemented as a single statement, you can use an [expression body definition](../statements-expressions-operators/expression-bodied-members.md).</span></span> <span data-ttu-id="76cf5-116">Im folgenden Beispiel wird eine `Location`-Klasse definiert, deren Klassenkonstruktor einen einzelnen Zeichenfolgenparameter namens *name* enthält.</span><span class="sxs-lookup"><span data-stu-id="76cf5-116">The following example defines a `Location` class whose constructor has a single string parameter named *name*.</span></span> <span data-ttu-id="76cf5-117">Die Ausdruckstextdefinition weist das Argument dem Feld `locationName` zu.</span><span class="sxs-lookup"><span data-stu-id="76cf5-117">The expression body definition assigns the argument to the `locationName` field.</span></span>

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

## <a name="static-constructors"></a><span data-ttu-id="76cf5-118">Statische Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="76cf5-118">Static constructors</span></span>

<span data-ttu-id="76cf5-119">Die vorherigen Beispiele haben alle Instanzkonstruktoren gezeigt, die ein neues Objekt erstellen.</span><span class="sxs-lookup"><span data-stu-id="76cf5-119">The previous examples have all shown instance constructors, which create a new object.</span></span> <span data-ttu-id="76cf5-120">Eine Klasse oder Struktur kann auch einen statischen Konstruktor haben, der statische Member dieses Typs initialisiert.</span><span class="sxs-lookup"><span data-stu-id="76cf5-120">A class or struct can also have a static constructor, which initializes static members of the type.</span></span>  <span data-ttu-id="76cf5-121">Statische Konstruktoren sind parameterlos.</span><span class="sxs-lookup"><span data-stu-id="76cf5-121">Static constructors are parameterless.</span></span> <span data-ttu-id="76cf5-122">Wenn Sie keinen statischen Konstruktor zum Initialisieren von statischen Feldern angeben, initialisiert der C#-Compiler statische Felder mit ihrem Standardwert, wie in der [Tabelle für Standardwerte](../../language-reference/keywords/default-values-table.md) aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="76cf5-122">If you don't provide a static constructor to initialize static fields, the C# compiler initializes static fields to their default value as listed in the [Default Values Table](../../language-reference/keywords/default-values-table.md).</span></span>

<span data-ttu-id="76cf5-123">Im folgenden Beispiel wird ein statischer Konstruktor verwendet, um ein statisches Feld zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="76cf5-123">The following example uses a static constructor to initialize a static field.</span></span>

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#2)]  

<span data-ttu-id="76cf5-124">Sie können einen statischen Konstruktor auch mit einer Ausdruckstextdefinition definieren, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="76cf5-124">You can also define a static constructor with an expression body definition, as the following example shows.</span></span> 

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#3)]  

<span data-ttu-id="76cf5-125">Weitere Informationen und Beispiele finden Sie unter [Statische Konstruktoren](./static-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="76cf5-125">For more information and examples, see [Static Constructors](./static-constructors.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="76cf5-126">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="76cf5-126">In This Section</span></span>  
 [<span data-ttu-id="76cf5-127">Verwenden von Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="76cf5-127">Using Constructors</span></span>](./using-constructors.md)  
  
 [<span data-ttu-id="76cf5-128">Instanzkonstruktoren</span><span class="sxs-lookup"><span data-stu-id="76cf5-128">Instance Constructors</span></span>](./instance-constructors.md)  
  
 [<span data-ttu-id="76cf5-129">Private Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="76cf5-129">Private Constructors</span></span>](./private-constructors.md)  
  
 [<span data-ttu-id="76cf5-130">Statische Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="76cf5-130">Static Constructors</span></span>](./static-constructors.md)  
  
 [<span data-ttu-id="76cf5-131">Schreiben eines Kopierkonstruktors</span><span class="sxs-lookup"><span data-stu-id="76cf5-131">How to write a copy constructor</span></span>](./how-to-write-a-copy-constructor.md)  
  
## <a name="see-also"></a><span data-ttu-id="76cf5-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="76cf5-132">See also</span></span>

- [<span data-ttu-id="76cf5-133">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="76cf5-133">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="76cf5-134">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="76cf5-134">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="76cf5-135">Finalizer</span><span class="sxs-lookup"><span data-stu-id="76cf5-135">Finalizers</span></span>](./destructors.md)
- [<span data-ttu-id="76cf5-136">static</span><span class="sxs-lookup"><span data-stu-id="76cf5-136">static</span></span>](../../language-reference/keywords/static.md)
- [<span data-ttu-id="76cf5-137">Why Do Initializers Run In The Opposite Order As Constructors? Part One (Warum werden Initialisierer In der entgegengesetzten Reihenfolge ausgeführt wie Konstruktoren? Teil Eins)</span><span class="sxs-lookup"><span data-stu-id="76cf5-137">Why Do Initializers Run In The Opposite Order As Constructors? Part One</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2008/02/15/why-do-initializers-run-in-the-opposite-order-as-constructors-part-one)
