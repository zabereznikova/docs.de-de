---
title: Konstruktoren
description: Informationen Sie zum Definieren und Verwenden von Konstruktoren in F# zu erstellen und initialisieren die Klasse und Struktur von Objekten.
ms.date: 05/16/2016
ms.openlocfilehash: 34989e2877b29f6f9fe1f6cc05e3fd7c90a1306a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61903967"
---
# <a name="constructors"></a><span data-ttu-id="b1e24-103">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="b1e24-103">Constructors</span></span>

<span data-ttu-id="b1e24-104">Dieses Thema beschreibt das Definieren und Verwenden von Konstruktoren zum Erstellen und Initialisieren von Objekten für Klasse und Struktur.</span><span class="sxs-lookup"><span data-stu-id="b1e24-104">This topic describes how to define and use constructors to create and initialize class and structure objects.</span></span>

## <a name="construction-of-class-objects"></a><span data-ttu-id="b1e24-105">Erstellung von Klassenobjekten</span><span class="sxs-lookup"><span data-stu-id="b1e24-105">Construction of Class Objects</span></span>

<span data-ttu-id="b1e24-106">Objekte von Klassentypen verfügen über Konstruktoren.</span><span class="sxs-lookup"><span data-stu-id="b1e24-106">Objects of class types have constructors.</span></span> <span data-ttu-id="b1e24-107">Es gibt zwei Arten von Konstruktoren.</span><span class="sxs-lookup"><span data-stu-id="b1e24-107">There are two kinds of constructors.</span></span> <span data-ttu-id="b1e24-108">Eine ist der primäre Konstruktor, dessen Parameter in Klammern direkt nach dem Typnamen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b1e24-108">One is the primary constructor, whose parameters appear in parentheses just after the type name.</span></span> <span data-ttu-id="b1e24-109">Sie andere, optionale zusätzliche Konstruktoren angeben, indem die `new` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="b1e24-109">You specify other, optional additional constructors by using the `new` keyword.</span></span> <span data-ttu-id="b1e24-110">Alle diese zusätzlichen Konstruktoren müssen den primären Konstruktor aufrufen.</span><span class="sxs-lookup"><span data-stu-id="b1e24-110">Any such additional constructors must call the primary constructor.</span></span>

<span data-ttu-id="b1e24-111">Der primäre Konstruktor enthält `let` und `do` Bindungen, die zu Beginn der Definition der Klasse angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b1e24-111">The primary constructor contains `let` and `do` bindings that appear at the start of the class definition.</span></span> <span data-ttu-id="b1e24-112">Ein `let` Bindung deklariert die privaten Felder und Methoden der Klasse; eine `do` Bindung führt Code aus.</span><span class="sxs-lookup"><span data-stu-id="b1e24-112">A `let` binding declares private fields and methods of the class; a `do` binding executes code.</span></span> <span data-ttu-id="b1e24-113">Weitere Informationen zu `let` Bindungen in der Klasse, Konstruktoren, finden Sie unter [ `let` Bindungen in Klassen](let-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="b1e24-113">For more information about `let` bindings in class constructors, see [`let` Bindings in Classes](let-bindings-in-classes.md).</span></span> <span data-ttu-id="b1e24-114">Weitere Informationen zu `do` Bindungen in Konstruktoren finden Sie unter [ `do` Bindungen in Klassen](do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="b1e24-114">For more information about `do` bindings in constructors, see [`do` Bindings in Classes](do-bindings-in-classes.md).</span></span>

<span data-ttu-id="b1e24-115">Unabhängig davon, ob der Konstruktor aufgerufen werden soll, einen primären Konstruktor oder einen zusätzlichen Konstruktor ist, können Sie Objekte erstellen, mit einem `new` Ausdruck, mit oder ohne die optionale `new` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="b1e24-115">Regardless of whether the constructor you want to call is a primary constructor or an additional constructor, you can create objects by using a `new` expression, with or without the optional `new` keyword.</span></span> <span data-ttu-id="b1e24-116">Sie initialisieren Ihre Objekte zusammen mit Konstruktorargumente, entweder durch Auflisten der Argumente in der Reihenfolge und durch Kommas getrennt und eingeschlossen in Klammern oder mithilfe von benannten Argumente und Werte in Klammern angegeben.</span><span class="sxs-lookup"><span data-stu-id="b1e24-116">You initialize your objects together with constructor arguments, either by listing the arguments in order and separated by commas and enclosed in parentheses, or by using named arguments and values in parentheses.</span></span> <span data-ttu-id="b1e24-117">Sie können Eigenschaften auch für ein Objekt während der Erstellung des Objekts festlegen, mit die Eigenschaftennamen und Zuweisen von Werten, genauso wie Sie mit dem Namen Konstruktorargumente.</span><span class="sxs-lookup"><span data-stu-id="b1e24-117">You can also set properties on an object during the construction of the object by using the property names and assigning values just as you use named constructor arguments.</span></span>

<span data-ttu-id="b1e24-118">Der folgende Code veranschaulicht eine Klasse mit einem Konstruktor und die verschiedenen Möglichkeiten zum Erstellen von Objekten.</span><span class="sxs-lookup"><span data-stu-id="b1e24-118">The following code illustrates a class that has a constructor and various ways of creating objects.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3501.fs)]

<span data-ttu-id="b1e24-119">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="b1e24-119">The output is as follows.</span></span>

```console
Initialized object that has coordinates (1, 2, 3)
Initialized object that has coordinates (4, 5, 6)
Initialized object that has coordinates (7, 8, 9)
Initialized object that has coordinates (0, 0, 0)
```

## <a name="construction-of-structures"></a><span data-ttu-id="b1e24-120">Erstellung von Strukturen</span><span class="sxs-lookup"><span data-stu-id="b1e24-120">Construction of Structures</span></span>

<span data-ttu-id="b1e24-121">Strukturen führen Sie alle Regeln der Klassen.</span><span class="sxs-lookup"><span data-stu-id="b1e24-121">Structures follow all the rules of classes.</span></span> <span data-ttu-id="b1e24-122">Aus diesem Grund können Sie einen primären Konstruktor verfügen, und Sie können zusätzliche Konstruktoren angeben, mit `new`.</span><span class="sxs-lookup"><span data-stu-id="b1e24-122">Therefore, you can have a primary constructor, and you can provide additional constructors by using `new`.</span></span> <span data-ttu-id="b1e24-123">Es ist jedoch ein wichtiger Unterschied zwischen Strukturen und Klassen: Strukturen können über einen Standardkonstruktor (d. h. eine ohne Argumente) verfügen, auch wenn keine primärer Konstruktor definiert ist.</span><span class="sxs-lookup"><span data-stu-id="b1e24-123">However, there is one important difference between structures and classes: structures can have a default constructor (that is, one with no arguments) even if no primary constructor is defined.</span></span> <span data-ttu-id="b1e24-124">Der Standardkonstruktor initialisiert alle Felder auf den Standardwert für diesen Typ, in der Regel 0 (null) oder dessen Entsprechung.</span><span class="sxs-lookup"><span data-stu-id="b1e24-124">The default constructor initializes all the fields to the default value for that type, usually zero or its equivalent.</span></span> <span data-ttu-id="b1e24-125">Keine Konstruktoren, die Sie für die Strukturen zu definieren, müssen mindestens ein Argument, damit sie nicht mit dem Standardkonstruktor in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="b1e24-125">Any constructors that you define for structures must have at least one argument so that they do not conflict with the default constructor.</span></span>

<span data-ttu-id="b1e24-126">Strukturen enthalten darüber hinaus oft Felder, die mit der `val` Schlüsselwort Klassen können auch über diese Felder verfügen.</span><span class="sxs-lookup"><span data-stu-id="b1e24-126">Also, structures often have fields that are created by using the `val` keyword; classes can also have these fields.</span></span> <span data-ttu-id="b1e24-127">Strukturen und Klassen, die mithilfe von definierten Felder den `val` Schlüsselwort kann auch in Konstruktoren initialisiert werden zusätzliche Datensatzausdrücken, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b1e24-127">Structures and classes that have fields defined by using the `val` keyword can also be initialized in additional constructors by using record expressions, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3502.fs)]

<span data-ttu-id="b1e24-128">Weitere Informationen finden Sie unter [explizite Felder: Die `val` Schlüsselwort](explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="b1e24-128">For more information, see [Explicit Fields: The `val` Keyword](explicit-fields-the-val-keyword.md).</span></span>

## <a name="executing-side-effects-in-constructors"></a><span data-ttu-id="b1e24-129">Ausführen von Nebeneffekten in Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="b1e24-129">Executing Side Effects in Constructors</span></span>

<span data-ttu-id="b1e24-130">Führen Sie ein primärer Konstruktor in einer Klasse kann Code in einem `do` Bindung.</span><span class="sxs-lookup"><span data-stu-id="b1e24-130">A primary constructor in a class can execute code in a `do` binding.</span></span> <span data-ttu-id="b1e24-131">Was geschieht, wenn Sie müssen jedoch ohne Ausführung von Code in einem zusätzlichen Konstruktor eine `do` Bindung?</span><span class="sxs-lookup"><span data-stu-id="b1e24-131">However, what if you have to execute code in an additional constructor, without a `do` binding?</span></span> <span data-ttu-id="b1e24-132">Zu diesem Zweck verwenden Sie die `then` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="b1e24-132">To do this, you use the `then` keyword.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3503.fs)]

<span data-ttu-id="b1e24-133">Die Nebeneffekte des primären Konstruktors ist immer noch ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b1e24-133">The side effects of the primary constructor still execute.</span></span> <span data-ttu-id="b1e24-134">Aus diesem Grund ist die Ausgabe wie folgt ein.</span><span class="sxs-lookup"><span data-stu-id="b1e24-134">Therefore, the output is as follows.</span></span>

```console
Created a person object.
Created a person object.
Created an invalid person object.
```

## <a name="self-identifiers-in-constructors"></a><span data-ttu-id="b1e24-135">Selbstbezeichner in Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="b1e24-135">Self Identifiers in Constructors</span></span>

<span data-ttu-id="b1e24-136">In anderen Mitgliedern geben Sie einen Namen für das aktuelle Objekt in der Definition der einzelnen Member.</span><span class="sxs-lookup"><span data-stu-id="b1e24-136">In other members, you provide a name for the current object in the definition of each member.</span></span> <span data-ttu-id="b1e24-137">Sie können auch den Selbstbezeichner in der ersten Zeile der Definition der Klasse einfügen, mit der `as` -Schlüsselwort direkt hinter der Parameter des Konstruktors.</span><span class="sxs-lookup"><span data-stu-id="b1e24-137">You can also put the self identifier on the first line of the class definition by using the `as` keyword immediately following the constructor parameters.</span></span> <span data-ttu-id="b1e24-138">Das folgende Beispiel veranschaulicht diese Syntax.</span><span class="sxs-lookup"><span data-stu-id="b1e24-138">The following example illustrates this syntax.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3504.fs)]

<span data-ttu-id="b1e24-139">In zusätzlichen Konstruktoren können Sie auch einen Selbstbezeichner definieren, durch Einfügen der `as` Klausel direkt nach dem Parameter des Konstruktors.</span><span class="sxs-lookup"><span data-stu-id="b1e24-139">In additional constructors, you can also define a self identifier by putting the `as` clause right after the constructor parameters.</span></span> <span data-ttu-id="b1e24-140">Das folgende Beispiel veranschaulicht diese Syntax.</span><span class="sxs-lookup"><span data-stu-id="b1e24-140">The following example illustrates this syntax.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3505.fs)]

<span data-ttu-id="b1e24-141">Es können Probleme auftreten, wenn Sie versuchen, ein Objekt zu verwenden, bevor sie vollständig definiert ist.</span><span class="sxs-lookup"><span data-stu-id="b1e24-141">Problems can occur when you try to use an object before it is fully defined.</span></span> <span data-ttu-id="b1e24-142">Aus diesem Grund kann der Selbstbezeichner verwendet den Compiler eine Warnung ausgeben, und fügen Sie zusätzliche Überprüfungen, um sicherzustellen, dass der Member eines Objekts nicht zugegriffen werden, bevor das Objekt initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="b1e24-142">Therefore, uses of the self identifier can cause the compiler to emit a warning and insert additional checks to ensure the members of an object are not accessed before the object is initialized.</span></span> <span data-ttu-id="b1e24-143">Verwenden Sie nur den Selbstbezeichner in die `do` Bindungen des primären Konstruktors oder nach der `then` -Schlüsselwort in zusätzliche Konstruktoren.</span><span class="sxs-lookup"><span data-stu-id="b1e24-143">You should only use the self identifier in the `do` bindings of the primary constructor, or after the `then` keyword in additional constructors.</span></span>

<span data-ttu-id="b1e24-144">Der Name des der Selbstbezeichner muss keine werden `this`.</span><span class="sxs-lookup"><span data-stu-id="b1e24-144">The name of the self identifier does not have to be `this`.</span></span> <span data-ttu-id="b1e24-145">Es kann jeder gültige Bezeichner sein.</span><span class="sxs-lookup"><span data-stu-id="b1e24-145">It can be any valid identifier.</span></span>

## <a name="assigning-values-to-properties-at-initialization"></a><span data-ttu-id="b1e24-146">Zuweisen von Werten zu Eigenschaften, die bei der Initialisierung</span><span class="sxs-lookup"><span data-stu-id="b1e24-146">Assigning Values to Properties at Initialization</span></span>

<span data-ttu-id="b1e24-147">Sie können die Eigenschaften eines Klassenobjekts im Initialisierungscode Werte zuweisen, durch eine Liste der Zuweisungen der Form Anfügen `property = value` an die Argumentliste für einen Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="b1e24-147">You can assign values to the properties of a class object in the initialization code by appending a list of assignments of the form `property = value` to the argument list for a constructor.</span></span> <span data-ttu-id="b1e24-148">Dies wird im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b1e24-148">This is shown in the following code example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="b1e24-149">Die folgende Version des obigen Codes zeigt die Kombination der normale Argumente und optionale Argumente eigenschafteneinstellungen in einen Konstruktoraufruf enthalten.</span><span class="sxs-lookup"><span data-stu-id="b1e24-149">The following version of the previous code illustrates the combination of ordinary arguments, optional arguments, and property settings in one constructor call.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3507.fs)]

## <a name="constructors-in-inherited-class"></a><span data-ttu-id="b1e24-150">Konstruktoren in der geerbten Klasse</span><span class="sxs-lookup"><span data-stu-id="b1e24-150">Constructors in inherited class</span></span>

<span data-ttu-id="b1e24-151">Wenn von einer Basisklasse zu erben, die über einen Konstruktor verfügt, müssen Sie die Argumente in der Klausel erben angeben.</span><span class="sxs-lookup"><span data-stu-id="b1e24-151">When inheriting from a base class that has a constructor, you must specify its arguments in the inherit clause.</span></span> <span data-ttu-id="b1e24-152">Weitere Informationen finden Sie unter [Konstruktoren und Vererbung](../inheritance.md#constructors-and-inheritance).</span><span class="sxs-lookup"><span data-stu-id="b1e24-152">For more information, see [Constructors and inheritance](../inheritance.md#constructors-and-inheritance).</span></span>

## <a name="static-constructors-or-type-constructors"></a><span data-ttu-id="b1e24-153">Statische Konstruktoren oder Konstruktoren Typen</span><span class="sxs-lookup"><span data-stu-id="b1e24-153">Static Constructors or Type Constructors</span></span>

<span data-ttu-id="b1e24-154">Zusätzlich zur Angabe von Code zum Erstellen von Objekten, statische `let` und `do` Bindungen in Klassentypen, die ausgeführt werden, bevor der Typ zuerst verwendet wird, für die Initialisierung auf Typebene erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="b1e24-154">In addition to specifying code for creating objects, static `let` and `do` bindings can be authored in class types that execute before the type is first used to perform initialization at the type level.</span></span> <span data-ttu-id="b1e24-155">Weitere Informationen finden Sie unter [ `let` Bindungen in Klassen](let-bindings-in-classes.md) und [ `do` Bindungen in Klassen](do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="b1e24-155">For more information, see [`let` Bindings in Classes](let-bindings-in-classes.md) and [`do` Bindings in Classes](do-bindings-in-classes.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b1e24-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1e24-156">See also</span></span>

- [<span data-ttu-id="b1e24-157">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="b1e24-157">Members</span></span>](index.md)