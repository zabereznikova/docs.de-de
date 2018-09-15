---
title: Attribute (F#)
description: Erfahren Sie, wie F#--Attribute für Metadaten, die auf ein Programmierungskonstrukt angewendet werden können.
ms.date: 05/16/2016
ms.openlocfilehash: 3e7f1d0ff383e1070b3db72e633f80ea37150548
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2018
ms.locfileid: "45647949"
---
# <a name="attributes"></a><span data-ttu-id="ac70f-103">Attribute</span><span class="sxs-lookup"><span data-stu-id="ac70f-103">Attributes</span></span>

<span data-ttu-id="ac70f-104">Attribute ermöglichen, Metadaten, die auf ein Programmierungskonstrukt angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="ac70f-104">Attributes enable metadata to be applied to a programming construct.</span></span>

## <a name="syntax"></a><span data-ttu-id="ac70f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ac70f-105">Syntax</span></span>

```fsharp
[<target:attribute-name(arguments)>]
```

## <a name="remarks"></a><span data-ttu-id="ac70f-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ac70f-106">Remarks</span></span>

<span data-ttu-id="ac70f-107">In der vorherigen Syntax wird die *Ziel* ist optional, und, falls vorhanden, gibt die Art der Programmentität, die auf das Attribut angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="ac70f-107">In the previous syntax, the *target* is optional and, if present, specifies the kind of program entity that the attribute applies to.</span></span> <span data-ttu-id="ac70f-108">Gültige Werte für *Ziel* werden angezeigt, in der Tabelle, die weiter unten in diesem Dokument angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ac70f-108">Valid values for *target* are shown in the table that appears later in this document.</span></span>

<span data-ttu-id="ac70f-109">Die *Attributname* bezieht sich auf der (möglicherweise mit Namespaces qualifizierte) Name, der einen gültigen Attributtyp, mit oder ohne das Suffix `Attribute` , die in der Regel in den Typnamen des Attributs verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ac70f-109">The *attribute-name* refers to the name (possibly qualified with namespaces) of a valid attribute type, with or without the suffix `Attribute` that is usually used in attribute type names.</span></span> <span data-ttu-id="ac70f-110">Z. B. den Typ `ObsoleteAttribute` können verkürzt werden `Obsolete` in diesem Kontext.</span><span class="sxs-lookup"><span data-stu-id="ac70f-110">For example, the type `ObsoleteAttribute` can be shortened to just `Obsolete` in this context.</span></span>

<span data-ttu-id="ac70f-111">Die *Argumente* sind die Argumente an den Konstruktor für den Attributtyp.</span><span class="sxs-lookup"><span data-stu-id="ac70f-111">The *arguments* are the arguments to the constructor for the attribute type.</span></span> <span data-ttu-id="ac70f-112">Wenn ein Attribut einen Standardkonstruktor verfügt, können die Liste von Argumenten und die Klammern weggelassen werden.</span><span class="sxs-lookup"><span data-stu-id="ac70f-112">If an attribute has a default constructor, the argument list and parentheses can be omitted.</span></span> <span data-ttu-id="ac70f-113">Attribute unterstützen sowohl Positionsargumente als auch benannte Argumente.</span><span class="sxs-lookup"><span data-stu-id="ac70f-113">Attributes support both positional arguments and named arguments.</span></span> <span data-ttu-id="ac70f-114">*Positionelle Argumente* sind Argumente, die in der Reihenfolge verwendet werden, in der sie angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ac70f-114">*Positional arguments* are arguments that are used in the order in which they appear.</span></span> <span data-ttu-id="ac70f-115">Benannte Argumente können verwendet werden, wenn das Attribut mit öffentliche Eigenschaften aufweist.</span><span class="sxs-lookup"><span data-stu-id="ac70f-115">Named arguments can be used if the attribute has public properties.</span></span> <span data-ttu-id="ac70f-116">Sie können diese mit der folgenden Syntax in der Argumentliste festlegen.</span><span class="sxs-lookup"><span data-stu-id="ac70f-116">You can set these by using the following syntax in the argument list.</span></span>

```
*property-name* = *property-value*
```

<span data-ttu-id="ac70f-117">Solche eigenschafteninitialisierungen in beliebiger Reihenfolge möglich, aber sie müssen keine positionellen Argumente folgen.</span><span class="sxs-lookup"><span data-stu-id="ac70f-117">Such property initializations can be in any order, but they must follow any positional arguments.</span></span> <span data-ttu-id="ac70f-118">Es folgt ein Beispiel für ein Attribut, das positionelle Argumente und eigenschafteninitialisierungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="ac70f-118">Following is an example of an attribute that uses positional arguments and property initializations.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6202.fs)]

<span data-ttu-id="ac70f-119">In diesem Beispiel wird das Attribut `DllImportAttribute`, hier in Kurzform verwendet.</span><span class="sxs-lookup"><span data-stu-id="ac70f-119">In this example, the attribute is `DllImportAttribute`, here used in shortened form.</span></span> <span data-ttu-id="ac70f-120">Das erste Argument ist ein Positionsparameter, und die zweite ist eine Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="ac70f-120">The first argument is a positional parameter and the second is a property.</span></span>

<span data-ttu-id="ac70f-121">Attribute sind ein .NET programming Konstrukt, ein Objekt, bekannt als ein *Attribut* , einen Typ oder anderes Programmelement zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ac70f-121">Attributes are a .NET programming construct that enables an object known as an *attribute* to be associated with a type or other program element.</span></span> <span data-ttu-id="ac70f-122">Das Programmelement, das auf das ein Attribut angewendet wird, wird als bezeichnet die *Attributziel*.</span><span class="sxs-lookup"><span data-stu-id="ac70f-122">The program element to which an attribute is applied is known as the *attribute target*.</span></span> <span data-ttu-id="ac70f-123">Das Attribut enthält in der Regel die Metadaten zum Ziel.</span><span class="sxs-lookup"><span data-stu-id="ac70f-123">The attribute usually contains metadata about its target.</span></span> <span data-ttu-id="ac70f-124">In diesem Kontext möglicherweise Metadaten von Daten zu den anderen Typ als ihre Felder und Elemente.</span><span class="sxs-lookup"><span data-stu-id="ac70f-124">In this context, metadata could be any data about the type other than its fields and members.</span></span>

<span data-ttu-id="ac70f-125">Attribute in f# können angewendet werden, um die folgenden Konstrukte der Programmierung: Funktionen, Methoden, Assemblys, Modulen, Typen (Klassen, Datensätze, Strukturen, Schnittstellen, Delegaten, Enumerationen, Unions und So weiter), Konstruktoren, Eigenschaften, Felder, Parameter Geben Sie Parameter und Rückgabewerte.</span><span class="sxs-lookup"><span data-stu-id="ac70f-125">Attributes in F# can be applied to the following programming constructs: functions, methods, assemblies, modules, types (classes, records, structures, interfaces, delegates, enumerations, unions, and so on), constructors, properties, fields, parameters, type parameters, and return values.</span></span> <span data-ttu-id="ac70f-126">Attribute dürfen nicht auf `let` Bindungen in Klassen, Ausdrücke oder Ausdrücke für Workflows.</span><span class="sxs-lookup"><span data-stu-id="ac70f-126">Attributes are not allowed on `let` bindings inside classes, expressions, or workflow expressions.</span></span>

<span data-ttu-id="ac70f-127">In der Regel wird die Deklaration des Attributs direkt vor der Deklaration des Attributziels angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ac70f-127">Typically, the attribute declaration appears directly before the declaration of the attribute target.</span></span> <span data-ttu-id="ac70f-128">Mehrere Attributdeklarationen können verwendet werden, zusammen, wie folgt.</span><span class="sxs-lookup"><span data-stu-id="ac70f-128">Multiple attribute declarations can be used together, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6603.fs)]

<span data-ttu-id="ac70f-129">Sie können Attribute zur Laufzeit mit .NET-Reflektion Abfragen.</span><span class="sxs-lookup"><span data-stu-id="ac70f-129">You can query attributes at run time by using .NET reflection.</span></span>

<span data-ttu-id="ac70f-130">Sie können mehrere Attribute einzeln zu deklarieren, wie im vorherigen Codebeispiel, oder Sie können diese in einem Satz von Klammern deklarieren, wenn Sie ein Semikolon verwenden, den einzelnen Attributen und Konstruktoren, wie hier gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ac70f-130">You can declare multiple attributes individually, as in the previous code example, or you can declare them in one set of brackets if you use a semicolon to separate the individual attributes and constructors, as shown here.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6604.fs)]

<span data-ttu-id="ac70f-131">Gängigen Attributen zählen die `Obsolete` -Attribut, Attribute, sicherheitsüberlegungen, Attribute, für COM-Unterstützung, Attribute, die im Zusammenhang mit den Besitz des Codes und Attribute, die angibt, ob ein Typ serialisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="ac70f-131">Typically encountered attributes include the `Obsolete` attribute, attributes for security considerations, attributes for COM support, attributes that relate to ownership of code, and attributes indicating whether a type can be serialized.</span></span> <span data-ttu-id="ac70f-132">Das folgende Beispiel zeigt die Verwendung der `Obsolete` Attribut.</span><span class="sxs-lookup"><span data-stu-id="ac70f-132">The following example demonstrates the use of the `Obsolete` attribute.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6605.fs)]

<span data-ttu-id="ac70f-133">Für das Attribut abzielt `assembly` und `module`, wenden Sie die Attribute auf oberster Ebene `do` in der Assembly binden.</span><span class="sxs-lookup"><span data-stu-id="ac70f-133">For the attribute targets `assembly` and `module`, you apply the attributes to a top-level `do` binding in your assembly.</span></span> <span data-ttu-id="ac70f-134">Sie können das Wort einschließen `assembly` oder `module` in der Attributdeklaration, wie folgt.</span><span class="sxs-lookup"><span data-stu-id="ac70f-134">You can include the word `assembly` or `module` in the attribute declaration, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6606.fs)]

<span data-ttu-id="ac70f-135">Wenn Sie weglassen, dass das Attributziel für ein Attribut auf eine `do` Bindung, die f#-Compiler versucht, das Attributziel zu bestimmen, die sinnvoll für dieses Attribut ist.</span><span class="sxs-lookup"><span data-stu-id="ac70f-135">If you omit the attribute target for an attribute applied to a `do` binding, the F# compiler attempts to determine the attribute target that makes sense for that attribute.</span></span> <span data-ttu-id="ac70f-136">Viele Attributklassen verfügen über ein Attribut des Typs `System.AttributeUsageAttribute` , enthält Informationen zu den möglichen Zielen, die für dieses Attribut unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ac70f-136">Many attribute classes have an attribute of type `System.AttributeUsageAttribute` that includes information about the possible targets supported for that attribute.</span></span> <span data-ttu-id="ac70f-137">Wenn die `System.AttributeUsageAttribute` gibt an, dass das Attribut unterstützt die Funktionen als Ziele, die das Attribut verwendet, um auf den primären Einstiegspunkt des Programms anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="ac70f-137">If the `System.AttributeUsageAttribute` indicates that the attribute supports functions as targets, the attribute is taken to apply to the main entry point of the program.</span></span> <span data-ttu-id="ac70f-138">Wenn die `System.AttributeUsageAttribute` gibt an, dass das Attribut unterstützt Assemblys als Ziele, nimmt der Compiler das Attribut, auf die Assembly angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ac70f-138">If the `System.AttributeUsageAttribute` indicates that the attribute supports assemblies as targets, the compiler takes the attribute to apply to the assembly.</span></span> <span data-ttu-id="ac70f-139">Die meisten Attribute nicht für Funktionen und Assemblys, aber in Fällen, in denen dies der Fall, wird das Attribut zuweisen des Programms "main"-Funktion erstellt.</span><span class="sxs-lookup"><span data-stu-id="ac70f-139">Most attributes do not apply to both functions and assemblies, but in cases where they do, the attribute is taken to apply to the program's main function.</span></span> <span data-ttu-id="ac70f-140">Wenn das Attributziel explizit angegeben wird, wird das Attribut auf das angegebene Ziel angewendet.</span><span class="sxs-lookup"><span data-stu-id="ac70f-140">If the attribute target is specified explicitly, the attribute is applied to the specified target.</span></span>

<span data-ttu-id="ac70f-141">Obwohl Sie nicht in der Regel benötigen, geben Sie das Attributziel explizit gültige Werte für *Ziel* werden in einem Attribut in der folgenden Tabelle, und Beispiele für die Nutzung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ac70f-141">Although you do not usually need to specify the attribute target explicitly, valid values for *target* in an attribute are shown in the following table, along with examples of usage.</span></span>

<table>
  <tr>
    <th><span data-ttu-id="ac70f-142">Attributziel</span><span class="sxs-lookup"><span data-stu-id="ac70f-142">Attribute target</span></span></td>
    <th><span data-ttu-id="ac70f-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ac70f-143">Example</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="ac70f-144">Assembly</span><span class="sxs-lookup"><span data-stu-id="ac70f-144">assembly</span></span></td>
    <td><span data-ttu-id="ac70f-145">`[<assembly: AssemblyVersionAttribute("1.0.0.0")>]`</span><span class="sxs-lookup"><span data-stu-id="ac70f-145">`[<assembly: AssemblyVersionAttribute("1.0.0.0")>]`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="ac70f-146">return</span><span class="sxs-lookup"><span data-stu-id="ac70f-146">return</span></span></td>
    <td><span data-ttu-id="ac70f-147">"Funktion1 können X: [<return: Obsolete>] Int = X + 1"</span><span class="sxs-lookup"><span data-stu-id="ac70f-147">`let function1 x : [<return: Obsolete>] int = x + 1`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="ac70f-148">Feld</span><span class="sxs-lookup"><span data-stu-id="ac70f-148">field</span></span></td>
    <td><span data-ttu-id="ac70f-149">"[<field: DefaultValue>] Val änderbare X: int"</span><span class="sxs-lookup"><span data-stu-id="ac70f-149">`[<field: DefaultValue>] val mutable x: int`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="ac70f-150">property</span><span class="sxs-lookup"><span data-stu-id="ac70f-150">property</span></span></td>
    <td><span data-ttu-id="ac70f-151">"[<property: Obsolete>] dies. MyProperty = X "</span><span class="sxs-lookup"><span data-stu-id="ac70f-151">`[<property: Obsolete>] this.MyProperty = x`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="ac70f-152">Parameter</span><span class="sxs-lookup"><span data-stu-id="ac70f-152">param</span></span></td>
    <td><span data-ttu-id="ac70f-153">' Member dieser. MyMethod ([<param: Out>] X: Ref<int>) = X: = 10'</span><span class="sxs-lookup"><span data-stu-id="ac70f-153">`member this.MyMethod([<param: Out>] x : ref<int>) = x := 10`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="ac70f-154">Typ</span><span class="sxs-lookup"><span data-stu-id="ac70f-154">type</span></span></td>
    <td><span data-ttu-id="ac70f-155">
        ```
        [<type: StructLayout(Sequential)>] MyStruct geben Struktur = X: Byte-y: Int-Ende ```
    </span><span class="sxs-lookup"><span data-stu-id="ac70f-155">
        ```
        [<type: StructLayout(Sequential)>] type MyStruct = struct x : byte y : int end ```
    </span></span></td> 
  </tr>
</table>

## <a name="see-also"></a><span data-ttu-id="ac70f-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac70f-156">See also</span></span>

- [<span data-ttu-id="ac70f-157">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="ac70f-157">F# Language Reference</span></span>](index.md)
