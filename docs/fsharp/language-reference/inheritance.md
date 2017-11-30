---
title: Vererbung (F#)
description: "Informationen Sie zum f# vererbungsbeziehungen mit dem Schlüsselwort \"inherit\" angeben."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: b38ab2f6-7ba7-4839-8eff-e6bd6cfd2b2f
ms.openlocfilehash: 331c8f4e39aacd9d5e55bfbaf584f037e58d36a1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="inheritance"></a><span data-ttu-id="f1a28-104">Vererbung</span><span class="sxs-lookup"><span data-stu-id="f1a28-104">Inheritance</span></span>

<span data-ttu-id="f1a28-105">Die Vererbung wird verwendet, um die Beziehung "ist-a" zu modellieren oder Untertypen, bei der objektorientierten Programmierung.</span><span class="sxs-lookup"><span data-stu-id="f1a28-105">Inheritance is used to model the "is-a" relationship, or subtyping, in object-oriented programming.</span></span>


## <a name="specifying-inheritance-relationships"></a><span data-ttu-id="f1a28-106">Vererbungsbeziehungen angeben</span><span class="sxs-lookup"><span data-stu-id="f1a28-106">Specifying Inheritance Relationships</span></span>
<span data-ttu-id="f1a28-107">Geben Sie vererbungsbeziehungen mithilfe der `inherit` Schlüsselwort in einer Klassendeklaration.</span><span class="sxs-lookup"><span data-stu-id="f1a28-107">You specify inheritance relationships by using the `inherit` keyword in a class declaration.</span></span> <span data-ttu-id="f1a28-108">Im folgenden Beispiel wird die grundlegende syntaktische Form angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f1a28-108">The basic syntactical form is shown in the following example.</span></span>

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

<span data-ttu-id="f1a28-109">Eine Klasse kann höchstens eine direkte Basisklasse haben.</span><span class="sxs-lookup"><span data-stu-id="f1a28-109">A class can have at most one direct base class.</span></span> <span data-ttu-id="f1a28-110">Wenn Sie eine Basisklasse keinen mithilfe angeben der `inherit` -Schlüsselwort, die Klasse erbt implizit von `System.Object`.</span><span class="sxs-lookup"><span data-stu-id="f1a28-110">If you do not specify a base class by using the `inherit` keyword, the class implicitly inherits from `System.Object`.</span></span>


## <a name="inherited-members"></a><span data-ttu-id="f1a28-111">Geerbte Member</span><span class="sxs-lookup"><span data-stu-id="f1a28-111">Inherited Members</span></span>
<span data-ttu-id="f1a28-112">Wenn eine Klasse von einer anderen Klasse erbt, sind die Methoden und Member der Basisklasse für Benutzer der abgeleiteten Klasse verfügbar, als wären sie direkte Member der abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="f1a28-112">If a class inherits from another class, the methods and members of the base class are available to users of the derived class as if they were direct members of the derived class.</span></span>

<span data-ttu-id="f1a28-113">Alle let-Bindungen und Konstruktorparameter auf eine Klasse privat sind und daher können nicht von abgeleiteten Klassen zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="f1a28-113">Any let bindings and constructor parameters are private to a class and, therefore, cannot be accessed from derived classes.</span></span>

<span data-ttu-id="f1a28-114">Das Schlüsselwort `base` steht in abgeleiteten Klassen und bezieht sich auf die Instanz der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="f1a28-114">The keyword `base` is available in derived classes and refers to the base class instance.</span></span> <span data-ttu-id="f1a28-115">Es wird wie der Selbstbezeichner verwendet.</span><span class="sxs-lookup"><span data-stu-id="f1a28-115">It is used like the self-identifier.</span></span>


## <a name="virtual-methods-and-overrides"></a><span data-ttu-id="f1a28-116">Virtuelle Methoden und Außerkraftsetzungen anpassen</span><span class="sxs-lookup"><span data-stu-id="f1a28-116">Virtual Methods and Overrides</span></span>
<span data-ttu-id="f1a28-117">Virtuelle Methoden (und Eigenschaften) funktioniert etwas anders in F#-im Vergleich zu anderen.</span><span class="sxs-lookup"><span data-stu-id="f1a28-117">Virtual methods (and properties) work somewhat differently in F# as compared to other .NET languages.</span></span> <span data-ttu-id="f1a28-118">Um einen neuen virtuellen Member zu deklarieren, verwenden Sie die `abstract` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="f1a28-118">To declare a new virtual member, you use the `abstract` keyword.</span></span> <span data-ttu-id="f1a28-119">Dies geschieht unabhängig davon, ob Sie eine standardmäßige Implementierung dieser Methode bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f1a28-119">You do this regardless of whether you provide a default implementation for that method.</span></span> <span data-ttu-id="f1a28-120">Eine vollständige Definition einer virtuellen Methode in einer Basisklasse folgt daher diesem Muster:</span><span class="sxs-lookup"><span data-stu-id="f1a28-120">Thus a complete definition of a virtual method in a base class follows this pattern:</span></span>

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="f1a28-121">Und in einer abgeleiteten Klasse eine Überschreibung der virtuellen Methode folgt diesem Muster:</span><span class="sxs-lookup"><span data-stu-id="f1a28-121">And in a derived class, an override of this virtual method follows this pattern:</span></span>

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="f1a28-122">Wenn Sie die standardmäßige Implementierung in der Basisklasse weglassen, wird die Basisklasse eine abstrakte Klasse.</span><span class="sxs-lookup"><span data-stu-id="f1a28-122">If you omit the default implementation in the base class, the base class becomes an abstract class.</span></span>

<span data-ttu-id="f1a28-123">Das folgende Codebeispiel veranschaulicht die Deklaration einer neuen virtuellen Methode `function1` in einer Basisklasse und wie Sie es in einer abgeleiteten Klasse überschreiben.</span><span class="sxs-lookup"><span data-stu-id="f1a28-123">The following code example illustrates the declaration of a new virtual method `function1` in a base class and how to override it in a derived class.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]
    
## <a name="constructors-and-inheritance"></a><span data-ttu-id="f1a28-124">Konstruktoren und Vererbung</span><span class="sxs-lookup"><span data-stu-id="f1a28-124">Constructors and Inheritance</span></span>
<span data-ttu-id="f1a28-125">Der Konstruktor für die Basisklasse muss in der abgeleiteten Klasse aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f1a28-125">The constructor for the base class must be called in the derived class.</span></span> <span data-ttu-id="f1a28-126">Die Argumente für den Konstruktor der Basisklasse angezeigt, in der Argumentliste der `inherit` Klausel.</span><span class="sxs-lookup"><span data-stu-id="f1a28-126">The arguments for the base class constructor appear in the argument list in the `inherit` clause.</span></span> <span data-ttu-id="f1a28-127">Die Werte, die verwendet werden, müssen aus Argumente, die dem abgeleiteten Klassenkonstruktor ermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="f1a28-127">The values that are used must be determined from the arguments supplied to the derived class constructor.</span></span>

<span data-ttu-id="f1a28-128">Der folgende Code zeigt eine Basisklasse und eine abgeleitete Klasse, wenn die abgeleitete Klasse den Basisklassenkonstruktor in der erben-Klausel aufruft:</span><span class="sxs-lookup"><span data-stu-id="f1a28-128">The following code shows a base class and a derived class, where the derived class calls the base class constructor in the inherit clause:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

<span data-ttu-id="f1a28-129">Im Fall von mehreren Konstruktoren kann der folgende Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f1a28-129">In the case of multiple constructors, the following code can be used.</span></span> <span data-ttu-id="f1a28-130">Die erste Zeile der abgeleiteten Klassenkonstruktoren wird der `inherit` -Klausel und die Felder werden als explizite Felder, die mit deklariert werden die `val` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="f1a28-130">The first line of the derived class constructors is the `inherit` clause, and the fields appear as explicit fields that are declared with the `val` keyword.</span></span> <span data-ttu-id="f1a28-131">Weitere Informationen finden Sie unter [explizite Felder: das `val` Schlüsselwort](members/explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="f1a28-131">For more information, see [Explicit Fields: The `val` Keyword](members/explicit-fields-the-val-keyword.md).</span></span>

```fsharp
type BaseClass =
    val string1 : string
    new (str) = { string1 = str }
    new () = { string1 = "" }

type DerivedClass =
    inherit BaseClass

    val string2 : string
    new (str1, str2) = { inherit BaseClass(str1); string2 = str2 }
    new (str2) = { inherit BaseClass(); string2 = str2 }

let obj1 = DerivedClass("A", "B")
let obj2 = DerivedClass("A")
```

## <a name="alternatives-to-inheritance"></a><span data-ttu-id="f1a28-132">Alternativen zur Vererbung</span><span class="sxs-lookup"><span data-stu-id="f1a28-132">Alternatives to Inheritance</span></span>
<span data-ttu-id="f1a28-133">In Fällen, in denen eine kleinere Änderung eines Typs erforderlich ist, sollten Sie in Erwägung ziehen, ein Objektausdrücke als Alternative zur Vererbung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f1a28-133">In cases where a minor modification of a type is required, consider using an object expression as an alternative to inheritance.</span></span> <span data-ttu-id="f1a28-134">Das folgende Beispiel veranschaulicht die Verwendung eines Ausdrucks Objekt als Alternative zum Erstellen eines neuen abgeleiteten Typs:</span><span class="sxs-lookup"><span data-stu-id="f1a28-134">The following example illustrates the use of an object expression as an alternative to creating a new derived type:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

<span data-ttu-id="f1a28-135">Weitere Informationen zu Objektausdrücke, finden Sie unter [Objektausdrücke](object-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="f1a28-135">For more information about object expressions, see [Object Expressions](object-expressions.md).</span></span>

<span data-ttu-id="f1a28-136">Wenn Sie Objekthierarchien erstellen, erwägen Sie, die eine Unterscheidungs-Union anstelle der Vererbung.</span><span class="sxs-lookup"><span data-stu-id="f1a28-136">When you are creating object hierarchies, consider using a discriminated union instead of inheritance.</span></span> <span data-ttu-id="f1a28-137">Unterscheidungs-Unions können auch verschiedene Modellverhalten unterschiedlichen Objekten, die einen gemeinsamen allgemeinen Typ aufweisen.</span><span class="sxs-lookup"><span data-stu-id="f1a28-137">Discriminated unions can also model varied behavior of different objects that share a common overall type.</span></span> <span data-ttu-id="f1a28-138">Eine einzelne Unterscheidungs-Union kann häufig nicht erforderlich für eine Reihe von abgeleiteten Klassen aus, die geringfügige Unterschiede voneinander sind.</span><span class="sxs-lookup"><span data-stu-id="f1a28-138">A single discriminated union can often eliminate the need for a number of derived classes that are minor variations of each other.</span></span> <span data-ttu-id="f1a28-139">Informationen zu Unterscheidungs-Unions finden Sie unter [Unterscheidungs-Unions](discriminated-unions.md).</span><span class="sxs-lookup"><span data-stu-id="f1a28-139">For information about discriminated unions, see [Discriminated Unions](discriminated-unions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="f1a28-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f1a28-140">See Also</span></span>
[<span data-ttu-id="f1a28-141">Objektausdrücke</span><span class="sxs-lookup"><span data-stu-id="f1a28-141">Object Expressions</span></span>](object-expressions.md)

[<span data-ttu-id="f1a28-142">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="f1a28-142">F# Language Reference</span></span>](index.md)
