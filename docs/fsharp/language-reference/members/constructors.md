---
title: Konstruktoren
description: Informationen Sie zum Definieren und Verwenden von Konstruktoren in F# zu erstellen und initialisieren die Klasse und Struktur von Objekten.
ms.date: 05/16/2016
ms.openlocfilehash: 6769ec7fc6768090d8ae68e21946a58829b6eea0
ms.sourcegitcommit: 878ca7550b653114c3968ef8906da2b3e60e3c7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2019
ms.locfileid: "71736847"
---
# <a name="constructors"></a><span data-ttu-id="15941-103">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="15941-103">Constructors</span></span>

<span data-ttu-id="15941-104">In diesem Artikel wird beschrieben, wie Konstruktoren definiert und verwendet werden, um Klassen-und Struktur Objekte zu erstellen und zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="15941-104">This article describes how to define and use constructors to create and initialize class and structure objects.</span></span>

## <a name="construction-of-class-objects"></a><span data-ttu-id="15941-105">Konstruktion von Klassen Objekten</span><span class="sxs-lookup"><span data-stu-id="15941-105">Construction of class objects</span></span>

<span data-ttu-id="15941-106">Objekte von Klassentypen verfügen über Konstruktoren.</span><span class="sxs-lookup"><span data-stu-id="15941-106">Objects of class types have constructors.</span></span> <span data-ttu-id="15941-107">Es gibt zwei Arten von Konstruktoren.</span><span class="sxs-lookup"><span data-stu-id="15941-107">There are two kinds of constructors.</span></span> <span data-ttu-id="15941-108">Eine ist der primäre Konstruktor, dessen Parameter in Klammern direkt nach dem Typnamen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="15941-108">One is the primary constructor, whose parameters appear in parentheses just after the type name.</span></span> <span data-ttu-id="15941-109">Mithilfe des `new` -Schlüssel Worts geben Sie weitere optionale zusätzliche Konstruktoren an.</span><span class="sxs-lookup"><span data-stu-id="15941-109">You specify other, optional additional constructors by using the `new` keyword.</span></span> <span data-ttu-id="15941-110">Alle diese zusätzlichen Konstruktoren müssen den primären Konstruktor aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="15941-110">Any such additional constructors must call the primary constructor.</span></span>

<span data-ttu-id="15941-111">Der primäre Konstruktor enthält `let` - `do` und-Bindungen, die am Anfang der Klassendefinition angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="15941-111">The primary constructor contains `let` and `do` bindings that appear at the start of the class definition.</span></span> <span data-ttu-id="15941-112">Eine `let` Bindung deklariert private Felder und Methoden der-Klasse. eine `do` Bindung führt Code aus.</span><span class="sxs-lookup"><span data-stu-id="15941-112">A `let` binding declares private fields and methods of the class; a `do` binding executes code.</span></span> <span data-ttu-id="15941-113">Weitere Informationen zu `let` Bindungen in Klassenkonstruktoren finden [ `let` Sie unter Bindungen in Klassen](let-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="15941-113">For more information about `let` bindings in class constructors, see [`let` Bindings in Classes](let-bindings-in-classes.md).</span></span> <span data-ttu-id="15941-114">Weitere Informationen zu `do` Bindungen in Konstruktoren finden [ `do` Sie unter Bindungen in Klassen](do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="15941-114">For more information about `do` bindings in constructors, see [`do` Bindings in Classes](do-bindings-in-classes.md).</span></span>

<span data-ttu-id="15941-115">Unabhängig davon, ob der Konstruktor, den Sie aufzurufen, ein primärer Konstruktor oder ein zusätzlicher Konstruktor ist, können Sie- `new` Objekte erstellen, indem Sie einen- `new` Ausdruck mit oder ohne das optionale-Schlüsselwort verwenden.</span><span class="sxs-lookup"><span data-stu-id="15941-115">Regardless of whether the constructor you want to call is a primary constructor or an additional constructor, you can create objects by using a `new` expression, with or without the optional `new` keyword.</span></span> <span data-ttu-id="15941-116">Sie initialisieren die Objekte mit Konstruktorargumenten, indem Sie entweder die Argumente in der Reihenfolge auflisten und durch Kommas getrennt und in Klammern eingeschlossen sind, oder indem Sie benannte Argumente und Werte in Klammern verwenden.</span><span class="sxs-lookup"><span data-stu-id="15941-116">You initialize your objects together with constructor arguments, either by listing the arguments in order and separated by commas and enclosed in parentheses, or by using named arguments and values in parentheses.</span></span> <span data-ttu-id="15941-117">Sie können auch Eigenschaften für ein Objekt während der Erstellung des Objekts festlegen, indem Sie die Eigenschaftsnamen verwenden und Werte zuweisen, genauso wie Sie benannte Konstruktorargumente verwenden.</span><span class="sxs-lookup"><span data-stu-id="15941-117">You can also set properties on an object during the construction of the object by using the property names and assigning values just as you use named constructor arguments.</span></span>

<span data-ttu-id="15941-118">Der folgende Code veranschaulicht eine-Klasse, die über einen Konstruktor und verschiedene Methoden zum Erstellen von-Objekten verfügt:</span><span class="sxs-lookup"><span data-stu-id="15941-118">The following code illustrates a class that has a constructor and various ways of creating objects:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3501.fs)]

<span data-ttu-id="15941-119">Die Ausgabe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="15941-119">The output is as follows:</span></span>

```console
Initialized object that has coordinates (1, 2, 3)
Initialized object that has coordinates (4, 5, 6)
Initialized object that has coordinates (7, 8, 9)
Initialized object that has coordinates (0, 0, 0)
```

## <a name="construction-of-structures"></a><span data-ttu-id="15941-120">Konstruktion von Strukturen</span><span class="sxs-lookup"><span data-stu-id="15941-120">Construction of structures</span></span>

<span data-ttu-id="15941-121">Strukturen befolgen alle Regeln der Klassen.</span><span class="sxs-lookup"><span data-stu-id="15941-121">Structures follow all the rules of classes.</span></span> <span data-ttu-id="15941-122">Daher können Sie über einen primären Konstruktor verfügen, und Sie können zusätzliche Konstruktoren mithilfe `new`von bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="15941-122">Therefore, you can have a primary constructor, and you can provide additional constructors by using `new`.</span></span> <span data-ttu-id="15941-123">Es gibt jedoch einen wichtigen Unterschied zwischen Strukturen und Klassen: Strukturen können über einen Parameter losen Konstruktor (d. h. einen ohne Argumente) verfügen, auch wenn kein primärer Konstruktor definiert ist.</span><span class="sxs-lookup"><span data-stu-id="15941-123">However, there is one important difference between structures and classes: structures can have a parameterless constructor (that is, one with no arguments) even if no primary constructor is defined.</span></span> <span data-ttu-id="15941-124">Der Parameter lose Konstruktor initialisiert alle Felder mit dem Standardwert für diesen Typ, normalerweise 0 (null) oder dessen Entsprechung.</span><span class="sxs-lookup"><span data-stu-id="15941-124">The parameterless constructor initializes all the fields to the default value for that type, usually zero or its equivalent.</span></span> <span data-ttu-id="15941-125">Alle Konstruktoren, die Sie für Strukturen definieren, müssen mindestens ein Argument aufweisen, damit Sie nicht mit dem Parameter losen Konstruktor in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="15941-125">Any constructors that you define for structures must have at least one argument so that they do not conflict with the parameterless constructor.</span></span>

<span data-ttu-id="15941-126">Außerdem verfügen Strukturen häufig über Felder, die mithilfe des `val` Schlüssel Worts erstellt werden. Klassen können auch über diese Felder verfügen.</span><span class="sxs-lookup"><span data-stu-id="15941-126">Also, structures often have fields that are created by using the `val` keyword; classes can also have these fields.</span></span> <span data-ttu-id="15941-127">Strukturen und Klassen, die mithilfe des `val` -Schlüssel Worts definierte Felder haben, können auch in zusätzlichen Konstruktoren mithilfe von Daten Satz Ausdrücken initialisiert werden, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="15941-127">Structures and classes that have fields defined by using the `val` keyword can also be initialized in additional constructors by using record expressions, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3502.fs)]

<span data-ttu-id="15941-128">Weitere Informationen finden [Sie unter Explizite Felder: Das `val` Schlüssel](explicit-fields-the-val-keyword.md)Wort.</span><span class="sxs-lookup"><span data-stu-id="15941-128">For more information, see [Explicit Fields: The `val` Keyword](explicit-fields-the-val-keyword.md).</span></span>

## <a name="executing-side-effects-in-constructors"></a><span data-ttu-id="15941-129">Ausführen von Nebeneffekten in Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="15941-129">Executing side effects in constructors</span></span>

<span data-ttu-id="15941-130">Ein primärer Konstruktor in einer Klasse kann Code in einer `do` Bindung ausführen.</span><span class="sxs-lookup"><span data-stu-id="15941-130">A primary constructor in a class can execute code in a `do` binding.</span></span> <span data-ttu-id="15941-131">Was geschieht jedoch, wenn Sie Code in einem zusätzlichen Konstruktor ohne `do` Bindung ausführen müssen?</span><span class="sxs-lookup"><span data-stu-id="15941-131">However, what if you have to execute code in an additional constructor, without a `do` binding?</span></span> <span data-ttu-id="15941-132">Verwenden Sie hierzu das `then` -Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="15941-132">To do this, you use the `then` keyword.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3503.fs)]

<span data-ttu-id="15941-133">Die Nebeneffekte des primären Konstruktors werden weiterhin ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="15941-133">The side effects of the primary constructor still execute.</span></span> <span data-ttu-id="15941-134">Aus diesem Grund lautet die Ausgabe wie folgt:</span><span class="sxs-lookup"><span data-stu-id="15941-134">Therefore, the output is as follows:</span></span>

```console
Created a person object.
Created a person object.
Created an invalid person object.
```

## <a name="self-identifiers-in-constructors"></a><span data-ttu-id="15941-135">Self-IDs in Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="15941-135">Self identifiers in constructors</span></span>

<span data-ttu-id="15941-136">In anderen Membern geben Sie einen Namen für das aktuelle Objekt in der Definition der einzelnen Member an.</span><span class="sxs-lookup"><span data-stu-id="15941-136">In other members, you provide a name for the current object in the definition of each member.</span></span> <span data-ttu-id="15941-137">Sie können auch den selbst Bezeichner in die erste Zeile der Klassendefinition einfügen, indem Sie `as` das Schlüsselwort direkt nach den Konstruktorparametern verwenden.</span><span class="sxs-lookup"><span data-stu-id="15941-137">You can also put the self identifier on the first line of the class definition by using the `as` keyword immediately following the constructor parameters.</span></span> <span data-ttu-id="15941-138">Diese Syntax wird im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="15941-138">The following example illustrates this syntax.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3504.fs)]

<span data-ttu-id="15941-139">In zusätzlichen Konstruktoren können Sie auch einen selbst Bezeichner definieren, indem Sie `as` die-Klausel direkt nach den Konstruktorparametern platzieren.</span><span class="sxs-lookup"><span data-stu-id="15941-139">In additional constructors, you can also define a self identifier by putting the `as` clause right after the constructor parameters.</span></span> <span data-ttu-id="15941-140">Das folgende Beispiel veranschaulicht diese Syntax:</span><span class="sxs-lookup"><span data-stu-id="15941-140">The following example illustrates this syntax:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3505.fs)]

<span data-ttu-id="15941-141">Probleme können auftreten, wenn Sie versuchen, ein Objekt zu verwenden, bevor es vollständig definiert ist.</span><span class="sxs-lookup"><span data-stu-id="15941-141">Problems can occur when you try to use an object before it is fully defined.</span></span> <span data-ttu-id="15941-142">Daher kann die Verwendung des Self-Bezeichners bewirken, dass der Compiler eine Warnung ausgibt und zusätzliche Überprüfungen einfügt, um sicherzustellen, dass auf die Member eines Objekts nicht zugegriffen wird, bevor das Objekt initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="15941-142">Therefore, uses of the self identifier can cause the compiler to emit a warning and insert additional checks to ensure the members of an object are not accessed before the object is initialized.</span></span> <span data-ttu-id="15941-143">Sie sollten den Self-Identifier nur in den `do` Bindungen des primären Konstruktors oder nach dem `then` -Schlüsselwort in zusätzlichen Konstruktoren verwenden.</span><span class="sxs-lookup"><span data-stu-id="15941-143">You should only use the self identifier in the `do` bindings of the primary constructor, or after the `then` keyword in additional constructors.</span></span>

<span data-ttu-id="15941-144">Der Name des selbst Bezeichners muss nicht sein `this`.</span><span class="sxs-lookup"><span data-stu-id="15941-144">The name of the self identifier does not have to be `this`.</span></span> <span data-ttu-id="15941-145">Dies kann ein beliebiger gültiger Bezeichner sein.</span><span class="sxs-lookup"><span data-stu-id="15941-145">It can be any valid identifier.</span></span>

## <a name="assigning-values-to-properties-at-initialization"></a><span data-ttu-id="15941-146">Zuweisen von Werten zu Eigenschaften bei der Initialisierung</span><span class="sxs-lookup"><span data-stu-id="15941-146">Assigning values to properties at initialization</span></span>

<span data-ttu-id="15941-147">Sie können den Eigenschaften eines Klassen Objekts im Initialisierungs Code Werte zuweisen, indem Sie eine Liste der Zuweisungen des Formulars `property = value` an die Argumentliste für einen Konstruktor anhängen.</span><span class="sxs-lookup"><span data-stu-id="15941-147">You can assign values to the properties of a class object in the initialization code by appending a list of assignments of the form `property = value` to the argument list for a constructor.</span></span> <span data-ttu-id="15941-148">Dies wird im folgenden Codebeispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="15941-148">This is shown in the following code example:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="15941-149">In der folgenden Version des vorherigen Codes wird die Kombination aus normalen Argumenten, optionalen Argumenten und Eigenschafts Einstellungen in einem konstruktorbefehl veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="15941-149">The following version of the previous code illustrates the combination of ordinary arguments, optional arguments, and property settings in one constructor call:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3507.fs)]

## <a name="constructors-in-inherited-class"></a><span data-ttu-id="15941-150">Konstruktoren in der geerbten Klasse</span><span class="sxs-lookup"><span data-stu-id="15941-150">Constructors in inherited class</span></span>

<span data-ttu-id="15941-151">Beim Erben von einer Basisklasse, die über einen Konstruktor verfügt, müssen Sie die Argumente in der Vererbungs Klausel angeben.</span><span class="sxs-lookup"><span data-stu-id="15941-151">When inheriting from a base class that has a constructor, you must specify its arguments in the inherit clause.</span></span> <span data-ttu-id="15941-152">Weitere Informationen finden Sie unter [Konstruktoren und Vererbung](../inheritance.md#constructors-and-inheritance).</span><span class="sxs-lookup"><span data-stu-id="15941-152">For more information, see [Constructors and inheritance](../inheritance.md#constructors-and-inheritance).</span></span>

## <a name="static-constructors-or-type-constructors"></a><span data-ttu-id="15941-153">Statische Konstruktoren oder Typkonstruktoren</span><span class="sxs-lookup"><span data-stu-id="15941-153">Static constructors or type constructors</span></span>

<span data-ttu-id="15941-154">Neben dem Angeben von Code zum Erstellen von Objekten können `let` statische `do` -und-Bindungen in Klassentypen erstellt werden, die ausgeführt werden, bevor der-Typ zum ersten Mal für die Initialisierung auf Typebene verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="15941-154">In addition to specifying code for creating objects, static `let` and `do` bindings can be authored in class types that execute before the type is first used to perform initialization at the type level.</span></span> <span data-ttu-id="15941-155">Weitere Informationen finden [ `let` Sie unter Bindungen in Klassen](let-bindings-in-classes.md) und [ `do` Bindungen in Klassen](do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="15941-155">For more information, see [`let` Bindings in Classes](let-bindings-in-classes.md) and [`do` Bindings in Classes](do-bindings-in-classes.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="15941-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15941-156">See also</span></span>

- [<span data-ttu-id="15941-157">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="15941-157">Members</span></span>](index.md)
