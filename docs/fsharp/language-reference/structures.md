---
title: Strukturen (F#)
description: "Erfahren Sie mehr über die f#-Struktur, ein kompakter Objekttyp, der häufig effizienter als eine Klasse für Typen mit einer kleinen Menge an Daten und einfaches Verhalten."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 50819506-3210-418f-9602-0ee1c9a52177
ms.openlocfilehash: 542b69a5aacb8fcfb0e8f6d6c943fe1954c4c59c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="structures"></a><span data-ttu-id="26d5a-104">Strukturen</span><span class="sxs-lookup"><span data-stu-id="26d5a-104">Structures</span></span>

<span data-ttu-id="26d5a-105">Ein *Struktur* ist ein kompakter Objekttyp, die effizienter als eine Klasse für Typen sein kann, die eine kleine Menge von Daten und ein einfaches Verhalten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="26d5a-105">A *structure* is a compact object type that can be more efficient than a class for types that have a small amount of data and simple behavior.</span></span>

## <a name="syntax"></a><span data-ttu-id="26d5a-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="26d5a-106">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    struct
        type-definition-elements
    end
// or
[ attributes ]
[<StructAttribute>]
type [accessibility-modifier] type-name =
    type-definition-elements
```

## <a name="remarks"></a><span data-ttu-id="26d5a-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="26d5a-107">Remarks</span></span>
<span data-ttu-id="26d5a-108">Strukturen sind *Werttypen*, dies bedeutet, dass diese gespeichert sind, direkt auf dem Stapel oder, wenn sie als verwendet werden, dass Felder oder Array-Elemente Inline in der übergeordneten Tabelle geben.</span><span class="sxs-lookup"><span data-stu-id="26d5a-108">Structures are *value types*, which means that they are stored directly on the stack or, when they are used as fields or array elements, inline in the parent type.</span></span> <span data-ttu-id="26d5a-109">Im Gegensatz zu Klassen und Datensätzen verfügen Strukturen über eine Übergabewertsemantik.</span><span class="sxs-lookup"><span data-stu-id="26d5a-109">Unlike classes and records, structures have pass-by-value semantics.</span></span> <span data-ttu-id="26d5a-110">Dies bedeutet, dass sie hauptsächlich für kleine Datenaggregate sinnvoll sind, die häufig aufgerufen und kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="26d5a-110">This means that they are useful primarily for small aggregates of data that are accessed and copied frequently.</span></span>

<span data-ttu-id="26d5a-111">In der vorherigen Syntax werden zwei Formen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="26d5a-111">In the previous syntax, two forms are shown.</span></span> <span data-ttu-id="26d5a-112">Die erste ist nicht die einfache Syntax, aber sie wird trotzdem häufig verwendet, da Sie bei Verwendung der Schlüsselwörter `struct` und `end` das `StructAttribute`-Attribut auslassen können, das in der zweiten Form angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="26d5a-112">The first is not the lightweight syntax, but it is nevertheless frequently used because, when you use the `struct` and `end` keywords, you can omit the `StructAttribute` attribute, which appears in the second form.</span></span> <span data-ttu-id="26d5a-113">Sie können `StructAttribute` zu `Struct` abkürzen.</span><span class="sxs-lookup"><span data-stu-id="26d5a-113">You can abbreviate `StructAttribute` to just `Struct`.</span></span>

<span data-ttu-id="26d5a-114">Die *-Definitions-Elemente* in der vorherigen Syntax stellt Memberdeklarationen und-Definitionen.</span><span class="sxs-lookup"><span data-stu-id="26d5a-114">The *type-definition-elements* in the previous syntax represents member declarations and definitions.</span></span> <span data-ttu-id="26d5a-115">Strukturen können über Konstruktoren sowie änderbare und unveränderliche Felder verfügen, und sie können Member und Schnittstellenimplementierungen deklarieren.</span><span class="sxs-lookup"><span data-stu-id="26d5a-115">Structures can have constructors and mutable and immutable fields, and they can declare members and interface implementations.</span></span> <span data-ttu-id="26d5a-116">Weitere Informationen finden Sie unter [Elemente](members/index.md).</span><span class="sxs-lookup"><span data-stu-id="26d5a-116">For more information, see [Members](members/index.md).</span></span>

<span data-ttu-id="26d5a-117">Strukturen können nicht an der Vererbung beteiligt sein, sie können keine `let`- oder `do`-Bindungen enthalten und können nicht rekursiv Felder des eigenen Typs enthalten (obwohl sie Verweiszellen enthalten können, die auf den eigenen Typ verweisen).</span><span class="sxs-lookup"><span data-stu-id="26d5a-117">Structures cannot participate in inheritance, cannot contain `let` or `do` bindings, and cannot recursively contain fields of their own type (although they can contain reference cells that reference their own type).</span></span>

<span data-ttu-id="26d5a-118">Da Strukturen keine `let`-Bindungen zulassen, müssen Sie Felder in Strukturen mit dem `val`-Schlüsselwort deklarieren.</span><span class="sxs-lookup"><span data-stu-id="26d5a-118">Because structures do not allow `let` bindings, you must declare fields in structures by using the `val` keyword.</span></span> <span data-ttu-id="26d5a-119">Das `val`-Schlüsselwort definiert ein Feld und den Typ, es lässt jedoch keine Initialisierung zu.</span><span class="sxs-lookup"><span data-stu-id="26d5a-119">The `val` keyword defines a field and its type but does not allow initialization.</span></span> <span data-ttu-id="26d5a-120">In diesem Fall werden `val`-Deklarationen mit 0 oder null initialisiert.</span><span class="sxs-lookup"><span data-stu-id="26d5a-120">Instead, `val` declarations are initialized to zero or null.</span></span> <span data-ttu-id="26d5a-121">Aus diesem Grund erfordern Strukturen, die über einen impliziten Konstruktor verfügen (d. h. Parameter, die direkt nach dem Strukturnamen in der Deklaration angegeben werden), dass `val`-Deklarationen mit dem `DefaultValue`-Attribut gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="26d5a-121">For this reason, structures that have an implicit constructor (that is, parameters that are given immediately after the structure name in the declaration) require that `val` declarations be annotated with the `DefaultValue` attribute.</span></span> <span data-ttu-id="26d5a-122">Strukturen, die über einen definierten Konstruktor verfügen, unterstützen weiterhin die Initialisierung mit 0 (null).</span><span class="sxs-lookup"><span data-stu-id="26d5a-122">Structures that have a defined constructor still support zero-initialization.</span></span> <span data-ttu-id="26d5a-123">Aus diesem Grund ist das `DefaultValue`-Attribut eine Deklaration, dass der Wert 0 (Null) für das Feld gültig ist.</span><span class="sxs-lookup"><span data-stu-id="26d5a-123">Therefore, the `DefaultValue` attribute is a declaration that such a zero value is valid for the field.</span></span> <span data-ttu-id="26d5a-124">Implizite Konstruktoren für Strukturen führen keine Aktionen aus, da `let`- und `do`-Bindungen für den Typ nicht zulässig sind, aber die übergebenen impliziten Konstruktorparameterwerte sind als private Felder verfügbar.</span><span class="sxs-lookup"><span data-stu-id="26d5a-124">Implicit constructors for structures do not perform any actions because `let` and `do` bindings aren’t allowed on the type, but the implicit constructor parameter values passed in are available as private fields.</span></span>

<span data-ttu-id="26d5a-125">Explizite Konstruktoren können eine Initialisierung von Feldwerten beinhalten.</span><span class="sxs-lookup"><span data-stu-id="26d5a-125">Explicit constructors might involve initialization of field values.</span></span> <span data-ttu-id="26d5a-126">Wenn Sie eine Struktur mit einem expliziten Konstruktor haben, unterstützt sie weiterhin die Initialisierung mit 0 (Null); Sie verwenden jedoch nicht das `DefaultValue`-Attribut auf den `val`-Deklarationen, da es mit dem expliziten Konstruktor in Konflikt steht.</span><span class="sxs-lookup"><span data-stu-id="26d5a-126">When you have a structure that has an explicit constructor, it still supports zero-initialization; however, you do not use the `DefaultValue` attribute on the `val` declarations because it conflicts with the explicit constructor.</span></span> <span data-ttu-id="26d5a-127">Weitere Informationen zu `val` Deklarationen finden Sie unter [explizite Felder: das `val` Schlüsselwort](members/explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="26d5a-127">For more information about `val` declarations, see [Explicit Fields: The `val` Keyword](members/explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="26d5a-128">Attribute und Zugriffsmodifizierer sind für Strukturen zulässig und folgen denselben Regeln wie jene für andere Typen.</span><span class="sxs-lookup"><span data-stu-id="26d5a-128">Attributes and accessibility modifiers are allowed on structures, and follow the same rules as those for other types.</span></span> <span data-ttu-id="26d5a-129">Weitere Informationen finden Sie unter [Attribute](attributes.md) und [Access Control](access-control.md).</span><span class="sxs-lookup"><span data-stu-id="26d5a-129">For more information, see [Attributes](attributes.md) and [Access Control](access-control.md).</span></span>

<span data-ttu-id="26d5a-130">Die folgenden Codebeispiele veranschaulichen Strukturdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="26d5a-130">The following code examples illustrate structure definitions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2501.fs)]

## <a name="struct-records-and-discriminated-unions"></a><span data-ttu-id="26d5a-131">Struct-Datensätze und Unterscheidungs-Unions</span><span class="sxs-lookup"><span data-stu-id="26d5a-131">Struct Records and Discriminated Unions</span></span>

<span data-ttu-id="26d5a-132">Ab f# 4.1, Sie können darstellen [Datensätze](records.md) und [Unterscheidungs-Unions](discriminated-unions.md) als Strukturen mit dem `[<Struct>]` Attribut.</span><span class="sxs-lookup"><span data-stu-id="26d5a-132">Starting with F# 4.1, you can represent [Records](records.md) and [Discriminated Unions](discriminated-unions.md) as structs with the `[<Struct>]` attribute.</span></span>  <span data-ttu-id="26d5a-133">Finden Sie unter jeder Artikel, um mehr zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="26d5a-133">See each article to learn more.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="26d5a-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="26d5a-134">See Also</span></span>
[<span data-ttu-id="26d5a-135">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="26d5a-135">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="26d5a-136">Klassen</span><span class="sxs-lookup"><span data-stu-id="26d5a-136">Classes</span></span>](classes.md)

[<span data-ttu-id="26d5a-137">Datensätze</span><span class="sxs-lookup"><span data-stu-id="26d5a-137">Records</span></span>](records.md)

[<span data-ttu-id="26d5a-138">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="26d5a-138">Members</span></span>](members/index.md)
