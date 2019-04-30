---
title: Vererbung
description: Erfahren Sie, wie an F# vererbungsbeziehungen, die mit dem Schlüsselwort "inherit".
ms.date: 05/16/2016
ms.openlocfilehash: 775ee52039caf4c4ab65f82fa21d4e536135a12a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937461"
---
# <a name="inheritance"></a><span data-ttu-id="47f13-103">Vererbung</span><span class="sxs-lookup"><span data-stu-id="47f13-103">Inheritance</span></span>

<span data-ttu-id="47f13-104">Vererbung wird verwendet, um die Beziehung "ist-ein" zu modellieren oder von Untertypen in der objektorientierten Programmierung.</span><span class="sxs-lookup"><span data-stu-id="47f13-104">Inheritance is used to model the "is-a" relationship, or subtyping, in object-oriented programming.</span></span>

## <a name="specifying-inheritance-relationships"></a><span data-ttu-id="47f13-105">Angeben von Vererbungsbeziehungen</span><span class="sxs-lookup"><span data-stu-id="47f13-105">Specifying Inheritance Relationships</span></span>

<span data-ttu-id="47f13-106">Geben Sie vererbungsbeziehungen mithilfe der `inherit` Schlüsselwort in einer Klassendeklaration.</span><span class="sxs-lookup"><span data-stu-id="47f13-106">You specify inheritance relationships by using the `inherit` keyword in a class declaration.</span></span> <span data-ttu-id="47f13-107">Im folgenden Beispiel wird die grundlegende syntaktische Form angezeigt.</span><span class="sxs-lookup"><span data-stu-id="47f13-107">The basic syntactical form is shown in the following example.</span></span>

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

<span data-ttu-id="47f13-108">Eine Klasse kann höchstens eine direkte Basisklasse verfügen.</span><span class="sxs-lookup"><span data-stu-id="47f13-108">A class can have at most one direct base class.</span></span> <span data-ttu-id="47f13-109">Wenn Sie keine Basisklasse mithilfe von angeben der `inherit` Schlüsselworts die Klasse erbt implizit von `System.Object`.</span><span class="sxs-lookup"><span data-stu-id="47f13-109">If you do not specify a base class by using the `inherit` keyword, the class implicitly inherits from `System.Object`.</span></span>

## <a name="inherited-members"></a><span data-ttu-id="47f13-110">Vererbte Member</span><span class="sxs-lookup"><span data-stu-id="47f13-110">Inherited Members</span></span>

<span data-ttu-id="47f13-111">Wenn eine Klasse von einer anderen Klasse erbt, sind die Methoden und Member der Basisklasse für Benutzer der abgeleiteten Klasse verfügbar, als wären sie direkte Member der abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="47f13-111">If a class inherits from another class, the methods and members of the base class are available to users of the derived class as if they were direct members of the derived class.</span></span>

<span data-ttu-id="47f13-112">Eine let-Bindungen und Konstruktorparameter auf eine Klasse privat sind und aus diesem Grund können nicht von abgeleiteten Klassen zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="47f13-112">Any let bindings and constructor parameters are private to a class and, therefore, cannot be accessed from derived classes.</span></span>

<span data-ttu-id="47f13-113">Das Schlüsselwort `base` steht in abgeleiteten Klassen aus, und verweist auf die Instanz der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="47f13-113">The keyword `base` is available in derived classes and refers to the base class instance.</span></span> <span data-ttu-id="47f13-114">Es wird wie der Selbstbezeichner verwendet.</span><span class="sxs-lookup"><span data-stu-id="47f13-114">It is used like the self-identifier.</span></span>

## <a name="virtual-methods-and-overrides"></a><span data-ttu-id="47f13-115">Virtuelle Methoden und Außerkraftsetzungen</span><span class="sxs-lookup"><span data-stu-id="47f13-115">Virtual Methods and Overrides</span></span>

<span data-ttu-id="47f13-116">Virtuelle Methoden (und Eigenschaften) funktioniert etwas anders darüber F# im Vergleich zu anderen.</span><span class="sxs-lookup"><span data-stu-id="47f13-116">Virtual methods (and properties) work somewhat differently in F# as compared to other .NET languages.</span></span> <span data-ttu-id="47f13-117">Um ein neuer virtueller Member zu deklarieren, verwenden Sie die `abstract` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="47f13-117">To declare a new virtual member, you use the `abstract` keyword.</span></span> <span data-ttu-id="47f13-118">Dies geschieht unabhängig davon, ob Sie eine Standardimplementierung für diese Methode bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="47f13-118">You do this regardless of whether you provide a default implementation for that method.</span></span> <span data-ttu-id="47f13-119">Eine vollständige Definition der eine virtuelle Methode in einer Basisklasse folgt daher diesem Muster:</span><span class="sxs-lookup"><span data-stu-id="47f13-119">Thus a complete definition of a virtual method in a base class follows this pattern:</span></span>

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="47f13-120">Und in einer abgeleiteten Klasse eine Überschreibung der virtuellen Methode folgt diesem Muster:</span><span class="sxs-lookup"><span data-stu-id="47f13-120">And in a derived class, an override of this virtual method follows this pattern:</span></span>

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="47f13-121">Wenn Sie die standardmäßige Implementierung in der Basisklasse auslassen, wird die Basisklasse eine abstrakte Klasse.</span><span class="sxs-lookup"><span data-stu-id="47f13-121">If you omit the default implementation in the base class, the base class becomes an abstract class.</span></span>

<span data-ttu-id="47f13-122">Das folgende Codebeispiel veranschaulicht die Deklaration einer neuen virtuellen Methode `function1` in einer Basisklasse und wie es in einer abgeleiteten Klasse überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="47f13-122">The following code example illustrates the declaration of a new virtual method `function1` in a base class and how to override it in a derived class.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]

## <a name="constructors-and-inheritance"></a><span data-ttu-id="47f13-123">Konstruktoren und Vererbung</span><span class="sxs-lookup"><span data-stu-id="47f13-123">Constructors and Inheritance</span></span>

<span data-ttu-id="47f13-124">Der Konstruktor der Basisklasse muss in der abgeleiteten Klasse aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="47f13-124">The constructor for the base class must be called in the derived class.</span></span> <span data-ttu-id="47f13-125">Die Argumente für den Konstruktor der Basisklasse angezeigt, in der Argumentliste in die `inherit` Klausel.</span><span class="sxs-lookup"><span data-stu-id="47f13-125">The arguments for the base class constructor appear in the argument list in the `inherit` clause.</span></span> <span data-ttu-id="47f13-126">Die Werte, die verwendet werden, müssen aus Argumente, die dem abgeleiteten Klassenkonstruktor ermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="47f13-126">The values that are used must be determined from the arguments supplied to the derived class constructor.</span></span>

<span data-ttu-id="47f13-127">Der folgende Code zeigt eine Basisklasse und einer abgeleiteten Klasse, in denen die abgeleitete Klasse den Basisklassenkonstruktor in der Klausel erben aufruft:</span><span class="sxs-lookup"><span data-stu-id="47f13-127">The following code shows a base class and a derived class, where the derived class calls the base class constructor in the inherit clause:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

<span data-ttu-id="47f13-128">Im Fall von mehreren Konstruktoren kann der folgende Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="47f13-128">In the case of multiple constructors, the following code can be used.</span></span> <span data-ttu-id="47f13-129">Die erste Zeile der abgeleiteten Klassenkonstruktoren ist die `inherit` -Klausel und die Felder angezeigt als explizite Felder, die mit deklariert werden die `val` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="47f13-129">The first line of the derived class constructors is the `inherit` clause, and the fields appear as explicit fields that are declared with the `val` keyword.</span></span> <span data-ttu-id="47f13-130">Weitere Informationen finden Sie unter [explizite Felder: Die `val` Schlüsselwort](members/explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="47f13-130">For more information, see [Explicit Fields: The `val` Keyword](members/explicit-fields-the-val-keyword.md).</span></span>

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

## <a name="alternatives-to-inheritance"></a><span data-ttu-id="47f13-131">Alternativen zur Vererbung</span><span class="sxs-lookup"><span data-stu-id="47f13-131">Alternatives to Inheritance</span></span>

<span data-ttu-id="47f13-132">In Fällen, in denen eine geringfügige Änderung eines Typs erforderlich ist, sollten Sie in Erwägung ziehen, einen Object-Ausdruck als Alternative zur Vererbung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="47f13-132">In cases where a minor modification of a type is required, consider using an object expression as an alternative to inheritance.</span></span> <span data-ttu-id="47f13-133">Das folgende Beispiel veranschaulicht die Verwendung von Objektausdruck als Alternative zum Erstellen eines neuen abgeleiteten Typs:</span><span class="sxs-lookup"><span data-stu-id="47f13-133">The following example illustrates the use of an object expression as an alternative to creating a new derived type:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

<span data-ttu-id="47f13-134">Weitere Informationen zu Object-Ausdrücke, finden Sie unter [Objektausdrücke](object-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="47f13-134">For more information about object expressions, see [Object Expressions](object-expressions.md).</span></span>

<span data-ttu-id="47f13-135">Wenn Sie Objekthierarchien erstellen, erwägen Sie, die eine Unterscheidungs-Union anstelle von Vererbung.</span><span class="sxs-lookup"><span data-stu-id="47f13-135">When you are creating object hierarchies, consider using a discriminated union instead of inheritance.</span></span> <span data-ttu-id="47f13-136">Unterscheidungs-Unions können auch verschiedene Modellverhalten unterschiedlicher Objekte, die einen gemeinsamen allgemeinen Typ gemeinsam nutzen.</span><span class="sxs-lookup"><span data-stu-id="47f13-136">Discriminated unions can also model varied behavior of different objects that share a common overall type.</span></span> <span data-ttu-id="47f13-137">Eine einzelne Unterscheidungs-Union kann häufig nicht erforderlich für eine Reihe von abgeleiteten Klassen, die geringfügige Unterschiede voneinander sind.</span><span class="sxs-lookup"><span data-stu-id="47f13-137">A single discriminated union can often eliminate the need for a number of derived classes that are minor variations of each other.</span></span> <span data-ttu-id="47f13-138">Weitere Informationen zu Unterscheidungs-Unions, finden Sie unter [Unterscheidungs-Unions](discriminated-unions.md).</span><span class="sxs-lookup"><span data-stu-id="47f13-138">For information about discriminated unions, see [Discriminated Unions](discriminated-unions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="47f13-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47f13-139">See also</span></span>

- [<span data-ttu-id="47f13-140">Objektausdrücke</span><span class="sxs-lookup"><span data-stu-id="47f13-140">Object Expressions</span></span>](object-expressions.md)
- [<span data-ttu-id="47f13-141">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="47f13-141">F# Language Reference</span></span>](index.md)