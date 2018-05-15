---
title: Einschränkungen (F#)
description: Informationen Sie zu F#-Einschränkungen, die für generische Typparameter an die Anforderungen für die ein Type-Argument in einem generischen Typ oder einer Funktion gültig.
ms.date: 05/16/2016
ms.openlocfilehash: f0722cafe27a4e2c38dfbf091973edb136cf5228
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="constraints"></a><span data-ttu-id="a170b-103">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="a170b-103">Constraints</span></span>

<span data-ttu-id="a170b-104">In diesem Thema wird beschrieben, Einschränkungen, die Sie für generische gelten können Typparameter an die Anforderungen für die ein Type-Argument in einer generischen Typ- oder Funktion.</span><span class="sxs-lookup"><span data-stu-id="a170b-104">This topic describes constraints that you can apply to generic type parameters to specify the requirements for a type argument in a generic type or function.</span></span>


## <a name="syntax"></a><span data-ttu-id="a170b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a170b-105">Syntax</span></span>

```fsharp
type-parameter-list when constraint1 [ and constraint2]
```

## <a name="remarks"></a><span data-ttu-id="a170b-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a170b-106">Remarks</span></span>
<span data-ttu-id="a170b-107">Es gibt mehrere unterschiedliche Einschränkungen, die Sie anwenden können, um die Typen beschränken, die in einem generischen Typ verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="a170b-107">There are several different constraints you can apply to limit the types that can be used in a generic type.</span></span> <span data-ttu-id="a170b-108">In der folgenden Tabelle aufgelistet und beschrieben von diesen Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="a170b-108">The following table lists and describes these constraints.</span></span>

|<span data-ttu-id="a170b-109">Constraint</span><span class="sxs-lookup"><span data-stu-id="a170b-109">Constraint</span></span>|<span data-ttu-id="a170b-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="a170b-110">Syntax</span></span>|<span data-ttu-id="a170b-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a170b-111">Description</span></span>|
|----------|------|-----------|
|<span data-ttu-id="a170b-112">Typeinschränkung</span><span class="sxs-lookup"><span data-stu-id="a170b-112">Type Constraint</span></span>|<span data-ttu-id="a170b-113">*Typparameter* :&gt; *Typ*</span><span class="sxs-lookup"><span data-stu-id="a170b-113">*type-parameter* :&gt; *type*</span></span>|<span data-ttu-id="a170b-114">Der bereitgestellte Typ muss gleich oder abgeleiteten aus dem angegebenen Typ oder, wenn der Typ eine Schnittstelle ist, muss der angegebene Typ der Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="a170b-114">The provided type must be equal to or derived from the type specified, or, if the type is an interface, the provided type must implement the interface.</span></span>|
|<span data-ttu-id="a170b-115">NULL-Einschränkung</span><span class="sxs-lookup"><span data-stu-id="a170b-115">Null Constraint</span></span>|<span data-ttu-id="a170b-116">*Typparameter* : null</span><span class="sxs-lookup"><span data-stu-id="a170b-116">*type-parameter* : null</span></span>|<span data-ttu-id="a170b-117">Der angegebene Typ muss das null-Literal unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a170b-117">The provided type must support the null literal.</span></span> <span data-ttu-id="a170b-118">Dies schließt alle Objekttypen .NET jedoch nicht F#-Liste, Tupel, Funktion, Klasse, Datensatz oder union-Typen.</span><span class="sxs-lookup"><span data-stu-id="a170b-118">This includes all .NET object types but not F# list, tuple, function, class, record, or union types.</span></span>|
|<span data-ttu-id="a170b-119">Explizites Mitglied-Einschränkung</span><span class="sxs-lookup"><span data-stu-id="a170b-119">Explicit Member Constraint</span></span>|<span data-ttu-id="a170b-120">[()]*Typparameter* [oder... oder *Typparameter*)]: (* Membersignatur *)</span><span class="sxs-lookup"><span data-stu-id="a170b-120">[(]*type-parameter* [or ... or *type-parameter*)] : (*member-signature *)</span></span>|<span data-ttu-id="a170b-121">Mindestens eines der bereitgestellten Typargumente benötigen ein Element, das die angegebene Signatur verfügt; nicht für die allgemeine Verwendung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="a170b-121">At least one of the type arguments provided must have a member that has the specified signature; not intended for common use.</span></span> <span data-ttu-id="a170b-122">Mitglieder müssen entweder explizit auf den Typ oder die Teil einer Erweiterung impliziter Typ werden als gültige Ziele für eine explizite Schnittstellenmember-Einschränkung definiert werden.</span><span class="sxs-lookup"><span data-stu-id="a170b-122">Members must be either explicitly defined on the type or part of an implicit type extension to be valid targets for an Explicit Member Constraint.</span></span>|
|<span data-ttu-id="a170b-123">Konstruktoreinschränkung</span><span class="sxs-lookup"><span data-stu-id="a170b-123">Constructor Constraint</span></span>|<span data-ttu-id="a170b-124">*Typparameter* : (new: Einheit -&gt; "ein)</span><span class="sxs-lookup"><span data-stu-id="a170b-124">*type-parameter* : ( new : unit -&gt; 'a )</span></span>|<span data-ttu-id="a170b-125">Der bereitgestellte Typ muss einen Standardkonstruktor verfügen.</span><span class="sxs-lookup"><span data-stu-id="a170b-125">The provided type must have a default constructor.</span></span>|
|<span data-ttu-id="a170b-126">Werttypeinschränkung</span><span class="sxs-lookup"><span data-stu-id="a170b-126">Value Type Constraint</span></span>|<span data-ttu-id="a170b-127">: Struktur</span><span class="sxs-lookup"><span data-stu-id="a170b-127">: struct</span></span>|<span data-ttu-id="a170b-128">Der angegebene Typ muss ein Werttyp .NET.</span><span class="sxs-lookup"><span data-stu-id="a170b-128">The provided type must be a .NET value type.</span></span>|
|<span data-ttu-id="a170b-129">Reference-Typ-Einschränkung</span><span class="sxs-lookup"><span data-stu-id="a170b-129">Reference Type Constraint</span></span>|<span data-ttu-id="a170b-130">: nicht-Struktur</span><span class="sxs-lookup"><span data-stu-id="a170b-130">: not struct</span></span>|<span data-ttu-id="a170b-131">Der angegebene Typ muss ein Verweistyp .NET.</span><span class="sxs-lookup"><span data-stu-id="a170b-131">The provided type must be a .NET reference type.</span></span>|
|<span data-ttu-id="a170b-132">Enumeration Typeinschränkung</span><span class="sxs-lookup"><span data-stu-id="a170b-132">Enumeration Type Constraint</span></span>|<span data-ttu-id="a170b-133">: Enum&lt;*zugrunde liegenden Typ*&gt;</span><span class="sxs-lookup"><span data-stu-id="a170b-133">: enum&lt;*underlying-type*&gt;</span></span>|<span data-ttu-id="a170b-134">Der bereitgestellte Typ muss ein enumerierter Typ, mit dem angegebenen zugrunde liegenden Datentyp; nicht für die allgemeine Verwendung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="a170b-134">The provided type must be an enumerated type that has the specified underlying type; not intended for common use.</span></span>|
|<span data-ttu-id="a170b-135">Delegieren der Einschränkung</span><span class="sxs-lookup"><span data-stu-id="a170b-135">Delegate Constraint</span></span>|<span data-ttu-id="a170b-136">: Delegieren&lt;*Tupel Parametertyp*, *Return-Type*&gt;</span><span class="sxs-lookup"><span data-stu-id="a170b-136">: delegate&lt;*tuple-parameter-type*, *return-type*&gt;</span></span>|<span data-ttu-id="a170b-137">Der bereitgestellte Typ muss werden einem Delegattyp als Typ, der die angegebenen Argumenten verfügt und Rückgabewert; nicht für die allgemeine Verwendung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="a170b-137">The provided type must be a delegate type that has the specified arguments and return value; not intended for common use.</span></span>|
|<span data-ttu-id="a170b-138">Vergleich-Einschränkung</span><span class="sxs-lookup"><span data-stu-id="a170b-138">Comparison Constraint</span></span>|<span data-ttu-id="a170b-139">: Vergleich</span><span class="sxs-lookup"><span data-stu-id="a170b-139">: comparison</span></span>|<span data-ttu-id="a170b-140">Der angegebene Typ muss Vergleich unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a170b-140">The provided type must support comparison.</span></span>|
|<span data-ttu-id="a170b-141">Equality-Einschränkung</span><span class="sxs-lookup"><span data-stu-id="a170b-141">Equality Constraint</span></span>|<span data-ttu-id="a170b-142">: auf Gleichheit</span><span class="sxs-lookup"><span data-stu-id="a170b-142">: equality</span></span>|<span data-ttu-id="a170b-143">Der angegebene Typ muss Gleichheit unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a170b-143">The provided type must support equality.</span></span>|
|<span data-ttu-id="a170b-144">Nicht verwaltete Einschränkung</span><span class="sxs-lookup"><span data-stu-id="a170b-144">Unmanaged Constraint</span></span>|<span data-ttu-id="a170b-145">: nicht verwaltete</span><span class="sxs-lookup"><span data-stu-id="a170b-145">: unmanaged</span></span>|<span data-ttu-id="a170b-146">Der angegebene Typ muss einen nicht verwalteten Typ.</span><span class="sxs-lookup"><span data-stu-id="a170b-146">The provided type must be an unmanaged type.</span></span> <span data-ttu-id="a170b-147">Nicht verwaltete Typen sind entweder bestimmte primitiven Typen (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, oder `decimal`), Enumerationstypen, `nativeptr&lt;_&gt;`, oder eine nicht generische Struktur, deren Felder alle nicht verwalteten Typen.</span><span class="sxs-lookup"><span data-stu-id="a170b-147">Unmanaged types are either certain primitive types (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, or `decimal`), enumeration types, `nativeptr&lt;_&gt;`, or a non-generic structure whose fields are all unmanaged types.</span></span>|
<span data-ttu-id="a170b-148">Sie müssen eine Einschränkung hinzufügen, wenn der Code hat eine Funktion verwenden, die in der Regel auf den Einschränkungstyp jedoch nicht für Typen verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="a170b-148">You have to add a constraint when your code has to use a feature that is available on the constraint type but not on types in general.</span></span> <span data-ttu-id="a170b-149">Wenn Sie die Einschränkung des Typs verwenden, um einen Klassentyp anzugeben, können Sie eine der Methoden dieser Klasse in der generischen Funktion oder einen Typ verwenden.</span><span class="sxs-lookup"><span data-stu-id="a170b-149">For example, if you use the type constraint to specify a class type, you can use any one of the methods of that class in the generic function or type.</span></span>

<span data-ttu-id="a170b-150">Angeben von Einschränkungen ist manchmal erforderlich, wenn Typparameter explizit zu schreiben, da ohne Einschränkung, hat der Compiler keine Möglichkeit zu überprüfen, dass die Funktionen, mit dem Sie, auf einen beliebigen Typ zur Verfügung stehen, der zur Laufzeit für den Typ angegeben werden kann Parameter.</span><span class="sxs-lookup"><span data-stu-id="a170b-150">Specifying constraints is sometimes required when writing type parameters explicitly, because without a constraint, the compiler has no way of verifying that the features that you are using will be available on any type that might be supplied at run time for the type parameter.</span></span>

<span data-ttu-id="a170b-151">Die am häufigsten verwendeten Einschränkungen, die in f#-Code verwendet werden, typeinschränkungen, die Basisklassen oder Schnittstellen angeben.</span><span class="sxs-lookup"><span data-stu-id="a170b-151">The most common constraints you use in F# code are type constraints that specify base classes or interfaces.</span></span> <span data-ttu-id="a170b-152">Die anderen Einschränkungen werden entweder von der f#-Bibliothek verwendet, um bestimmte Funktionen, z. B. die Einschränkung explizites Mitglied zu implementieren, wird verwendet, um den Operator für arithmetische Operatoren überladen implementieren oder dienen hauptsächlich da f# das vollständige unterstützt ein Satz von Einschränkungen, die von der common Language Runtime unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="a170b-152">The other constraints are either used by the F# library to implement certain functionality, such as the explicit member constraint, which is used to implement operator overloading for arithmetic operators, or are provided mainly because F# supports the complete set of constraints that is supported by the common language runtime.</span></span>

<span data-ttu-id="a170b-153">Beim Rückschlussprozess Typ sind einige Einschränkungen automatisch vom Compiler abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="a170b-153">During the type inference process, some constraints are inferred automatically by the compiler.</span></span> <span data-ttu-id="a170b-154">Angenommen, Sie verwenden die `+` -Operator in einer Funktion, leitet der Compiler eine explizite Schnittstellenmember-Einschränkung für Variablentypen, die im Ausdruck verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a170b-154">For example, if you use the `+` operator in a function, the compiler infers an explicit member constraint on variable types that are used in the expression.</span></span>

<span data-ttu-id="a170b-155">Der folgende Code zeigt einige Einschränkung Deklarationen.</span><span class="sxs-lookup"><span data-stu-id="a170b-155">The following code illustrates some constraint declarations.</span></span>

```fsharp
// Base Type Constraint
type Class1<'T when 'T :> System.Exception> =
class end

// Interface Type Constraint
type Class2<'T when 'T :> System.IComparable> = 
class end

// Null constraint
type Class3<'T when 'T : null> =
class end

// Member constraint with static member
type Class4<'T when 'T : (static member staticMethod1 : unit -> 'T) > =
class end

// Member constraint with instance member
type Class5<'T when 'T : (member Method1 : 'T -> int)> =
class end

// Member constraint with property
type Class6<'T when 'T : (member Property1 : int)> =
class end

// Constructor constraint
type Class7<'T when 'T : (new : unit -> 'T)>() =
member val Field = new 'T()

// Reference type constraint
type Class8<'T when 'T : not struct> =
class end

// Enumeration constraint with underlying value specified
type Class9<'T when 'T : enum<uint32>> =
class end

// 'T must implement IComparable, or be an array type with comparable
// elements, or be System.IntPtr or System.UIntPtr. Also, 'T must not have
// the NoComparison attribute.
type Class10<'T when 'T : comparison> =
class end

// 'T must support equality. This is true for any type that does not
// have the NoEquality attribute.
type Class11<'T when 'T : equality> =
class end

type Class12<'T when 'T : delegate<obj * System.EventArgs, unit>> =
class end

type Class13<'T when 'T : unmanaged> =
class end

// Member constraints with two type parameters
// Most often used with static type parameters in inline functions
let inline add(value1 : ^T when ^T : (static member (+) : ^T * ^T -> ^T), value2: ^T) =
value1 + value2

// ^T and ^U must support operator +
let inline heterogenousAdd(value1 : ^T when (^T or ^U) : (static member (+) : ^T * ^U -> ^T), value2 : ^U) =
value1 + value2

// If there are multiple constraints, use the and keyword to separate them.
type Class14<'T,'U when 'T : equality and 'U : equality> =
class end
```

## <a name="see-also"></a><span data-ttu-id="a170b-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a170b-156">See Also</span></span>
[<span data-ttu-id="a170b-157">Generika</span><span class="sxs-lookup"><span data-stu-id="a170b-157">Generics</span></span>](index.md)

[<span data-ttu-id="a170b-158">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="a170b-158">Constraints</span></span>](constraints.md)
