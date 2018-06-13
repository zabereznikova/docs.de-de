---
title: Strukturen (F#)
description: Erfahren Sie mehr über die f#-Struktur, ein kompakter Objekttyp, der häufig effizienter als eine Klasse für Typen mit einer kleinen Menge an Daten und einfaches Verhalten.
ms.date: 05/16/2016
ms.openlocfilehash: 57c4148aec1d6a19237d74aa99824ef475c3632e
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2018
ms.locfileid: "34172463"
---
# <a name="structures"></a><span data-ttu-id="b4a73-103">Strukturen</span><span class="sxs-lookup"><span data-stu-id="b4a73-103">Structures</span></span>

<span data-ttu-id="b4a73-104">Ein *Struktur* ist ein kompakter Objekttyp, die effizienter als eine Klasse für Typen sein kann, die eine kleine Menge von Daten und ein einfaches Verhalten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="b4a73-104">A *structure* is a compact object type that can be more efficient than a class for types that have a small amount of data and simple behavior.</span></span>

## <a name="syntax"></a><span data-ttu-id="b4a73-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4a73-105">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    struct
        type-definition-elements-and-members
    end
// or
[ attributes ]
[<StructAttribute>]
type [accessibility-modifier] type-name =
    type-definition-elements-and-members
```

## <a name="remarks"></a><span data-ttu-id="b4a73-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b4a73-106">Remarks</span></span>
<span data-ttu-id="b4a73-107">Strukturen sind *Werttypen*, dies bedeutet, dass diese gespeichert sind, direkt auf dem Stapel oder, wenn sie als verwendet werden, dass Felder oder Array-Elemente Inline in der übergeordneten Tabelle geben.</span><span class="sxs-lookup"><span data-stu-id="b4a73-107">Structures are *value types*, which means that they are stored directly on the stack or, when they are used as fields or array elements, inline in the parent type.</span></span> <span data-ttu-id="b4a73-108">Im Gegensatz zu Klassen und Datensätzen verfügen Strukturen über eine Übergabewertsemantik.</span><span class="sxs-lookup"><span data-stu-id="b4a73-108">Unlike classes and records, structures have pass-by-value semantics.</span></span> <span data-ttu-id="b4a73-109">Dies bedeutet, dass sie hauptsächlich für kleine Datenaggregate sinnvoll sind, die häufig aufgerufen und kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="b4a73-109">This means that they are useful primarily for small aggregates of data that are accessed and copied frequently.</span></span>

<span data-ttu-id="b4a73-110">In der vorherigen Syntax werden zwei Formen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b4a73-110">In the previous syntax, two forms are shown.</span></span> <span data-ttu-id="b4a73-111">Die erste ist nicht die einfache Syntax, aber sie wird trotzdem häufig verwendet, da Sie bei Verwendung der Schlüsselwörter `struct` und `end` das `StructAttribute`-Attribut auslassen können, das in der zweiten Form angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b4a73-111">The first is not the lightweight syntax, but it is nevertheless frequently used because, when you use the `struct` and `end` keywords, you can omit the `StructAttribute` attribute, which appears in the second form.</span></span> <span data-ttu-id="b4a73-112">Sie können `StructAttribute` zu `Struct` abkürzen.</span><span class="sxs-lookup"><span data-stu-id="b4a73-112">You can abbreviate `StructAttribute` to just `Struct`.</span></span>

<span data-ttu-id="b4a73-113">Die *-Definition-Elemente-und-Typmember* in der vorherigen Syntax stellt Memberdeklarationen und-Definitionen.</span><span class="sxs-lookup"><span data-stu-id="b4a73-113">The *type-definition-elements-and-members* in the previous syntax represents member declarations and definitions.</span></span> <span data-ttu-id="b4a73-114">Strukturen können über Konstruktoren sowie änderbare und unveränderliche Felder verfügen, und sie können Member und Schnittstellenimplementierungen deklarieren.</span><span class="sxs-lookup"><span data-stu-id="b4a73-114">Structures can have constructors and mutable and immutable fields, and they can declare members and interface implementations.</span></span> <span data-ttu-id="b4a73-115">Weitere Informationen finden Sie unter [Elemente](members/index.md).</span><span class="sxs-lookup"><span data-stu-id="b4a73-115">For more information, see [Members](members/index.md).</span></span>

<span data-ttu-id="b4a73-116">Strukturen können nicht an der Vererbung beteiligt sein, sie können keine `let`- oder `do`-Bindungen enthalten und können nicht rekursiv Felder des eigenen Typs enthalten (obwohl sie Verweiszellen enthalten können, die auf den eigenen Typ verweisen).</span><span class="sxs-lookup"><span data-stu-id="b4a73-116">Structures cannot participate in inheritance, cannot contain `let` or `do` bindings, and cannot recursively contain fields of their own type (although they can contain reference cells that reference their own type).</span></span>

<span data-ttu-id="b4a73-117">Da Strukturen keine `let`-Bindungen zulassen, müssen Sie Felder in Strukturen mit dem `val`-Schlüsselwort deklarieren.</span><span class="sxs-lookup"><span data-stu-id="b4a73-117">Because structures do not allow `let` bindings, you must declare fields in structures by using the `val` keyword.</span></span> <span data-ttu-id="b4a73-118">Das `val`-Schlüsselwort definiert ein Feld und den Typ, es lässt jedoch keine Initialisierung zu.</span><span class="sxs-lookup"><span data-stu-id="b4a73-118">The `val` keyword defines a field and its type but does not allow initialization.</span></span> <span data-ttu-id="b4a73-119">In diesem Fall werden `val`-Deklarationen mit 0 oder null initialisiert.</span><span class="sxs-lookup"><span data-stu-id="b4a73-119">Instead, `val` declarations are initialized to zero or null.</span></span> <span data-ttu-id="b4a73-120">Aus diesem Grund erfordern Strukturen, die über einen impliziten Konstruktor verfügen (d. h. Parameter, die direkt nach dem Strukturnamen in der Deklaration angegeben werden), dass `val`-Deklarationen mit dem `DefaultValue`-Attribut gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="b4a73-120">For this reason, structures that have an implicit constructor (that is, parameters that are given immediately after the structure name in the declaration) require that `val` declarations be annotated with the `DefaultValue` attribute.</span></span> <span data-ttu-id="b4a73-121">Strukturen, die über einen definierten Konstruktor verfügen, unterstützen weiterhin die Initialisierung mit 0 (null).</span><span class="sxs-lookup"><span data-stu-id="b4a73-121">Structures that have a defined constructor still support zero-initialization.</span></span> <span data-ttu-id="b4a73-122">Aus diesem Grund ist das `DefaultValue`-Attribut eine Deklaration, dass der Wert 0 (Null) für das Feld gültig ist.</span><span class="sxs-lookup"><span data-stu-id="b4a73-122">Therefore, the `DefaultValue` attribute is a declaration that such a zero value is valid for the field.</span></span> <span data-ttu-id="b4a73-123">Implizite Konstruktoren für Strukturen führen keine Aktionen aus, da `let`- und `do`-Bindungen für den Typ nicht zulässig sind, aber die übergebenen impliziten Konstruktorparameterwerte sind als private Felder verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b4a73-123">Implicit constructors for structures do not perform any actions because `let` and `do` bindings aren’t allowed on the type, but the implicit constructor parameter values passed in are available as private fields.</span></span>

<span data-ttu-id="b4a73-124">Explizite Konstruktoren können eine Initialisierung von Feldwerten beinhalten.</span><span class="sxs-lookup"><span data-stu-id="b4a73-124">Explicit constructors might involve initialization of field values.</span></span> <span data-ttu-id="b4a73-125">Wenn Sie eine Struktur mit einem expliziten Konstruktor haben, unterstützt sie weiterhin die Initialisierung mit 0 (Null); Sie verwenden jedoch nicht das `DefaultValue`-Attribut auf den `val`-Deklarationen, da es mit dem expliziten Konstruktor in Konflikt steht.</span><span class="sxs-lookup"><span data-stu-id="b4a73-125">When you have a structure that has an explicit constructor, it still supports zero-initialization; however, you do not use the `DefaultValue` attribute on the `val` declarations because it conflicts with the explicit constructor.</span></span> <span data-ttu-id="b4a73-126">Weitere Informationen zu `val` Deklarationen finden Sie unter [explizite Felder: das `val` Schlüsselwort](members/explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="b4a73-126">For more information about `val` declarations, see [Explicit Fields: The `val` Keyword](members/explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="b4a73-127">Attribute und Zugriffsmodifizierer sind für Strukturen zulässig und folgen denselben Regeln wie jene für andere Typen.</span><span class="sxs-lookup"><span data-stu-id="b4a73-127">Attributes and accessibility modifiers are allowed on structures, and follow the same rules as those for other types.</span></span> <span data-ttu-id="b4a73-128">Weitere Informationen finden Sie unter [Attribute](attributes.md) und [Access Control](access-control.md).</span><span class="sxs-lookup"><span data-stu-id="b4a73-128">For more information, see [Attributes](attributes.md) and [Access Control](access-control.md).</span></span>

<span data-ttu-id="b4a73-129">Die folgenden Codebeispiele veranschaulichen Strukturdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="b4a73-129">The following code examples illustrate structure definitions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2501.fs)]

## <a name="struct-records-and-discriminated-unions"></a><span data-ttu-id="b4a73-130">Struct-Datensätze und Unterscheidungs-Unions</span><span class="sxs-lookup"><span data-stu-id="b4a73-130">Struct Records and Discriminated Unions</span></span>

<span data-ttu-id="b4a73-131">Ab f# 4.1, Sie können darstellen [Datensätze](records.md) und [Unterscheidungs-Unions](discriminated-unions.md) als Strukturen mit dem `[<Struct>]` Attribut.</span><span class="sxs-lookup"><span data-stu-id="b4a73-131">Starting with F# 4.1, you can represent [Records](records.md) and [Discriminated Unions](discriminated-unions.md) as structs with the `[<Struct>]` attribute.</span></span>  <span data-ttu-id="b4a73-132">Finden Sie unter jeder Artikel, um mehr zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="b4a73-132">See each article to learn more.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b4a73-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4a73-133">See Also</span></span>
[<span data-ttu-id="b4a73-134">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="b4a73-134">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="b4a73-135">Klassen</span><span class="sxs-lookup"><span data-stu-id="b4a73-135">Classes</span></span>](classes.md)

[<span data-ttu-id="b4a73-136">Datensätze</span><span class="sxs-lookup"><span data-stu-id="b4a73-136">Records</span></span>](records.md)

[<span data-ttu-id="b4a73-137">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="b4a73-137">Members</span></span>](members/index.md)
