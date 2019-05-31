---
title: Einschränkungen
description: Erfahren Sie mehr über F# Einschränkungen, die für generische Typparameter an die Anforderungen für die ein Typargument in einer generischen Typ oder eine Funktion gelten.
ms.date: 05/16/2016
ms.openlocfilehash: bb6625636f0465dd608ae2e8a8986d043b62b6e4
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/30/2019
ms.locfileid: "66378187"
---
# <a name="constraints"></a><span data-ttu-id="4b274-103">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="4b274-103">Constraints</span></span>

<span data-ttu-id="4b274-104">In diesem Thema wird beschrieben, Einschränkungen, die Sie auf generische anwenden können Geben Sie Parameter, um die Anforderungen für die ein Typargument in einer generischen Typ oder eine Funktion anzugeben.</span><span class="sxs-lookup"><span data-stu-id="4b274-104">This topic describes constraints that you can apply to generic type parameters to specify the requirements for a type argument in a generic type or function.</span></span>

## <a name="syntax"></a><span data-ttu-id="4b274-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4b274-105">Syntax</span></span>

```fsharp
type-parameter-list when constraint1 [ and constraint2]
```

## <a name="remarks"></a><span data-ttu-id="4b274-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4b274-106">Remarks</span></span>

<span data-ttu-id="4b274-107">Es gibt mehrere andere Einschränkungen, die Sie anwenden können, um die Typen beschränken, die in einem generischen Typ verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="4b274-107">There are several different constraints you can apply to limit the types that can be used in a generic type.</span></span> <span data-ttu-id="4b274-108">Die folgende Tabelle enthält und beschreibt diese Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="4b274-108">The following table lists and describes these constraints.</span></span>

|<span data-ttu-id="4b274-109">Constraint</span><span class="sxs-lookup"><span data-stu-id="4b274-109">Constraint</span></span>|<span data-ttu-id="4b274-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="4b274-110">Syntax</span></span>|<span data-ttu-id="4b274-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4b274-111">Description</span></span>|
|----------|------|-----------|
|<span data-ttu-id="4b274-112">Typeinschränkung</span><span class="sxs-lookup"><span data-stu-id="4b274-112">Type Constraint</span></span>|<span data-ttu-id="4b274-113">*type-parameter* :&gt; *type*</span><span class="sxs-lookup"><span data-stu-id="4b274-113">*type-parameter* :&gt; *type*</span></span>|<span data-ttu-id="4b274-114">Der bereitgestellte Typ muss gleich oder abgeleitet aus dem angegebenen Typ oder, wenn der Typ eine Schnittstelle ist, muss der angegebene Typ die Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="4b274-114">The provided type must be equal to or derived from the type specified, or, if the type is an interface, the provided type must implement the interface.</span></span>|
|<span data-ttu-id="4b274-115">NULL-Einschränkung</span><span class="sxs-lookup"><span data-stu-id="4b274-115">Null Constraint</span></span>|<span data-ttu-id="4b274-116">*type-parameter* : null</span><span class="sxs-lookup"><span data-stu-id="4b274-116">*type-parameter* : null</span></span>|<span data-ttu-id="4b274-117">Der angegebene Typ muss es sich um das null-Literal unterstützen.</span><span class="sxs-lookup"><span data-stu-id="4b274-117">The provided type must support the null literal.</span></span> <span data-ttu-id="4b274-118">Dies schließt alle Objekttypen in .NET, nicht jedoch F# Liste, Tupel, Funktion, Klasse, Datensatzes oder union-Typen.</span><span class="sxs-lookup"><span data-stu-id="4b274-118">This includes all .NET object types but not F# list, tuple, function, class, record, or union types.</span></span>|
|<span data-ttu-id="4b274-119">Explizites Mitglied-Einschränkung</span><span class="sxs-lookup"><span data-stu-id="4b274-119">Explicit Member Constraint</span></span>|<span data-ttu-id="4b274-120">[(]*Typparameter* [oder... oder *Typparameter*)]: (*Membersignatur*)</span><span class="sxs-lookup"><span data-stu-id="4b274-120">[(]*type-parameter* [or ... or *type-parameter*)] : (*member-signature*)</span></span>|<span data-ttu-id="4b274-121">Mindestens eines der bereitgestellten Typargumente müssen ein Mitglied, das die angegebene Signatur verfügt; nicht für die allgemeine Verwendung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="4b274-121">At least one of the type arguments provided must have a member that has the specified signature; not intended for common use.</span></span> <span data-ttu-id="4b274-122">Mitglieder müssen entweder explizit auf den Typ oder einem Teil einer Erweiterung impliziter Typ werden gültige Ziele für eine explizite Einschränkung für Member definiert werden.</span><span class="sxs-lookup"><span data-stu-id="4b274-122">Members must be either explicitly defined on the type or part of an implicit type extension to be valid targets for an Explicit Member Constraint.</span></span>|
|<span data-ttu-id="4b274-123">Konstruktoreinschränkung</span><span class="sxs-lookup"><span data-stu-id="4b274-123">Constructor Constraint</span></span>|<span data-ttu-id="4b274-124">*Typparameter* : (neu: Unit -&gt; "ein)</span><span class="sxs-lookup"><span data-stu-id="4b274-124">*type-parameter* : ( new : unit -&gt; 'a )</span></span>|<span data-ttu-id="4b274-125">Der angegebene Typ muss einen Standardkonstruktor verfügen.</span><span class="sxs-lookup"><span data-stu-id="4b274-125">The provided type must have a default constructor.</span></span>|
|<span data-ttu-id="4b274-126">Werttypeinschränkung</span><span class="sxs-lookup"><span data-stu-id="4b274-126">Value Type Constraint</span></span>|<span data-ttu-id="4b274-127">: Struktur</span><span class="sxs-lookup"><span data-stu-id="4b274-127">: struct</span></span>|<span data-ttu-id="4b274-128">Der angegebene Typ muss ein.</span><span class="sxs-lookup"><span data-stu-id="4b274-128">The provided type must be a .NET value type.</span></span>|
|<span data-ttu-id="4b274-129">Verweistypeinschränkung</span><span class="sxs-lookup"><span data-stu-id="4b274-129">Reference Type Constraint</span></span>|<span data-ttu-id="4b274-130">: nicht-Struktur</span><span class="sxs-lookup"><span data-stu-id="4b274-130">: not struct</span></span>|<span data-ttu-id="4b274-131">Der angegebene Typ muss ein Verweistyp für .NET.</span><span class="sxs-lookup"><span data-stu-id="4b274-131">The provided type must be a .NET reference type.</span></span>|
|<span data-ttu-id="4b274-132">Eine Einschränkung für Enumeration</span><span class="sxs-lookup"><span data-stu-id="4b274-132">Enumeration Type Constraint</span></span>|<span data-ttu-id="4b274-133">: enum&lt;*underlying-type*&gt;</span><span class="sxs-lookup"><span data-stu-id="4b274-133">: enum&lt;*underlying-type*&gt;</span></span>|<span data-ttu-id="4b274-134">Der bereitgestellte Typ muss es sich um ein enumerierter Typ sein, der den angegebenen zugrunde liegenden Typ aufweist; nicht für die allgemeine Verwendung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="4b274-134">The provided type must be an enumerated type that has the specified underlying type; not intended for common use.</span></span>|
|<span data-ttu-id="4b274-135">Delegieren der Einschränkung</span><span class="sxs-lookup"><span data-stu-id="4b274-135">Delegate Constraint</span></span>|<span data-ttu-id="4b274-136">: delegate&lt;*tuple-parameter-type*, *return-type*&gt;</span><span class="sxs-lookup"><span data-stu-id="4b274-136">: delegate&lt;*tuple-parameter-type*, *return-type*&gt;</span></span>|<span data-ttu-id="4b274-137">Der angegebene Typ muss ein Delegattyp, die die angegebenen Argumenten sein und Rückgabewert; nicht für die allgemeine Verwendung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="4b274-137">The provided type must be a delegate type that has the specified arguments and return value; not intended for common use.</span></span>|
|<span data-ttu-id="4b274-138">Comparison-Einschränkung</span><span class="sxs-lookup"><span data-stu-id="4b274-138">Comparison Constraint</span></span>|<span data-ttu-id="4b274-139">: comparison</span><span class="sxs-lookup"><span data-stu-id="4b274-139">: comparison</span></span>|<span data-ttu-id="4b274-140">Der angegebene Typ muss es sich um Vergleich unterstützen.</span><span class="sxs-lookup"><span data-stu-id="4b274-140">The provided type must support comparison.</span></span>|
|<span data-ttu-id="4b274-141">Equality-Einschränkung</span><span class="sxs-lookup"><span data-stu-id="4b274-141">Equality Constraint</span></span>|<span data-ttu-id="4b274-142">: auf Gleichheit</span><span class="sxs-lookup"><span data-stu-id="4b274-142">: equality</span></span>|<span data-ttu-id="4b274-143">Der angegebene Typ muss die Gleichheit unterstützen.</span><span class="sxs-lookup"><span data-stu-id="4b274-143">The provided type must support equality.</span></span>|
|<span data-ttu-id="4b274-144">Nicht verwaltete Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="4b274-144">Unmanaged Constraint</span></span>|<span data-ttu-id="4b274-145">: nicht verwaltete</span><span class="sxs-lookup"><span data-stu-id="4b274-145">: unmanaged</span></span>|<span data-ttu-id="4b274-146">Der angegebene Typ muss es sich um einen nicht verwalteten Typ sein.</span><span class="sxs-lookup"><span data-stu-id="4b274-146">The provided type must be an unmanaged type.</span></span> <span data-ttu-id="4b274-147">Nicht verwaltete Typen sind entweder bestimmten primitiven Typen (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, oder `decimal`), Enumerationstypen, `nativeptr<_>`, oder eine nicht generische Struktur, deren Felder alle nicht verwalteten Typen werden.</span><span class="sxs-lookup"><span data-stu-id="4b274-147">Unmanaged types are either certain primitive types (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, or `decimal`), enumeration types, `nativeptr<_>`, or a non-generic structure whose fields are all unmanaged types.</span></span>|

<span data-ttu-id="4b274-148">Sie müssen eine Einschränkung hinzufügen, wenn Ihr Code muss eine Funktion verwenden, die in der Regel auf den Einschränkungstyp jedoch nicht für Typen verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="4b274-148">You have to add a constraint when your code has to use a feature that is available on the constraint type but not on types in general.</span></span> <span data-ttu-id="4b274-149">Wenn Sie die typeinschränkung verwenden, um einen Klassentyp anzugeben, können Sie z. B. eine der Methoden dieser Klasse in der generischen Funktion oder einen Typ verwenden.</span><span class="sxs-lookup"><span data-stu-id="4b274-149">For example, if you use the type constraint to specify a class type, you can use any one of the methods of that class in the generic function or type.</span></span>

<span data-ttu-id="4b274-150">Angeben von Einschränkungen ist manchmal erforderlich, wenn Typparameter explizit zu schreiben, da ohne Einschränkung, der Compiler kann nicht überprüft haben, dass die Funktionen, die Sie verwenden in einen beliebigen Typ verfügbar sein werden, der zur Laufzeit für den Typ angegeben werden kann der Parameter.</span><span class="sxs-lookup"><span data-stu-id="4b274-150">Specifying constraints is sometimes required when writing type parameters explicitly, because without a constraint, the compiler has no way of verifying that the features that you are using will be available on any type that might be supplied at run time for the type parameter.</span></span>

<span data-ttu-id="4b274-151">Die am häufigsten verwendeten Einschränkungen, die Sie in verwenden F# Code typeinschränkungen, die angeben, Basisklassen oder Schnittstellen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4b274-151">The most common constraints you use in F# code are type constraints that specify base classes or interfaces.</span></span> <span data-ttu-id="4b274-152">Die anderen Einschränkungen werden entweder von der F#-Bibliothek verwendet, um bestimmte Funktionen, z. B. die Einschränkung explizites Mitglied zu implementieren, die zum Implementieren von arithmetischen Operatoren überladen verwendet oder dienen hauptsächlich deshalb, weil F# die vollständige unterstützt Reihe von Einschränkungen, die von der common Language Runtime unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="4b274-152">The other constraints are either used by the F# library to implement certain functionality, such as the explicit member constraint, which is used to implement operator overloading for arithmetic operators, or are provided mainly because F# supports the complete set of constraints that is supported by the common language runtime.</span></span>

<span data-ttu-id="4b274-153">Beim Rückschlussprozess geben sind einige Einschränkungen automatisch vom Compiler abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="4b274-153">During the type inference process, some constraints are inferred automatically by the compiler.</span></span> <span data-ttu-id="4b274-154">Angenommen, Sie verwenden die `+` Operator in einer Funktion, leitet der Compiler eine explizite Mitglieder-Einschränkung auf Variablen Typen, die im Ausdruck verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4b274-154">For example, if you use the `+` operator in a function, the compiler infers an explicit member constraint on variable types that are used in the expression.</span></span>

<span data-ttu-id="4b274-155">Der folgende Code zeigt einige Einschränkung-Deklarationen.</span><span class="sxs-lookup"><span data-stu-id="4b274-155">The following code illustrates some constraint declarations.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="4b274-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b274-156">See also</span></span>

- [<span data-ttu-id="4b274-157">Generika</span><span class="sxs-lookup"><span data-stu-id="4b274-157">Generics</span></span>](index.md)
- [<span data-ttu-id="4b274-158">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="4b274-158">Constraints</span></span>](constraints.md)
