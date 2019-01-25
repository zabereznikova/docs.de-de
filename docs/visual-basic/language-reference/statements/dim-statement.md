---
title: Dim-Anweisung (Visual Basic)
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
ms.openlocfilehash: 487e2ff55f256bc06a463043dd2849a404eb82cd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54567736"
---
# <a name="dim-statement-visual-basic"></a><span data-ttu-id="0308c-102">Dim-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0308c-102">Dim Statement (Visual Basic)</span></span>
<span data-ttu-id="0308c-103">Deklariert und reserviert Speicherplatz für eine oder mehrere Variablen.</span><span class="sxs-lookup"><span data-stu-id="0308c-103">Declares and allocates storage space for one or more variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0308c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0308c-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] [[ Shared ] [ Shadows ] | [ Static ]] [ ReadOnly ]   
Dim [ WithEvents ] variablelist  
```  
  
## <a name="parts"></a><span data-ttu-id="0308c-105">Teile</span><span class="sxs-lookup"><span data-stu-id="0308c-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="0308c-106">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="0308c-106">Optional.</span></span> <span data-ttu-id="0308c-107">Finden Sie unter [Liste](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="0308c-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="0308c-108">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="0308c-108">Optional.</span></span> <span data-ttu-id="0308c-109">Einer der folgenden Werte ist möglich:</span><span class="sxs-lookup"><span data-stu-id="0308c-109">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="0308c-110">Public</span><span class="sxs-lookup"><span data-stu-id="0308c-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="0308c-111">Protected</span><span class="sxs-lookup"><span data-stu-id="0308c-111">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="0308c-112">Friend</span><span class="sxs-lookup"><span data-stu-id="0308c-112">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="0308c-113">Private</span><span class="sxs-lookup"><span data-stu-id="0308c-113">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   [<span data-ttu-id="0308c-114">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="0308c-114">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)
    
    - [<span data-ttu-id="0308c-115">Private Protected</span><span class="sxs-lookup"><span data-stu-id="0308c-115">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)

     <span data-ttu-id="0308c-116">Siehe [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="0308c-116">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `Shared`  
  
     <span data-ttu-id="0308c-117">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="0308c-117">Optional.</span></span> <span data-ttu-id="0308c-118">Finden Sie unter [freigegebene](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="0308c-118">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="0308c-119">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="0308c-119">Optional.</span></span> <span data-ttu-id="0308c-120">Finden Sie unter [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="0308c-120">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
-   `Static`  
  
     <span data-ttu-id="0308c-121">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="0308c-121">Optional.</span></span> <span data-ttu-id="0308c-122">Finden Sie unter [statische](../../../visual-basic/language-reference/modifiers/static.md).</span><span class="sxs-lookup"><span data-stu-id="0308c-122">See [Static](../../../visual-basic/language-reference/modifiers/static.md).</span></span>  
  
-   `ReadOnly`  
  
     <span data-ttu-id="0308c-123">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="0308c-123">Optional.</span></span> <span data-ttu-id="0308c-124">Finden Sie unter [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="0308c-124">See [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
-   `WithEvents`  
  
     <span data-ttu-id="0308c-125">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="0308c-125">Optional.</span></span> <span data-ttu-id="0308c-126">Gibt an, dass diese Objektvariablen, die auf Instanzen einer Klasse zu verweisen, die Ereignisse auslösen kann.</span><span class="sxs-lookup"><span data-stu-id="0308c-126">Specifies that these are object variables that refer to instances of a class that can raise events.</span></span> <span data-ttu-id="0308c-127">Finden Sie unter [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md).</span><span class="sxs-lookup"><span data-stu-id="0308c-127">See [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md).</span></span>  
  
-   `variablelist`  
  
     <span data-ttu-id="0308c-128">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0308c-128">Required.</span></span> <span data-ttu-id="0308c-129">Liste der Variablen, die in dieser Anweisung deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="0308c-129">List of variables being declared in this statement.</span></span>  
  
     `variable [ , variable ... ]`  
  
     <span data-ttu-id="0308c-130">Jede `variable` weist folgende Syntax und Bestandteile auf:</span><span class="sxs-lookup"><span data-stu-id="0308c-130">Each `variable` has the following syntax and parts:</span></span>  
  
     <span data-ttu-id="0308c-131">`variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="0308c-131">`variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`</span></span>  
  
    |<span data-ttu-id="0308c-132">Segment</span><span class="sxs-lookup"><span data-stu-id="0308c-132">Part</span></span>|<span data-ttu-id="0308c-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0308c-133">Description</span></span>|  
    |---|---|  
    |`variablename`|<span data-ttu-id="0308c-134">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0308c-134">Required.</span></span> <span data-ttu-id="0308c-135">Name der Variablen.</span><span class="sxs-lookup"><span data-stu-id="0308c-135">Name of the variable.</span></span> <span data-ttu-id="0308c-136">Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="0308c-136">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
    |`boundslist`|<span data-ttu-id="0308c-137">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="0308c-137">Optional.</span></span> <span data-ttu-id="0308c-138">Liste der Grenzen der einzelnen Dimensionen des Arrayvariable.</span><span class="sxs-lookup"><span data-stu-id="0308c-138">List of bounds of each dimension of an array variable.</span></span>|  
    |`New`|<span data-ttu-id="0308c-139">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="0308c-139">Optional.</span></span> <span data-ttu-id="0308c-140">Erstellt eine neue Instanz der Klasse bei der `Dim` Anweisung wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0308c-140">Creates a new instance of the class when the `Dim` statement runs.</span></span>|  
    |`datatype`|<span data-ttu-id="0308c-141">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="0308c-141">Optional.</span></span> <span data-ttu-id="0308c-142">Der Datentyp der Variablen.</span><span class="sxs-lookup"><span data-stu-id="0308c-142">Data type of the variable.</span></span>|  
    |`With`|<span data-ttu-id="0308c-143">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="0308c-143">Optional.</span></span> <span data-ttu-id="0308c-144">Führt der Objektinitialisiererliste.</span><span class="sxs-lookup"><span data-stu-id="0308c-144">Introduces the object initializer list.</span></span>|  
    |`propertyname`|<span data-ttu-id="0308c-145">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="0308c-145">Optional.</span></span> <span data-ttu-id="0308c-146">Der Name einer Eigenschaft in der Klasse nutzen Sie eine Instanz von.</span><span class="sxs-lookup"><span data-stu-id="0308c-146">The name of a property in the class you are making an instance of.</span></span>|  
    |`propinitializer`|<span data-ttu-id="0308c-147">Nach dem erforderlichen `propertyname` =.</span><span class="sxs-lookup"><span data-stu-id="0308c-147">Required after `propertyname` =.</span></span> <span data-ttu-id="0308c-148">Der Ausdruck, der ausgewertet und auf den Eigenschaftennamen zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="0308c-148">The expression that is evaluated and assigned to the property name.</span></span>|  
    |`initializer`|<span data-ttu-id="0308c-149">Optional, wenn `New` nicht angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="0308c-149">Optional if `New` is not specified.</span></span> <span data-ttu-id="0308c-150">Ein Ausdruck, der ausgewertet und bei der Erstellung der Variablen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="0308c-150">Expression that is evaluated and assigned to the variable when it is created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0308c-151">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0308c-151">Remarks</span></span>  
 <span data-ttu-id="0308c-152">Visual Basic-Compiler verwendet die `Dim` Anweisung, um zu bestimmen, die Variable den Datentyp und andere Informationen, z. B. welcher Code auf die Variable zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="0308c-152">The Visual Basic compiler uses the `Dim` statement to determine the variable's data type and other information, such as what code can access the variable.</span></span> <span data-ttu-id="0308c-153">Das folgende Beispiel deklariert eine Variable für ein `Integer` Wert.</span><span class="sxs-lookup"><span data-stu-id="0308c-153">The following example declares a variable to hold an `Integer` value.</span></span>  
  
```vb  
Dim numberOfStudents As Integer  
```  
  
 <span data-ttu-id="0308c-154">Sie können einen beliebigen Datentyp aufweisen oder den Namen einer Enumeration, Struktur, Klasse oder Schnittstelle angeben.</span><span class="sxs-lookup"><span data-stu-id="0308c-154">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>  
  
```vb  
Dim finished As Boolean  
Dim monitorBox As System.Windows.Forms.Form  
```  
  
 <span data-ttu-id="0308c-155">Für einen Verweistyp handelt, Sie verwenden die `New` Schlüsselwort, um eine neue Instanz der Klasse zu erstellen oder eine Struktur, die durch den-Datentyp angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="0308c-155">For a reference type, you use the `New` keyword to create a new instance of the class or structure that is specified by the data type.</span></span> <span data-ttu-id="0308c-156">Bei Verwendung von `New`, verwenden Sie einen Initialisiererausdruck nicht.</span><span class="sxs-lookup"><span data-stu-id="0308c-156">If you use `New`, you do not use an initializer expression.</span></span> <span data-ttu-id="0308c-157">Stattdessen geben Sie Argumente, wenn erforderlich, an den Konstruktor der Klasse sind von denen Sie die Variable erstellen.</span><span class="sxs-lookup"><span data-stu-id="0308c-157">Instead, you supply arguments, if they are required, to the constructor of the class from which you are creating the variable.</span></span>  
  
```vb  
Dim bottomLabel As New System.Windows.Forms.Label  
```  
  
 <span data-ttu-id="0308c-158">Sie können eine Variable in einer Prozedur, blockieren, Klasse, Struktur oder Modul deklarieren.</span><span class="sxs-lookup"><span data-stu-id="0308c-158">You can declare a variable in a procedure, block, class, structure, or module.</span></span> <span data-ttu-id="0308c-159">Sie können eine Variable in einer Quelldatei, Namespace oder Schnittstelle nicht deklarieren.</span><span class="sxs-lookup"><span data-stu-id="0308c-159">You cannot declare a variable in a source file, namespace, or interface.</span></span> <span data-ttu-id="0308c-160">Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="0308c-160">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="0308c-161">Eine Variable, die auf Modulebene außerhalb einer Prozedur, deklariert ist ist eine *Membervariable* oder *Feld*.</span><span class="sxs-lookup"><span data-stu-id="0308c-161">A variable that is declared at module level, outside any procedure, is a *member variable* or *field*.</span></span> <span data-ttu-id="0308c-162">Membervariablen sind in der gesamten die Klasse, Struktur oder Modul.</span><span class="sxs-lookup"><span data-stu-id="0308c-162">Member variables are in scope throughout their class, structure, or module.</span></span> <span data-ttu-id="0308c-163">Eine Variable, die auf Prozedurebene deklariert wird ist eine *lokale Variable*.</span><span class="sxs-lookup"><span data-stu-id="0308c-163">A variable that is declared at procedure level is a *local variable*.</span></span> <span data-ttu-id="0308c-164">Lokale Variablen sind nur in die Prozedur oder eines Blocks.</span><span class="sxs-lookup"><span data-stu-id="0308c-164">Local variables are in scope only within their procedure or block.</span></span>  
  
 <span data-ttu-id="0308c-165">Die folgenden Zugriffsmodifizierer zum Deklarieren von Variablen, die außerhalb einer Prozedur verwendet werden: `Public`, `Protected`, `Friend`, `Protected Friend`, und `Private`.</span><span class="sxs-lookup"><span data-stu-id="0308c-165">The following access modifiers are used to declare variables outside a procedure: `Public`, `Protected`, `Friend`, `Protected Friend`, and `Private`.</span></span> <span data-ttu-id="0308c-166">Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="0308c-166">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="0308c-167">Die `Dim` Schlüsselwort ist optional und in der Regel weggelassen wird, wenn Sie einen der folgenden Modifizierer angeben: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, oder `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="0308c-167">The `Dim` keyword is optional and usually omitted if you specify any of the following modifiers: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, or `WithEvents`.</span></span>  
  
```vb  
Public maximumAllowed As Double  
Protected Friend currentUserName As String  
Private salary As Decimal  
Static runningTotal As Integer  
```  
  
 <span data-ttu-id="0308c-168">Wenn `Option Explicit` ist aktiviert (Standard), erfordert der Compiler eine Deklaration für jede Variable, die Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="0308c-168">If `Option Explicit` is on (the default), the compiler requires a declaration for every variable you use.</span></span> <span data-ttu-id="0308c-169">Weitere Informationen finden Sie unter [Option Explicit-Anweisung](../../../visual-basic/language-reference/statements/option-explicit-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0308c-169">For more information, see [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md).</span></span>  
  
## <a name="specifying-an-initial-value"></a><span data-ttu-id="0308c-170">Geben Sie einen anfänglichen Wert</span><span class="sxs-lookup"><span data-stu-id="0308c-170">Specifying an Initial Value</span></span>  
 <span data-ttu-id="0308c-171">Sie können einen Wert einer Variablen zuweisen, bei der Erstellung.</span><span class="sxs-lookup"><span data-stu-id="0308c-171">You can assign a value to a variable when it is created.</span></span> <span data-ttu-id="0308c-172">Für einen Werttyp handelt, Sie verwenden eine *Initialisierer* , geben Sie einen Ausdruck, der Variablen zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="0308c-172">For a value type, you use an *initializer* to supply an expression to be assigned to the variable.</span></span> <span data-ttu-id="0308c-173">Der Ausdruck muss mit einer Konstante ausgewertet werden, die zur Kompilierzeit berechnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="0308c-173">The expression must evaluate to a constant that can be calculated at compile time.</span></span>  
  
```vb  
Dim quantity As Integer = 10  
Dim message As String = "Just started"  
```  
  
 <span data-ttu-id="0308c-174">Wenn ein Initialisierer angegeben ist, und ein Datentyp nicht, in angegeben ist eine `As` -Klausel *Typrückschluss* wird verwendet, um den Datentyp aus dem Initialisierer abzuleiten.</span><span class="sxs-lookup"><span data-stu-id="0308c-174">If an initializer is specified and a data type is not specified in an `As` clause, *type inference* is used to infer the data type from the initializer.</span></span> <span data-ttu-id="0308c-175">Im folgenden Beispiel beide `num1` und `num2` sind stark typisiert, als ganze Zahlen.</span><span class="sxs-lookup"><span data-stu-id="0308c-175">In the following example, both `num1` and `num2` are strongly typed as integers.</span></span> <span data-ttu-id="0308c-176">In der zweiten Deklaration leitet der Typrückschluss den Typ aus dem Wert 3.</span><span class="sxs-lookup"><span data-stu-id="0308c-176">In the second declaration, type inference infers the type from the value 3.</span></span>  
  
```vb  
' Use explicit typing.  
Dim num1 As Integer = 3  
  
' Use local type inference.  
Dim num2 = 3  
```  
  
 <span data-ttu-id="0308c-177">Typrückschluss ist auf Prozedurebene gültig.</span><span class="sxs-lookup"><span data-stu-id="0308c-177">Type inference applies at the procedure level.</span></span> <span data-ttu-id="0308c-178">Es gilt nicht außerhalb einer Prozedur in einer Klasse, Struktur, Modul oder Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="0308c-178">It does not apply outside a procedure in a class, structure, module, or interface.</span></span> <span data-ttu-id="0308c-179">Weitere Informationen zu den Typrückschluss, finden Sie unter [Option Infer-Anweisung](../../../visual-basic/language-reference/statements/option-infer-statement.md) und [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="0308c-179">For more information about type inference, see [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
 <span data-ttu-id="0308c-180">Informationen darüber, was geschieht, wenn einer/m / -Datentyp nicht angegeben ist, finden Sie unter [-Standarddatentypen und-Werte](../../../visual-basic/language-reference/statements/dim-statement.md#default) weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="0308c-180">For information about what happens when a data type or initializer is not specified, see [Default Data Types and Values](../../../visual-basic/language-reference/statements/dim-statement.md#default) later in this topic.</span></span>  
  
 <span data-ttu-id="0308c-181">Sie können eine *Objektinitialisierer* um Instanzen von benannten und anonymen Typen zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="0308c-181">You can use an *object initializer* to declare instances of named and anonymous types.</span></span> <span data-ttu-id="0308c-182">Der folgende Code erstellt eine Instanz von einem `Student` Klasse und verwendet Sie einen Objektinitialisierer, um Eigenschaften zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="0308c-182">The following code creates an instance of a `Student` class and uses an object initializer to initialize properties.</span></span>  
  
```vb  
Dim student1 As New Student With {.First = "Michael",   
                                  .Last = "Tucker"}  
```  
  
 <span data-ttu-id="0308c-183">Weitere Informationen über Objektinitialisierer finden Sie unter [Vorgehensweise: Deklarieren eines Objekts mithilfe eines Objektinitialisierers](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [Objektinitialisierer: Benannte und anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), und [anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="0308c-183">For more information about object initializers, see [How to: Declare an Object by Using an Object Initializer](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [Object Initializers: Named and Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), and [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
## <a name="declaring-multiple-variables"></a><span data-ttu-id="0308c-184">Deklarieren Sie mehrere Variablen</span><span class="sxs-lookup"><span data-stu-id="0308c-184">Declaring Multiple Variables</span></span>  
 <span data-ttu-id="0308c-185">Sie können mehrere Variablen in einer deklarationsanweisung, deklarieren, der Variablenname, der für jede einzelne und den nachfolgenden jedes Arrayname in Klammern angeben.</span><span class="sxs-lookup"><span data-stu-id="0308c-185">You can declare several variables in one declaration statement, specifying the variable name for each one, and following each array name with parentheses.</span></span> <span data-ttu-id="0308c-186">Mehrere Variablen werden durch Kommas voneinander getrennt.</span><span class="sxs-lookup"><span data-stu-id="0308c-186">Multiple variables are separated by commas.</span></span>  
  
```vb  
Dim lastTime, nextTime, allTimes() As Date  
```  
  
 <span data-ttu-id="0308c-187">Wenn Sie mehr als eine Variable mit einem deklarieren `As` -Klausel kann keinen Initialisierer für diese Gruppe von Variablen nicht bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0308c-187">If you declare more than one variable with one `As` clause, you cannot supply an initializer for that group of variables.</span></span>  
  
 <span data-ttu-id="0308c-188">Sie können unterschiedliche Datentypen für verschiedene Variablen angeben, über ein separates `As` -Klausel für jede Variable, die Sie deklarieren.</span><span class="sxs-lookup"><span data-stu-id="0308c-188">You can specify different data types for different variables by using a separate `As` clause for each variable you declare.</span></span> <span data-ttu-id="0308c-189">Jede Variable wird in der ersten angegebenen Datentyp `As` -Klausel nach dem die `variablename` Teil.</span><span class="sxs-lookup"><span data-stu-id="0308c-189">Each variable takes the data type specified in the first `As` clause encountered after its `variablename` part.</span></span>  
  
```vb  
Dim a, b, c As Single, x, y As Double, i As Integer  
' a, b, and c are all Single; x and y are both Double  
```  
  
## <a name="arrays"></a><span data-ttu-id="0308c-190">Arrays</span><span class="sxs-lookup"><span data-stu-id="0308c-190">Arrays</span></span>  
 <span data-ttu-id="0308c-191">Sie können eine Variable für deklarieren eine *Array*, die mehrere Werte enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="0308c-191">You can declare a variable to hold an *array*, which can hold multiple values.</span></span> <span data-ttu-id="0308c-192">Um anzugeben, dass eine Variable ein Array enthält, führen Sie die `variablename` sofort mit Klammern.</span><span class="sxs-lookup"><span data-stu-id="0308c-192">To specify that a variable holds an array, follow its `variablename` immediately with parentheses.</span></span> <span data-ttu-id="0308c-193">Weitere Informationen zu Arrays finden Sie unter [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="0308c-193">For more information about arrays, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
 <span data-ttu-id="0308c-194">Sie können die untere und obere Grenze jeder Dimension eines Arrays angeben.</span><span class="sxs-lookup"><span data-stu-id="0308c-194">You can specify the lower and upper bound of each dimension of an array.</span></span> <span data-ttu-id="0308c-195">Um dies zu erreichen, fügen einen `boundslist` innerhalb der Klammern.</span><span class="sxs-lookup"><span data-stu-id="0308c-195">To do this, include a `boundslist` inside the parentheses.</span></span> <span data-ttu-id="0308c-196">Für jede Dimension die `boundslist` gibt an, die obere Grenze und optional die untere Grenze.</span><span class="sxs-lookup"><span data-stu-id="0308c-196">For each dimension, the `boundslist` specifies the upper bound and optionally the lower bound.</span></span> <span data-ttu-id="0308c-197">Die Untergrenze ist immer 0 (null), ob Sie es angeben.</span><span class="sxs-lookup"><span data-stu-id="0308c-197">The lower bound is always zero, whether you specify it or not.</span></span> <span data-ttu-id="0308c-198">Jeder Index kann von 0 (null), durch den Wert der oberen Grenze variieren.</span><span class="sxs-lookup"><span data-stu-id="0308c-198">Each index can vary from zero through its upper bound value.</span></span>  
  
 <span data-ttu-id="0308c-199">Die folgenden beiden Anweisungen sind gleichwertig.</span><span class="sxs-lookup"><span data-stu-id="0308c-199">The following two statements are equivalent.</span></span> <span data-ttu-id="0308c-200">Jede Anweisung deklariert ein Array von 21 `Integer` Elemente.</span><span class="sxs-lookup"><span data-stu-id="0308c-200">Each statement declares an array of 21 `Integer` elements.</span></span> <span data-ttu-id="0308c-201">Wenn Sie das Array zugreifen, kann der Index von 0 bis 20 variieren.</span><span class="sxs-lookup"><span data-stu-id="0308c-201">When you access the array, the index can vary from 0 through 20.</span></span>  
  
```vb  
Dim totals(20) As Integer  
Dim totals(0 To 20) As Integer  
```  
  
 <span data-ttu-id="0308c-202">Die folgende Anweisung deklariert ein zweidimensionales Array vom Typ `Double`.</span><span class="sxs-lookup"><span data-stu-id="0308c-202">The following statement declares a two-dimensional array of type `Double`.</span></span> <span data-ttu-id="0308c-203">Das Array hat 4 Zeilen (3 + 1) der 6 Spalten (5 + 1).</span><span class="sxs-lookup"><span data-stu-id="0308c-203">The array has 4 rows (3 + 1) of 6 columns (5 + 1) each.</span></span> <span data-ttu-id="0308c-204">Beachten Sie, dass eine Obergrenze den höchsten möglichen Wert für den Index, nicht die Länge der Dimension darstellt.</span><span class="sxs-lookup"><span data-stu-id="0308c-204">Note that an upper bound represents the highest possible value for the index, not the length of the dimension.</span></span> <span data-ttu-id="0308c-205">Die Länge der Dimension ist die obere Grenze plus eins.</span><span class="sxs-lookup"><span data-stu-id="0308c-205">The length of the dimension is the upper bound plus one.</span></span>  
  
```vb  
Dim matrix2(3, 5) As Double  
```  
  
 <span data-ttu-id="0308c-206">Ein Array kann von 1 bis 32 Dimensionen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="0308c-206">An array can have from 1 to 32 dimensions.</span></span>  
  
 <span data-ttu-id="0308c-207">Sie können alle Grenzen in eine Arraydeklaration leer lassen.</span><span class="sxs-lookup"><span data-stu-id="0308c-207">You can leave all the bounds blank in an array declaration.</span></span> <span data-ttu-id="0308c-208">Wenn Sie dies tun, das Array hat die Anzahl der Dimensionen, die Sie angeben, aber es ist nicht initialisiert.</span><span class="sxs-lookup"><span data-stu-id="0308c-208">If you do this, the array has the number of dimensions you specify, but it is uninitialized.</span></span> <span data-ttu-id="0308c-209">Es hat den Wert `Nothing` bis Sie über mindestens initialisieren einige seiner Elemente.</span><span class="sxs-lookup"><span data-stu-id="0308c-209">It has a value of `Nothing` until you initialize at least some of its elements.</span></span> <span data-ttu-id="0308c-210">Die `Dim` -Anweisung muss entweder Grenzen für alle Dimensionen oder für keine Dimensionen angegeben.</span><span class="sxs-lookup"><span data-stu-id="0308c-210">The `Dim` statement must specify bounds either for all dimensions or for no dimensions.</span></span>  
  
```vb  
' Declare an array with blank array bounds.  
Dim messages() As String  
' Initialize the array.  
ReDim messages(4)  
```  
  
 <span data-ttu-id="0308c-211">Wenn das Array mehr als eine Dimension hat, müssen Sie Kommas zwischen die Klammern an, dass die Anzahl der Dimensionen einschließen.</span><span class="sxs-lookup"><span data-stu-id="0308c-211">If the array has more than one dimension, you must include commas between the parentheses to indicate the number of dimensions.</span></span>  
  
```vb  
Dim oneDimension(), twoDimensions(,), threeDimensions(,,) As Byte  
```  
  
 <span data-ttu-id="0308c-212">Sie können deklarieren, ein *Array der Länge 0 (null)* durch deklarieren eine der Dimensionen des Arrays -1 sein.</span><span class="sxs-lookup"><span data-stu-id="0308c-212">You can declare a *zero-length array* by declaring one of the array's dimensions to be -1.</span></span> <span data-ttu-id="0308c-213">Eine Variable, ein Array der Länge 0 (null) enthält, keinen Wert `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="0308c-213">A variable that holds a zero-length array does not have the value `Nothing`.</span></span> <span data-ttu-id="0308c-214">Arrays mit der Länge 0 (null) sind bestimmte Funktionen der common Language Runtime erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0308c-214">Zero-length arrays are required by certain common language runtime functions.</span></span> <span data-ttu-id="0308c-215">Wenn Sie versuchen, ein entsprechendes Array zugreifen, tritt eine Ausnahme zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="0308c-215">If you try to access such an array, a runtime exception occurs.</span></span> <span data-ttu-id="0308c-216">Weitere Informationen finden Sie unter [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="0308c-216">For more information, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
 <span data-ttu-id="0308c-217">Sie können die Werte eines Arrays mit einem Arrayliteral initialisieren.</span><span class="sxs-lookup"><span data-stu-id="0308c-217">You can initialize the values of an array by using an array literal.</span></span> <span data-ttu-id="0308c-218">Umschließen Sie zu diesem Zweck die Initialisierungswerte mit geschweiften Klammern (`{}`).</span><span class="sxs-lookup"><span data-stu-id="0308c-218">To do this, surround the initialization values with braces (`{}`).</span></span>  
  
```vb  
Dim longArray() As Long = {0, 1, 2, 3}  
```  
  
 <span data-ttu-id="0308c-219">Für mehrdimensionale Arrays wird die Initialisierung für jede separate Dimension in geschweiften Klammern in der äußeren Dimension eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="0308c-219">For multidimensional arrays, the initialization for each separate dimension is enclosed in braces in the outer dimension.</span></span> <span data-ttu-id="0308c-220">Die Elemente werden in zeilengerichteter Reihenfolge angegeben.</span><span class="sxs-lookup"><span data-stu-id="0308c-220">The elements are specified in row-major order.</span></span>  
  
```vb  
Dim twoDimensions(,) As Integer = {{0, 1, 2}, {10, 11, 12}}  
```  
  
 <span data-ttu-id="0308c-221">Weitere Informationen zu den Array-Literale, finden Sie unter [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="0308c-221">For more information about array literals, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
##  <a name="default"></a> <span data-ttu-id="0308c-222">Standarddatentypen und-Werte</span><span class="sxs-lookup"><span data-stu-id="0308c-222">Default Data Types and Values</span></span>  
 <span data-ttu-id="0308c-223">Die folgende Tabelle beschreibt die Ergebnisse der verschiedenen Kombinationen der Spezifizierung von Datentyp und Initialisierung in einer `Dim`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="0308c-223">The following table describes the results of various combinations of specifying the data type and initializer in a `Dim` statement.</span></span>  
  
|<span data-ttu-id="0308c-224">Datentyp angegeben?</span><span class="sxs-lookup"><span data-stu-id="0308c-224">Data type specified?</span></span>|<span data-ttu-id="0308c-225">Initialisierung angegeben?</span><span class="sxs-lookup"><span data-stu-id="0308c-225">Initializer specified?</span></span>|<span data-ttu-id="0308c-226">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0308c-226">Example</span></span>|<span data-ttu-id="0308c-227">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="0308c-227">Result</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="0308c-228">Nein</span><span class="sxs-lookup"><span data-stu-id="0308c-228">No</span></span>|<span data-ttu-id="0308c-229">Nein</span><span class="sxs-lookup"><span data-stu-id="0308c-229">No</span></span>|`Dim qty`|<span data-ttu-id="0308c-230">Wenn [Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) ist off (Standardeinstellung), die Variable festgelegt ist, um `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="0308c-230">If [Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) is off (the default), the variable is set to `Nothing`.</span></span><br /><br /> <span data-ttu-id="0308c-231">Wenn `Option Strict` aktiviert ist, tritt ein Kompilierzeitfehler auf.</span><span class="sxs-lookup"><span data-stu-id="0308c-231">If `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="0308c-232">Nein</span><span class="sxs-lookup"><span data-stu-id="0308c-232">No</span></span>|<span data-ttu-id="0308c-233">Ja</span><span class="sxs-lookup"><span data-stu-id="0308c-233">Yes</span></span>|`Dim qty = 5`|<span data-ttu-id="0308c-234">Wenn [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) ist (Standardeinstellung), geben Sie die Variable verwendet die Daten des Initialisierers.</span><span class="sxs-lookup"><span data-stu-id="0308c-234">If [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) is on (the default), the variable takes the data type of the initializer.</span></span> <span data-ttu-id="0308c-235">Finden Sie unter [lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="0308c-235">See [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span><br /><br /> <span data-ttu-id="0308c-236">Wenn `Option Infer` und `Option Strict` ausgeschaltet sind, nimmt die Variable den Datentyp des `Object` an.</span><span class="sxs-lookup"><span data-stu-id="0308c-236">If `Option Infer` is off and `Option Strict` is off, the variable takes the data type of `Object`.</span></span><br /><br /> <span data-ttu-id="0308c-237">Wenn `Option Infer` deaktiviert ist und `Option Strict` aktiviert ist, tritt ein Kompilierungsfehler auf.</span><span class="sxs-lookup"><span data-stu-id="0308c-237">If `Option Infer` is off and `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="0308c-238">Ja</span><span class="sxs-lookup"><span data-stu-id="0308c-238">Yes</span></span>|<span data-ttu-id="0308c-239">Nein</span><span class="sxs-lookup"><span data-stu-id="0308c-239">No</span></span>|`Dim qty As Integer`|<span data-ttu-id="0308c-240">Die Variable wird auf den Standardwert für den Datentyp initialisiert.</span><span class="sxs-lookup"><span data-stu-id="0308c-240">The variable is initialized to the default value for the data type.</span></span> <span data-ttu-id="0308c-241">Siehe Tabelle weiter unten in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="0308c-241">See the table later in this section.</span></span>|  
|<span data-ttu-id="0308c-242">Ja</span><span class="sxs-lookup"><span data-stu-id="0308c-242">Yes</span></span>|<span data-ttu-id="0308c-243">Ja</span><span class="sxs-lookup"><span data-stu-id="0308c-243">Yes</span></span>|`Dim qty  As Integer = 5`|<span data-ttu-id="0308c-244">Wenn der Datentyp der Initialisierung nicht in den angegebenen Datentyp konvertiert werden kann, tritt ein Fehler während der Kompilierung auf.</span><span class="sxs-lookup"><span data-stu-id="0308c-244">If the data type of the initializer is not convertible to the specified data type, a compile-time error occurs.</span></span>|  
  
 <span data-ttu-id="0308c-245">Wenn Sie einen Datentyp angeben, aber Sie einen Initialisierer nicht geben, initialisiert die Visual Basic die Variable auf den Standardwert für seinen Datentyp.</span><span class="sxs-lookup"><span data-stu-id="0308c-245">If you specify a data type but do not specify an initializer, Visual Basic initializes the variable to the default value for its data type.</span></span> <span data-ttu-id="0308c-246">Die folgende Tabelle zeigt die Initialisierungswerte.</span><span class="sxs-lookup"><span data-stu-id="0308c-246">The following table shows the default initialization values.</span></span>  
  
|<span data-ttu-id="0308c-247">Datentyp</span><span class="sxs-lookup"><span data-stu-id="0308c-247">Data type</span></span>|<span data-ttu-id="0308c-248">Standardwert</span><span class="sxs-lookup"><span data-stu-id="0308c-248">Default value</span></span>|  
|---|---|  
|<span data-ttu-id="0308c-249">Alle numerischen Typen (einschließlich `Byte` und `SByte`)</span><span class="sxs-lookup"><span data-stu-id="0308c-249">All numeric types (including `Byte` and `SByte`)</span></span>|<span data-ttu-id="0308c-250">0</span><span class="sxs-lookup"><span data-stu-id="0308c-250">0</span></span>|  
|`Char`|<span data-ttu-id="0308c-251">Binäre 0</span><span class="sxs-lookup"><span data-stu-id="0308c-251">Binary 0</span></span>|  
|<span data-ttu-id="0308c-252">Alle Referenztypen (einschließlich `Object`, `String`, und alle Arrays)</span><span class="sxs-lookup"><span data-stu-id="0308c-252">All reference types (including `Object`, `String`, and all arrays)</span></span>|`Nothing`|  
|`Boolean`|`False`|  
|`Date`|<span data-ttu-id="0308c-253">12:00 Uhr des 1. Januar des Jahres 1 (01/01/0001 12:00:00 Uhr)</span><span class="sxs-lookup"><span data-stu-id="0308c-253">12:00 AM of January 1 of the year 1 (01/01/0001 12:00:00 AM)</span></span>|  
  
 <span data-ttu-id="0308c-254">Jedes Element einer Struktur wird initialisiert, als handele es sich um eine separate Variable.</span><span class="sxs-lookup"><span data-stu-id="0308c-254">Each element of a structure is initialized as if it were a separate variable.</span></span> <span data-ttu-id="0308c-255">Wenn Sie die Länge eines Arrays deklarieren, aber die Elemente nicht initialisieren, wird jedes Element initialisiert, als handele es sich um eine separate Variable.</span><span class="sxs-lookup"><span data-stu-id="0308c-255">If you declare the length of an array but do not initialize its elements, each element is initialized as if it were a separate variable.</span></span>  
  
## <a name="static-local-variable-lifetime"></a><span data-ttu-id="0308c-256">Lebensdauer der statischen lokalen Variablen</span><span class="sxs-lookup"><span data-stu-id="0308c-256">Static Local Variable Lifetime</span></span>  
 <span data-ttu-id="0308c-257">Ein `Static` lokale Variable hat eine längere Lebensdauer als die Prozedur, die in der sie deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="0308c-257">A `Static` local variable has a longer lifetime than that of the procedure in which it is declared.</span></span> <span data-ttu-id="0308c-258">Die Grenzen der die Lebensdauer der Variablen ist davon abhängig, in die Prozedur deklariert wird und ob es sich handelt `Shared`.</span><span class="sxs-lookup"><span data-stu-id="0308c-258">The boundaries of the variable's lifetime depend on where the procedure is declared and whether it is `Shared`.</span></span>  
  
|<span data-ttu-id="0308c-259">Deklaration der Prozedur</span><span class="sxs-lookup"><span data-stu-id="0308c-259">Procedure declaration</span></span>|<span data-ttu-id="0308c-260">Variable ist initialisiert</span><span class="sxs-lookup"><span data-stu-id="0308c-260">Variable initialized</span></span>|<span data-ttu-id="0308c-261">Variable beendet vorhandene</span><span class="sxs-lookup"><span data-stu-id="0308c-261">Variable stops existing</span></span>|  
|---|---|---|  
|<span data-ttu-id="0308c-262">In einem Modul</span><span class="sxs-lookup"><span data-stu-id="0308c-262">In a module</span></span>|<span data-ttu-id="0308c-263">Beim ersten wird die Prozedur aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="0308c-263">The first time the procedure is called</span></span>|<span data-ttu-id="0308c-264">Wenn Ihr Programm die Ausführung angehalten wird</span><span class="sxs-lookup"><span data-stu-id="0308c-264">When your program stops execution</span></span>|  
|<span data-ttu-id="0308c-265">In einer Klasse oder Struktur ist Prozedur `Shared`</span><span class="sxs-lookup"><span data-stu-id="0308c-265">In a class or structure, procedure is `Shared`</span></span>|<span data-ttu-id="0308c-266">Beim ersten wird die Prozedur auf eine bestimmte Instanz oder auf die Klasse oder Struktur selbst aufgerufen</span><span class="sxs-lookup"><span data-stu-id="0308c-266">The first time the procedure is called either on a specific instance or on the class or structure itself</span></span>|<span data-ttu-id="0308c-267">Wenn Ihr Programm die Ausführung angehalten wird</span><span class="sxs-lookup"><span data-stu-id="0308c-267">When your program stops execution</span></span>|  
|<span data-ttu-id="0308c-268">Ist nicht in einer Klasse oder Struktur die Prozedur `Shared`</span><span class="sxs-lookup"><span data-stu-id="0308c-268">In a class or structure, procedure isn't `Shared`</span></span>|<span data-ttu-id="0308c-269">Beim ersten wird die Prozedur in einer bestimmten Instanz aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="0308c-269">The first time the procedure is called on a specific instance</span></span>|<span data-ttu-id="0308c-270">Wenn die Instanz für die Garbagecollection (GC) freigegeben wird</span><span class="sxs-lookup"><span data-stu-id="0308c-270">When the instance is released for garbage collection (GC)</span></span>|  
  
## <a name="attributes-and-modifiers"></a><span data-ttu-id="0308c-271">Attribute und Modifizierer</span><span class="sxs-lookup"><span data-stu-id="0308c-271">Attributes and Modifiers</span></span>  
 <span data-ttu-id="0308c-272">Sie können Attribute anwenden, nur Membervariablen, nicht für lokale Variablen.</span><span class="sxs-lookup"><span data-stu-id="0308c-272">You can apply attributes only to member variables, not to local variables.</span></span> <span data-ttu-id="0308c-273">Ein Attribut fügt Informationen an den Metadaten der Assembly, die hat keine Bedeutung für die temporäre Speicherung, z. B. lokale Variablen.</span><span class="sxs-lookup"><span data-stu-id="0308c-273">An attribute contributes information to the assembly's metadata, which is not meaningful for temporary storage such as local variables.</span></span>  
  
 <span data-ttu-id="0308c-274">Sie können nicht auf Modulebene verwenden die `Static` Modifizierer zum Deklarieren von Variablen Member.</span><span class="sxs-lookup"><span data-stu-id="0308c-274">At module level, you cannot use the `Static` modifier to declare member variables.</span></span> <span data-ttu-id="0308c-275">Auf Prozedurebene, können keine `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, Zugriffsmodifizierern Lokale Variablen deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="0308c-275">At procedure level, you cannot use `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, or any access modifiers to declare local variables.</span></span>  
  
 <span data-ttu-id="0308c-276">Sie können angeben, welcher Code eine Variable durch Angabe zugreifen kann ein `accessmodifier`.</span><span class="sxs-lookup"><span data-stu-id="0308c-276">You can specify what code can access a variable by supplying an `accessmodifier`.</span></span> <span data-ttu-id="0308c-277">-Klasse Variablen (außerhalb einer Prozedur) standardmäßig und in privaten Zugriff und Strukturmembervariablen in öffentlichen Zugriff.</span><span class="sxs-lookup"><span data-stu-id="0308c-277">Class and module member variables (outside any procedure) default to private access, and structure member variables default to public access.</span></span> <span data-ttu-id="0308c-278">Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.</span><span class="sxs-lookup"><span data-stu-id="0308c-278">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="0308c-279">Sie können keine Zugriffsmodifizierer für lokale Variablen (innerhalb einer Prozedur).</span><span class="sxs-lookup"><span data-stu-id="0308c-279">You cannot use access modifiers on local variables (inside a procedure).</span></span>  
  
 <span data-ttu-id="0308c-280">Sie können angeben, `WithEvents` nur für die Membervariablen und nicht für lokale Variablen innerhalb einer Prozedur.</span><span class="sxs-lookup"><span data-stu-id="0308c-280">You can specify `WithEvents` only on member variables, not on local variables inside a procedure.</span></span> <span data-ttu-id="0308c-281">Bei Angabe von `WithEvents`, der Datentyp der Variablen muss einen bestimmten Klassentyp nicht `Object`.</span><span class="sxs-lookup"><span data-stu-id="0308c-281">If you specify `WithEvents`, the data type of the variable must be a specific class type, not `Object`.</span></span> <span data-ttu-id="0308c-282">Sie können nicht deklarieren ein Array mit `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="0308c-282">You cannot declare an array with `WithEvents`.</span></span> <span data-ttu-id="0308c-283">Weitere Informationen zu Ereignissen finden Sie unter [Ereignisse](../../../visual-basic/programming-guide/language-features/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="0308c-283">For more information about events, see [Events](../../../visual-basic/programming-guide/language-features/events/index.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0308c-284">Code außerhalb einer Klasse, einer Struktur oder das Modul muss eine Membervariable den Namen durch den Namen dieser Klasse, Struktur oder Modul qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="0308c-284">Code outside a class, structure, or module must qualify a member variable's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="0308c-285">Code außerhalb einer Prozedur oder einem Block kann auf alle lokalen Variablen in dieser Prozedur oder eines Blocks verweisen.</span><span class="sxs-lookup"><span data-stu-id="0308c-285">Code outside a procedure or block cannot refer to any local variables within that procedure or block.</span></span>  
  
## <a name="releasing-managed-resources"></a><span data-ttu-id="0308c-286">Freigeben von verwalteten Ressourcen</span><span class="sxs-lookup"><span data-stu-id="0308c-286">Releasing Managed Resources</span></span>  
 <span data-ttu-id="0308c-287">Der Garbagecollector von .NET Framework gibt ohne zusätzliche Programmierkenntnisse ihrerseits verwalteten Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="0308c-287">The .NET Framework garbage collector disposes of managed resources without any extra coding on your part.</span></span> <span data-ttu-id="0308c-288">Allerdings können Sie die Freigabe einer verwalteten Ressource anstatt abzuwarten, bis der Garbage Collection erzwingen.</span><span class="sxs-lookup"><span data-stu-id="0308c-288">However, you can force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>  
  
 <span data-ttu-id="0308c-289">Wenn eine Klasse auf eine besonders nützliche und knappe Ressource (z. B. eine Datenbank-Verbindung oder die Dateihandle) enthält, möchten Sie nicht warten, bis die nächste Garbagecollection zum Bereinigen der Instanz einer Klasse, die nicht mehr verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0308c-289">If a class holds onto a particularly valuable and scarce resource (such as a database connection or file handle), you might not want to wait until the next garbage collection to clean up a class instance that's no longer in use.</span></span> <span data-ttu-id="0308c-290">Implementieren der <xref:System.IDisposable> Schnittstelle, um die Möglichkeit, Ressourcen, bevor eine Garbagecollection freigegeben.</span><span class="sxs-lookup"><span data-stu-id="0308c-290">A class may implement the <xref:System.IDisposable> interface to provide a way to release resources before a garbage collection.</span></span> <span data-ttu-id="0308c-291">Stellt eine Klasse, die diese Schnittstelle implementiert einen `Dispose` -Methode, die aufgerufen werden kann, um wertvolle Ressourcen sofort freigegeben werden zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="0308c-291">A class that implements that interface exposes a `Dispose` method that can be called to force valuable resources to be released immediately.</span></span>  
  
 <span data-ttu-id="0308c-292">Die `Using` Anweisung automatisiert den Prozess der Erwerb einer Ressourcensatzes, eine Reihe von Anweisungen ausgeführt und dann die Ressource freigegeben.</span><span class="sxs-lookup"><span data-stu-id="0308c-292">The `Using` statement automates the process of acquiring a resource, executing a set of statements, and then disposing of the resource.</span></span> <span data-ttu-id="0308c-293">Allerdings muss die Ressource implementieren die <xref:System.IDisposable> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="0308c-293">However, the resource must implement the <xref:System.IDisposable> interface.</span></span> <span data-ttu-id="0308c-294">Weitere Informationen finden Sie unter [using-Anweisung](../../../visual-basic/language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0308c-294">For more information, see [Using Statement](../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0308c-295">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0308c-295">Example</span></span>  
 <span data-ttu-id="0308c-296">Das folgende Beispiel deklariert Variablen mithilfe der `Dim` -Anweisung mit verschiedenen Optionen.</span><span class="sxs-lookup"><span data-stu-id="0308c-296">The following example declares variables by using the `Dim` statement with various options.</span></span>  
  
 [!code-vb[VbVbalrStatements#141](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="0308c-297">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0308c-297">Example</span></span>  
 <span data-ttu-id="0308c-298">Das folgende Beispiel listet die Primzahlen zwischen 1 und 30.</span><span class="sxs-lookup"><span data-stu-id="0308c-298">The following example lists the prime numbers between 1 and 30.</span></span> <span data-ttu-id="0308c-299">Der Bereich der lokalen Variablen wird in den Kommentaren im Code beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0308c-299">The scope of local variables is described in code comments.</span></span>  
  
 [!code-vb[VbVbalrStatements#142](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="0308c-300">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0308c-300">Example</span></span>  
 <span data-ttu-id="0308c-301">Im folgenden Beispiel die `speedValue` Variable auf Klassenebene deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="0308c-301">In the following example, the `speedValue` variable is declared at the class level.</span></span> <span data-ttu-id="0308c-302">Die `Private` -Schlüsselwort wird verwendet, um die Variable zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="0308c-302">The `Private` keyword is used to declare the variable.</span></span> <span data-ttu-id="0308c-303">Die Variable kann zugegriffen werden, von einer Prozedur in der `Car` Klasse.</span><span class="sxs-lookup"><span data-stu-id="0308c-303">The variable can be accessed by any procedure in the `Car` class.</span></span>  
  
 [!code-vb[VbVbalrStatements#144](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_3.vb)]  
  
 [!code-vb[VbVbalrStatements#145](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="0308c-304">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0308c-304">See also</span></span>
- [<span data-ttu-id="0308c-305">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0308c-305">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)
- [<span data-ttu-id="0308c-306">ReDim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0308c-306">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="0308c-307">Option Explicit-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0308c-307">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="0308c-308">Option Infer-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0308c-308">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="0308c-309">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0308c-309">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="0308c-310">Seite „Kompilieren“, Projekt-Designer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0308c-310">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [<span data-ttu-id="0308c-311">Variablendeklaration</span><span class="sxs-lookup"><span data-stu-id="0308c-311">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="0308c-312">Arrays</span><span class="sxs-lookup"><span data-stu-id="0308c-312">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="0308c-313">Objektinitialisierer: Benannte und anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="0308c-313">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="0308c-314">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="0308c-314">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="0308c-315">Objektinitialisierer: Benannte und anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="0308c-315">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="0308c-316">Vorgehensweise: Deklarieren eines Objekts mithilfe eines Objektinitialisierers</span><span class="sxs-lookup"><span data-stu-id="0308c-316">How to: Declare an Object by Using an Object Initializer</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
- [<span data-ttu-id="0308c-317">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="0308c-317">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
