---
title: Attribute (F#)
description: Erfahren Sie, wie f# Attribute ermöglichen, dass Metadaten auf ein Programmiermodell angewendet werden soll.
ms.date: 05/16/2016
ms.openlocfilehash: 107f5d9cbcce28c97fc5b738759ef27649fc45a4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565424"
---
# <a name="attributes"></a><span data-ttu-id="4bc98-103">Attribute</span><span class="sxs-lookup"><span data-stu-id="4bc98-103">Attributes</span></span>

<span data-ttu-id="4bc98-104">Attribute ermöglichen, Metadaten auf ein Programmiermodell angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4bc98-104">Attributes enable metadata to be applied to a programming construct.</span></span>

## <a name="syntax"></a><span data-ttu-id="4bc98-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4bc98-105">Syntax</span></span>

```fsharp
[<target:attribute-name(arguments)>]
```

## <a name="remarks"></a><span data-ttu-id="4bc98-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4bc98-106">Remarks</span></span>

<span data-ttu-id="4bc98-107">In der vorherigen Syntax der *Ziel* ist optional und, falls vorhanden, gibt die Art der Programmentität, die auf das Attribut angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="4bc98-107">In the previous syntax, the *target* is optional and, if present, specifies the kind of program entity that the attribute applies to.</span></span> <span data-ttu-id="4bc98-108">Gültige Werte für *Ziel* werden in der Tabelle, die weiter unten in diesem Dokument genannten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4bc98-108">Valid values for *target* are shown in the table that appears later in this document.</span></span>

<span data-ttu-id="4bc98-109">Die *Attributnamen* bezieht sich auf den Namen (möglicherweise mit Namespaces qualifiziert) eines gültigen Attributtyps, mit oder ohne das Suffix `Attribute` , die in der Regel in Attributnamen-Typ verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4bc98-109">The *attribute-name* refers to the name (possibly qualified with namespaces) of a valid attribute type, with or without the suffix `Attribute` that is usually used in attribute type names.</span></span> <span data-ttu-id="4bc98-110">Z. B. den Typ `ObsoleteAttribute` gekürzt werden können, um den gerade `Obsolete` in diesem Kontext.</span><span class="sxs-lookup"><span data-stu-id="4bc98-110">For example, the type `ObsoleteAttribute` can be shortened to just `Obsolete` in this context.</span></span>

<span data-ttu-id="4bc98-111">Die *Argumente* sind die Argumente des Konstruktors für den Typ des Attributs.</span><span class="sxs-lookup"><span data-stu-id="4bc98-111">The *arguments* are the arguments to the constructor for the attribute type.</span></span> <span data-ttu-id="4bc98-112">Wenn ein Attribut über einen Standardkonstruktor verfügt, können der Argumentliste und die Klammern weggelassen werden.</span><span class="sxs-lookup"><span data-stu-id="4bc98-112">If an attribute has a default constructor, the argument list and parentheses can be omitted.</span></span> <span data-ttu-id="4bc98-113">Attribute unterstützen sowohl Positionsargumente und benannte Argumente.</span><span class="sxs-lookup"><span data-stu-id="4bc98-113">Attributes support both positional arguments and named arguments.</span></span> <span data-ttu-id="4bc98-114">*Positionsargumente* sind Argumente, die in der Reihenfolge verwendet werden, in der sie angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="4bc98-114">*Positional arguments* are arguments that are used in the order in which they appear.</span></span> <span data-ttu-id="4bc98-115">Benannte Argumente können verwendet werden, wenn das Attribut öffentliche Eigenschaften besitzt.</span><span class="sxs-lookup"><span data-stu-id="4bc98-115">Named arguments can be used if the attribute has public properties.</span></span> <span data-ttu-id="4bc98-116">Sie können diese Ereignisse mithilfe der folgenden Syntax in der Argumentliste festlegen.</span><span class="sxs-lookup"><span data-stu-id="4bc98-116">You can set these by using the following syntax in the argument list.</span></span>

```
*property-name* = *property-value*
```

<span data-ttu-id="4bc98-117">Eine solche Eigenschaft Initialisierungen können in beliebiger Reihenfolge sein, aber sie müssen alle Positionsargumente entsprechen.</span><span class="sxs-lookup"><span data-stu-id="4bc98-117">Such property initializations can be in any order, but they must follow any positional arguments.</span></span> <span data-ttu-id="4bc98-118">Es folgt ein Beispiel für ein Attribut, das Positions- und Initialisierungen der Eigenschaft verwendet.</span><span class="sxs-lookup"><span data-stu-id="4bc98-118">Following is an example of an attribute that uses positional arguments and property initializations.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6202.fs)]

<span data-ttu-id="4bc98-119">In diesem Beispiel wird das Attribut `DllImportAttribute`, hier in Kurzform verwendet.</span><span class="sxs-lookup"><span data-stu-id="4bc98-119">In this example, the attribute is `DllImportAttribute`, here used in shortened form.</span></span> <span data-ttu-id="4bc98-120">Das erste Argument ist ein Positionsparameter und die zweite ist eine Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="4bc98-120">The first argument is a positional parameter and the second is a property.</span></span>

<span data-ttu-id="4bc98-121">Attribute sind ein .NET Programmiermodell, das ein Objekt, das als bezeichnet ermöglicht eine *Attribut* einen Typ oder ein anderes Programmelement zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4bc98-121">Attributes are a .NET programming construct that enables an object known as an *attribute* to be associated with a type or other program element.</span></span> <span data-ttu-id="4bc98-122">Das Programmelement, das auf die ein Attribut angewendet wird, wird als bezeichnet den *Attributziel*.</span><span class="sxs-lookup"><span data-stu-id="4bc98-122">The program element to which an attribute is applied is known as the *attribute target*.</span></span> <span data-ttu-id="4bc98-123">Das Attribut enthält normalerweise Metadaten zum Ziel.</span><span class="sxs-lookup"><span data-stu-id="4bc98-123">The attribute usually contains metadata about its target.</span></span> <span data-ttu-id="4bc98-124">In diesem Kontext möglicherweise Metadaten Daten über den Typ als dessen Felder und Member.</span><span class="sxs-lookup"><span data-stu-id="4bc98-124">In this context, metadata could be any data about the type other than its fields and members.</span></span>

<span data-ttu-id="4bc98-125">Attribute in f# können auf die folgenden Programmierungskonstrukte angewendet werden: Funktionen, Methoden, Assemblys, Module, Typen (Klassen, Datensätze, Strukturen, Schnittstellen, Delegaten, Enumerationen, Unions und So weiter), Konstruktoren, Eigenschaften, Felder, Parameter Geben Sie die Parameter und Rückgabewerte.</span><span class="sxs-lookup"><span data-stu-id="4bc98-125">Attributes in F# can be applied to the following programming constructs: functions, methods, assemblies, modules, types (classes, records, structures, interfaces, delegates, enumerations, unions, and so on), constructors, properties, fields, parameters, type parameters, and return values.</span></span> <span data-ttu-id="4bc98-126">Attribute dürfen nicht auf `let` Bindungen in Klassen, Ausdrücke oder Ausdrücke für Workflows.</span><span class="sxs-lookup"><span data-stu-id="4bc98-126">Attributes are not allowed on `let` bindings inside classes, expressions, or workflow expressions.</span></span>

<span data-ttu-id="4bc98-127">In der Regel wird die Attributdeklaration direkt vor der Deklaration des Attributziels angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4bc98-127">Typically, the attribute declaration appears directly before the declaration of the attribute target.</span></span> <span data-ttu-id="4bc98-128">Mehrere Attributdeklarationen können verwendet werden, zusammen, wie folgt.</span><span class="sxs-lookup"><span data-stu-id="4bc98-128">Multiple attribute declarations can be used together, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6603.fs)]

<span data-ttu-id="4bc98-129">Sie können Attribute zur Laufzeit mithilfe der .NET-Spiegelung Abfragen.</span><span class="sxs-lookup"><span data-stu-id="4bc98-129">You can query attributes at run time by using .NET reflection.</span></span>

<span data-ttu-id="4bc98-130">Sie können mehrere Attribute einzeln deklarieren, wie im vorherigen Codebeispiel, oder Sie können diese in einem Satz von Klammern deklarieren, wenn Sie ein Semikolon verwenden, trennen Sie die einzelnen Attribute und Konstruktoren, wie hier gezeigt.</span><span class="sxs-lookup"><span data-stu-id="4bc98-130">You can declare multiple attributes individually, as in the previous code example, or you can declare them in one set of brackets if you use a semicolon to separate the individual attributes and constructors, as shown here.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6604.fs)]

<span data-ttu-id="4bc98-131">In der Regel beim Attribute enthalten die `Obsolete` Attribut Attribute für Sicherheitsaspekte, Attribute, für COM-Unterstützung, Attribute, der Besitz des Codes in Bezug auf, und Attribute, die angibt, ob ein Typ serialisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="4bc98-131">Typically encountered attributes include the `Obsolete` attribute, attributes for security considerations, attributes for COM support, attributes that relate to ownership of code, and attributes indicating whether a type can be serialized.</span></span> <span data-ttu-id="4bc98-132">Das folgende Beispiel veranschaulicht die Verwendung von der `Obsolete` Attribut.</span><span class="sxs-lookup"><span data-stu-id="4bc98-132">The following example demonstrates the use of the `Obsolete` attribute.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6605.fs)]

<span data-ttu-id="4bc98-133">Für das Attribut abzielt `assembly` und `module`, wenden Sie die Attribute auf einem der obersten Ebene `do` in Ihrer Assembly binden.</span><span class="sxs-lookup"><span data-stu-id="4bc98-133">For the attribute targets `assembly` and `module`, you apply the attributes to a top-level `do` binding in your assembly.</span></span> <span data-ttu-id="4bc98-134">Sie können das Wort einschließen `assembly` oder `module` in der Attributdeklaration wie folgt.</span><span class="sxs-lookup"><span data-stu-id="4bc98-134">You can include the word `assembly` or `module` in the attribute declaration, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6606.fs)]

<span data-ttu-id="4bc98-135">Wenn Sie Attributziel für ein Attribut weglassen auf eine `do` binden, f#-Compiler versucht Attributziel zu ermitteln, die für dieses Attribut sinnvoll ist.</span><span class="sxs-lookup"><span data-stu-id="4bc98-135">If you omit the attribute target for an attribute applied to a `do` binding, the F# compiler attempts to determine the attribute target that makes sense for that attribute.</span></span> <span data-ttu-id="4bc98-136">Viele Attributklassen verfügen über ein Attribut des Typs `System.AttributeUsageAttribute` , enthält Informationen zu den möglichen Ziele für dieses Attribut unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4bc98-136">Many attribute classes have an attribute of type `System.AttributeUsageAttribute` that includes information about the possible targets supported for that attribute.</span></span> <span data-ttu-id="4bc98-137">Wenn die `System.AttributeUsageAttribute` gibt an, dass das Attribut Funktionen als Ziele unterstützt, das Attribut wird verwendet, um auf den Haupteinstiegspunkt des Programms anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="4bc98-137">If the `System.AttributeUsageAttribute` indicates that the attribute supports functions as targets, the attribute is taken to apply to the main entry point of the program.</span></span> <span data-ttu-id="4bc98-138">Wenn die `System.AttributeUsageAttribute` gibt an, dass das Attribut Assemblys als Ziele unterstützt, nimmt der Compiler das Attribut für die Assembly angewendet.</span><span class="sxs-lookup"><span data-stu-id="4bc98-138">If the `System.AttributeUsageAttribute` indicates that the attribute supports assemblies as targets, the compiler takes the attribute to apply to the assembly.</span></span> <span data-ttu-id="4bc98-139">Die meisten Attribute gelten nicht für Funktionen und Assemblys, aber in Fällen, in denen dies der Fall, wird das Attribut an, das Programm main-Funktion übernommen.</span><span class="sxs-lookup"><span data-stu-id="4bc98-139">Most attributes do not apply to both functions and assemblies, but in cases where they do, the attribute is taken to apply to the program's main function.</span></span> <span data-ttu-id="4bc98-140">Wenn das Attributziel explizit angegeben wird, wird das Attribut auf das angegebene Ziel angewendet.</span><span class="sxs-lookup"><span data-stu-id="4bc98-140">If the attribute target is specified explicitly, the attribute is applied to the specified target.</span></span>

<span data-ttu-id="4bc98-141">Obwohl Sie nicht in der Regel benötigen, geben Sie das Attribut als Ziel explizit, gültige Werte für *Ziel* in einem Attribut werden in der folgenden Tabelle zusammen mit Beispielen, die Verwendung von angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4bc98-141">Although you do not usually need to specify the attribute target explicitly, valid values for *target* in an attribute are shown in the following table, along with examples of usage.</span></span>

<table>
  <tr>
    <th><span data-ttu-id="4bc98-142">Attributziel</span><span class="sxs-lookup"><span data-stu-id="4bc98-142">Attribute target</span></span></td>
    <th><span data-ttu-id="4bc98-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4bc98-143">Example</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="4bc98-144">Assembly</span><span class="sxs-lookup"><span data-stu-id="4bc98-144">assembly</span></span></td>
    <td><span data-ttu-id="4bc98-145">`[<assembly: AssemblyVersionAttribute("1.0.0.0")>]`</span><span class="sxs-lookup"><span data-stu-id="4bc98-145">`[<assembly: AssemblyVersionAttribute("1.0.0.0")>]`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="4bc98-146">return</span><span class="sxs-lookup"><span data-stu-id="4bc98-146">return</span></span></td>
    <td><span data-ttu-id="4bc98-147">"Funktion1 können X: [<return: Obsolete>] Int = X + 1"</span><span class="sxs-lookup"><span data-stu-id="4bc98-147">`let function1 x : [<return: Obsolete>] int = x + 1`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="4bc98-148">Feld</span><span class="sxs-lookup"><span data-stu-id="4bc98-148">field</span></span></td>
    <td><span data-ttu-id="4bc98-149">"[<field: DefaultValue>] Val änderbare X: int"</span><span class="sxs-lookup"><span data-stu-id="4bc98-149">`[<field: DefaultValue>] val mutable x: int`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="4bc98-150">property</span><span class="sxs-lookup"><span data-stu-id="4bc98-150">property</span></span></td>
    <td><span data-ttu-id="4bc98-151">"[<property: Obsolete>] dies. MyProperty = X "</span><span class="sxs-lookup"><span data-stu-id="4bc98-151">`[<property: Obsolete>] this.MyProperty = x`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="4bc98-152">Param</span><span class="sxs-lookup"><span data-stu-id="4bc98-152">param</span></span></td>
    <td><span data-ttu-id="4bc98-153">"Member dies. MyMethod ([<param: Out>] X: Ref<int>) = X: = 10'</span><span class="sxs-lookup"><span data-stu-id="4bc98-153">`member this.MyMethod([<param: Out>] x : ref<int>) = x := 10`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="4bc98-154">Typ</span><span class="sxs-lookup"><span data-stu-id="4bc98-154">type</span></span></td>
    <td><span data-ttu-id="4bc98-155">
        ```
        [<type: StructLayout(Sequential)>] geben MyStruct Struktur = X: Byte y: Int-Ende ```
    </span><span class="sxs-lookup"><span data-stu-id="4bc98-155">
        ```
        [<type: StructLayout(Sequential)>] type MyStruct = struct x : byte y : int end ```
    </span></span></td> 
  </tr>
</table>

## <a name="see-also"></a><span data-ttu-id="4bc98-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4bc98-156">See Also</span></span>

[<span data-ttu-id="4bc98-157">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="4bc98-157">F# Language Reference</span></span>](index.md)
