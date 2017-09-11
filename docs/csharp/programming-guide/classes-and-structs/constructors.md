---
title: Konstruktoren (C#-Programmierhandbuch)
ms.date: 2017-05-05
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- constructors [C#]
- classes [C#], constructors
- C# language, constructors
ms.assetid: df2e2e9d-7998-418b-8e7d-890c17ff6c95
caps.latest.revision: 23
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 400afcda2fe30bf0e3621ee4c4247486e01d3ee4
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="constructors-c-programming-guide"></a><span data-ttu-id="837b0-102">Konstruktoren (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="837b0-102">Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="837b0-103">Wenn eine [class](../../../csharp/language-reference/keywords/class.md) oder [struct](../../../csharp/language-reference/keywords/struct.md) erstellt wird, wird deren Konstruktor aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="837b0-103">Whenever a [class](../../../csharp/language-reference/keywords/class.md) or [struct](../../../csharp/language-reference/keywords/struct.md) is created, its constructor is called.</span></span> <span data-ttu-id="837b0-104">Eine Klasse oder Struktur verfügt möglicherweise über mehrere Konstruktoren, die andere Argumente verwenden.</span><span class="sxs-lookup"><span data-stu-id="837b0-104">A class or struct may have multiple constructors that take different arguments.</span></span> <span data-ttu-id="837b0-105">Mit Konstruktoren können Programmierer Standardwerte festlegen, Instanziierungen einschränken und Code schreiben, der flexibel und leicht zu lesen ist.</span><span class="sxs-lookup"><span data-stu-id="837b0-105">Constructors enable the programmer to set default values, limit instantiation, and write code that is flexible and easy to read.</span></span> <span data-ttu-id="837b0-106">Weitere Informationen und Beispiele finden Sie unter [Verwenden von Konstruktoren](../../../csharp/programming-guide/classes-and-structs/using-constructors.md) und [Instanzkonstruktoren](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="837b0-106">For more information and examples, see [Using Constructors](../../../csharp/programming-guide/classes-and-structs/using-constructors.md) and [Instance Constructors](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span></span>  

## <a name="default-constructors"></a><span data-ttu-id="837b0-107">Standardkonstruktoren</span><span class="sxs-lookup"><span data-stu-id="837b0-107">Default constructors</span></span>
  
<span data-ttu-id="837b0-108">Wenn Sie keinen Konstruktor für die Klasse angeben, erstellt C# standardmäßig einen, der das Objekt instanziiert und Membervariablen auf die Standardwerte festlegt, wie in der [Tabelle für Standardwerte](../../../csharp/language-reference/keywords/default-values-table.md) aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="837b0-108">If you don't provide a constructor for your class, C# creates one by default that instantiates the object and sets member variables to the default values as listed in the [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span> <span data-ttu-id="837b0-109">Wenn Sie keinen Konstruktor für die Struktur angeben, stützt sich C# auf einen *impliziten Standardkonstruktor*, um automatisch jedes Feld eines Werttyps auf seinen Standardwert zu initialisieren, wie in der [Tabelle für Standardwerte](../../../csharp/language-reference/keywords/default-values-table.md) aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="837b0-109">If you don't provide a constructor for your struct, C# relies on an *implicit default constructor* to automatically initialize each field of a value type to its default value as listed in the [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span> <span data-ttu-id="837b0-110">Weitere Informationen und Beispiele finden Sie unter [Instanzkonstruktoren](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="837b0-110">For more information and examples, see [Instance Constructors](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span></span>  

## <a name="constructor-syntax"></a><span data-ttu-id="837b0-111">Konstruktorsyntax</span><span class="sxs-lookup"><span data-stu-id="837b0-111">Constructor syntax</span></span>

<span data-ttu-id="837b0-112">Ein Konstruktor ist eine Methode, dessen Name derselbe ist wie der seines Typs.</span><span class="sxs-lookup"><span data-stu-id="837b0-112">A constructor is a method whose name is the same as the name of its type.</span></span> <span data-ttu-id="837b0-113">Die Methodensignatur enthält nur den Methodennamen und die Parameterliste; ein Rückgabetyp ist nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="837b0-113">Its method signature includes only the method name and its parameter list; it does not include a return type.</span></span> <span data-ttu-id="837b0-114">Im folgenden Beispiel wird der Konstruktor für eine Klasse mit dem Namen `Person` gezeigt.</span><span class="sxs-lookup"><span data-stu-id="837b0-114">The following example shows the constructor for a class named `Person`.</span></span>

<span data-ttu-id="837b0-115">[!code-cs[Konstruktoren](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="837b0-115">[!code-cs[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#1)]</span></span>  

<span data-ttu-id="837b0-116">Wenn ein Konstruktor als einzelne Anweisung implementiert werden kann, können Sie eine [expression body definition (Ausdruckstextdefinition)](../statements-expressions-operators/expression-bodied-members.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="837b0-116">If a constructor can be implemented as a single statement, you can use an [expression body definition](../statements-expressions-operators/expression-bodied-members.md).</span></span> <span data-ttu-id="837b0-117">Im folgenden Beispiel wird eine `Location`-Klasse definiert, deren Klassenkonstruktor einen einzelnen Zeichenfolgenparameter namens *name* enthält.</span><span class="sxs-lookup"><span data-stu-id="837b0-117">The following example defines a `Location` class whose constructor has a single string parameter named *name*.</span></span> <span data-ttu-id="837b0-118">Die Ausdruckstextdefinition weist das Argument dem Feld `locationName` zu.</span><span class="sxs-lookup"><span data-stu-id="837b0-118">The expression body definition assigns the argument to the `locationName` field.</span></span>

<span data-ttu-id="837b0-119">[!code-cs[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="837b0-119">[!code-cs[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]</span></span>  

## <a name="static-constructors"></a><span data-ttu-id="837b0-120">Statische Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="837b0-120">Static constructors</span></span>

<span data-ttu-id="837b0-121">Die vorherigen Beispiele haben alle Instanzkonstruktoren gezeigt, die ein neues Objekt erstellen.</span><span class="sxs-lookup"><span data-stu-id="837b0-121">The previous examples have all shown instance constructors, which create a new object.</span></span> <span data-ttu-id="837b0-122">Eine Klasse oder Struktur kann auch einen statischen Konstruktor haben, der statische Member dieses Typs initialisiert.</span><span class="sxs-lookup"><span data-stu-id="837b0-122">A class or struct can also have a static constructor, which initializes static members of the type.</span></span>  <span data-ttu-id="837b0-123">Statische Konstruktoren sind parameterlos.</span><span class="sxs-lookup"><span data-stu-id="837b0-123">Static constructors are parameterless.</span></span> <span data-ttu-id="837b0-124">Wenn Sie keinen statischen Konstruktor zum Initialisieren von statischen Feldern angeben, wird der C#-Compiler einen statischen Standardkonstruktor bereitstellen, der statische Felder auf ihren Standardwert initialisiert, wie in der [Tabelle für Standardwerte](../../../csharp/language-reference/keywords/default-values-table.md) aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="837b0-124">If you don't provide a static constructor to initialize static fields, the C# compiler will supply a default static constructor that initializes static fields to their default value as listed in the [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span> 

<span data-ttu-id="837b0-125">Im folgenden Beispiel wird ein statischer Konstruktor verwendet, um ein statisches Feld zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="837b0-125">The following example uses a static constructor to initialize a static field.</span></span>

<span data-ttu-id="837b0-126">[!code-cs[Konstruktoren](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#2)]</span><span class="sxs-lookup"><span data-stu-id="837b0-126">[!code-cs[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#2)]</span></span>  

<span data-ttu-id="837b0-127">Sie können einen statischen Konstruktor auch mit einer Ausdruckstextdefinition definieren, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="837b0-127">You can also define a static constructor with an expression body definition, as the following example shows.</span></span> 

<span data-ttu-id="837b0-128">[!code-cs[Konstruktoren](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#3)]</span><span class="sxs-lookup"><span data-stu-id="837b0-128">[!code-cs[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#3)]</span></span>  

<span data-ttu-id="837b0-129">Weitere Informationen und Beispiele finden Sie unter [Statische Konstruktoren](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="837b0-129">For more information and examples, see [Static Constructors](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="837b0-130">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="837b0-130">In This Section</span></span>  
 [<span data-ttu-id="837b0-131">Verwenden von Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="837b0-131">Using Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)  
  
 [<span data-ttu-id="837b0-132">Instanzkonstruktoren</span><span class="sxs-lookup"><span data-stu-id="837b0-132">Instance Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)  
  
 [<span data-ttu-id="837b0-133">Private Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="837b0-133">Private Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/private-constructors.md)  
  
 [<span data-ttu-id="837b0-134">Statische Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="837b0-134">Static Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)  
  
 [<span data-ttu-id="837b0-135">Gewusst wie: Schreiben eines Kopierkonstruktors</span><span class="sxs-lookup"><span data-stu-id="837b0-135">How to: Write a Copy Constructor</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-write-a-copy-constructor.md)  
  
## <a name="see-also"></a><span data-ttu-id="837b0-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="837b0-136">See Also</span></span>  
 <span data-ttu-id="837b0-137">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="837b0-137">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="837b0-138">[Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="837b0-138">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="837b0-139">[Finalizer](../../../csharp/programming-guide/classes-and-structs/destructors.md) </span><span class="sxs-lookup"><span data-stu-id="837b0-139">[Finalizers](../../../csharp/programming-guide/classes-and-structs/destructors.md) </span></span>  
 <span data-ttu-id="837b0-140">[static](../../../csharp/language-reference/keywords/static.md) </span><span class="sxs-lookup"><span data-stu-id="837b0-140">[static](../../../csharp/language-reference/keywords/static.md) </span></span>  
 [<span data-ttu-id="837b0-141">Why Do Initializers Run In The Opposite Order As Constructors? Part One (Warum werden Initialisierer In der entgegengesetzten Reihenfolge ausgeführt wie Konstruktoren? Teil Eins)</span><span class="sxs-lookup"><span data-stu-id="837b0-141">Why Do Initializers Run In The Opposite Order As Constructors? Part One</span></span>](http://go.microsoft.com/fwlink/?LinkId=112374)

