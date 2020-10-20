---
title: Vererbung
description: "Erfahren Sie, wie Sie F #-Vererbungs Beziehungen mithilfe des Schlüssel Worts ' erben ' angeben."
ms.date: 05/16/2016
ms.openlocfilehash: 5ab891a93528427a66e4eb8f7bfeccbf6e4d2c7e
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2020
ms.locfileid: "92223848"
---
# <a name="inheritance"></a><span data-ttu-id="52ce0-103">Vererbung</span><span class="sxs-lookup"><span data-stu-id="52ce0-103">Inheritance</span></span>

<span data-ttu-id="52ce0-104">Vererbung wird verwendet, um die "is-a"-Beziehung oder die unter Typisierung in der objektorientierten Programmierung zu modellieren.</span><span class="sxs-lookup"><span data-stu-id="52ce0-104">Inheritance is used to model the "is-a" relationship, or subtyping, in object-oriented programming.</span></span>

## <a name="specifying-inheritance-relationships"></a><span data-ttu-id="52ce0-105">Angeben von Vererbungs Beziehungen</span><span class="sxs-lookup"><span data-stu-id="52ce0-105">Specifying Inheritance Relationships</span></span>

<span data-ttu-id="52ce0-106">Sie geben Vererbungs Beziehungen mithilfe des- `inherit` Schlüssel Worts in einer Klassen Deklaration an.</span><span class="sxs-lookup"><span data-stu-id="52ce0-106">You specify inheritance relationships by using the `inherit` keyword in a class declaration.</span></span> <span data-ttu-id="52ce0-107">Das grundlegende syntaktische Formular wird im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="52ce0-107">The basic syntactical form is shown in the following example.</span></span>

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

<span data-ttu-id="52ce0-108">Eine Klasse kann höchstens über eine direkte Basisklasse verfügen.</span><span class="sxs-lookup"><span data-stu-id="52ce0-108">A class can have at most one direct base class.</span></span> <span data-ttu-id="52ce0-109">Wenn Sie mit dem-Schlüsselwort keine Basisklasse angeben `inherit` , erbt die-Klasse implizit von `System.Object` .</span><span class="sxs-lookup"><span data-stu-id="52ce0-109">If you do not specify a base class by using the `inherit` keyword, the class implicitly inherits from `System.Object`.</span></span>

## <a name="inherited-members"></a><span data-ttu-id="52ce0-110">Geerbte Elemente</span><span class="sxs-lookup"><span data-stu-id="52ce0-110">Inherited Members</span></span>

<span data-ttu-id="52ce0-111">Wenn eine Klasse von einer anderen Klasse erbt, sind die Methoden und Member der Basisklasse für Benutzer der abgeleiteten Klasse so verfügbar, als wären Sie direkte Member der abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="52ce0-111">If a class inherits from another class, the methods and members of the base class are available to users of the derived class as if they were direct members of the derived class.</span></span>

<span data-ttu-id="52ce0-112">Alle let-Bindungen und Konstruktorparameter sind in einer Klasse privat und können daher nicht von abgeleiteten Klassen aus aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="52ce0-112">Any let bindings and constructor parameters are private to a class and, therefore, cannot be accessed from derived classes.</span></span>

<span data-ttu-id="52ce0-113">Das Schlüsselwort `base` ist in abgeleiteten Klassen verfügbar und verweist auf die Instanz der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="52ce0-113">The keyword `base` is available in derived classes and refers to the base class instance.</span></span> <span data-ttu-id="52ce0-114">Es wird wie der selbst Bezeichner verwendet.</span><span class="sxs-lookup"><span data-stu-id="52ce0-114">It is used like the self-identifier.</span></span>

## <a name="virtual-methods-and-overrides"></a><span data-ttu-id="52ce0-115">Virtuelle Methoden und über schreibungen</span><span class="sxs-lookup"><span data-stu-id="52ce0-115">Virtual Methods and Overrides</span></span>

<span data-ttu-id="52ce0-116">Virtuelle Methoden (und Eigenschaften) funktionieren in F # in Bezug auf andere .NET-Sprachen etwas anders.</span><span class="sxs-lookup"><span data-stu-id="52ce0-116">Virtual methods (and properties) work somewhat differently in F# as compared to other .NET languages.</span></span> <span data-ttu-id="52ce0-117">Um einen neuen virtuellen Member zu deklarieren, verwenden Sie das- `abstract` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="52ce0-117">To declare a new virtual member, you use the `abstract` keyword.</span></span> <span data-ttu-id="52ce0-118">Dies geschieht unabhängig davon, ob Sie eine Standard Implementierung für diese Methode bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="52ce0-118">You do this regardless of whether you provide a default implementation for that method.</span></span> <span data-ttu-id="52ce0-119">Daher folgt eine komplette Definition einer virtuellen Methode in einer Basisklasse diesem Muster:</span><span class="sxs-lookup"><span data-stu-id="52ce0-119">Thus a complete definition of a virtual method in a base class follows this pattern:</span></span>

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="52ce0-120">Und in einer abgeleiteten Klasse folgt eine außer Kraft setzung dieser virtuellen Methode diesem Muster:</span><span class="sxs-lookup"><span data-stu-id="52ce0-120">And in a derived class, an override of this virtual method follows this pattern:</span></span>

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="52ce0-121">Wenn Sie die Standard Implementierung in der Basisklasse weglassen, wird die Basisklasse zu einer abstrakten Klasse.</span><span class="sxs-lookup"><span data-stu-id="52ce0-121">If you omit the default implementation in the base class, the base class becomes an abstract class.</span></span>

<span data-ttu-id="52ce0-122">Im folgenden Codebeispiel wird die Deklaration einer neuen virtuellen Methode `function1` in einer Basisklasse und die Überschreibung in einer abgeleiteten Klasse veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="52ce0-122">The following code example illustrates the declaration of a new virtual method `function1` in a base class and how to override it in a derived class.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]

## <a name="constructors-and-inheritance"></a><span data-ttu-id="52ce0-123">Konstruktoren und Vererbung</span><span class="sxs-lookup"><span data-stu-id="52ce0-123">Constructors and Inheritance</span></span>

<span data-ttu-id="52ce0-124">Der Konstruktor für die Basisklasse muss in der abgeleiteten Klasse aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="52ce0-124">The constructor for the base class must be called in the derived class.</span></span> <span data-ttu-id="52ce0-125">Die Argumente für den Basisklassenkonstruktor werden in der Argumentliste in der- `inherit` Klausel angezeigt.</span><span class="sxs-lookup"><span data-stu-id="52ce0-125">The arguments for the base class constructor appear in the argument list in the `inherit` clause.</span></span> <span data-ttu-id="52ce0-126">Die verwendeten Werte müssen von den Argumenten bestimmt werden, die für den Konstruktor der abgeleiteten Klasse bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="52ce0-126">The values that are used must be determined from the arguments supplied to the derived class constructor.</span></span>

<span data-ttu-id="52ce0-127">Der folgende Code zeigt eine Basisklasse und eine abgeleitete Klasse, in der die abgeleitete Klasse den Basisklassenkonstruktor in der Vererbungs Klausel aufruft:</span><span class="sxs-lookup"><span data-stu-id="52ce0-127">The following code shows a base class and a derived class, where the derived class calls the base class constructor in the inherit clause:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

<span data-ttu-id="52ce0-128">Bei mehreren Konstruktoren kann der folgende Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="52ce0-128">In the case of multiple constructors, the following code can be used.</span></span> <span data-ttu-id="52ce0-129">Die erste Zeile der abgeleiteten Klassenkonstruktoren ist die `inherit` -Klausel, und die Felder werden als explizite Felder angezeigt, die mit dem- `val` Schlüsselwort deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="52ce0-129">The first line of the derived class constructors is the `inherit` clause, and the fields appear as explicit fields that are declared with the `val` keyword.</span></span> <span data-ttu-id="52ce0-130">Weitere Informationen finden Sie unter [Explizite Felder: das- `val` Schlüsselwort](./members/explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="52ce0-130">For more information, see [Explicit Fields: The `val` Keyword](./members/explicit-fields-the-val-keyword.md).</span></span>

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

## <a name="alternatives-to-inheritance"></a><span data-ttu-id="52ce0-131">Alternativen zur Vererbung</span><span class="sxs-lookup"><span data-stu-id="52ce0-131">Alternatives to Inheritance</span></span>

<span data-ttu-id="52ce0-132">In Fällen, in denen eine geringfügige Änderung eines Typs erforderlich ist, sollten Sie die Verwendung eines Objekt Ausdrucks als Alternative zu Vererbung in Erwägung gezogen.</span><span class="sxs-lookup"><span data-stu-id="52ce0-132">In cases where a minor modification of a type is required, consider using an object expression as an alternative to inheritance.</span></span> <span data-ttu-id="52ce0-133">Das folgende Beispiel veranschaulicht die Verwendung eines Objekt Ausdrucks als Alternative zum Erstellen eines neuen abgeleiteten Typs:</span><span class="sxs-lookup"><span data-stu-id="52ce0-133">The following example illustrates the use of an object expression as an alternative to creating a new derived type:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

<span data-ttu-id="52ce0-134">Weitere Informationen zu Objekt Ausdrücken finden Sie unter [Object Expressions](object-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="52ce0-134">For more information about object expressions, see [Object Expressions](object-expressions.md).</span></span>

<span data-ttu-id="52ce0-135">Wenn Sie Objekt Hierarchien erstellen, sollten Sie die Verwendung einer Unterscheidungs-Union anstelle der Vererbung in Erwägung gezogen.</span><span class="sxs-lookup"><span data-stu-id="52ce0-135">When you are creating object hierarchies, consider using a discriminated union instead of inheritance.</span></span> <span data-ttu-id="52ce0-136">Unterscheidungs-Unions können auch ein unterschiedliches Verhalten verschiedener Objekte modellieren, die einen gemeinsamen allgemeinen Typ haben.</span><span class="sxs-lookup"><span data-stu-id="52ce0-136">Discriminated unions can also model varied behavior of different objects that share a common overall type.</span></span> <span data-ttu-id="52ce0-137">Eine einzelne Unterscheidungs-Union kann häufig den Bedarf an einer Reihe abgeleiteter Klassen ausschließen, die neben Abweichungen darstellen.</span><span class="sxs-lookup"><span data-stu-id="52ce0-137">A single discriminated union can often eliminate the need for a number of derived classes that are minor variations of each other.</span></span> <span data-ttu-id="52ce0-138">Informationen zu Unterscheidungs-Unions finden Sie unter Unterscheidungs- [Unions](discriminated-unions.md).</span><span class="sxs-lookup"><span data-stu-id="52ce0-138">For information about discriminated unions, see [Discriminated Unions](discriminated-unions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="52ce0-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="52ce0-139">See also</span></span>

- [<span data-ttu-id="52ce0-140">Objektausdrücke</span><span class="sxs-lookup"><span data-stu-id="52ce0-140">Object Expressions</span></span>](object-expressions.md)
- [<span data-ttu-id="52ce0-141">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="52ce0-141">F# Language Reference</span></span>](index.md)
