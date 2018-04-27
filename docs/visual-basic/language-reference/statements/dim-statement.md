---
title: Dim-Anweisung (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 72
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 36e2d416e4653bfa6fe212b75b92ae2d90775d53
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="dim-statement-visual-basic"></a><span data-ttu-id="e24fd-102">Dim-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e24fd-102">Dim Statement (Visual Basic)</span></span>
<span data-ttu-id="e24fd-103">Deklariert und reserviert Speicherplatz für eine oder mehrere Variablen.</span><span class="sxs-lookup"><span data-stu-id="e24fd-103">Declares and allocates storage space for one or more variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e24fd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e24fd-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] [[ Shared ] [ Shadows ] | [ Static ]] [ ReadOnly ]   
Dim [ WithEvents ] variablelist  
```  
  
## <a name="parts"></a><span data-ttu-id="e24fd-105">Teile</span><span class="sxs-lookup"><span data-stu-id="e24fd-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="e24fd-106">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="e24fd-106">Optional.</span></span> <span data-ttu-id="e24fd-107">Finden Sie unter [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="e24fd-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="e24fd-108">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="e24fd-108">Optional.</span></span> <span data-ttu-id="e24fd-109">Einer der folgenden Werte ist möglich:</span><span class="sxs-lookup"><span data-stu-id="e24fd-109">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="e24fd-110">Public</span><span class="sxs-lookup"><span data-stu-id="e24fd-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="e24fd-111">Protected</span><span class="sxs-lookup"><span data-stu-id="e24fd-111">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="e24fd-112">Friend</span><span class="sxs-lookup"><span data-stu-id="e24fd-112">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="e24fd-113">Private</span><span class="sxs-lookup"><span data-stu-id="e24fd-113">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   `Protected Friend`  
  
     <span data-ttu-id="e24fd-114">Finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="e24fd-114">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `Shared`  
  
     <span data-ttu-id="e24fd-115">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="e24fd-115">Optional.</span></span> <span data-ttu-id="e24fd-116">Finden Sie unter [freigegebene](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="e24fd-116">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="e24fd-117">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="e24fd-117">Optional.</span></span> <span data-ttu-id="e24fd-118">Finden Sie unter [Schatten](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="e24fd-118">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
-   `Static`  
  
     <span data-ttu-id="e24fd-119">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="e24fd-119">Optional.</span></span> <span data-ttu-id="e24fd-120">Finden Sie unter [statische](../../../visual-basic/language-reference/modifiers/static.md).</span><span class="sxs-lookup"><span data-stu-id="e24fd-120">See [Static](../../../visual-basic/language-reference/modifiers/static.md).</span></span>  
  
-   `ReadOnly`  
  
     <span data-ttu-id="e24fd-121">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="e24fd-121">Optional.</span></span> <span data-ttu-id="e24fd-122">Finden Sie unter [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="e24fd-122">See [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
-   `WithEvents`  
  
     <span data-ttu-id="e24fd-123">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="e24fd-123">Optional.</span></span> <span data-ttu-id="e24fd-124">Gibt an, dass diese Objektvariablen, die auf Instanzen einer Klasse verweisen, die Ereignisse auslösen kann.</span><span class="sxs-lookup"><span data-stu-id="e24fd-124">Specifies that these are object variables that refer to instances of a class that can raise events.</span></span> <span data-ttu-id="e24fd-125">Finden Sie unter [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md).</span><span class="sxs-lookup"><span data-stu-id="e24fd-125">See [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md).</span></span>  
  
-   `variablelist`  
  
     <span data-ttu-id="e24fd-126">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e24fd-126">Required.</span></span> <span data-ttu-id="e24fd-127">Liste der Variablen, die in dieser Anweisung deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="e24fd-127">List of variables being declared in this statement.</span></span>  
  
     `variable [ , variable ... ]`  
  
     <span data-ttu-id="e24fd-128">Jede `variable` weist folgende Syntax und Bestandteile auf:</span><span class="sxs-lookup"><span data-stu-id="e24fd-128">Each `variable` has the following syntax and parts:</span></span>  
  
     <span data-ttu-id="e24fd-129">`variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="e24fd-129">`variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`</span></span>  
  
    |<span data-ttu-id="e24fd-130">Segment</span><span class="sxs-lookup"><span data-stu-id="e24fd-130">Part</span></span>|<span data-ttu-id="e24fd-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e24fd-131">Description</span></span>|  
    |---|---|  
    |`variablename`|<span data-ttu-id="e24fd-132">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e24fd-132">Required.</span></span> <span data-ttu-id="e24fd-133">Der Name der Variablen.</span><span class="sxs-lookup"><span data-stu-id="e24fd-133">Name of the variable.</span></span> <span data-ttu-id="e24fd-134">Finden Sie unter [deklarierte Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="e24fd-134">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
    |`boundslist`|<span data-ttu-id="e24fd-135">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="e24fd-135">Optional.</span></span> <span data-ttu-id="e24fd-136">Liste der Grenzen jeder Dimension des Arrayvariable.</span><span class="sxs-lookup"><span data-stu-id="e24fd-136">List of bounds of each dimension of an array variable.</span></span>|  
    |`New`|<span data-ttu-id="e24fd-137">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="e24fd-137">Optional.</span></span> <span data-ttu-id="e24fd-138">Erstellt eine neue Instanz der Klasse bei der `Dim` Anweisung wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e24fd-138">Creates a new instance of the class when the `Dim` statement runs.</span></span>|  
    |`datatype`|<span data-ttu-id="e24fd-139">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="e24fd-139">Optional.</span></span> <span data-ttu-id="e24fd-140">Der Datentyp der Variablen.</span><span class="sxs-lookup"><span data-stu-id="e24fd-140">Data type of the variable.</span></span>|  
    |`With`|<span data-ttu-id="e24fd-141">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="e24fd-141">Optional.</span></span> <span data-ttu-id="e24fd-142">Führt der Objektinitialisiererliste.</span><span class="sxs-lookup"><span data-stu-id="e24fd-142">Introduces the object initializer list.</span></span>|  
    |`propertyname`|<span data-ttu-id="e24fd-143">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="e24fd-143">Optional.</span></span> <span data-ttu-id="e24fd-144">Der Name einer Eigenschaft in der Klasse werden Sie eine Instanz von herstellen.</span><span class="sxs-lookup"><span data-stu-id="e24fd-144">The name of a property in the class you are making an instance of.</span></span>|  
    |`propinitializer`|<span data-ttu-id="e24fd-145">Nach der erforderlichen `propertyname` =.</span><span class="sxs-lookup"><span data-stu-id="e24fd-145">Required after `propertyname` =.</span></span> <span data-ttu-id="e24fd-146">Der Ausdruck, der ausgewertet und den Namen der Eigenschaft zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="e24fd-146">The expression that is evaluated and assigned to the property name.</span></span>|  
    |`initializer`|<span data-ttu-id="e24fd-147">Optional, wenn `New` nicht angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e24fd-147">Optional if `New` is not specified.</span></span> <span data-ttu-id="e24fd-148">Ausdruck, der ausgewertet und bei der Erstellung der Variablen zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="e24fd-148">Expression that is evaluated and assigned to the variable when it is created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e24fd-149">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e24fd-149">Remarks</span></span>  
 <span data-ttu-id="e24fd-150">Visual Basic-Compiler verwendet den `Dim` Anweisung, um festzustellen, Datentyp der Variablen und andere Informationen, z. B. welcher Code auf die Variable zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="e24fd-150">The Visual Basic compiler uses the `Dim` statement to determine the variable's data type and other information, such as what code can access the variable.</span></span> <span data-ttu-id="e24fd-151">Das folgende Beispiel deklariert eine Variable für ein `Integer` Wert.</span><span class="sxs-lookup"><span data-stu-id="e24fd-151">The following example declares a variable to hold an `Integer` value.</span></span>  
  
```vb  
Dim numberOfStudents As Integer  
```  
  
 <span data-ttu-id="e24fd-152">Sie können einen beliebigen Datentyp aufweisen oder den Namen einer Enumeration, Struktur, Klasse oder Schnittstelle angeben.</span><span class="sxs-lookup"><span data-stu-id="e24fd-152">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>  
  
```vb  
Dim finished As Boolean  
Dim monitorBox As System.Windows.Forms.Form  
```  
  
 <span data-ttu-id="e24fd-153">Für einen Verweistyp handelt, verwenden Sie die `New` -Schlüsselwort zum Erstellen einer neuen Instanz der Klasse oder Struktur, durch den-Datentyp angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="e24fd-153">For a reference type, you use the `New` keyword to create a new instance of the class or structure that is specified by the data type.</span></span> <span data-ttu-id="e24fd-154">Bei Verwendung von `New`, einen Initialisiererausdruck nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="e24fd-154">If you use `New`, you do not use an initializer expression.</span></span> <span data-ttu-id="e24fd-155">Stattdessen geben Sie Argumente, sofern diese erforderlich ist, an den Konstruktor der Klasse sind aus denen Sie die Variable erstellen.</span><span class="sxs-lookup"><span data-stu-id="e24fd-155">Instead, you supply arguments, if they are required, to the constructor of the class from which you are creating the variable.</span></span>  
  
```vb  
Dim bottomLabel As New System.Windows.Forms.Label  
```  
  
 <span data-ttu-id="e24fd-156">Sie können eine Variable in einer Prozedur, Block, Klasse, Struktur oder Modul deklarieren.</span><span class="sxs-lookup"><span data-stu-id="e24fd-156">You can declare a variable in a procedure, block, class, structure, or module.</span></span> <span data-ttu-id="e24fd-157">Sie können eine Variable in einer Quelldatei, Namespace oder Schnittstelle nicht deklarieren.</span><span class="sxs-lookup"><span data-stu-id="e24fd-157">You cannot declare a variable in a source file, namespace, or interface.</span></span> <span data-ttu-id="e24fd-158">Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="e24fd-158">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="e24fd-159">Ist eine Variable, die auf Modulebene außerhalb einer Prozedur deklariert ist ein *Membervariable* oder *Feld*.</span><span class="sxs-lookup"><span data-stu-id="e24fd-159">A variable that is declared at module level, outside any procedure, is a *member variable* or *field*.</span></span> <span data-ttu-id="e24fd-160">Membervariablen sind im Gültigkeitsbereich ihrer Klasse, Struktur oder eines Moduls.</span><span class="sxs-lookup"><span data-stu-id="e24fd-160">Member variables are in scope throughout their class, structure, or module.</span></span> <span data-ttu-id="e24fd-161">Eine auf Prozedurebene deklarierte Variable ist eine *lokale Variable*.</span><span class="sxs-lookup"><span data-stu-id="e24fd-161">A variable that is declared at procedure level is a *local variable*.</span></span> <span data-ttu-id="e24fd-162">Lokale Variablen sind nur innerhalb ihrer Prozedur oder eines Blocks.</span><span class="sxs-lookup"><span data-stu-id="e24fd-162">Local variables are in scope only within their procedure or block.</span></span>  
  
 <span data-ttu-id="e24fd-163">Die folgenden Zugriffsmodifizierer werden zum Deklarieren von Variablen, die außerhalb einer Prozedur verwendet: `Public`, `Protected`, `Friend`, `Protected Friend`, und `Private`.</span><span class="sxs-lookup"><span data-stu-id="e24fd-163">The following access modifiers are used to declare variables outside a procedure: `Public`, `Protected`, `Friend`, `Protected Friend`, and `Private`.</span></span> <span data-ttu-id="e24fd-164">Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="e24fd-164">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="e24fd-165">Die `Dim` Schlüsselwort ist optional und in der Regel nicht angegeben wird, wenn Sie eine der folgenden Modifizierer angeben: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, oder `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="e24fd-165">The `Dim` keyword is optional and usually omitted if you specify any of the following modifiers: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, or `WithEvents`.</span></span>  
  
```vb  
Public maximumAllowed As Double  
Protected Friend currentUserName As String  
Private salary As Decimal  
Static runningTotal As Integer  
```  
  
 <span data-ttu-id="e24fd-166">Wenn `Option Explicit` ist (Standard), erfordert der Compiler eine Deklaration für jede Variable, die Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="e24fd-166">If `Option Explicit` is on (the default), the compiler requires a declaration for every variable you use.</span></span> <span data-ttu-id="e24fd-167">Weitere Informationen finden Sie unter [Option Explicit-Anweisung](../../../visual-basic/language-reference/statements/option-explicit-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e24fd-167">For more information, see [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md).</span></span>  
  
## <a name="specifying-an-initial-value"></a><span data-ttu-id="e24fd-168">Einen Anfangswert angeben</span><span class="sxs-lookup"><span data-stu-id="e24fd-168">Specifying an Initial Value</span></span>  
 <span data-ttu-id="e24fd-169">Sie können einer Variablen einen Wert zuweisen, während der Erstellung.</span><span class="sxs-lookup"><span data-stu-id="e24fd-169">You can assign a value to a variable when it is created.</span></span> <span data-ttu-id="e24fd-170">Für einen Werttyp aufweist, verwenden Sie eine *Initialisierer* , geben Sie einen Ausdruck, der Variablen zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="e24fd-170">For a value type, you use an *initializer* to supply an expression to be assigned to the variable.</span></span> <span data-ttu-id="e24fd-171">Der Ausdruck muss auf eine Konstante ausgewertet werden, die zur Kompilierzeit berechnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="e24fd-171">The expression must evaluate to a constant that can be calculated at compile time.</span></span>  
  
```vb  
Dim quantity As Integer = 10  
Dim message As String = "Just started"  
```  
  
 <span data-ttu-id="e24fd-172">Wenn ein Initialisierer angegeben ist und ein Datentyp nicht, in angegeben ist einer `As` -Klausel, *Typrückschluss* wird verwendet, um den Datentyp aus dem Initialisierer abzuleiten.</span><span class="sxs-lookup"><span data-stu-id="e24fd-172">If an initializer is specified and a data type is not specified in an `As` clause, *type inference* is used to infer the data type from the initializer.</span></span> <span data-ttu-id="e24fd-173">Im folgenden Beispiel sowohl `num1` und `num2` sind stark typisiert als ganze Zahlen.</span><span class="sxs-lookup"><span data-stu-id="e24fd-173">In the following example, both `num1` and `num2` are strongly typed as integers.</span></span> <span data-ttu-id="e24fd-174">In der zweiten Deklaration leitet der Typrückschluss den Typ aus dem Wert 3 ab.</span><span class="sxs-lookup"><span data-stu-id="e24fd-174">In the second declaration, type inference infers the type from the value 3.</span></span>  
  
```vb  
' Use explicit typing.  
Dim num1 As Integer = 3  
  
' Use local type inference.  
Dim num2 = 3  
```  
  
 <span data-ttu-id="e24fd-175">Typrückschluss ist auf Prozedurebene gültig.</span><span class="sxs-lookup"><span data-stu-id="e24fd-175">Type inference applies at the procedure level.</span></span> <span data-ttu-id="e24fd-176">Es gilt nicht außerhalb einer Prozedur in einer Klasse, Struktur, Modul oder Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="e24fd-176">It does not apply outside a procedure in a class, structure, module, or interface.</span></span> <span data-ttu-id="e24fd-177">Weitere Informationen zu den Typ abzuleiten, finden Sie unter [Option Infer-Anweisung](../../../visual-basic/language-reference/statements/option-infer-statement.md) und [lokalen Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="e24fd-177">For more information about type inference, see [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
 <span data-ttu-id="e24fd-178">Informationen, was geschieht, wenn ein Datentyp oder einen Initialisierer nicht angegeben ist, finden Sie unter [-Standarddatentypen und-Werte](../../../visual-basic/language-reference/statements/dim-statement.md#default) weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="e24fd-178">For information about what happens when a data type or initializer is not specified, see [Default Data Types and Values](../../../visual-basic/language-reference/statements/dim-statement.md#default) later in this topic.</span></span>  
  
 <span data-ttu-id="e24fd-179">Können Sie eine *-Objekt Initialisierer* Instanzen benannte und anonyme Typen zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="e24fd-179">You can use an *object initializer* to declare instances of named and anonymous types.</span></span> <span data-ttu-id="e24fd-180">Der folgende Code erstellt eine Instanz von einem `Student` Klasse und verwendet einen Objektinitialisierer, um Eigenschaften zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="e24fd-180">The following code creates an instance of a `Student` class and uses an object initializer to initialize properties.</span></span>  
  
```vb  
Dim student1 As New Student With {.First = "Michael",   
                                  .Last = "Tucker"}  
```  
  
 <span data-ttu-id="e24fd-181">Weitere Informationen über Objektinitialisierer finden Sie unter [wie: Deklarieren eines Objekts mithilfe eines Objektinitialisierers](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [Objektinitialisierer: benannte und anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), und [anonyme Typen ](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="e24fd-181">For more information about object initializers, see [How to: Declare an Object by Using an Object Initializer](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [Object Initializers: Named and Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), and [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
## <a name="declaring-multiple-variables"></a><span data-ttu-id="e24fd-182">Mehrere Variablen deklariert werden</span><span class="sxs-lookup"><span data-stu-id="e24fd-182">Declaring Multiple Variables</span></span>  
 <span data-ttu-id="e24fd-183">Sie können mehrere Variablen in einer Deklaration-Anweisung deklarieren, die den Variablennamen für jede einzelne und nach jeder Arrayname mit Klammern angeben.</span><span class="sxs-lookup"><span data-stu-id="e24fd-183">You can declare several variables in one declaration statement, specifying the variable name for each one, and following each array name with parentheses.</span></span> <span data-ttu-id="e24fd-184">Mehrere Variablen werden durch Kommas voneinander getrennt.</span><span class="sxs-lookup"><span data-stu-id="e24fd-184">Multiple variables are separated by commas.</span></span>  
  
```vb  
Dim lastTime, nextTime, allTimes() As Date  
```  
  
 <span data-ttu-id="e24fd-185">Wenn Sie mehr als eine Variable mit einem deklarieren `As` -Klausel keine Initialisierer für diese Gruppe von Variablen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e24fd-185">If you declare more than one variable with one `As` clause, you cannot supply an initializer for that group of variables.</span></span>  
  
 <span data-ttu-id="e24fd-186">Sie können für verschiedene Variablen unterschiedliche Datentypen angeben, indem Sie eine separate `As` -Klausel für jede Variable, die Sie deklarieren.</span><span class="sxs-lookup"><span data-stu-id="e24fd-186">You can specify different data types for different variables by using a separate `As` clause for each variable you declare.</span></span> <span data-ttu-id="e24fd-187">Jede Variable nimmt in der ersten angegebenen Datentyp `As` -Klausel nach seiner `variablename` Teil.</span><span class="sxs-lookup"><span data-stu-id="e24fd-187">Each variable takes the data type specified in the first `As` clause encountered after its `variablename` part.</span></span>  
  
```vb  
Dim a, b, c As Single, x, y As Double, i As Integer  
' a, b, and c are all Single; x and y are both Double  
```  
  
## <a name="arrays"></a><span data-ttu-id="e24fd-188">Arrays</span><span class="sxs-lookup"><span data-stu-id="e24fd-188">Arrays</span></span>  
 <span data-ttu-id="e24fd-189">Sie können deklarieren eine Variable für ein *Array*, die mehrere Werte enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="e24fd-189">You can declare a variable to hold an *array*, which can hold multiple values.</span></span> <span data-ttu-id="e24fd-190">Um anzugeben, dass eine Variable ein Array enthält, führen Sie die `variablename` sofort mit Klammern.</span><span class="sxs-lookup"><span data-stu-id="e24fd-190">To specify that a variable holds an array, follow its `variablename` immediately with parentheses.</span></span> <span data-ttu-id="e24fd-191">Weitere Informationen zu Arrays finden Sie unter [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="e24fd-191">For more information about arrays, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
 <span data-ttu-id="e24fd-192">Sie können die untere und obere Grenze der einzelnen Dimensionen eines Arrays angeben.</span><span class="sxs-lookup"><span data-stu-id="e24fd-192">You can specify the lower and upper bound of each dimension of an array.</span></span> <span data-ttu-id="e24fd-193">Um dies zu erreichen, fügen einen `boundslist` innerhalb der Klammern.</span><span class="sxs-lookup"><span data-stu-id="e24fd-193">To do this, include a `boundslist` inside the parentheses.</span></span> <span data-ttu-id="e24fd-194">Für jede Dimension die `boundslist` gibt die obere Grenze und optional die untere Grenze.</span><span class="sxs-lookup"><span data-stu-id="e24fd-194">For each dimension, the `boundslist` specifies the upper bound and optionally the lower bound.</span></span> <span data-ttu-id="e24fd-195">Die untere Grenze ist immer 0 (null), ob Sie es angeben.</span><span class="sxs-lookup"><span data-stu-id="e24fd-195">The lower bound is always zero, whether you specify it or not.</span></span> <span data-ttu-id="e24fd-196">Jeder Index kann von 0 (null), über den Wert der oberen Grenze variieren.</span><span class="sxs-lookup"><span data-stu-id="e24fd-196">Each index can vary from zero through its upper bound value.</span></span>  
  
 <span data-ttu-id="e24fd-197">Die folgenden beiden Anweisungen sind gleichwertig.</span><span class="sxs-lookup"><span data-stu-id="e24fd-197">The following two statements are equivalent.</span></span> <span data-ttu-id="e24fd-198">Jede Anweisung deklariert ein Array von 21 `Integer` Elemente.</span><span class="sxs-lookup"><span data-stu-id="e24fd-198">Each statement declares an array of 21 `Integer` elements.</span></span> <span data-ttu-id="e24fd-199">Wenn Sie das Array zugreifen, kann der Index von 0 bis 20 abweichen.</span><span class="sxs-lookup"><span data-stu-id="e24fd-199">When you access the array, the index can vary from 0 through 20.</span></span>  
  
```vb  
Dim totals(20) As Integer  
Dim totals(0 To 20) As Integer  
```  
  
 <span data-ttu-id="e24fd-200">Die folgende Anweisung deklariert ein zweidimensionales Array vom Typ `Double`.</span><span class="sxs-lookup"><span data-stu-id="e24fd-200">The following statement declares a two-dimensional array of type `Double`.</span></span> <span data-ttu-id="e24fd-201">Das Array verfügt über 6 Spalten (5 + 1) jeweils 4 Zeilen (3 + 1).</span><span class="sxs-lookup"><span data-stu-id="e24fd-201">The array has 4 rows (3 + 1) of 6 columns (5 + 1) each.</span></span> <span data-ttu-id="e24fd-202">Beachten Sie, dass eine obere Grenze den höchsten möglichen Wert für den Index, nicht die Länge der Dimension darstellt.</span><span class="sxs-lookup"><span data-stu-id="e24fd-202">Note that an upper bound represents the highest possible value for the index, not the length of the dimension.</span></span> <span data-ttu-id="e24fd-203">Die Länge der Dimension ist die obere Grenze plus eins.</span><span class="sxs-lookup"><span data-stu-id="e24fd-203">The length of the dimension is the upper bound plus one.</span></span>  
  
```vb  
Dim matrix2(3, 5) As Double  
```  
  
 <span data-ttu-id="e24fd-204">Ein Array kann von 1 bis 32 Dimensionen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="e24fd-204">An array can have from 1 to 32 dimensions.</span></span>  
  
 <span data-ttu-id="e24fd-205">Sie können alle Grenzen in der Arraydeklaration eines leer lassen.</span><span class="sxs-lookup"><span data-stu-id="e24fd-205">You can leave all the bounds blank in an array declaration.</span></span> <span data-ttu-id="e24fd-206">Wenn Sie so vorgehen, das Array verfügt über die Anzahl der Dimensionen, die Sie angeben, aber es ist nicht initialisiert.</span><span class="sxs-lookup"><span data-stu-id="e24fd-206">If you do this, the array has the number of dimensions you specify, but it is uninitialized.</span></span> <span data-ttu-id="e24fd-207">Der Wert des `Nothing` bis Sie mindestens initialisieren einige seiner Elemente.</span><span class="sxs-lookup"><span data-stu-id="e24fd-207">It has a value of `Nothing` until you initialize at least some of its elements.</span></span> <span data-ttu-id="e24fd-208">Die `Dim` -Anweisung darf Grenzen für alle Dimensionen oder für keine Dimensionen angegeben.</span><span class="sxs-lookup"><span data-stu-id="e24fd-208">The `Dim` statement must specify bounds either for all dimensions or for no dimensions.</span></span>  
  
```vb  
' Declare an array with blank array bounds.  
Dim messages() As String  
' Initialize the array.  
ReDim messages(4)  
```  
  
 <span data-ttu-id="e24fd-209">Wenn das Array mehr als eine Dimension hat, müssen Sie zwischen den Klammern an, dass die Anzahl der Dimensionen als Trennzeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="e24fd-209">If the array has more than one dimension, you must include commas between the parentheses to indicate the number of dimensions.</span></span>  
  
```vb  
Dim oneDimension(), twoDimensions(,), threeDimensions(,,) As Byte  
```  
  
 <span data-ttu-id="e24fd-210">Sie können deklarieren eine *Array der Länge null* durch deklarieren eine der Dimensionen des Arrays als-1 sein.</span><span class="sxs-lookup"><span data-stu-id="e24fd-210">You can declare a *zero-length array* by declaring one of the array's dimensions to be -1.</span></span> <span data-ttu-id="e24fd-211">Eine Variable, ein Array der Länge 0 (null) enthält, verfügt nicht über den Wert `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="e24fd-211">A variable that holds a zero-length array does not have the value `Nothing`.</span></span> <span data-ttu-id="e24fd-212">Arrays mit der Länge 0 (null) sind bestimmte Funktionen der common Language Runtime erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e24fd-212">Zero-length arrays are required by certain common language runtime functions.</span></span> <span data-ttu-id="e24fd-213">Wenn Sie versuchen, ein solches Array zuzugreifen, tritt eine Laufzeitausnahme.</span><span class="sxs-lookup"><span data-stu-id="e24fd-213">If you try to access such an array, a runtime exception occurs.</span></span> <span data-ttu-id="e24fd-214">Weitere Informationen finden Sie unter [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="e24fd-214">For more information, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
 <span data-ttu-id="e24fd-215">Sie können die Werte eines Arrays mit einem Arrayliteral initialisieren.</span><span class="sxs-lookup"><span data-stu-id="e24fd-215">You can initialize the values of an array by using an array literal.</span></span> <span data-ttu-id="e24fd-216">Umschließen Sie zu diesem Zweck die Initialisierungswerte mit geschweiften Klammern (`{}`).</span><span class="sxs-lookup"><span data-stu-id="e24fd-216">To do this, surround the initialization values with braces (`{}`).</span></span>  
  
```vb  
Dim longArray() As Long = {0, 1, 2, 3}  
```  
  
 <span data-ttu-id="e24fd-217">Für mehrdimensionale Arrays wird die Initialisierung für jede separate Dimension in der geschweiften Klammern in der äußeren Dimension eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="e24fd-217">For multidimensional arrays, the initialization for each separate dimension is enclosed in braces in the outer dimension.</span></span> <span data-ttu-id="e24fd-218">Die Elemente werden in zeilengerichteter Reihenfolge angegeben.</span><span class="sxs-lookup"><span data-stu-id="e24fd-218">The elements are specified in row-major order.</span></span>  
  
```vb  
Dim twoDimensions(,) As Integer = {{0, 1, 2}, {10, 11, 12}}  
```  
  
 <span data-ttu-id="e24fd-219">Weitere Informationen zu Arrayliterale, finden Sie unter [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="e24fd-219">For more information about array literals, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
##  <a name="default"></a> <span data-ttu-id="e24fd-220">Standarddatentypen und-Werte</span><span class="sxs-lookup"><span data-stu-id="e24fd-220">Default Data Types and Values</span></span>  
 <span data-ttu-id="e24fd-221">Die folgende Tabelle beschreibt die Ergebnisse der verschiedenen Kombinationen der Spezifizierung von Datentyp und Initialisierung in einer `Dim`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="e24fd-221">The following table describes the results of various combinations of specifying the data type and initializer in a `Dim` statement.</span></span>  
  
|<span data-ttu-id="e24fd-222">Datentyp angegeben?</span><span class="sxs-lookup"><span data-stu-id="e24fd-222">Data type specified?</span></span>|<span data-ttu-id="e24fd-223">Initialisierung angegeben?</span><span class="sxs-lookup"><span data-stu-id="e24fd-223">Initializer specified?</span></span>|<span data-ttu-id="e24fd-224">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e24fd-224">Example</span></span>|<span data-ttu-id="e24fd-225">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="e24fd-225">Result</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="e24fd-226">Nein</span><span class="sxs-lookup"><span data-stu-id="e24fd-226">No</span></span>|<span data-ttu-id="e24fd-227">Nein</span><span class="sxs-lookup"><span data-stu-id="e24fd-227">No</span></span>|`Dim qty`|<span data-ttu-id="e24fd-228">Wenn [Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) ist off (Standardeinstellung), wird die Variable festgelegt, um `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="e24fd-228">If [Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) is off (the default), the variable is set to `Nothing`.</span></span><br /><br /> <span data-ttu-id="e24fd-229">Wenn `Option Strict` aktiviert ist, tritt ein Kompilierungsfehler auf.</span><span class="sxs-lookup"><span data-stu-id="e24fd-229">If `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="e24fd-230">Nein</span><span class="sxs-lookup"><span data-stu-id="e24fd-230">No</span></span>|<span data-ttu-id="e24fd-231">Ja</span><span class="sxs-lookup"><span data-stu-id="e24fd-231">Yes</span></span>|`Dim qty = 5`|<span data-ttu-id="e24fd-232">Wenn [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) ist (Standard), übernimmt die Variable die Daten des Initialisierers geben.</span><span class="sxs-lookup"><span data-stu-id="e24fd-232">If [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) is on (the default), the variable takes the data type of the initializer.</span></span> <span data-ttu-id="e24fd-233">Finden Sie unter [lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="e24fd-233">See [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span><br /><br /> <span data-ttu-id="e24fd-234">Wenn `Option Infer` und `Option Strict` ausgeschaltet sind, nimmt die Variable den Datentyp des `Object` an.</span><span class="sxs-lookup"><span data-stu-id="e24fd-234">If `Option Infer` is off and `Option Strict` is off, the variable takes the data type of `Object`.</span></span><br /><br /> <span data-ttu-id="e24fd-235">Wenn `Option Infer` deaktiviert ist und `Option Strict` aktiviert ist, tritt ein Kompilierungsfehler auf.</span><span class="sxs-lookup"><span data-stu-id="e24fd-235">If `Option Infer` is off and `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="e24fd-236">Ja</span><span class="sxs-lookup"><span data-stu-id="e24fd-236">Yes</span></span>|<span data-ttu-id="e24fd-237">Nein</span><span class="sxs-lookup"><span data-stu-id="e24fd-237">No</span></span>|`Dim qty As Integer`|<span data-ttu-id="e24fd-238">Die Variable wird auf den Standardwert für den Datentyp initialisiert.</span><span class="sxs-lookup"><span data-stu-id="e24fd-238">The variable is initialized to the default value for the data type.</span></span> <span data-ttu-id="e24fd-239">Finden Sie in der Tabelle weiter unten in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="e24fd-239">See the table later in this section.</span></span>|  
|<span data-ttu-id="e24fd-240">Ja</span><span class="sxs-lookup"><span data-stu-id="e24fd-240">Yes</span></span>|<span data-ttu-id="e24fd-241">Ja</span><span class="sxs-lookup"><span data-stu-id="e24fd-241">Yes</span></span>|`Dim qty  As Integer = 5`|<span data-ttu-id="e24fd-242">Wenn der Datentyp der Initialisierung nicht in den angegebenen Datentyp konvertiert werden kann, tritt ein Fehler während der Kompilierung auf.</span><span class="sxs-lookup"><span data-stu-id="e24fd-242">If the data type of the initializer is not convertible to the specified data type, a compile-time error occurs.</span></span>|  
  
 <span data-ttu-id="e24fd-243">Wenn Sie einen Datentyp angeben, aber Sie keine Initialisierer geben, initialisiert Visual Basic die Variable auf den Standardwert für seinen Datentyp.</span><span class="sxs-lookup"><span data-stu-id="e24fd-243">If you specify a data type but do not specify an initializer, Visual Basic initializes the variable to the default value for its data type.</span></span> <span data-ttu-id="e24fd-244">Die folgende Tabelle zeigt die Initialisierungswerte.</span><span class="sxs-lookup"><span data-stu-id="e24fd-244">The following table shows the default initialization values.</span></span>  
  
|<span data-ttu-id="e24fd-245">Datentyp</span><span class="sxs-lookup"><span data-stu-id="e24fd-245">Data type</span></span>|<span data-ttu-id="e24fd-246">Standardwert</span><span class="sxs-lookup"><span data-stu-id="e24fd-246">Default value</span></span>|  
|---|---|  
|<span data-ttu-id="e24fd-247">Alle numerischen Typen (einschließlich `Byte` und `SByte`)</span><span class="sxs-lookup"><span data-stu-id="e24fd-247">All numeric types (including `Byte` and `SByte`)</span></span>|<span data-ttu-id="e24fd-248">0</span><span class="sxs-lookup"><span data-stu-id="e24fd-248">0</span></span>|  
|`Char`|<span data-ttu-id="e24fd-249">Binäre 0</span><span class="sxs-lookup"><span data-stu-id="e24fd-249">Binary 0</span></span>|  
|<span data-ttu-id="e24fd-250">Alle Verweistypen (einschließlich `Object`, `String`, und alle Arrays)</span><span class="sxs-lookup"><span data-stu-id="e24fd-250">All reference types (including `Object`, `String`, and all arrays)</span></span>|`Nothing`|  
|`Boolean`|`False`|  
|`Date`|<span data-ttu-id="e24fd-251">12:00 Uhr am 1. Januar des Jahres 1 (01/01/0001 12:00:00 Uhr)</span><span class="sxs-lookup"><span data-stu-id="e24fd-251">12:00 AM of January 1 of the year 1 (01/01/0001 12:00:00 AM)</span></span>|  
  
 <span data-ttu-id="e24fd-252">Jedes Element einer Struktur wird initialisiert, als handele es sich um eine separate Variable.</span><span class="sxs-lookup"><span data-stu-id="e24fd-252">Each element of a structure is initialized as if it were a separate variable.</span></span> <span data-ttu-id="e24fd-253">Wenn Sie die Länge eines Arrays deklariert, aber seine Elemente nicht initialisieren, wird jedes Element initialisiert, als handele es sich um eine separate Variable.</span><span class="sxs-lookup"><span data-stu-id="e24fd-253">If you declare the length of an array but do not initialize its elements, each element is initialized as if it were a separate variable.</span></span>  
  
## <a name="static-local-variable-lifetime"></a><span data-ttu-id="e24fd-254">Lebensdauer der statischen lokalen Variablen</span><span class="sxs-lookup"><span data-stu-id="e24fd-254">Static Local Variable Lifetime</span></span>  
 <span data-ttu-id="e24fd-255">Ein `Static` lokale Variable verfügt über eine längere Lebensdauer als die Prozedur, die in der sie deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="e24fd-255">A `Static` local variable has a longer lifetime than that of the procedure in which it is declared.</span></span> <span data-ttu-id="e24fd-256">Die Grenzen der Lebensdauer der Variablen ist davon abhängig, in die Prozedur deklariert wird und ob es sich handelt `Shared`.</span><span class="sxs-lookup"><span data-stu-id="e24fd-256">The boundaries of the variable's lifetime depend on where the procedure is declared and whether it is `Shared`.</span></span>  
  
|<span data-ttu-id="e24fd-257">Prozedurdeklaration</span><span class="sxs-lookup"><span data-stu-id="e24fd-257">Procedure declaration</span></span>|<span data-ttu-id="e24fd-258">Variable ist initialisiert</span><span class="sxs-lookup"><span data-stu-id="e24fd-258">Variable initialized</span></span>|<span data-ttu-id="e24fd-259">Variable beendet vorhandene</span><span class="sxs-lookup"><span data-stu-id="e24fd-259">Variable stops existing</span></span>|  
|---|---|---|  
|<span data-ttu-id="e24fd-260">In einem Modul</span><span class="sxs-lookup"><span data-stu-id="e24fd-260">In a module</span></span>|<span data-ttu-id="e24fd-261">Das erste Mal wird die Prozedur aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="e24fd-261">The first time the procedure is called</span></span>|<span data-ttu-id="e24fd-262">Wenn das Programm die Ausführung beendet.</span><span class="sxs-lookup"><span data-stu-id="e24fd-262">When your program stops execution</span></span>|  
|<span data-ttu-id="e24fd-263">In einer Klasse oder Struktur ist Prozedur `Shared`</span><span class="sxs-lookup"><span data-stu-id="e24fd-263">In a class or structure, procedure is `Shared`</span></span>|<span data-ttu-id="e24fd-264">Das erste Mal wird die Prozedur in einer bestimmten Instanz oder für die Klasse oder Struktur selbst aufgerufen</span><span class="sxs-lookup"><span data-stu-id="e24fd-264">The first time the procedure is called either on a specific instance or on the class or structure itself</span></span>|<span data-ttu-id="e24fd-265">Wenn das Programm die Ausführung beendet.</span><span class="sxs-lookup"><span data-stu-id="e24fd-265">When your program stops execution</span></span>|  
|<span data-ttu-id="e24fd-266">Ist nicht in einer Klasse oder Struktur die Prozedur `Shared`</span><span class="sxs-lookup"><span data-stu-id="e24fd-266">In a class or structure, procedure isn't `Shared`</span></span>|<span data-ttu-id="e24fd-267">Das erste Mal wird die Prozedur in einer bestimmten Instanz aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="e24fd-267">The first time the procedure is called on a specific instance</span></span>|<span data-ttu-id="e24fd-268">Wenn die Instanz freigegeben wird, für die Garbagecollection (GC)</span><span class="sxs-lookup"><span data-stu-id="e24fd-268">When the instance is released for garbage collection (GC)</span></span>|  
  
## <a name="attributes-and-modifiers"></a><span data-ttu-id="e24fd-269">Attribute und -Modifizierern</span><span class="sxs-lookup"><span data-stu-id="e24fd-269">Attributes and Modifiers</span></span>  
 <span data-ttu-id="e24fd-270">Sie können Attribute nur für Membervariablen und nicht auf lokale Variablen anwenden.</span><span class="sxs-lookup"><span data-stu-id="e24fd-270">You can apply attributes only to member variables, not to local variables.</span></span> <span data-ttu-id="e24fd-271">Ein Attribut trägt dazu bei Informationen zu den Metadaten der Assembly, die hat keine Bedeutung für die temporäre Speicherung, z. B. lokale Variablen.</span><span class="sxs-lookup"><span data-stu-id="e24fd-271">An attribute contributes information to the assembly's metadata, which is not meaningful for temporary storage such as local variables.</span></span>  
  
 <span data-ttu-id="e24fd-272">Auf Modulebene, können Sie keine der `Static` Modifizierer, um Member Variablen zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="e24fd-272">At module level, you cannot use the `Static` modifier to declare member variables.</span></span> <span data-ttu-id="e24fd-273">Auf Prozedurebene, können keine `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, Zugriffsmodifizierern Lokale Variablen deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="e24fd-273">At procedure level, you cannot use `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, or any access modifiers to declare local variables.</span></span>  
  
 <span data-ttu-id="e24fd-274">Sie können angeben, welcher Code eine Variable durch Angabe zugreifen kann ein `accessmodifier`.</span><span class="sxs-lookup"><span data-stu-id="e24fd-274">You can specify what code can access a variable by supplying an `accessmodifier`.</span></span> <span data-ttu-id="e24fd-275">Standardmäßig gilt für Klassen- und Variablen (außerhalb einer Prozedur) privaten Zugriff und Strukturmembervariablen in öffentlichen Zugriff.</span><span class="sxs-lookup"><span data-stu-id="e24fd-275">Class and module member variables (outside any procedure) default to private access, and structure member variables default to public access.</span></span> <span data-ttu-id="e24fd-276">Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.</span><span class="sxs-lookup"><span data-stu-id="e24fd-276">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="e24fd-277">Sie können keine Zugriffsmodifizierer für lokale Variablen (innerhalb einer Prozedur).</span><span class="sxs-lookup"><span data-stu-id="e24fd-277">You cannot use access modifiers on local variables (inside a procedure).</span></span>  
  
 <span data-ttu-id="e24fd-278">Sie können angeben, `WithEvents` nur auf Membervariablen und nicht auf lokale Variablen innerhalb einer Prozedur.</span><span class="sxs-lookup"><span data-stu-id="e24fd-278">You can specify `WithEvents` only on member variables, not on local variables inside a procedure.</span></span> <span data-ttu-id="e24fd-279">Bei Angabe von `WithEvents`, der Datentyp der Variablen muss einen bestimmten Klassentyp sein, nicht `Object`.</span><span class="sxs-lookup"><span data-stu-id="e24fd-279">If you specify `WithEvents`, the data type of the variable must be a specific class type, not `Object`.</span></span> <span data-ttu-id="e24fd-280">Sie können ein Array mit nicht deklarieren `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="e24fd-280">You cannot declare an array with `WithEvents`.</span></span> <span data-ttu-id="e24fd-281">Weitere Informationen zu Ereignissen finden Sie unter [Ereignisse](../../../visual-basic/programming-guide/language-features/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="e24fd-281">For more information about events, see [Events](../../../visual-basic/programming-guide/language-features/events/index.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e24fd-282">Code außerhalb einer Klasse, einer Struktur oder eines Moduls muss den Namen einer Membervariablen mit dem Namen der Klasse, der Struktur oder des Moduls qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="e24fd-282">Code outside a class, structure, or module must qualify a member variable's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="e24fd-283">Code außerhalb einer Prozedur oder eines Blocks kann auf alle lokalen Variablen in dieser Prozedur oder eines Blocks verweisen.</span><span class="sxs-lookup"><span data-stu-id="e24fd-283">Code outside a procedure or block cannot refer to any local variables within that procedure or block.</span></span>  
  
## <a name="releasing-managed-resources"></a><span data-ttu-id="e24fd-284">Verwaltete Ressourcen freizugeben</span><span class="sxs-lookup"><span data-stu-id="e24fd-284">Releasing Managed Resources</span></span>  
 <span data-ttu-id="e24fd-285">Der Garbagecollector von .NET Framework gibt ohne zusätzliche Codierung ihrerseits verwalteten Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="e24fd-285">The .NET Framework garbage collector disposes of managed resources without any extra coding on your part.</span></span> <span data-ttu-id="e24fd-286">Sie können jedoch das Verwerfen einer verwalteten Ressource nicht erst, wenn für den Garbage Collector erzwingen.</span><span class="sxs-lookup"><span data-stu-id="e24fd-286">However, you can force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>  
  
 <span data-ttu-id="e24fd-287">Wenn eine Klasse auf eine besonders wertvolle und knappe Ressource (z. B. eine Verbindung oder eine Datei Datenbankhandle) enthält, sollten Sie nicht warten, bis zur nächsten Garbagecollection auf eine Klasseninstanz bereinigen, die nicht mehr verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e24fd-287">If a class holds onto a particularly valuable and scarce resource (such as a database connection or file handle), you might not want to wait until the next garbage collection to clean up a class instance that's no longer in use.</span></span> <span data-ttu-id="e24fd-288">Implementieren der <xref:System.IDisposable> Schnittstelle, um eine Möglichkeit, Ressourcen, bevor eine Garbagecollection freigegeben bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="e24fd-288">A class may implement the <xref:System.IDisposable> interface to provide a way to release resources before a garbage collection.</span></span> <span data-ttu-id="e24fd-289">Macht eine Klasse, die diese Schnittstelle implementiert eine `Dispose` Methode, die aufgerufen werden kann, um wertvolle Ressourcen sofort freigegeben werden zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="e24fd-289">A class that implements that interface exposes a `Dispose` method that can be called to force valuable resources to be released immediately.</span></span>  
  
 <span data-ttu-id="e24fd-290">Die `Using` Anweisung automatisiert den Prozess der Erwerb einer Ressourcenpools, eine Reihe von Anweisungen ausgeführt und dann löschen, mit der die Ressource.</span><span class="sxs-lookup"><span data-stu-id="e24fd-290">The `Using` statement automates the process of acquiring a resource, executing a set of statements, and then disposing of the resource.</span></span> <span data-ttu-id="e24fd-291">Allerdings muss die Ressource implementieren die <xref:System.IDisposable> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="e24fd-291">However, the resource must implement the <xref:System.IDisposable> interface.</span></span> <span data-ttu-id="e24fd-292">Weitere Informationen finden Sie unter [using-Anweisung](../../../visual-basic/language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e24fd-292">For more information, see [Using Statement](../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e24fd-293">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e24fd-293">Example</span></span>  
 <span data-ttu-id="e24fd-294">Das folgende Beispiel deklariert Variablen mithilfe der `Dim` -Anweisung mit verschiedenen Optionen.</span><span class="sxs-lookup"><span data-stu-id="e24fd-294">The following example declares variables by using the `Dim` statement with various options.</span></span>  
  
 [!code-vb[VbVbalrStatements#141](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="e24fd-295">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e24fd-295">Example</span></span>  
 <span data-ttu-id="e24fd-296">Das folgende Beispiel listet die Primzahlen zwischen 1 und 30 ein.</span><span class="sxs-lookup"><span data-stu-id="e24fd-296">The following example lists the prime numbers between 1 and 30.</span></span> <span data-ttu-id="e24fd-297">Der Gültigkeitsbereich der lokalen Variablen wird in den Kommentaren im Code beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e24fd-297">The scope of local variables is described in code comments.</span></span>  
  
 [!code-vb[VbVbalrStatements#142](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="e24fd-298">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e24fd-298">Example</span></span>  
 <span data-ttu-id="e24fd-299">Im folgenden Beispiel die `speedValue` Variablen auf Klassenebene deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="e24fd-299">In the following example, the `speedValue` variable is declared at the class level.</span></span> <span data-ttu-id="e24fd-300">Die `Private` Schlüsselwort wird verwendet, um die Variable zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="e24fd-300">The `Private` keyword is used to declare the variable.</span></span> <span data-ttu-id="e24fd-301">Die Variable kann zugegriffen werden, von einer Prozedur in der `Car` Klasse.</span><span class="sxs-lookup"><span data-stu-id="e24fd-301">The variable can be accessed by any procedure in the `Car` class.</span></span>  
  
 [!code-vb[VbVbalrStatements#144](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_3.vb)]  
  
 [!code-vb[VbVbalrStatements#145](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="e24fd-302">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e24fd-302">See Also</span></span>  
 [<span data-ttu-id="e24fd-303">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e24fd-303">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
 [<span data-ttu-id="e24fd-304">ReDim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e24fd-304">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="e24fd-305">Option Explicit-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e24fd-305">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [<span data-ttu-id="e24fd-306">Option Infer-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e24fd-306">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [<span data-ttu-id="e24fd-307">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e24fd-307">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="e24fd-308">Seite „Kompilieren“, Projekt-Designer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e24fd-308">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)  
 [<span data-ttu-id="e24fd-309">Variablendeklaration</span><span class="sxs-lookup"><span data-stu-id="e24fd-309">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="e24fd-310">Arrays</span><span class="sxs-lookup"><span data-stu-id="e24fd-310">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="e24fd-311">Objektinitialisierer: Benannte und anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="e24fd-311">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [<span data-ttu-id="e24fd-312">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="e24fd-312">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [<span data-ttu-id="e24fd-313">Objektinitialisierer: Benannte und anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="e24fd-313">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [<span data-ttu-id="e24fd-314">Gewusst wie: Deklarieren eines Objekts mithilfe eines Objektinitialisierers</span><span class="sxs-lookup"><span data-stu-id="e24fd-314">How to: Declare an Object by Using an Object Initializer</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)  
 [<span data-ttu-id="e24fd-315">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="e24fd-315">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
