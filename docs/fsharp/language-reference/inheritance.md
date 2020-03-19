---
title: Vererbung
description: Erfahren Sie, wie Sie die Vererbungsbeziehungen von F- und Vererbungsbeziehungen mithilfe des Schlüsselworts "erben" angeben.
ms.date: 05/16/2016
ms.openlocfilehash: 5ab891a93528427a66e4eb8f7bfeccbf6e4d2c7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401130"
---
# <a name="inheritance"></a><span data-ttu-id="ae77c-103">Vererbung</span><span class="sxs-lookup"><span data-stu-id="ae77c-103">Inheritance</span></span>

<span data-ttu-id="ae77c-104">Vererbung wird verwendet, um die "is-a"-Beziehung oder Untertypisierung in der objektorientierten Programmierung zu modellieren.</span><span class="sxs-lookup"><span data-stu-id="ae77c-104">Inheritance is used to model the "is-a" relationship, or subtyping, in object-oriented programming.</span></span>

## <a name="specifying-inheritance-relationships"></a><span data-ttu-id="ae77c-105">Angeben von Vererbungsbeziehungen</span><span class="sxs-lookup"><span data-stu-id="ae77c-105">Specifying Inheritance Relationships</span></span>

<span data-ttu-id="ae77c-106">Sie geben Vererbungsbeziehungen an, indem Sie das `inherit` Schlüsselwort in einer Klassendeklaration verwenden.</span><span class="sxs-lookup"><span data-stu-id="ae77c-106">You specify inheritance relationships by using the `inherit` keyword in a class declaration.</span></span> <span data-ttu-id="ae77c-107">Die grundlegende syntaktische Form wird im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ae77c-107">The basic syntactical form is shown in the following example.</span></span>

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

<span data-ttu-id="ae77c-108">Eine Klasse kann höchstens eine direkte Basisklasse haben.</span><span class="sxs-lookup"><span data-stu-id="ae77c-108">A class can have at most one direct base class.</span></span> <span data-ttu-id="ae77c-109">Wenn Sie keine Basisklasse mithilfe `inherit` des Schlüsselworts angeben, erbt die Klasse implizit von `System.Object`.</span><span class="sxs-lookup"><span data-stu-id="ae77c-109">If you do not specify a base class by using the `inherit` keyword, the class implicitly inherits from `System.Object`.</span></span>

## <a name="inherited-members"></a><span data-ttu-id="ae77c-110">Geerbte Elemente</span><span class="sxs-lookup"><span data-stu-id="ae77c-110">Inherited Members</span></span>

<span data-ttu-id="ae77c-111">Wenn eine Klasse von einer anderen Klasse erbt, stehen die Methoden und Member der Basisklasse Benutzern der abgeleiteten Klasse zur Verfügung, als wären sie direkte Member der abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="ae77c-111">If a class inherits from another class, the methods and members of the base class are available to users of the derived class as if they were direct members of the derived class.</span></span>

<span data-ttu-id="ae77c-112">Alle let-Bindungen und Konstruktorparameter sind für eine Klasse privat und können daher nicht von abgeleiteten Klassen aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ae77c-112">Any let bindings and constructor parameters are private to a class and, therefore, cannot be accessed from derived classes.</span></span>

<span data-ttu-id="ae77c-113">Das `base` Schlüsselwort ist in abgeleiteten Klassen verfügbar und bezieht sich auf die Basisklasseninstanz.</span><span class="sxs-lookup"><span data-stu-id="ae77c-113">The keyword `base` is available in derived classes and refers to the base class instance.</span></span> <span data-ttu-id="ae77c-114">Es wird wie die Selbstbezeichnerverwendet.</span><span class="sxs-lookup"><span data-stu-id="ae77c-114">It is used like the self-identifier.</span></span>

## <a name="virtual-methods-and-overrides"></a><span data-ttu-id="ae77c-115">Virtuelle Methoden und Überschreibungen</span><span class="sxs-lookup"><span data-stu-id="ae77c-115">Virtual Methods and Overrides</span></span>

<span data-ttu-id="ae77c-116">Virtuelle Methoden (und Eigenschaften) funktionieren in F-Code etwas anders als in anderen .NET-Sprachen.</span><span class="sxs-lookup"><span data-stu-id="ae77c-116">Virtual methods (and properties) work somewhat differently in F# as compared to other .NET languages.</span></span> <span data-ttu-id="ae77c-117">Um ein neues virtuelles Mitglied `abstract` zu deklarieren, verwenden Sie das Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="ae77c-117">To declare a new virtual member, you use the `abstract` keyword.</span></span> <span data-ttu-id="ae77c-118">Sie tun dies unabhängig davon, ob Sie eine Standardimplementierung für diese Methode bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ae77c-118">You do this regardless of whether you provide a default implementation for that method.</span></span> <span data-ttu-id="ae77c-119">Daher folgt eine vollständige Definition einer virtuellen Methode in einer Basisklasse diesem Muster:</span><span class="sxs-lookup"><span data-stu-id="ae77c-119">Thus a complete definition of a virtual method in a base class follows this pattern:</span></span>

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="ae77c-120">Und in einer abgeleiteten Klasse folgt eine Außerkraftsetzung dieser virtuellen Methode diesem Muster:</span><span class="sxs-lookup"><span data-stu-id="ae77c-120">And in a derived class, an override of this virtual method follows this pattern:</span></span>

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="ae77c-121">Wenn Sie die Standardimplementierung in der Basisklasse weglassen, wird die Basisklasse zu einer abstrakten Klasse.</span><span class="sxs-lookup"><span data-stu-id="ae77c-121">If you omit the default implementation in the base class, the base class becomes an abstract class.</span></span>

<span data-ttu-id="ae77c-122">Das folgende Codebeispiel veranschaulicht die Deklaration einer neuen virtuellen Methode `function1` in einer Basisklasse und wie sie in einer abgeleiteten Klasse überschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="ae77c-122">The following code example illustrates the declaration of a new virtual method `function1` in a base class and how to override it in a derived class.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]

## <a name="constructors-and-inheritance"></a><span data-ttu-id="ae77c-123">Konstruktoren und Vererbung</span><span class="sxs-lookup"><span data-stu-id="ae77c-123">Constructors and Inheritance</span></span>

<span data-ttu-id="ae77c-124">Der Konstruktor für die Basisklasse muss in der abgeleiteten Klasse aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ae77c-124">The constructor for the base class must be called in the derived class.</span></span> <span data-ttu-id="ae77c-125">Die Argumente für den Basisklassenkonstruktor werden `inherit` in der Argumentliste in der Klausel angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ae77c-125">The arguments for the base class constructor appear in the argument list in the `inherit` clause.</span></span> <span data-ttu-id="ae77c-126">Die verwendeten Werte müssen aus den Argumenten bestimmt werden, die dem abgeleiteten Klassenkonstruktor bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ae77c-126">The values that are used must be determined from the arguments supplied to the derived class constructor.</span></span>

<span data-ttu-id="ae77c-127">Der folgende Code zeigt eine Basisklasse und eine abgeleitete Klasse, bei der die abgeleitete Klasse den Basisklassenkonstruktor in der erben-Klausel aufruft:</span><span class="sxs-lookup"><span data-stu-id="ae77c-127">The following code shows a base class and a derived class, where the derived class calls the base class constructor in the inherit clause:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

<span data-ttu-id="ae77c-128">Bei mehreren Konstruktoren kann der folgende Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ae77c-128">In the case of multiple constructors, the following code can be used.</span></span> <span data-ttu-id="ae77c-129">Die erste Zeile der abgeleiteten Klassenkonstruktoren ist die `inherit` Klausel, und die `val` Felder werden als explizite Felder angezeigt, die mit dem Schlüsselwort deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="ae77c-129">The first line of the derived class constructors is the `inherit` clause, and the fields appear as explicit fields that are declared with the `val` keyword.</span></span> <span data-ttu-id="ae77c-130">Weitere Informationen finden Sie unter [Explizite Felder: `val` Das Schlüsselwort](./members/explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="ae77c-130">For more information, see [Explicit Fields: The `val` Keyword](./members/explicit-fields-the-val-keyword.md).</span></span>

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

## <a name="alternatives-to-inheritance"></a><span data-ttu-id="ae77c-131">Alternativen zur Vererbung</span><span class="sxs-lookup"><span data-stu-id="ae77c-131">Alternatives to Inheritance</span></span>

<span data-ttu-id="ae77c-132">In Fällen, in denen eine geringfügige Änderung eines Typs erforderlich ist, sollten Sie einen Objektausdruck als Alternative zur Vererbung verwenden.</span><span class="sxs-lookup"><span data-stu-id="ae77c-132">In cases where a minor modification of a type is required, consider using an object expression as an alternative to inheritance.</span></span> <span data-ttu-id="ae77c-133">Das folgende Beispiel veranschaulicht die Verwendung eines Objektausdrucks als Alternative zum Erstellen eines neuen abgeleiteten Typs:</span><span class="sxs-lookup"><span data-stu-id="ae77c-133">The following example illustrates the use of an object expression as an alternative to creating a new derived type:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

<span data-ttu-id="ae77c-134">Weitere Informationen zu Objektausdrücken finden Sie unter [Objektausdrücke](object-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="ae77c-134">For more information about object expressions, see [Object Expressions](object-expressions.md).</span></span>

<span data-ttu-id="ae77c-135">Wenn Sie Objekthierarchien erstellen, sollten Sie eine diskriminierte Union anstelle der Vererbung verwenden.</span><span class="sxs-lookup"><span data-stu-id="ae77c-135">When you are creating object hierarchies, consider using a discriminated union instead of inheritance.</span></span> <span data-ttu-id="ae77c-136">Diskriminierte Vereinigungen können auch unterschiedliches Verhalten verschiedener Objekte modellieren, die einen gemeinsamen Gesamttyp aufweisen.</span><span class="sxs-lookup"><span data-stu-id="ae77c-136">Discriminated unions can also model varied behavior of different objects that share a common overall type.</span></span> <span data-ttu-id="ae77c-137">Eine einzelne diskriminierte Union kann oft die Notwendigkeit einer Reihe abgeleiteter Klassen eliminieren, die geringfügige Abweichungen voneinander sind.</span><span class="sxs-lookup"><span data-stu-id="ae77c-137">A single discriminated union can often eliminate the need for a number of derived classes that are minor variations of each other.</span></span> <span data-ttu-id="ae77c-138">Informationen zu diskriminierten Gewerkschaften finden Sie unter [Diskriminierte Gewerkschaften](discriminated-unions.md).</span><span class="sxs-lookup"><span data-stu-id="ae77c-138">For information about discriminated unions, see [Discriminated Unions](discriminated-unions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ae77c-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ae77c-139">See also</span></span>

- [<span data-ttu-id="ae77c-140">Objektausdrücke</span><span class="sxs-lookup"><span data-stu-id="ae77c-140">Object Expressions</span></span>](object-expressions.md)
- [<span data-ttu-id="ae77c-141">Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="ae77c-141">F# Language Reference</span></span>](index.md)
