---
title: Dim-Anweisung
ms.date: 05/12/2018
f1_keywords:
- vb.Dim
- Dim
helpviewer_keywords:
- Public keyword [Visual Basic], in Dim statement
- Dim statement [Visual Basic]
- fixed-length strings [Visual Basic], declaring
- variables [Visual Basic], declaring
- WithEvents keyword [Visual Basic], Dim statement
- dynamic arrays [Visual Basic], Dim statement
- variables [Visual Basic], initializing
- '{} braces'
- fields [Visual Basic], as member variables
- declarations [Visual Basic], dynamic arrays
- member variables [Visual Basic]
- default values [Visual Basic]
- data types [Visual Basic], assigning
- braces {}
- As keyword [Visual Basic], in Dim statement
- arrays [Visual Basic], declaring
- New keyword [Visual Basic], Dim statement
- To keyword [Visual Basic], in Dim statement
- storage [Visual Basic], allocating
- local variables [Visual Basic]
- declaration statements [Visual Basic]
- Dim statement [Visual Basic], syntax
- variables [Visual Basic], member and local
ms.assetid: fae3eca1-f0b2-4400-994b-7aa58a848448
ms.openlocfilehash: 1b0c3089c366c417af926c8c0703cea021674432
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744721"
---
# <a name="dim-statement-visual-basic"></a><span data-ttu-id="06ecc-102">Dim-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="06ecc-102">Dim statement (Visual Basic)</span></span>

<span data-ttu-id="06ecc-103">Deklariert und ordnet Speicherplatz für eine oder mehrere Variablen zu.</span><span class="sxs-lookup"><span data-stu-id="06ecc-103">Declares and allocates storage space for one or more variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="06ecc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="06ecc-104">Syntax</span></span>

```vb
[ <attributelist> ] [ accessmodifier ] [[ Shared ] [ Shadows ] | [ Static ]] [ ReadOnly ]
Dim [ WithEvents ] variablelist
```

## <a name="parts"></a><span data-ttu-id="06ecc-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="06ecc-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="06ecc-106">Optional.</span><span class="sxs-lookup"><span data-stu-id="06ecc-106">Optional.</span></span> <span data-ttu-id="06ecc-107">Siehe [Attribut Liste](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="06ecc-107">See [Attribute List](attribute-list.md).</span></span>

- `accessmodifier`

  <span data-ttu-id="06ecc-108">Optional.</span><span class="sxs-lookup"><span data-stu-id="06ecc-108">Optional.</span></span> <span data-ttu-id="06ecc-109">Dabei kann es sich um eine der folgenden Methoden handeln:</span><span class="sxs-lookup"><span data-stu-id="06ecc-109">Can be one of the following:</span></span>

  - [<span data-ttu-id="06ecc-110">Public</span><span class="sxs-lookup"><span data-stu-id="06ecc-110">Public</span></span>](../modifiers/public.md)

  - [<span data-ttu-id="06ecc-111">Protected</span><span class="sxs-lookup"><span data-stu-id="06ecc-111">Protected</span></span>](../modifiers/protected.md)

  - [<span data-ttu-id="06ecc-112">Friend</span><span class="sxs-lookup"><span data-stu-id="06ecc-112">Friend</span></span>](../modifiers/friend.md)

  - [<span data-ttu-id="06ecc-113">Privat</span><span class="sxs-lookup"><span data-stu-id="06ecc-113">Private</span></span>](../modifiers/private.md)

  - [<span data-ttu-id="06ecc-114">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="06ecc-114">Protected Friend</span></span>](../modifiers/protected-friend.md)

  - [<span data-ttu-id="06ecc-115">Private Protected</span><span class="sxs-lookup"><span data-stu-id="06ecc-115">Private Protected</span></span>](../modifiers/private-protected.md)

  <span data-ttu-id="06ecc-116">Siehe [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="06ecc-116">See [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `Shared`

  <span data-ttu-id="06ecc-117">Optional.</span><span class="sxs-lookup"><span data-stu-id="06ecc-117">Optional.</span></span> <span data-ttu-id="06ecc-118">Siehe [Shared](../modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="06ecc-118">See [Shared](../modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="06ecc-119">Optional.</span><span class="sxs-lookup"><span data-stu-id="06ecc-119">Optional.</span></span> <span data-ttu-id="06ecc-120">Siehe [Shadows](../modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="06ecc-120">See [Shadows](../modifiers/shadows.md).</span></span>

- `Static`

  <span data-ttu-id="06ecc-121">Optional.</span><span class="sxs-lookup"><span data-stu-id="06ecc-121">Optional.</span></span> <span data-ttu-id="06ecc-122">Siehe [static](../modifiers/static.md).</span><span class="sxs-lookup"><span data-stu-id="06ecc-122">See [Static](../modifiers/static.md).</span></span>

- `ReadOnly`

  <span data-ttu-id="06ecc-123">Optional.</span><span class="sxs-lookup"><span data-stu-id="06ecc-123">Optional.</span></span> <span data-ttu-id="06ecc-124">Siehe [nur](../modifiers/readonly.md)lesen.</span><span class="sxs-lookup"><span data-stu-id="06ecc-124">See [ReadOnly](../modifiers/readonly.md).</span></span>

- `WithEvents`

  <span data-ttu-id="06ecc-125">Optional.</span><span class="sxs-lookup"><span data-stu-id="06ecc-125">Optional.</span></span> <span data-ttu-id="06ecc-126">Gibt an, dass es sich hierbei um Objektvariablen handelt, die auf Instanzen einer Klasse verweisen, die Ereignisse hervorrufen können.</span><span class="sxs-lookup"><span data-stu-id="06ecc-126">Specifies that these are object variables that refer to instances of a class that can raise events.</span></span> <span data-ttu-id="06ecc-127">Siehe [wiwitvents](../modifiers/withevents.md).</span><span class="sxs-lookup"><span data-stu-id="06ecc-127">See [WithEvents](../modifiers/withevents.md).</span></span>

- `variablelist`

  <span data-ttu-id="06ecc-128">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="06ecc-128">Required.</span></span> <span data-ttu-id="06ecc-129">Liste der Variablen, die in dieser Anweisung deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="06ecc-129">List of variables being declared in this statement.</span></span>

  `variable [ , variable ... ]`

  <span data-ttu-id="06ecc-130">Jede `variable` weist folgende Syntax und Bestandteile auf:</span><span class="sxs-lookup"><span data-stu-id="06ecc-130">Each `variable` has the following syntax and parts:</span></span>

  <span data-ttu-id="06ecc-131">`variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="06ecc-131">`variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`</span></span>

  |<span data-ttu-id="06ecc-132">Teil</span><span class="sxs-lookup"><span data-stu-id="06ecc-132">Part</span></span>|<span data-ttu-id="06ecc-133">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="06ecc-133">Description</span></span>|
  |---|---|
  |`variablename`|<span data-ttu-id="06ecc-134">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="06ecc-134">Required.</span></span> <span data-ttu-id="06ecc-135">Name der Variable.</span><span class="sxs-lookup"><span data-stu-id="06ecc-135">Name of the variable.</span></span> <span data-ttu-id="06ecc-136">Siehe [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="06ecc-136">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|
  |`boundslist`|<span data-ttu-id="06ecc-137">Optional.</span><span class="sxs-lookup"><span data-stu-id="06ecc-137">Optional.</span></span> <span data-ttu-id="06ecc-138">Die Liste der Begrenzungen der einzelnen Dimensionen einer Array Variablen.</span><span class="sxs-lookup"><span data-stu-id="06ecc-138">List of bounds of each dimension of an array variable.</span></span>|
  |`New`|<span data-ttu-id="06ecc-139">Optional.</span><span class="sxs-lookup"><span data-stu-id="06ecc-139">Optional.</span></span> <span data-ttu-id="06ecc-140">Erstellt eine neue Instanz der-Klasse, wenn die `Dim`-Anweisung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="06ecc-140">Creates a new instance of the class when the `Dim` statement runs.</span></span>|
  |`datatype`|<span data-ttu-id="06ecc-141">Optional.</span><span class="sxs-lookup"><span data-stu-id="06ecc-141">Optional.</span></span> <span data-ttu-id="06ecc-142">Datentyp der Variablen.</span><span class="sxs-lookup"><span data-stu-id="06ecc-142">Data type of the variable.</span></span>|
  |`With`|<span data-ttu-id="06ecc-143">Optional.</span><span class="sxs-lookup"><span data-stu-id="06ecc-143">Optional.</span></span> <span data-ttu-id="06ecc-144">Führt die Objektinitialisiererliste ein.</span><span class="sxs-lookup"><span data-stu-id="06ecc-144">Introduces the object initializer list.</span></span>|
  |`propertyname`|<span data-ttu-id="06ecc-145">Optional.</span><span class="sxs-lookup"><span data-stu-id="06ecc-145">Optional.</span></span> <span data-ttu-id="06ecc-146">Der Name einer Eigenschaft in der Klasse, von der Sie eine Instanz erstellen.</span><span class="sxs-lookup"><span data-stu-id="06ecc-146">The name of a property in the class you are making an instance of.</span></span>|
  |`propinitializer`|<span data-ttu-id="06ecc-147">Erforderlich nach `propertyname` =.</span><span class="sxs-lookup"><span data-stu-id="06ecc-147">Required after `propertyname` =.</span></span> <span data-ttu-id="06ecc-148">Der Ausdruck, der ausgewertet und dem Eigenschaftsnamen zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="06ecc-148">The expression that is evaluated and assigned to the property name.</span></span>|
  |`initializer`|<span data-ttu-id="06ecc-149">Optional, wenn `New` nicht angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="06ecc-149">Optional if `New` is not specified.</span></span> <span data-ttu-id="06ecc-150">Ausdruck, der ausgewertet und der Variablen bei der Erstellung zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="06ecc-150">Expression that is evaluated and assigned to the variable when it is created.</span></span>|

## <a name="remarks"></a><span data-ttu-id="06ecc-151">Hinweise</span><span class="sxs-lookup"><span data-stu-id="06ecc-151">Remarks</span></span>

<span data-ttu-id="06ecc-152">Der Visual Basic-Compiler verwendet die `Dim`-Anweisung, um den Datentyp der Variablen und andere Informationen zu bestimmen, z. b. den Code, auf den die Variable zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="06ecc-152">The Visual Basic compiler uses the `Dim` statement to determine the variable's data type and other information, such as what code can access the variable.</span></span> <span data-ttu-id="06ecc-153">Im folgenden Beispiel wird eine Variable deklariert, die einen `Integer` Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="06ecc-153">The following example declares a variable to hold an `Integer` value.</span></span>

```vb
Dim numberOfStudents As Integer
```

<span data-ttu-id="06ecc-154">Sie können einen beliebigen Datentyp oder den Namen einer Enumeration, Struktur, Klasse oder Schnittstelle angeben.</span><span class="sxs-lookup"><span data-stu-id="06ecc-154">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>

```vb
Dim finished As Boolean
Dim monitorBox As System.Windows.Forms.Form
```

<span data-ttu-id="06ecc-155">Für einen Referenztyp verwenden Sie das `New`-Schlüsselwort, um eine neue Instanz der Klasse oder Struktur zu erstellen, die durch den-Datentyp angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="06ecc-155">For a reference type, you use the `New` keyword to create a new instance of the class or structure that is specified by the data type.</span></span> <span data-ttu-id="06ecc-156">Wenn Sie `New`verwenden, verwenden Sie keinen initialisiererausdruck.</span><span class="sxs-lookup"><span data-stu-id="06ecc-156">If you use `New`, you do not use an initializer expression.</span></span> <span data-ttu-id="06ecc-157">Stattdessen geben Sie Argumente (falls erforderlich) an den Konstruktor der Klasse an, aus der Sie die Variable erstellen.</span><span class="sxs-lookup"><span data-stu-id="06ecc-157">Instead, you supply arguments, if they are required, to the constructor of the class from which you are creating the variable.</span></span>

```vb
Dim bottomLabel As New System.Windows.Forms.Label
```

<span data-ttu-id="06ecc-158">Sie können eine Variable in einer Prozedur, einem Block, einer Klasse, einer Struktur oder einem Modul deklarieren.</span><span class="sxs-lookup"><span data-stu-id="06ecc-158">You can declare a variable in a procedure, block, class, structure, or module.</span></span> <span data-ttu-id="06ecc-159">Sie können eine Variable nicht in einer Quelldatei, einem Namespace oder einer Schnittstelle deklarieren.</span><span class="sxs-lookup"><span data-stu-id="06ecc-159">You cannot declare a variable in a source file, namespace, or interface.</span></span> <span data-ttu-id="06ecc-160">Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="06ecc-160">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="06ecc-161">Eine Variable, die auf Modulebene, außerhalb einer Prozedur deklariert wird, ist eine *Member-Variable* oder ein- *Feld*.</span><span class="sxs-lookup"><span data-stu-id="06ecc-161">A variable that is declared at module level, outside any procedure, is a *member variable* or *field*.</span></span> <span data-ttu-id="06ecc-162">Element Variablen befinden sich im Gültigkeitsbereich der Klasse, Struktur oder des Moduls.</span><span class="sxs-lookup"><span data-stu-id="06ecc-162">Member variables are in scope throughout their class, structure, or module.</span></span> <span data-ttu-id="06ecc-163">Eine Variable, die auf Prozedur Ebene deklariert wird, ist eine *lokale Variable*.</span><span class="sxs-lookup"><span data-stu-id="06ecc-163">A variable that is declared at procedure level is a *local variable*.</span></span> <span data-ttu-id="06ecc-164">Lokale Variablen befinden sich nur innerhalb ihrer Prozedur oder Ihres Blocks im Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="06ecc-164">Local variables are in scope only within their procedure or block.</span></span>

<span data-ttu-id="06ecc-165">Die folgenden Zugriffsmodifizierer werden verwendet, um Variablen außerhalb einer Prozedur zu deklarieren: `Public`, `Protected`, `Friend`, `Protected Friend`und `Private`.</span><span class="sxs-lookup"><span data-stu-id="06ecc-165">The following access modifiers are used to declare variables outside a procedure: `Public`, `Protected`, `Friend`, `Protected Friend`, and `Private`.</span></span> <span data-ttu-id="06ecc-166">Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="06ecc-166">For more information, see [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="06ecc-167">Das `Dim`-Schlüsselwort ist optional und wird normalerweise ausgelassen, wenn Sie einen der folgenden Modifizierer angeben: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`oder `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="06ecc-167">The `Dim` keyword is optional and usually omitted if you specify any of the following modifiers: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, or `WithEvents`.</span></span>

```vb
Public maximumAllowed As Double
Protected Friend currentUserName As String
Private salary As Decimal
Static runningTotal As Integer
```

<span data-ttu-id="06ecc-168">Wenn `Option Explicit` aktiviert ist (Standardeinstellung), benötigt der Compiler eine Deklaration für jede Variable, die Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="06ecc-168">If `Option Explicit` is on (the default), the compiler requires a declaration for every variable you use.</span></span> <span data-ttu-id="06ecc-169">Weitere Informationen finden Sie unter [Option explizite Anweisung](option-explicit-statement.md).</span><span class="sxs-lookup"><span data-stu-id="06ecc-169">For more information, see [Option Explicit Statement](option-explicit-statement.md).</span></span>

## <a name="specifying-an-initial-value"></a><span data-ttu-id="06ecc-170">Angeben eines Anfangs Werts</span><span class="sxs-lookup"><span data-stu-id="06ecc-170">Specifying an initial value</span></span>

<span data-ttu-id="06ecc-171">Sie können einer Variablen einen Wert zuweisen, wenn Sie erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="06ecc-171">You can assign a value to a variable when it is created.</span></span> <span data-ttu-id="06ecc-172">Bei einem Werttyp verwenden Sie einen *Initialisierer* , um einen Ausdruck anzugeben, der der Variablen zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="06ecc-172">For a value type, you use an *initializer* to supply an expression to be assigned to the variable.</span></span> <span data-ttu-id="06ecc-173">Der Ausdruck muss zu einer Konstanten ausgewertet werden, die zur Kompilierzeit berechnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="06ecc-173">The expression must evaluate to a constant that can be calculated at compile time.</span></span>

```vb
Dim quantity As Integer = 10
Dim message As String = "Just started"
```

<span data-ttu-id="06ecc-174">Wenn ein Initialisierer angegeben wird und ein Datentyp nicht in einer `As`-Klausel angegeben ist, wird der *Typrückschluss* verwendet, um den Datentyp vom Initialisierer abzuleiten.</span><span class="sxs-lookup"><span data-stu-id="06ecc-174">If an initializer is specified and a data type is not specified in an `As` clause, *type inference* is used to infer the data type from the initializer.</span></span> <span data-ttu-id="06ecc-175">Im folgenden Beispiel sind sowohl `num1` als auch `num2` stark als ganze Zahlen typisiert.</span><span class="sxs-lookup"><span data-stu-id="06ecc-175">In the following example, both `num1` and `num2` are strongly typed as integers.</span></span> <span data-ttu-id="06ecc-176">In der zweiten Deklaration leitet der Typrückschluss den Typ aus dem Wert 3 ab.</span><span class="sxs-lookup"><span data-stu-id="06ecc-176">In the second declaration, type inference infers the type from the value 3.</span></span>

```vb
' Use explicit typing.
Dim num1 As Integer = 3

' Use local type inference.
Dim num2 = 3
```

<span data-ttu-id="06ecc-177">Der Typrückschluss gilt für die Prozedur Ebene.</span><span class="sxs-lookup"><span data-stu-id="06ecc-177">Type inference applies at the procedure level.</span></span> <span data-ttu-id="06ecc-178">Sie gilt nicht außerhalb einer Prozedur in einer Klasse, Struktur, einem Modul oder einer Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="06ecc-178">It does not apply outside a procedure in a class, structure, module, or interface.</span></span> <span data-ttu-id="06ecc-179">Weitere Informationen zum Typrückschluss finden Sie unter [Option Infer-Anweisung](option-infer-statement.md) und [lokaler Typrückschluss](../../programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="06ecc-179">For more information about type inference, see [Option Infer Statement](option-infer-statement.md) and [Local Type Inference](../../programming-guide/language-features/variables/local-type-inference.md).</span></span>

<span data-ttu-id="06ecc-180">Informationen dazu, was geschieht, wenn ein Datentyp oder ein Initialisierer nicht angegeben wird, finden Sie unter [Standard Datentypen und-Werte](dim-statement.md#default) weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="06ecc-180">For information about what happens when a data type or initializer is not specified, see [Default Data Types and Values](dim-statement.md#default) later in this topic.</span></span>

<span data-ttu-id="06ecc-181">Sie können einen *Objektinitialisierer* verwenden, um Instanzen von benannten und anonymen Typen zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="06ecc-181">You can use an *object initializer* to declare instances of named and anonymous types.</span></span> <span data-ttu-id="06ecc-182">Der folgende Code erstellt eine Instanz einer `Student`-Klasse und verwendet einen Objektinitialisierer, um Eigenschaften zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="06ecc-182">The following code creates an instance of a `Student` class and uses an object initializer to initialize properties.</span></span>

```vb
Dim student1 As New Student With {.First = "Michael",
                                  .Last = "Tucker"}
```

<span data-ttu-id="06ecc-183">Weitere Informationen zu Objektinitialisierern finden Sie unter Gewusst [wie: Deklarieren eines Objekts mithilfe eines Objektinitialisierers](../../programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [Objektinitialisierer: benannte und anonyme Typen](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)und [Anonyme Typen](../../programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="06ecc-183">For more information about object initializers, see [How to: Declare an Object by Using an Object Initializer](../../programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [Object Initializers: Named and Anonymous Types](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), and [Anonymous Types](../../programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>

## <a name="declaring-multiple-variables"></a><span data-ttu-id="06ecc-184">Deklarieren mehrerer Variablen</span><span class="sxs-lookup"><span data-stu-id="06ecc-184">Declaring multiple variables</span></span>

<span data-ttu-id="06ecc-185">Sie können mehrere Variablen in einer Deklarations Anweisung deklarieren, den Variablennamen für jede Deklaration angeben und den einzelnen Array Namen mit Klammern folgen.</span><span class="sxs-lookup"><span data-stu-id="06ecc-185">You can declare several variables in one declaration statement, specifying the variable name for each one, and following each array name with parentheses.</span></span> <span data-ttu-id="06ecc-186">Mehrere Variablen werden durch Kommas voneinander getrennt.</span><span class="sxs-lookup"><span data-stu-id="06ecc-186">Multiple variables are separated by commas.</span></span>

```vb
Dim lastTime, nextTime, allTimes() As Date
```

<span data-ttu-id="06ecc-187">Wenn Sie mehr als eine Variable mit einer `As`-Klausel deklarieren, können Sie keinen Initialisierer für diese Gruppe von Variablen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="06ecc-187">If you declare more than one variable with one `As` clause, you cannot supply an initializer for that group of variables.</span></span>

<span data-ttu-id="06ecc-188">Sie können unterschiedliche Datentypen für verschiedene Variablen angeben, indem Sie für jede deklarierte Variable eine separate `As`-Klausel verwenden.</span><span class="sxs-lookup"><span data-stu-id="06ecc-188">You can specify different data types for different variables by using a separate `As` clause for each variable you declare.</span></span> <span data-ttu-id="06ecc-189">Jede Variable übernimmt den Datentyp, der in der ersten `As`-Klausel nach dem `variablename` Teil angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="06ecc-189">Each variable takes the data type specified in the first `As` clause encountered after its `variablename` part.</span></span>

```vb
Dim a, b, c As Single, x, y As Double, i As Integer
' a, b, and c are all Single; x and y are both Double
```

## <a name="arrays"></a><span data-ttu-id="06ecc-190">Arrays</span><span class="sxs-lookup"><span data-stu-id="06ecc-190">Arrays</span></span>

<span data-ttu-id="06ecc-191">Sie können eine Variable so deklarieren, dass Sie ein *Array*enthält, das mehrere Werte enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="06ecc-191">You can declare a variable to hold an *array*, which can hold multiple values.</span></span> <span data-ttu-id="06ecc-192">Um anzugeben, dass eine Variable ein Array enthält, befolgen Sie die entsprechenden `variablename` sofort mit Klammern.</span><span class="sxs-lookup"><span data-stu-id="06ecc-192">To specify that a variable holds an array, follow its `variablename` immediately with parentheses.</span></span> <span data-ttu-id="06ecc-193">Weitere Informationen zu Arrays finden Sie unter [Arrays](../../programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="06ecc-193">For more information about arrays, see [Arrays](../../programming-guide/language-features/arrays/index.md).</span></span>

<span data-ttu-id="06ecc-194">Sie können die untere und obere Grenze der einzelnen Dimensionen eines Arrays angeben.</span><span class="sxs-lookup"><span data-stu-id="06ecc-194">You can specify the lower and upper bound of each dimension of an array.</span></span> <span data-ttu-id="06ecc-195">Fügen Sie zu diesem Zweck eine `boundslist` in die Klammern ein.</span><span class="sxs-lookup"><span data-stu-id="06ecc-195">To do this, include a `boundslist` inside the parentheses.</span></span> <span data-ttu-id="06ecc-196">Für jede Dimension gibt das `boundslist` die obere Grenze und optional die untere Grenze an.</span><span class="sxs-lookup"><span data-stu-id="06ecc-196">For each dimension, the `boundslist` specifies the upper bound and optionally the lower bound.</span></span> <span data-ttu-id="06ecc-197">Die untere Grenze ist immer 0 (null), unabhängig davon, ob Sie Sie angeben oder nicht.</span><span class="sxs-lookup"><span data-stu-id="06ecc-197">The lower bound is always zero, whether you specify it or not.</span></span> <span data-ttu-id="06ecc-198">Jeder Index kann von 0 (null) bis zum oberen Grenzwert abweichen.</span><span class="sxs-lookup"><span data-stu-id="06ecc-198">Each index can vary from zero through its upper bound value.</span></span>

<span data-ttu-id="06ecc-199">Die folgenden zwei Anweisungen sind gleichwertig.</span><span class="sxs-lookup"><span data-stu-id="06ecc-199">The following two statements are equivalent.</span></span> <span data-ttu-id="06ecc-200">Jede-Anweisung deklariert ein Array aus 21 `Integer`-Elementen.</span><span class="sxs-lookup"><span data-stu-id="06ecc-200">Each statement declares an array of 21 `Integer` elements.</span></span> <span data-ttu-id="06ecc-201">Wenn Sie auf das Array zugreifen, kann der Index von 0 bis 20 abweichen.</span><span class="sxs-lookup"><span data-stu-id="06ecc-201">When you access the array, the index can vary from 0 through 20.</span></span>

```vb
Dim totals(20) As Integer
Dim totals(0 To 20) As Integer
```

<span data-ttu-id="06ecc-202">Mit der folgenden Anweisung wird ein zweidimensionales Array vom Typ "`Double`" deklariert.</span><span class="sxs-lookup"><span data-stu-id="06ecc-202">The following statement declares a two-dimensional array of type `Double`.</span></span> <span data-ttu-id="06ecc-203">Das Array hat vier Zeilen (3 + 1) von 6 Spalten (jeweils 5 + 1).</span><span class="sxs-lookup"><span data-stu-id="06ecc-203">The array has 4 rows (3 + 1) of 6 columns (5 + 1) each.</span></span> <span data-ttu-id="06ecc-204">Beachten Sie, dass eine obere Grenze den höchstmöglichen Wert für den Index und nicht die Länge der Dimension darstellt.</span><span class="sxs-lookup"><span data-stu-id="06ecc-204">Note that an upper bound represents the highest possible value for the index, not the length of the dimension.</span></span> <span data-ttu-id="06ecc-205">Die Länge der Dimension ist die obere Grenze plus 1.</span><span class="sxs-lookup"><span data-stu-id="06ecc-205">The length of the dimension is the upper bound plus one.</span></span>

```vb
Dim matrix2(3, 5) As Double
```

<span data-ttu-id="06ecc-206">Ein Array kann zwischen 1 und 32 Dimensionen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="06ecc-206">An array can have from 1 to 32 dimensions.</span></span>

<span data-ttu-id="06ecc-207">Sie können alle Begrenzungen in einer Array Deklaration leer lassen.</span><span class="sxs-lookup"><span data-stu-id="06ecc-207">You can leave all the bounds blank in an array declaration.</span></span> <span data-ttu-id="06ecc-208">Wenn Sie dies tun, verfügt das Array über die Anzahl der Dimensionen, die Sie angeben, aber es ist nicht initialisiert.</span><span class="sxs-lookup"><span data-stu-id="06ecc-208">If you do this, the array has the number of dimensions you specify, but it is uninitialized.</span></span> <span data-ttu-id="06ecc-209">Sie weist den Wert `Nothing` auf, bis Sie mindestens einige ihrer Elemente initialisieren.</span><span class="sxs-lookup"><span data-stu-id="06ecc-209">It has a value of `Nothing` until you initialize at least some of its elements.</span></span> <span data-ttu-id="06ecc-210">Die `Dim`-Anweisung muss Begrenzungen entweder für alle Dimensionen oder für keine Dimensionen angeben.</span><span class="sxs-lookup"><span data-stu-id="06ecc-210">The `Dim` statement must specify bounds either for all dimensions or for no dimensions.</span></span>

```vb
' Declare an array with blank array bounds.
Dim messages() As String
' Initialize the array.
ReDim messages(4)
```

<span data-ttu-id="06ecc-211">Wenn das Array über mehr als eine Dimension verfügt, müssen Sie Kommas zwischen den Klammern einschließen, um die Anzahl der Dimensionen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="06ecc-211">If the array has more than one dimension, you must include commas between the parentheses to indicate the number of dimensions.</span></span>

```vb
Dim oneDimension(), twoDimensions(,), threeDimensions(,,) As Byte
```

<span data-ttu-id="06ecc-212">Sie können ein *Array der Länge 0 (null* ) deklarieren, indem Sie eine der Dimensionen des Arrays als-1 deklarieren.</span><span class="sxs-lookup"><span data-stu-id="06ecc-212">You can declare a *zero-length array* by declaring one of the array's dimensions to be -1.</span></span> <span data-ttu-id="06ecc-213">Eine Variable, die ein Array der Länge 0 (null) enthält, hat nicht den Wert `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="06ecc-213">A variable that holds a zero-length array does not have the value `Nothing`.</span></span> <span data-ttu-id="06ecc-214">Arrays der Länge 0 (null) sind für bestimmte Common Language Runtime Funktionen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="06ecc-214">Zero-length arrays are required by certain common language runtime functions.</span></span> <span data-ttu-id="06ecc-215">Wenn Sie versuchen, auf ein solches Array zuzugreifen, tritt eine Lauf Zeit Ausnahme auf.</span><span class="sxs-lookup"><span data-stu-id="06ecc-215">If you try to access such an array, a runtime exception occurs.</span></span> <span data-ttu-id="06ecc-216">Weitere Informationen finden Sie unter [Arrays](../../programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="06ecc-216">For more information, see [Arrays](../../programming-guide/language-features/arrays/index.md).</span></span>

<span data-ttu-id="06ecc-217">Sie können die Werte eines Arrays mithilfe eines Arrayliterals initialisieren.</span><span class="sxs-lookup"><span data-stu-id="06ecc-217">You can initialize the values of an array by using an array literal.</span></span> <span data-ttu-id="06ecc-218">Umschließen Sie zu diesem Zweck die Initialisierungs Werte mit geschweiften Klammern (`{}`).</span><span class="sxs-lookup"><span data-stu-id="06ecc-218">To do this, surround the initialization values with braces (`{}`).</span></span>

```vb
Dim longArray() As Long = {0, 1, 2, 3}
```

<span data-ttu-id="06ecc-219">Bei mehrdimensionalen Arrays wird die Initialisierung für jede separate Dimension in geschweifte Klammern in der äußeren Dimension eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="06ecc-219">For multidimensional arrays, the initialization for each separate dimension is enclosed in braces in the outer dimension.</span></span> <span data-ttu-id="06ecc-220">Die Elemente werden in der Reihenfolge der Zeilen angegeben.</span><span class="sxs-lookup"><span data-stu-id="06ecc-220">The elements are specified in row-major order.</span></span>

```vb
Dim twoDimensions(,) As Integer = {{0, 1, 2}, {10, 11, 12}}
```

<span data-ttu-id="06ecc-221">Weitere Informationen zu Array literalen finden Sie unter [Arrays](../../programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="06ecc-221">For more information about array literals, see [Arrays](../../programming-guide/language-features/arrays/index.md).</span></span>

## <a name="default"></a><span data-ttu-id="06ecc-222">Standard Datentypen und-Werte</span><span class="sxs-lookup"><span data-stu-id="06ecc-222">Default data types and values</span></span>

<span data-ttu-id="06ecc-223">Die folgende Tabelle beschreibt die Ergebnisse der verschiedenen Kombinationen der Spezifizierung von Datentyp und Initialisierung in einer `Dim`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="06ecc-223">The following table describes the results of various combinations of specifying the data type and initializer in a `Dim` statement.</span></span>

|<span data-ttu-id="06ecc-224">Datentyp angegeben?</span><span class="sxs-lookup"><span data-stu-id="06ecc-224">Data type specified?</span></span>|<span data-ttu-id="06ecc-225">Initialisierung angegeben?</span><span class="sxs-lookup"><span data-stu-id="06ecc-225">Initializer specified?</span></span>|<span data-ttu-id="06ecc-226">Beispiel</span><span class="sxs-lookup"><span data-stu-id="06ecc-226">Example</span></span>|<span data-ttu-id="06ecc-227">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="06ecc-227">Result</span></span>|
|---|---|---|---|
|<span data-ttu-id="06ecc-228">Nein</span><span class="sxs-lookup"><span data-stu-id="06ecc-228">No</span></span>|<span data-ttu-id="06ecc-229">Nein</span><span class="sxs-lookup"><span data-stu-id="06ecc-229">No</span></span>|`Dim qty`|<span data-ttu-id="06ecc-230">Wenn [Option Strict](option-strict-statement.md) auf OFF festgelegt ist (Standardeinstellung), wird die Variable auf `Nothing`festgelegt.</span><span class="sxs-lookup"><span data-stu-id="06ecc-230">If [Option Strict](option-strict-statement.md) is off (the default), the variable is set to `Nothing`.</span></span><br /><br /> <span data-ttu-id="06ecc-231">Wenn `Option Strict` aktiviert ist, tritt ein Kompilierzeitfehler auf.</span><span class="sxs-lookup"><span data-stu-id="06ecc-231">If `Option Strict` is on, a compile-time error occurs.</span></span>|
|<span data-ttu-id="06ecc-232">Nein</span><span class="sxs-lookup"><span data-stu-id="06ecc-232">No</span></span>|<span data-ttu-id="06ecc-233">Ja</span><span class="sxs-lookup"><span data-stu-id="06ecc-233">Yes</span></span>|`Dim qty = 5`|<span data-ttu-id="06ecc-234">Wenn die [Option Infer](option-infer-statement.md) auf on (The default) (Standard) eingestellt ist, übernimmt die Variable den Datentyp des Initialisierers.</span><span class="sxs-lookup"><span data-stu-id="06ecc-234">If [Option Infer](option-infer-statement.md) is on (the default), the variable takes the data type of the initializer.</span></span> <span data-ttu-id="06ecc-235">Siehe [lokaler Typrückschluss](../../programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="06ecc-235">See [Local Type Inference](../../programming-guide/language-features/variables/local-type-inference.md).</span></span><br /><br /> <span data-ttu-id="06ecc-236">Wenn `Option Infer` und `Option Strict` ausgeschaltet sind, nimmt die Variable den Datentyp des `Object` an.</span><span class="sxs-lookup"><span data-stu-id="06ecc-236">If `Option Infer` is off and `Option Strict` is off, the variable takes the data type of `Object`.</span></span><br /><br /> <span data-ttu-id="06ecc-237">Wenn `Option Infer` deaktiviert ist und `Option Strict` aktiviert ist, tritt ein Kompilierzeitfehler auf.</span><span class="sxs-lookup"><span data-stu-id="06ecc-237">If `Option Infer` is off and `Option Strict` is on, a compile-time error occurs.</span></span>|
|<span data-ttu-id="06ecc-238">Ja</span><span class="sxs-lookup"><span data-stu-id="06ecc-238">Yes</span></span>|<span data-ttu-id="06ecc-239">Nein</span><span class="sxs-lookup"><span data-stu-id="06ecc-239">No</span></span>|`Dim qty As Integer`|<span data-ttu-id="06ecc-240">Die Variable wird auf den Standardwert für den Datentyp initialisiert.</span><span class="sxs-lookup"><span data-stu-id="06ecc-240">The variable is initialized to the default value for the data type.</span></span> <span data-ttu-id="06ecc-241">Informationen finden Sie in der Tabelle weiter unten in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="06ecc-241">See the table later in this section.</span></span>|
|<span data-ttu-id="06ecc-242">Ja</span><span class="sxs-lookup"><span data-stu-id="06ecc-242">Yes</span></span>|<span data-ttu-id="06ecc-243">Ja</span><span class="sxs-lookup"><span data-stu-id="06ecc-243">Yes</span></span>|`Dim qty  As Integer = 5`|<span data-ttu-id="06ecc-244">Wenn der Datentyp der Initialisierung nicht in den angegebenen Datentyp konvertiert werden kann, tritt ein Fehler während der Kompilierung auf.</span><span class="sxs-lookup"><span data-stu-id="06ecc-244">If the data type of the initializer is not convertible to the specified data type, a compile-time error occurs.</span></span>|

<span data-ttu-id="06ecc-245">Wenn Sie einen Datentyp angeben, aber keinen Initialisierer angeben, initialisiert Visual Basic die Variable mit dem Standardwert für ihren Datentyp.</span><span class="sxs-lookup"><span data-stu-id="06ecc-245">If you specify a data type but do not specify an initializer, Visual Basic initializes the variable to the default value for its data type.</span></span> <span data-ttu-id="06ecc-246">In der folgenden Tabelle werden die Standardinitialisierungswerte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="06ecc-246">The following table shows the default initialization values.</span></span>

|<span data-ttu-id="06ecc-247">Datentyp</span><span class="sxs-lookup"><span data-stu-id="06ecc-247">Data type</span></span>|<span data-ttu-id="06ecc-248">Standardwert</span><span class="sxs-lookup"><span data-stu-id="06ecc-248">Default value</span></span>|
|---|---|
|<span data-ttu-id="06ecc-249">Alle numerischen Typen (einschließlich `Byte` und `SByte`)</span><span class="sxs-lookup"><span data-stu-id="06ecc-249">All numeric types (including `Byte` and `SByte`)</span></span>|<span data-ttu-id="06ecc-250">0</span><span class="sxs-lookup"><span data-stu-id="06ecc-250">0</span></span>|
|`Char`|<span data-ttu-id="06ecc-251">Binärdatei 0</span><span class="sxs-lookup"><span data-stu-id="06ecc-251">Binary 0</span></span>|
|<span data-ttu-id="06ecc-252">Alle Verweis Typen (einschließlich `Object`, `String`und alle Arrays)</span><span class="sxs-lookup"><span data-stu-id="06ecc-252">All reference types (including `Object`, `String`, and all arrays)</span></span>|`Nothing`|
|`Boolean`|`False`|
|`Date`|<span data-ttu-id="06ecc-253">12:00 Uhr vom 1. Januar des Jahres 1 (01/01/0001 12:00:00 Uhr)</span><span class="sxs-lookup"><span data-stu-id="06ecc-253">12:00 AM of January 1 of the year 1 (01/01/0001 12:00:00 AM)</span></span>|

<span data-ttu-id="06ecc-254">Jedes Element einer Struktur wird initialisiert, als handele es sich um eine separate Variable.</span><span class="sxs-lookup"><span data-stu-id="06ecc-254">Each element of a structure is initialized as if it were a separate variable.</span></span> <span data-ttu-id="06ecc-255">Wenn Sie die Länge eines Arrays deklarieren, jedoch nicht die zugehörigen Elemente initialisieren, wird jedes Element so initialisiert, als wäre es eine separate Variable.</span><span class="sxs-lookup"><span data-stu-id="06ecc-255">If you declare the length of an array but do not initialize its elements, each element is initialized as if it were a separate variable.</span></span>

## <a name="static-local-variable-lifetime"></a><span data-ttu-id="06ecc-256">Lebensdauer statischer lokaler Variablen</span><span class="sxs-lookup"><span data-stu-id="06ecc-256">Static local variable lifetime</span></span>

<span data-ttu-id="06ecc-257">Eine `Static` lokale Variable hat eine längere Lebensdauer als die der Prozedur, in der Sie deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="06ecc-257">A `Static` local variable has a longer lifetime than that of the procedure in which it is declared.</span></span> <span data-ttu-id="06ecc-258">Die Grenzen der Variablen Lebensdauer hängen davon ab, wo die Prozedur deklariert wird und ob Sie `Shared`ist.</span><span class="sxs-lookup"><span data-stu-id="06ecc-258">The boundaries of the variable's lifetime depend on where the procedure is declared and whether it is `Shared`.</span></span>

|<span data-ttu-id="06ecc-259">Prozedur Deklaration</span><span class="sxs-lookup"><span data-stu-id="06ecc-259">Procedure declaration</span></span>|<span data-ttu-id="06ecc-260">Variable initialisiert</span><span class="sxs-lookup"><span data-stu-id="06ecc-260">Variable initialized</span></span>|<span data-ttu-id="06ecc-261">Variable beendet vorhandene</span><span class="sxs-lookup"><span data-stu-id="06ecc-261">Variable stops existing</span></span>|
|---|---|---|
|<span data-ttu-id="06ecc-262">In einem Modul</span><span class="sxs-lookup"><span data-stu-id="06ecc-262">In a module</span></span>|<span data-ttu-id="06ecc-263">Wenn die Prozedur zum ersten Mal aufgerufen wird</span><span class="sxs-lookup"><span data-stu-id="06ecc-263">The first time the procedure is called</span></span>|<span data-ttu-id="06ecc-264">Wenn das Programm die Ausführung beendet</span><span class="sxs-lookup"><span data-stu-id="06ecc-264">When your program stops execution</span></span>|
|<span data-ttu-id="06ecc-265">In einer Klasse oder Struktur ist die Prozedur `Shared`</span><span class="sxs-lookup"><span data-stu-id="06ecc-265">In a class or structure, procedure is `Shared`</span></span>|<span data-ttu-id="06ecc-266">Wenn die Prozedur zum ersten Mal entweder für eine bestimmte Instanz oder für die Klasse oder Struktur selbst aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="06ecc-266">The first time the procedure is called either on a specific instance or on the class or structure itself</span></span>|<span data-ttu-id="06ecc-267">Wenn das Programm die Ausführung beendet</span><span class="sxs-lookup"><span data-stu-id="06ecc-267">When your program stops execution</span></span>|
|<span data-ttu-id="06ecc-268">In einer Klasse oder Struktur ist die Prozedur nicht `Shared`</span><span class="sxs-lookup"><span data-stu-id="06ecc-268">In a class or structure, procedure isn't `Shared`</span></span>|<span data-ttu-id="06ecc-269">Wenn die Prozedur zum ersten Mal für eine bestimmte Instanz aufgerufen wird</span><span class="sxs-lookup"><span data-stu-id="06ecc-269">The first time the procedure is called on a specific instance</span></span>|<span data-ttu-id="06ecc-270">Wenn die Instanz für Garbage Collection (GC) freigegeben wird</span><span class="sxs-lookup"><span data-stu-id="06ecc-270">When the instance is released for garbage collection (GC)</span></span>|

## <a name="attributes-and-modifiers"></a><span data-ttu-id="06ecc-271">Attribute und modifiziererer</span><span class="sxs-lookup"><span data-stu-id="06ecc-271">Attributes and modifiers</span></span>

<span data-ttu-id="06ecc-272">Attribute können nur auf Element Variablen, nicht auf lokale Variablen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="06ecc-272">You can apply attributes only to member variables, not to local variables.</span></span> <span data-ttu-id="06ecc-273">Ein Attribut trägt Informationen zu den Metadaten der Assembly bei, was für temporäre Speicherung, z. b. lokale Variablen, nicht sinnvoll ist.</span><span class="sxs-lookup"><span data-stu-id="06ecc-273">An attribute contributes information to the assembly's metadata, which is not meaningful for temporary storage such as local variables.</span></span>

<span data-ttu-id="06ecc-274">Auf Modulebene können Sie den `Static` Modifizierer nicht verwenden, um Element Variablen zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="06ecc-274">At module level, you cannot use the `Static` modifier to declare member variables.</span></span> <span data-ttu-id="06ecc-275">Auf Prozedur Ebene können Sie keine `Shared`, `Shadows`, `ReadOnly`, `WithEvents`oder Zugriffsmodifizierer verwenden, um lokale Variablen zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="06ecc-275">At procedure level, you cannot use `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, or any access modifiers to declare local variables.</span></span>

<span data-ttu-id="06ecc-276">Sie können angeben, welcher Code auf eine Variable zugreifen kann, indem Sie eine `accessmodifier`bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="06ecc-276">You can specify what code can access a variable by supplying an `accessmodifier`.</span></span> <span data-ttu-id="06ecc-277">Klassen-und Modulmember-Variablen (außerhalb einer beliebigen Prozedur) werden standardmäßig auf den privaten Zugriff und die Strukturelement Variablen standardmäßig auf den öffentlichen Zugriff eingestellt.</span><span class="sxs-lookup"><span data-stu-id="06ecc-277">Class and module member variables (outside any procedure) default to private access, and structure member variables default to public access.</span></span> <span data-ttu-id="06ecc-278">Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.</span><span class="sxs-lookup"><span data-stu-id="06ecc-278">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="06ecc-279">Sie können keine Zugriffsmodifizierer für lokale Variablen (innerhalb einer Prozedur) verwenden.</span><span class="sxs-lookup"><span data-stu-id="06ecc-279">You cannot use access modifiers on local variables (inside a procedure).</span></span>

<span data-ttu-id="06ecc-280">Sie können `WithEvents` nur für Element Variablen angeben, nicht für lokale Variablen in einer Prozedur.</span><span class="sxs-lookup"><span data-stu-id="06ecc-280">You can specify `WithEvents` only on member variables, not on local variables inside a procedure.</span></span> <span data-ttu-id="06ecc-281">Wenn Sie `WithEvents`angeben, muss es sich beim Datentyp der Variablen um einen bestimmten Klassentyp handeln, nicht um `Object`.</span><span class="sxs-lookup"><span data-stu-id="06ecc-281">If you specify `WithEvents`, the data type of the variable must be a specific class type, not `Object`.</span></span> <span data-ttu-id="06ecc-282">Sie können ein Array nicht mit `WithEvents`deklarieren.</span><span class="sxs-lookup"><span data-stu-id="06ecc-282">You cannot declare an array with `WithEvents`.</span></span> <span data-ttu-id="06ecc-283">Weitere Informationen zu Ereignissen finden Sie unter [Ereignisse](../../programming-guide/language-features/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="06ecc-283">For more information about events, see [Events](../../programming-guide/language-features/events/index.md).</span></span>

> [!NOTE]
> <span data-ttu-id="06ecc-284">Code außerhalb einer Klasse, Struktur oder eines Moduls muss den Namen einer Element Variablen mit dem Namen der Klasse, Struktur oder des Moduls qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="06ecc-284">Code outside a class, structure, or module must qualify a member variable's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="06ecc-285">Code außerhalb einer Prozedur oder eines Blocks kann nicht auf lokale Variablen innerhalb dieser Prozedur oder eines Blocks verweisen.</span><span class="sxs-lookup"><span data-stu-id="06ecc-285">Code outside a procedure or block cannot refer to any local variables within that procedure or block.</span></span>

## <a name="releasing-managed-resources"></a><span data-ttu-id="06ecc-286">Freigeben von verwalteten Ressourcen</span><span class="sxs-lookup"><span data-stu-id="06ecc-286">Releasing managed resources</span></span>

<span data-ttu-id="06ecc-287">Der .NET Framework Garbage Collector verwaltete Ressourcen frei, ohne dass zusätzliche Codierungen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="06ecc-287">The .NET Framework garbage collector disposes of managed resources without any extra coding on your part.</span></span> <span data-ttu-id="06ecc-288">Sie können jedoch die Freigabe einer verwalteten Ressource erzwingen, anstatt auf die Garbage Collector zu warten.</span><span class="sxs-lookup"><span data-stu-id="06ecc-288">However, you can force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>

<span data-ttu-id="06ecc-289">Wenn eine Klasse eine besonders wertvolle und knappe Ressource (z. b. eine Datenbankverbindung oder ein Datei Handle) speichert, möchten Sie möglicherweise nicht warten, bis die nächste Garbage Collection eine nicht mehr verwendete Klasseninstanz bereinigen.</span><span class="sxs-lookup"><span data-stu-id="06ecc-289">If a class holds onto a particularly valuable and scarce resource (such as a database connection or file handle), you might not want to wait until the next garbage collection to clean up a class instance that's no longer in use.</span></span> <span data-ttu-id="06ecc-290">Eine Klasse kann die <xref:System.IDisposable>-Schnittstelle implementieren, um eine Möglichkeit bereitzustellen, Ressourcen vor einem Garbage Collection freizugeben.</span><span class="sxs-lookup"><span data-stu-id="06ecc-290">A class may implement the <xref:System.IDisposable> interface to provide a way to release resources before a garbage collection.</span></span> <span data-ttu-id="06ecc-291">Eine Klasse, die diese Schnittstelle implementiert, macht eine `Dispose` Methode verfügbar, die aufgerufen werden kann, um zu erzwingen, dass wertvolle Ressourcen sofort freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="06ecc-291">A class that implements that interface exposes a `Dispose` method that can be called to force valuable resources to be released immediately.</span></span>

<span data-ttu-id="06ecc-292">Die `Using`-Anweisung automatisiert das Abrufen einer Ressource, das Ausführen eines Satzes von Anweisungen und das anschließende verwerfen der Ressource.</span><span class="sxs-lookup"><span data-stu-id="06ecc-292">The `Using` statement automates the process of acquiring a resource, executing a set of statements, and then disposing of the resource.</span></span> <span data-ttu-id="06ecc-293">Die Ressource muss jedoch die <xref:System.IDisposable>-Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="06ecc-293">However, the resource must implement the <xref:System.IDisposable> interface.</span></span> <span data-ttu-id="06ecc-294">Weitere Informationen finden Sie unter [using-Anweisung](using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="06ecc-294">For more information, see [Using Statement](using-statement.md).</span></span>

## <a name="example"></a><span data-ttu-id="06ecc-295">Beispiel</span><span class="sxs-lookup"><span data-stu-id="06ecc-295">Example</span></span>

<span data-ttu-id="06ecc-296">Im folgenden Beispiel werden Variablen mithilfe der `Dim`-Anweisung mit verschiedenen Optionen deklariert.</span><span class="sxs-lookup"><span data-stu-id="06ecc-296">The following example declares variables by using the `Dim` statement with various options.</span></span>

[!code-vb[VbVbalrStatements#141](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#141)]

## <a name="example"></a><span data-ttu-id="06ecc-297">Beispiel</span><span class="sxs-lookup"><span data-stu-id="06ecc-297">Example</span></span>

<span data-ttu-id="06ecc-298">Im folgenden Beispiel werden die Primzahlen zwischen 1 und 30 aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="06ecc-298">The following example lists the prime numbers between 1 and 30.</span></span> <span data-ttu-id="06ecc-299">Der Bereich der lokalen Variablen wird in den Code Kommentaren beschrieben.</span><span class="sxs-lookup"><span data-stu-id="06ecc-299">The scope of local variables is described in code comments.</span></span>

[!code-vb[VbVbalrStatements#142](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#142)]

## <a name="example"></a><span data-ttu-id="06ecc-300">Beispiel</span><span class="sxs-lookup"><span data-stu-id="06ecc-300">Example</span></span>

<span data-ttu-id="06ecc-301">Im folgenden Beispiel wird die `speedValue` Variable auf Klassenebene deklariert.</span><span class="sxs-lookup"><span data-stu-id="06ecc-301">In the following example, the `speedValue` variable is declared at the class level.</span></span> <span data-ttu-id="06ecc-302">Das `Private`-Schlüsselwort wird verwendet, um die Variable zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="06ecc-302">The `Private` keyword is used to declare the variable.</span></span> <span data-ttu-id="06ecc-303">Auf die Variable kann von jeder Prozedur in der `Car`-Klasse zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="06ecc-303">The variable can be accessed by any procedure in the `Car` class.</span></span>

[!code-vb[VbVbalrStatements#144](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#144)]

[!code-vb[VbVbalrStatements#145](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#145)]

## <a name="see-also"></a><span data-ttu-id="06ecc-304">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="06ecc-304">See also</span></span>

- [<span data-ttu-id="06ecc-305">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="06ecc-305">Const Statement</span></span>](const-statement.md)
- [<span data-ttu-id="06ecc-306">ReDim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="06ecc-306">ReDim Statement</span></span>](redim-statement.md)
- [<span data-ttu-id="06ecc-307">Option Explicit-Anweisung</span><span class="sxs-lookup"><span data-stu-id="06ecc-307">Option Explicit Statement</span></span>](option-explicit-statement.md)
- [<span data-ttu-id="06ecc-308">Option Infer-Anweisung</span><span class="sxs-lookup"><span data-stu-id="06ecc-308">Option Infer Statement</span></span>](option-infer-statement.md)
- [<span data-ttu-id="06ecc-309">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="06ecc-309">Option Strict Statement</span></span>](option-strict-statement.md)
- [<span data-ttu-id="06ecc-310">Seite „Kompilieren“, Projekt-Designer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="06ecc-310">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [<span data-ttu-id="06ecc-311">Variablendeklaration</span><span class="sxs-lookup"><span data-stu-id="06ecc-311">Variable Declaration</span></span>](../../programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="06ecc-312">Arrays</span><span class="sxs-lookup"><span data-stu-id="06ecc-312">Arrays</span></span>](../../programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="06ecc-313">Objektinitialisierer: Benannte und anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="06ecc-313">Object Initializers: Named and Anonymous Types</span></span>](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="06ecc-314">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="06ecc-314">Anonymous Types</span></span>](../../programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="06ecc-315">Objektinitialisierer: Benannte und anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="06ecc-315">Object Initializers: Named and Anonymous Types</span></span>](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="06ecc-316">Gewusst wie: Deklarieren eines Objekts mithilfe eines Objektinitialisierers</span><span class="sxs-lookup"><span data-stu-id="06ecc-316">How to: Declare an Object by Using an Object Initializer</span></span>](../../programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
- [<span data-ttu-id="06ecc-317">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="06ecc-317">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
