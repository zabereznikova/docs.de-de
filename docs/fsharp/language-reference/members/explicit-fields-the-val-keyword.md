---
title: "Explizite Felder: Das val-Schlüsselwort (F#)"
description: "Erfahren Sie mehr über die F#-\"Val\" Schlüsselwort, das verwendet wird, um einen Speicherort zum Speichern eines Werts in einer Klasse oder Struktur, ohne die Initialisierung des Typs deklarieren."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 3bdbc745-436b-407f-bf54-5d11ca829cd0
ms.openlocfilehash: cee53a48f08aec89b0bdd40189ed331cadee877d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="explicit-fields-the-val-keyword"></a><span data-ttu-id="e0834-104">Explizite Felder: Das val-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="e0834-104">Explicit Fields: The val Keyword</span></span>

<span data-ttu-id="e0834-105">Das `val`-Schlüsselwort wird zum Deklarieren eines Speicherort zum Speichern eines Werts in einer Klasse oder einem Strukturtyp verwendet, ohne ihn zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="e0834-105">The `val` keyword is used to declare a location to store a value in a class or structure type, without initializing it.</span></span> <span data-ttu-id="e0834-106">Speicherorte, die auf diese Weise deklariert heißen *explizite Felder*.</span><span class="sxs-lookup"><span data-stu-id="e0834-106">Storage locations declared in this manner are called *explicit fields*.</span></span> <span data-ttu-id="e0834-107">Das `val`-Schlüsselwort kann auch zusammen mit dem `member`-Schlüsselwort verwendet werden, um eine automatisch implementierte Eigenschaft zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="e0834-107">Another use of the `val` keyword is in conjunction with the `member` keyword to declare an auto-implemented property.</span></span> <span data-ttu-id="e0834-108">Weitere Informationen zu automatisch implementierte Eigenschaften finden Sie unter [Eigenschaften](properties.md).</span><span class="sxs-lookup"><span data-stu-id="e0834-108">For more information on auto-implemented properties, see [Properties](properties.md).</span></span>


## <a name="syntax"></a><span data-ttu-id="e0834-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="e0834-109">Syntax</span></span>

```fsharp
val [ mutable ] [ access-modifier ] field-name : type-name
```

## <a name="remarks"></a><span data-ttu-id="e0834-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e0834-110">Remarks</span></span>
<span data-ttu-id="e0834-111">In der Regel werden Felder in einer Klasse oder einem Strukturtyp durch eine `let`-Bindung definiert.</span><span class="sxs-lookup"><span data-stu-id="e0834-111">The usual way to define fields in a class or structure type is to use a `let` binding.</span></span> <span data-ttu-id="e0834-112">`let`-Bindungen müssen jedoch als Teil des Klassenkonstruktors initialisiert werden, was nicht immer möglich, notwendig oder gewünscht ist.</span><span class="sxs-lookup"><span data-stu-id="e0834-112">However, `let` bindings must be initialized as part of the class constructor, which is not always possible, necessary, or desirable.</span></span> <span data-ttu-id="e0834-113">Sie können das `val`-Schlüsselwort verwenden, wenn Sie ein nicht initialisiertes Feld implementieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e0834-113">You can use the `val` keyword when you want a field that is uninitialized.</span></span>

<span data-ttu-id="e0834-114">Explizite Felder können statisch oder nicht statisch sein.</span><span class="sxs-lookup"><span data-stu-id="e0834-114">Explicit fields can be static or non-static.</span></span> <span data-ttu-id="e0834-115">Die *Zugriffsmodifizierer* kann `public`, `private`, oder `internal`.</span><span class="sxs-lookup"><span data-stu-id="e0834-115">The *access-modifier* can be `public`, `private`, or `internal`.</span></span> <span data-ttu-id="e0834-116">Standardmäßig sind explizite Felder öffentlich.</span><span class="sxs-lookup"><span data-stu-id="e0834-116">By default, explicit fields are public.</span></span> <span data-ttu-id="e0834-117">Dies unterscheidet sich von `let`-Bindungen in Klassen, die immer privat sind.</span><span class="sxs-lookup"><span data-stu-id="e0834-117">This differs from `let` bindings in classes, which are always private.</span></span>

<span data-ttu-id="e0834-118">Die ["DefaultValue"](https://msdn.microsoft.com/library/a3a3307b-8c05-441e-b109-245511614d58) Attribut muss für explizite Felder in Klassentypen, die über einen primären Konstruktor verfügen.</span><span class="sxs-lookup"><span data-stu-id="e0834-118">The [DefaultValue](https://msdn.microsoft.com/library/a3a3307b-8c05-441e-b109-245511614d58) attribute is required on explicit fields in class types that have a primary constructor.</span></span> <span data-ttu-id="e0834-119">Dieses Attribut gibt an, dass das Feld mit 0 (null) initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="e0834-119">This attribute specifies that the field is initialized to zero.</span></span> <span data-ttu-id="e0834-120">Der Typ des Felds muss die Initialisierung mit 0 (null) unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e0834-120">The type of the field must support zero-initialization.</span></span> <span data-ttu-id="e0834-121">Ein Typ unterstützt die Initialisierung mit 0 (null), wenn er eine der folgenden Bedingungen erfüllt:</span><span class="sxs-lookup"><span data-stu-id="e0834-121">A type supports zero-initialization if it is one of the following:</span></span>

- <span data-ttu-id="e0834-122">Ein primitiver Typ, der einen Wert von 0 (null) hat.</span><span class="sxs-lookup"><span data-stu-id="e0834-122">A primitive type that has a zero value.</span></span>

- <span data-ttu-id="e0834-123">Ein Typ, der den Wert 0 (null) unterstützt, entweder als ein normaler Wert, als ein nicht normaler Wert oder als Darstellung eines Werts.</span><span class="sxs-lookup"><span data-stu-id="e0834-123">A type that supports a null value, either as a normal value, as an abnormal value, or as a representation of a value.</span></span> <span data-ttu-id="e0834-124">Dazu gehören Klassen, Tupel, Datensätze, Funktionen, Schnittstellen, .NET-Verweistypen, der `unit`-Typ und diskriminierte Union-Typen.</span><span class="sxs-lookup"><span data-stu-id="e0834-124">This includes classes, tuples, records, functions, interfaces, .NET reference types, the `unit` type, and discriminated union types.</span></span>

- <span data-ttu-id="e0834-125">Ein .NET-Werttyp.</span><span class="sxs-lookup"><span data-stu-id="e0834-125">A .NET value type.</span></span>

- <span data-ttu-id="e0834-126">Eine Struktur, deren Felder alle einen Standardwert von 0 (null) unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e0834-126">A structure whose fields all support a default zero value.</span></span>


<span data-ttu-id="e0834-127">Ein unveränderliches Feld mit der Bezeichnung `someField` verfügt zum Beispiel über ein zugrunde liegendes Feld in der kompilierten .NET-Darstellung, das `someField@` heißt, und Sie greifen auf den gespeicherten Wert mit einer Eigenschaft mit der Bezeichnung `someField` zu.</span><span class="sxs-lookup"><span data-stu-id="e0834-127">For example, an immutable field called `someField` has a backing field in the .NET compiled representation with the name `someField@`, and you access the stored value using a property named `someField`.</span></span>

<span data-ttu-id="e0834-128">Bei einem veränderlichen Feld ist die kompilierte .NET-Darstellung ein .NET-Feld.</span><span class="sxs-lookup"><span data-stu-id="e0834-128">For a mutable field, the .NET compiled representation is a .NET field.</span></span>


>[!WARNING] 
<span data-ttu-id="e0834-129">`Note`.NET Framework-Namespaces `System.ComponentModel` enthält ein Attribut, das den gleichen Namen hat.</span><span class="sxs-lookup"><span data-stu-id="e0834-129">`Note` The .NET Framework namespace `System.ComponentModel` contains an attribute that has the same name.</span></span> <span data-ttu-id="e0834-130">Informationen zu diesem Attribut finden Sie unter `System.ComponentModel.DefaultValueAttribute`.</span><span class="sxs-lookup"><span data-stu-id="e0834-130">For information about this attribute, see `System.ComponentModel.DefaultValueAttribute`.</span></span>


<span data-ttu-id="e0834-131">Der folgende Code zeigt die Verwendung expliziter Felder und zum Vergleich eine `let`-Bindung in einer Klasse, die über einen primären Konstruktor verfügt.</span><span class="sxs-lookup"><span data-stu-id="e0834-131">The following code shows the use of explicit fields and, for comparison, a `let` binding in a class that has a primary constructor.</span></span> <span data-ttu-id="e0834-132">Beachten Sie, dass das `let`-gebundene Feld `myInt1` privat ist.</span><span class="sxs-lookup"><span data-stu-id="e0834-132">Note that the `let`-bound field `myInt1` is private.</span></span> <span data-ttu-id="e0834-133">Wenn das `let`-gebundene Feld `myInt1` von einer Membermethode referenziert wird, ist der Selbstbezeichner `this` nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e0834-133">When the `let`-bound field `myInt1` is referenced from a member method, the self identifier `this` is not required.</span></span> <span data-ttu-id="e0834-134">Wenn Sie jedoch die expliziten Felder `myInt2` und `myString` referenzieren, ist der Selbstbezeichner erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e0834-134">But when you are referencing the explicit fields `myInt2` and `myString`, the self identifier is required.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6701.fs)]

<span data-ttu-id="e0834-135">Die Ausgabe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e0834-135">The output is as follows:</span></span>

```
11 12 abc
30 def
```

<span data-ttu-id="e0834-136">Der folgende Code zeigt die Verwendung von expliziten Feldern in einer Klasse, die nicht über einen primären Konstruktor verfügt.</span><span class="sxs-lookup"><span data-stu-id="e0834-136">The following code shows the use of explicit fields in a class that does not have a primary constructor.</span></span> <span data-ttu-id="e0834-137">In diesem Fall ist das `DefaultValue`-Attribut nicht erforderlich, es müssen jedoch alle Felder in den Konstruktoren initialisiert werden, die für den Typ definiert sind.</span><span class="sxs-lookup"><span data-stu-id="e0834-137">In this case, the `DefaultValue` attribute is not required, but all the fields must be initialized in the constructors that are defined for the type.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6702.fs)]

<span data-ttu-id="e0834-138">Die Ausgabe lautet `35 22`.</span><span class="sxs-lookup"><span data-stu-id="e0834-138">The output is `35 22`.</span></span>

<span data-ttu-id="e0834-139">Der folgende Code zeigt die Verwendung von expliziten Feldern in einer Struktur.</span><span class="sxs-lookup"><span data-stu-id="e0834-139">The following code shows the use of explicit fields in a structure.</span></span> <span data-ttu-id="e0834-140">Da eine Struktur ein Werttyp ist, verfügt sie automatisch über einen Standardkonstruktor, der die Werte der zugehörigen Felder auf 0 (null) festlegt.</span><span class="sxs-lookup"><span data-stu-id="e0834-140">Because a structure is a value type, it automatically has a default constructor that sets the values of its fields to zero.</span></span> <span data-ttu-id="e0834-141">Daher ist das `DefaultValue`-Attribut nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e0834-141">Therefore, the `DefaultValue` attribute is not required.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6703.fs)]

<span data-ttu-id="e0834-142">Die Ausgabe lautet `11 xyz`.</span><span class="sxs-lookup"><span data-stu-id="e0834-142">The output is `11 xyz`.</span></span>

<span data-ttu-id="e0834-143">Explizite Felder sind nicht für die routinemäßige Verwendung gedacht.</span><span class="sxs-lookup"><span data-stu-id="e0834-143">Explicit fields are not intended for routine use.</span></span> <span data-ttu-id="e0834-144">Im Allgemeinen sollten Sie möglichst eine `let`-Bindung in einer Klasse verwenden, statt eines expliziten Felds.</span><span class="sxs-lookup"><span data-stu-id="e0834-144">In general, when possible you should use a `let` binding in a class instead of an explicit field.</span></span> <span data-ttu-id="e0834-145">Explizite Felder sind in bestimmten Interoperabilitätsszenarios hilfreich, wenn Sie z. B. eine Struktur definieren müssen, die in einem Plattformaufruf einer systemeigenen API oder in COM-Interop-Szenarien verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e0834-145">Explicit fields are useful in certain interoperability scenarios, such as when you need to define a structure that will be used in a platform invoke call to a native API, or in COM interop scenarios.</span></span> <span data-ttu-id="e0834-146">Weitere Informationen finden Sie unter [externe Funktionen](../functions/external-functions.md).</span><span class="sxs-lookup"><span data-stu-id="e0834-146">For more information, see [External Functions](../functions/external-functions.md).</span></span> <span data-ttu-id="e0834-147">Eine andere Situation, in der ein explizites Feld möglicherweise erforderlich, besteht dann, wenn Sie mit einem F#-Codegenerator arbeiten, der Klassen ohne primären Konstruktor ausgibt.</span><span class="sxs-lookup"><span data-stu-id="e0834-147">Another situation in which an explicit field might be necessary is when you are working with an F# code generator which emits classes without a primary constructor.</span></span> <span data-ttu-id="e0834-148">Explizite Felder sind auch für threadstatische Variablen oder ähnliche Konstrukte sinnvoll.</span><span class="sxs-lookup"><span data-stu-id="e0834-148">Explicit fields are also useful for thread-static variables or similar constructs.</span></span> <span data-ttu-id="e0834-149">Weitere Informationen finden Sie unter `System.ThreadStaticAttribute`.</span><span class="sxs-lookup"><span data-stu-id="e0834-149">For more information, see `System.ThreadStaticAttribute`.</span></span>

<span data-ttu-id="e0834-150">Wenn die Schlüsselwörter `member val` zusammen in einer Typdefinition angezeigt werden, handelt es sich um eine Definition einer automatisch implementierten Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e0834-150">When the keywords `member val` appear together in a type definition, it is a definition of an automatically implemented property.</span></span> <span data-ttu-id="e0834-151">Weitere Informationen finden Sie unter [Eigenschaften](properties.md).</span><span class="sxs-lookup"><span data-stu-id="e0834-151">For more information, see [Properties](properties.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="e0834-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0834-152">See Also</span></span>
[<span data-ttu-id="e0834-153">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="e0834-153">Properties</span></span>](properties.md)

[<span data-ttu-id="e0834-154">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="e0834-154">Members</span></span>](index.md)

[<span data-ttu-id="e0834-155">`let`-Bindungen in Klassen</span><span class="sxs-lookup"><span data-stu-id="e0834-155">`let` Bindings in Classes</span></span>](let-bindings-in-classes.md)
