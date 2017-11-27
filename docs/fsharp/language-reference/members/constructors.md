---
title: Konstruktoren (F#)
description: Informationen Sie zum Definieren und Verwenden von Konstruktoren in f# erstellen und Initialisieren der Klasse und Struktur-Objekte.
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: e0da2250-29de-4145-a1be-e5faff080759
ms.openlocfilehash: 60ed93f1c1dc15e99465d969c9e4fd3e61c28ffa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="constructors"></a><span data-ttu-id="00a2f-104">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="00a2f-104">Constructors</span></span>

<span data-ttu-id="00a2f-105">In diesem Thema wird beschrieben, wie zum Definieren und Verwenden von Konstruktoren zum Erstellen und Initialisieren von Objekten von Klasse und Struktur wird.</span><span class="sxs-lookup"><span data-stu-id="00a2f-105">This topic describes how to define and use constructors to create and initialize class and structure objects.</span></span>


## <a name="construction-of-class-objects"></a><span data-ttu-id="00a2f-106">Konstruktion von Klassenobjekten</span><span class="sxs-lookup"><span data-stu-id="00a2f-106">Construction of Class Objects</span></span>
<span data-ttu-id="00a2f-107">Objekte von Klassentypen verfügen über Konstruktoren.</span><span class="sxs-lookup"><span data-stu-id="00a2f-107">Objects of class types have constructors.</span></span> <span data-ttu-id="00a2f-108">Es gibt zwei Arten von Konstruktoren.</span><span class="sxs-lookup"><span data-stu-id="00a2f-108">There are two kinds of constructors.</span></span> <span data-ttu-id="00a2f-109">Eine ist der primäre Konstruktor, dessen Parameter in Klammern hinter dem Typnamen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="00a2f-109">One is the primary constructor, whose parameters appear in parentheses just after the type name.</span></span> <span data-ttu-id="00a2f-110">Geben Sie andere, optionale zusätzliche Konstruktoren, mit dem `new` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="00a2f-110">You specify other, optional additional constructors by using the `new` keyword.</span></span> <span data-ttu-id="00a2f-111">Alle diese zusätzlichen Konstruktoren müssen den primären Konstruktor aufrufen.</span><span class="sxs-lookup"><span data-stu-id="00a2f-111">Any such additional constructors must call the primary constructor.</span></span>

<span data-ttu-id="00a2f-112">Enthält die primäre Konstruktor `let` und `do` Bindungen, die zu Beginn der Definition der Klasse angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="00a2f-112">The primary constructor contains `let` and `do` bindings that appear at the start of the class definition.</span></span> <span data-ttu-id="00a2f-113">Ein `let` Bindung deklariert, private Felder und Methoden der Klasse; eine `do` Bindung führt Code aus.</span><span class="sxs-lookup"><span data-stu-id="00a2f-113">A `let` binding declares private fields and methods of the class; a `do` binding executes code.</span></span> <span data-ttu-id="00a2f-114">Weitere Informationen zu `let` Bindungen in der Klasse, Konstruktoren, finden Sie unter [ `let` Bindungen in Klassen](let-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="00a2f-114">For more information about `let` bindings in class constructors, see [`let` Bindings in Classes](let-bindings-in-classes.md).</span></span> <span data-ttu-id="00a2f-115">Weitere Informationen zu `do` Bindungen in Konstruktoren finden Sie unter [ `do` Bindungen in Klassen](do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="00a2f-115">For more information about `do` bindings in constructors, see [`do` Bindings in Classes](do-bindings-in-classes.md).</span></span>

<span data-ttu-id="00a2f-116">Unabhängig davon, ob der Konstruktor aufgerufen werden soll, einen primären Konstruktor oder einem zusätzlichen Konstruktor ist, können Sie Objekte erstellen, indem Sie mit einem `new` Ausdruck, mit oder ohne das optionale `new` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="00a2f-116">Regardless of whether the constructor you want to call is a primary constructor or an additional constructor, you can create objects by using a `new` expression, with or without the optional `new` keyword.</span></span> <span data-ttu-id="00a2f-117">Sie initialisieren die Objekte zusammen mit Konstruktorargumenten, entweder durch die Argumente in der Reihenfolge aufgelistet und durch Kommas getrennt und in Klammern oder mithilfe von benannten Argumenten und Werte in Klammern eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="00a2f-117">You initialize your objects together with constructor arguments, either by listing the arguments in order and separated by commas and enclosed in parentheses, or by using named arguments and values in parentheses.</span></span> <span data-ttu-id="00a2f-118">Sie können Eigenschaften auch für ein Objekt während der Erstellung des Objekts festlegen, mit dem Eigenschaftennamen und Zuweisen von Werten, genauso wie Sie mit dem Namen Konstruktorargumente.</span><span class="sxs-lookup"><span data-stu-id="00a2f-118">You can also set properties on an object during the construction of the object by using the property names and assigning values just as you use named constructor arguments.</span></span>

<span data-ttu-id="00a2f-119">Das folgende Codebeispiel veranschaulicht eine Klasse, die einen Konstruktor und verschiedene Methoden zum Erstellen von Objekten hat.</span><span class="sxs-lookup"><span data-stu-id="00a2f-119">The following code illustrates a class that has a constructor and various ways of creating objects.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3501.fs)]

<span data-ttu-id="00a2f-120">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="00a2f-120">The output is as follows.</span></span>

```console
Initialized object that has coordinates (1, 2, 3)
Initialized object that has coordinates (4, 5, 6)
Initialized object that has coordinates (7, 8, 9)
Initialized object that has coordinates (0, 0, 0)
```

## <a name="construction-of-structures"></a><span data-ttu-id="00a2f-121">Zur Erstellung von Strukturen</span><span class="sxs-lookup"><span data-stu-id="00a2f-121">Construction of Structures</span></span>
<span data-ttu-id="00a2f-122">Strukturen, gelten alle Regeln von Klassen.</span><span class="sxs-lookup"><span data-stu-id="00a2f-122">Structures follow all the rules of classes.</span></span> <span data-ttu-id="00a2f-123">Aus diesem Grund können Sie einen primären Konstruktor verfügen, und Sie können mit Weitere Konstruktoren bereitstellen `new`.</span><span class="sxs-lookup"><span data-stu-id="00a2f-123">Therefore, you can have a primary constructor, and you can provide additional constructors by using `new`.</span></span> <span data-ttu-id="00a2f-124">Es ist jedoch ein wichtiger Unterschied zwischen Strukturen und Klassen: Strukturen können über einen Standardkonstruktor (d. h. eine ohne Argumente) verfügen, auch wenn kein primärer Konstruktor definiert ist.</span><span class="sxs-lookup"><span data-stu-id="00a2f-124">However, there is one important difference between structures and classes: structures can have a default constructor (that is, one with no arguments) even if no primary constructor is defined.</span></span> <span data-ttu-id="00a2f-125">Der Standardkonstruktor initialisiert alle Felder auf den Standardwert für diesen Typ, in der Regel 0 (null) oder dessen Entsprechung.</span><span class="sxs-lookup"><span data-stu-id="00a2f-125">The default constructor initializes all the fields to the default value for that type, usually zero or its equivalent.</span></span> <span data-ttu-id="00a2f-126">Konstruktoren, die für Strukturen definiert, benötigen mindestens ein Argument, damit sie nicht mit dem Standardkonstruktor in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="00a2f-126">Any constructors that you define for structures must have at least one argument so that they do not conflict with the default constructor.</span></span>

<span data-ttu-id="00a2f-127">Strukturen müssen außerdem oft Felder, die mithilfe von erstellt werden die `val` Schlüsselwort Klassen können auch diese Felder haben.</span><span class="sxs-lookup"><span data-stu-id="00a2f-127">Also, structures often have fields that are created by using the `val` keyword; classes can also have these fields.</span></span> <span data-ttu-id="00a2f-128">Strukturen und Klassen, die mit definierten Felder verfügen über die `val` -Schlüsselwort kann auch in Konstruktoren initialisiert werden zusätzliche mithilfe von Datensatz Ausdrücken wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="00a2f-128">Structures and classes that have fields defined by using the `val` keyword can also be initialized in additional constructors by using record expressions, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3502.fs)]

<span data-ttu-id="00a2f-129">Weitere Informationen finden Sie unter [explizite Felder: das `val` Schlüsselwort](explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="00a2f-129">For more information, see [Explicit Fields: The `val` Keyword](explicit-fields-the-val-keyword.md).</span></span>


## <a name="executing-side-effects-in-constructors"></a><span data-ttu-id="00a2f-130">Ausführen von Nebeneffekten in Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="00a2f-130">Executing Side Effects in Constructors</span></span>
<span data-ttu-id="00a2f-131">Führen Sie ein primärer Konstruktor in einer Klasse kann Code in eine `do` Bindung.</span><span class="sxs-lookup"><span data-stu-id="00a2f-131">A primary constructor in a class can execute code in a `do` binding.</span></span> <span data-ttu-id="00a2f-132">Was geschieht, wenn Sie haben jedoch zum Ausführen von Code in einem zusätzlichen Konstruktor ohne eine `do` Bindung?</span><span class="sxs-lookup"><span data-stu-id="00a2f-132">However, what if you have to execute code in an additional constructor, without a `do` binding?</span></span> <span data-ttu-id="00a2f-133">Zu diesem Zweck verwenden Sie die `then` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="00a2f-133">To do this, you use the `then` keyword.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3503.fs)]

<span data-ttu-id="00a2f-134">Die Nebeneffekte des primären Konstruktor weiterhin ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="00a2f-134">The side effects of the primary constructor still execute.</span></span> <span data-ttu-id="00a2f-135">Daher ist die Ausgabe wie folgt.</span><span class="sxs-lookup"><span data-stu-id="00a2f-135">Therefore, the output is as follows.</span></span>

```console
Created a person object.
Created a person object.
Created an invalid person object.
```

## <a name="self-identifiers-in-constructors"></a><span data-ttu-id="00a2f-136">Selbstbezeichner in Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="00a2f-136">Self Identifiers in Constructors</span></span>
<span data-ttu-id="00a2f-137">In anderen Mitgliedern geben Sie einen Namen für das aktuelle Objekt in der Definition jedes Elements.</span><span class="sxs-lookup"><span data-stu-id="00a2f-137">In other members, you provide a name for the current object in the definition of each member.</span></span> <span data-ttu-id="00a2f-138">Sie können auch den Selbstbezeichner in der ersten Zeile der Klassendefinition platziert, mithilfe der `as` -Schlüsselwort direkt hinter die Konstruktorparametern.</span><span class="sxs-lookup"><span data-stu-id="00a2f-138">You can also put the self identifier on the first line of the class definition by using the `as` keyword immediately following the constructor parameters.</span></span> <span data-ttu-id="00a2f-139">Das folgende Beispiel veranschaulicht diese Syntax.</span><span class="sxs-lookup"><span data-stu-id="00a2f-139">The following example illustrates this syntax.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3504.fs)]

<span data-ttu-id="00a2f-140">In weiteren Konstruktoren können Sie auch einen Selbstbezeichner verlegen definieren die `as` Klausel direkt hinter den Konstruktorparametern.</span><span class="sxs-lookup"><span data-stu-id="00a2f-140">In additional constructors, you can also define a self identifier by putting the `as` clause right after the constructor parameters.</span></span> <span data-ttu-id="00a2f-141">Das folgende Beispiel veranschaulicht diese Syntax.</span><span class="sxs-lookup"><span data-stu-id="00a2f-141">The following example illustrates this syntax.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3505.fs)]

<span data-ttu-id="00a2f-142">Wenn Sie versuchen, ein Objekt zu verwenden, bevor sie vollständig definiert ist, können Probleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="00a2f-142">Problems can occur when you try to use an object before it is fully defined.</span></span> <span data-ttu-id="00a2f-143">Aus diesem Grund können Verwendungen von der Selbstbezeichner dazu führen, dass den Compiler eine Warnung ausgeben, und fügen Sie zusätzliche Überprüfungen durchgeführt, um sicherzustellen, dass der Member eines Objekts nicht zugegriffen werden, bevor das Objekt initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="00a2f-143">Therefore, uses of the self identifier can cause the compiler to emit a warning and insert additional checks to ensure the members of an object are not accessed before the object is initialized.</span></span> <span data-ttu-id="00a2f-144">Verwenden Sie ausschließlich den Selbstbezeichner in die `do` Bindungen von den primären Konstruktor oder nach der `then` -Schlüsselwort in weiteren Konstruktoren.</span><span class="sxs-lookup"><span data-stu-id="00a2f-144">You should only use the self identifier in the `do` bindings of the primary constructor, or after the `then` keyword in additional constructors.</span></span>

<span data-ttu-id="00a2f-145">Der Name des der Selbstbezeichner muss keine werden `this`.</span><span class="sxs-lookup"><span data-stu-id="00a2f-145">The name of the self identifier does not have to be `this`.</span></span> <span data-ttu-id="00a2f-146">Es kann ein gültiger Bezeichner sein.</span><span class="sxs-lookup"><span data-stu-id="00a2f-146">It can be any valid identifier.</span></span>


## <a name="assigning-values-to-properties-at-initialization"></a><span data-ttu-id="00a2f-147">Zuweisen von Werten zu Eigenschaften bei der Initialisierung</span><span class="sxs-lookup"><span data-stu-id="00a2f-147">Assigning Values to Properties at Initialization</span></span>
<span data-ttu-id="00a2f-148">Sie können die Eigenschaften eines Klassenobjekts in Initialisierungscode Werte zuweisen, durch Anfügen einer Liste von Zuweisungen der Form `property = value` an die Argumentliste für einen Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="00a2f-148">You can assign values to the properties of a class object in the initialization code by appending a list of assignments of the form `property = value` to the argument list for a constructor.</span></span> <span data-ttu-id="00a2f-149">Dies wird im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="00a2f-149">This is shown in the following code example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="00a2f-150">Die folgende Version der obige Code veranschaulicht die Kombination der normalen Argumente, optionale Argumente und eigenschafteneinstellungen in einen Konstruktoraufruf enthalten.</span><span class="sxs-lookup"><span data-stu-id="00a2f-150">The following version of the previous code illustrates the combination of ordinary arguments, optional arguments, and property settings in one constructor call.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3507.fs)]
    
## <a name="constructors-in-inherited-class"></a><span data-ttu-id="00a2f-151">Konstruktoren in einer geerbten Klasse</span><span class="sxs-lookup"><span data-stu-id="00a2f-151">Constructors in inherited class</span></span>
<span data-ttu-id="00a2f-152">Wenn von einer Basisklasse erben, die über einen Konstruktor verfügt, müssen Sie die Argumente in der erben-Klausel angeben.</span><span class="sxs-lookup"><span data-stu-id="00a2f-152">When inheriting from a base class that has a constructor, you must specify its arguments in the inherit clause.</span></span> <span data-ttu-id="00a2f-153">Weitere Informationen finden Sie unter [Konstruktoren und Vererbung](../inheritance.md#constructors-and-inheritance).</span><span class="sxs-lookup"><span data-stu-id="00a2f-153">For more information, see [Constructors and inheritance](../inheritance.md#constructors-and-inheritance).</span></span>

## <a name="static-constructors-or-type-constructors"></a><span data-ttu-id="00a2f-154">Statische Konstruktoren oder Typkonstruktoren</span><span class="sxs-lookup"><span data-stu-id="00a2f-154">Static Constructors or Type Constructors</span></span>
<span data-ttu-id="00a2f-155">Zusätzlich zum Angeben von Code zum Erstellen von Objekten, statische `let` und `do` Bindungen können in Klassentypen, die ausgeführt werden, bevor der Typ zuerst verwendet wird, für die Initialisierung auf Typebene erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="00a2f-155">In addition to specifying code for creating objects, static `let` and `do` bindings can be authored in class types that execute before the type is first used to perform initialization at the type level.</span></span> <span data-ttu-id="00a2f-156">Weitere Informationen finden Sie unter [ `let` Bindungen in Klassen](let-bindings-in-classes.md) und [ `do` Bindungen in Klassen](do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="00a2f-156">For more information, see [`let` Bindings in Classes](let-bindings-in-classes.md) and [`do` Bindings in Classes](do-bindings-in-classes.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="00a2f-157">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00a2f-157">See Also</span></span>
[<span data-ttu-id="00a2f-158">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="00a2f-158">Members</span></span>](index.md)
