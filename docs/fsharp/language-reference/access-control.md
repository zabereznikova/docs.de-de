---
title: Zugriffssteuerung
description: Erfahren Sie, wie Sie den Zugriff auf Programmier Elemente (z. b. Typen, Methoden und Funktionen F# ) in der Programmiersprache steuern können.
ms.date: 05/16/2016
ms.openlocfilehash: fe204a883a440794fdd033c54d6d8d4fb68e0ce2
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73425109"
---
# <a name="access-control"></a><span data-ttu-id="bce60-103">Zugriffssteuerung</span><span class="sxs-lookup"><span data-stu-id="bce60-103">Access Control</span></span>

<span data-ttu-id="bce60-104">*Access Control* bezieht sich auf die Deklaration, welche Clients bestimmte Programmelemente verwenden können, z. b. Typen, Methoden und Funktionen.</span><span class="sxs-lookup"><span data-stu-id="bce60-104">*Access control* refers to declaring which clients can use certain program elements, such as types, methods, and functions.</span></span>

## <a name="basics-of-access-control"></a><span data-ttu-id="bce60-105">Grundlagen von Access Control</span><span class="sxs-lookup"><span data-stu-id="bce60-105">Basics of Access Control</span></span>

<span data-ttu-id="bce60-106">In F#können die zugriffssteuerungsspezifizierer `public`, `internal`und `private` auf Module, Typen, Methoden, Wert Definitionen, Funktionen, Eigenschaften und explizite Felder angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="bce60-106">In F#, the access control specifiers `public`, `internal`, and `private` can be applied to modules, types, methods, value definitions, functions, properties, and explicit fields.</span></span>

- <span data-ttu-id="bce60-107">`public` gibt an, dass alle Aufrufer auf die Entität zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="bce60-107">`public` indicates that the entity can be accessed by all callers.</span></span>

- <span data-ttu-id="bce60-108">`internal` gibt an, dass auf die Entität nur von derselben Assembly aus zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="bce60-108">`internal` indicates that the entity can be accessed only from the same assembly.</span></span>

- <span data-ttu-id="bce60-109">`private` gibt an, dass nur vom einschließenden Typ oder Modul auf die Entität zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="bce60-109">`private` indicates that the entity can be accessed only from the enclosing type or module.</span></span>

> [!NOTE]
> <span data-ttu-id="bce60-110">Der Zugriffsspezifizierer `protected` wird F#in nicht verwendet. es ist jedoch akzeptabel, wenn Sie Typen verwenden, die in Sprachen erstellt wurden, die `protected` Zugriff unterstützen.</span><span class="sxs-lookup"><span data-stu-id="bce60-110">The access specifier `protected` is not used in F#, although it is acceptable if you are using types authored in languages that do support `protected` access.</span></span> <span data-ttu-id="bce60-111">Wenn Sie also eine geschützte Methode überschreiben, bleibt die Methode nur innerhalb der Klasse und der untergeordneten Elemente zugänglich.</span><span class="sxs-lookup"><span data-stu-id="bce60-111">Therefore, if you override a protected method, your method remains accessible only within the class and its descendents.</span></span>

<span data-ttu-id="bce60-112">Im Allgemeinen wird der Spezifizierer vor dem Namen der Entität eingefügt, es sei denn, ein `mutable` oder `inline` Spezifizierer wird verwendet, die nach dem zugriffssteuerungsspezifizierer angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="bce60-112">In general, the specifier is put in front of the name of the entity, except when a `mutable` or `inline` specifier is used, which appear after the access control specifier.</span></span>

<span data-ttu-id="bce60-113">Wenn kein Zugriffsspezifizierer verwendet wird, wird der Standardwert `public`, mit Ausnahme von `let` Bindungen in einem Typ, die immer dem Typ `private`.</span><span class="sxs-lookup"><span data-stu-id="bce60-113">If no access specifier is used, the default is `public`, except for `let` bindings in a type, which are always `private` to the type.</span></span>

<span data-ttu-id="bce60-114">Signaturen in F# bieten einen weiteren Mechanismus zum Steuern des F# Zugriffs auf Programmelemente.</span><span class="sxs-lookup"><span data-stu-id="bce60-114">Signatures in F# provide another mechanism for controlling access to F# program elements.</span></span> <span data-ttu-id="bce60-115">Signaturen sind für die Zugriffs Steuerung nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="bce60-115">Signatures are not required for access control.</span></span> <span data-ttu-id="bce60-116">Weitere Informationen finden Sie unter [Signaturen](signature-files.md).</span><span class="sxs-lookup"><span data-stu-id="bce60-116">For more information, see [Signatures](signature-files.md).</span></span>

## <a name="rules-for-access-control"></a><span data-ttu-id="bce60-117">Regeln für Access Control</span><span class="sxs-lookup"><span data-stu-id="bce60-117">Rules for Access Control</span></span>

<span data-ttu-id="bce60-118">Die Zugriffs Steuerung unterliegt den folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="bce60-118">Access control is subject to the following rules:</span></span>

- <span data-ttu-id="bce60-119">Vererbungs Deklarationen (d. h. die Verwendung von `inherit`, um eine Basisklasse für eine Klasse anzugeben), Schnittstellen Deklarationen (d. h. die Angabe, dass eine Klasse eine Schnittstelle implementiert) und abstrakte Member haben immer denselben Zugriff wie der einschließende Typ.</span><span class="sxs-lookup"><span data-stu-id="bce60-119">Inheritance declarations (that is, the use of `inherit` to specify a base class for a class), interface declarations (that is, specifying that a class implements an interface), and abstract members always have the same accessibility as the enclosing type.</span></span> <span data-ttu-id="bce60-120">Daher kann kein zugriffssteuerungsspezifizierer für diese Konstrukte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bce60-120">Therefore, an access control specifier cannot be used on these constructs.</span></span>

- <span data-ttu-id="bce60-121">Barrierefreiheit für einzelne Fälle in einer Unterscheidungs-Union wird durch den Zugriff auf die Unterscheidungs-Union selbst festgelegt.</span><span class="sxs-lookup"><span data-stu-id="bce60-121">Accessibility for individual cases in a discriminated union is determined by the accessibility of the discriminated union itself.</span></span> <span data-ttu-id="bce60-122">Das heißt, dass ein bestimmter Union-Fall nicht weniger zugreifbar ist als die Union selbst.</span><span class="sxs-lookup"><span data-stu-id="bce60-122">That is, a particular union case is no less accessible than the union itself.</span></span>

- <span data-ttu-id="bce60-123">Der Zugriff auf einzelne Felder eines Daten Satz Typs wird durch die Barrierefreiheit des Datensatzes bestimmt.</span><span class="sxs-lookup"><span data-stu-id="bce60-123">Accessibility for individual fields of a record type is determined by the accessibility of the record itself.</span></span> <span data-ttu-id="bce60-124">Das heißt, eine bestimmte Daten Satz Bezeichnung ist nicht weniger zugreifbar als der Datensatz selbst.</span><span class="sxs-lookup"><span data-stu-id="bce60-124">That is, a particular record label is no less accessible than the record itself.</span></span>

## <a name="example"></a><span data-ttu-id="bce60-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bce60-125">Example</span></span>

<span data-ttu-id="bce60-126">Der folgende Code veranschaulicht die Verwendung von zugriffssteuerungsorbezeichgern.</span><span class="sxs-lookup"><span data-stu-id="bce60-126">The following code illustrates the use of access control specifiers.</span></span> <span data-ttu-id="bce60-127">Das Projekt enthält zwei Dateien `Module1.fs` und `Module2.fs`.</span><span class="sxs-lookup"><span data-stu-id="bce60-127">There are two files in the project, `Module1.fs` and `Module2.fs`.</span></span> <span data-ttu-id="bce60-128">Jede Datei ist implizit ein Modul.</span><span class="sxs-lookup"><span data-stu-id="bce60-128">Each file is implicitly a module.</span></span> <span data-ttu-id="bce60-129">Daher gibt es zwei Module: `Module1` und `Module2`.</span><span class="sxs-lookup"><span data-stu-id="bce60-129">Therefore, there are two modules, `Module1` and `Module2`.</span></span> <span data-ttu-id="bce60-130">In `Module1`werden ein privater Typ und ein interner Typ definiert.</span><span class="sxs-lookup"><span data-stu-id="bce60-130">A private type and an internal type are defined in `Module1`.</span></span> <span data-ttu-id="bce60-131">Der Zugriff auf den privaten Typ ist aus `Module2`nicht möglich, der interne Typ ist jedoch möglich.</span><span class="sxs-lookup"><span data-stu-id="bce60-131">The private type cannot be accessed from `Module2`, but the internal type can.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/access-control/snippet1.fs)]

<span data-ttu-id="bce60-132">Der folgende Code testet den Zugriff auf die Typen, die in `Module1.fs`erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="bce60-132">The following code tests the accessibility of the types created in `Module1.fs`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/access-control/snippet2.fs)]

## <a name="see-also"></a><span data-ttu-id="bce60-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bce60-133">See also</span></span>

- [<span data-ttu-id="bce60-134">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="bce60-134">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="bce60-135">Signaturen</span><span class="sxs-lookup"><span data-stu-id="bce60-135">Signatures</span></span>](signature-files.md)
