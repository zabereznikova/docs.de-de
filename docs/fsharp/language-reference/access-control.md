---
title: Zugriffssteuerung
description: Informationen Sie zum Steuern des Zugriffs auf Programmierelemente wie Typen, Methoden und Funktionen, die in der Programmiersprache F#.
ms.date: 05/16/2016
ms.openlocfilehash: ed77a09cf87aabf9a4134276e89e84aa42abd3c3
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629960"
---
# <a name="access-control"></a><span data-ttu-id="3487e-103">Zugriffssteuerung</span><span class="sxs-lookup"><span data-stu-id="3487e-103">Access Control</span></span>

<span data-ttu-id="3487e-104">*Access Control* bezieht sich auf die Deklaration, welche Clients bestimmte Programmelemente verwenden können, z. b. Typen, Methoden und Funktionen.</span><span class="sxs-lookup"><span data-stu-id="3487e-104">*Access control* refers to declaring which clients can use certain program elements, such as types, methods, and functions.</span></span>

## <a name="basics-of-access-control"></a><span data-ttu-id="3487e-105">Grundlagen von Access Control</span><span class="sxs-lookup"><span data-stu-id="3487e-105">Basics of Access Control</span></span>

<span data-ttu-id="3487e-106">In F#, Steuern der Zugriff Spezifizierer `public`, `internal`, und `private` kann auf Module, Typen, Methoden, wertedefinitionen, Funktionen, Eigenschaften und explizite Felder angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="3487e-106">In F#, the access control specifiers `public`, `internal`, and `private` can be applied to modules, types, methods, value definitions, functions, properties, and explicit fields.</span></span>

- <span data-ttu-id="3487e-107">`public`Gibt an, dass alle Aufrufer auf die Entität zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="3487e-107">`public` indicates that the entity can be accessed by all callers.</span></span>

- <span data-ttu-id="3487e-108">`internal`Gibt an, dass auf die Entität nur aus derselben Assembly zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="3487e-108">`internal` indicates that the entity can be accessed only from the same assembly.</span></span>

- <span data-ttu-id="3487e-109">`private`Gibt an, dass nur vom einschließenden Typ oder Modul auf die Entität zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="3487e-109">`private` indicates that the entity can be accessed only from the enclosing type or module.</span></span>

> [!NOTE]
> <span data-ttu-id="3487e-110">Der Zugriffsspezifizierer `protected` wird nicht in F# verwendet, obwohl es akzeptabel ist, bei Verwendung von Typen, die in Sprachen, unterstützen erstellte `protected` Zugriff.</span><span class="sxs-lookup"><span data-stu-id="3487e-110">The access specifier `protected` is not used in F#, although it is acceptable if you are using types authored in languages that do support `protected` access.</span></span> <span data-ttu-id="3487e-111">Wenn Sie also eine geschützte Methode überschreiben, bleibt die Methode nur innerhalb der Klasse und der untergeordneten Elemente zugänglich.</span><span class="sxs-lookup"><span data-stu-id="3487e-111">Therefore, if you override a protected method, your method remains accessible only within the class and its descendents.</span></span>

<span data-ttu-id="3487e-112">Im Allgemeinen wird der Spezifizierer vor dem Namen der Entität eingefügt, es sei denn, es `mutable` wird `inline` ein-oder-Spezifizierer verwendet, der nach dem zugriffssteuerungsspezifizierer angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3487e-112">In general, the specifier is put in front of the name of the entity, except when a `mutable` or `inline` specifier is used, which appear after the access control specifier.</span></span>

<span data-ttu-id="3487e-113">Wenn kein Zugriffsspezifizierer verwendet wird, `public`ist der Standard `let` Wert, mit Ausnahme von Bindungen in einem `private` Typ, bei denen es sich immer um den-Typ handelt.</span><span class="sxs-lookup"><span data-stu-id="3487e-113">If no access specifier is used, the default is `public`, except for `let` bindings in a type, which are always `private` to the type.</span></span>

<span data-ttu-id="3487e-114">Signaturen in F#-Geben Sie einen anderen Mechanismus zur Steuerung des Zugriffs auf Programmelemente in F#.</span><span class="sxs-lookup"><span data-stu-id="3487e-114">Signatures in F# provide another mechanism for controlling access to F# program elements.</span></span> <span data-ttu-id="3487e-115">Signaturen sind für die Zugriffs Steuerung nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3487e-115">Signatures are not required for access control.</span></span> <span data-ttu-id="3487e-116">Weitere Informationen finden Sie unter [Signaturen](signatures.md).</span><span class="sxs-lookup"><span data-stu-id="3487e-116">For more information, see [Signatures](signatures.md).</span></span>

## <a name="rules-for-access-control"></a><span data-ttu-id="3487e-117">Regeln für Access Control</span><span class="sxs-lookup"><span data-stu-id="3487e-117">Rules for Access Control</span></span>

<span data-ttu-id="3487e-118">Die Zugriffs Steuerung unterliegt den folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="3487e-118">Access control is subject to the following rules:</span></span>

- <span data-ttu-id="3487e-119">Vererbungs Deklarationen (d. h. `inherit` die Verwendung von, um eine Basisklasse für eine Klasse anzugeben), Schnittstellen Deklarationen (d. h. die Angabe, dass eine Klasse eine Schnittstelle implementiert) und abstrakte Member haben immer die gleiche Barrierefreiheit wie der einschließende Typ.</span><span class="sxs-lookup"><span data-stu-id="3487e-119">Inheritance declarations (that is, the use of `inherit` to specify a base class for a class), interface declarations (that is, specifying that a class implements an interface), and abstract members always have the same accessibility as the enclosing type.</span></span> <span data-ttu-id="3487e-120">Daher kann kein zugriffssteuerungsspezifizierer für diese Konstrukte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3487e-120">Therefore, an access control specifier cannot be used on these constructs.</span></span>

- <span data-ttu-id="3487e-121">Barrierefreiheit für einzelne Fälle in einer Unterscheidungs-Union wird durch den Zugriff auf die Unterscheidungs-Union selbst festgelegt.</span><span class="sxs-lookup"><span data-stu-id="3487e-121">Accessibility for individual cases in a discriminated union is determined by the accessibility of the discriminated union itself.</span></span> <span data-ttu-id="3487e-122">Das heißt, dass ein bestimmter Union-Fall nicht weniger zugreifbar ist als die Union selbst.</span><span class="sxs-lookup"><span data-stu-id="3487e-122">That is, a particular union case is no less accessible than the union itself.</span></span>

- <span data-ttu-id="3487e-123">Der Zugriff auf einzelne Felder eines Daten Satz Typs kann nicht durch die Barrierefreiheit des Datensatzes bestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="3487e-123">Accessibility for individual fields of a record type cannot is determined by the accessibility of the record itself.</span></span> <span data-ttu-id="3487e-124">Das heißt, eine bestimmte Daten Satz Bezeichnung ist nicht weniger zugreifbar als der Datensatz selbst.</span><span class="sxs-lookup"><span data-stu-id="3487e-124">That is, a particular record label is no less accessible than the record itself.</span></span>

## <a name="example"></a><span data-ttu-id="3487e-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3487e-125">Example</span></span>

<span data-ttu-id="3487e-126">Der folgende Code veranschaulicht die Verwendung von zugriffssteuerungsorbezeichgern.</span><span class="sxs-lookup"><span data-stu-id="3487e-126">The following code illustrates the use of access control specifiers.</span></span> <span data-ttu-id="3487e-127">Das Projekt enthält zwei Dateien, `Module1.fs` und. `Module2.fs`</span><span class="sxs-lookup"><span data-stu-id="3487e-127">There are two files in the project, `Module1.fs` and `Module2.fs`.</span></span> <span data-ttu-id="3487e-128">Jede Datei ist implizit ein Modul.</span><span class="sxs-lookup"><span data-stu-id="3487e-128">Each file is implicitly a module.</span></span> <span data-ttu-id="3487e-129">Daher gibt es zwei Module: `Module1` und. `Module2`</span><span class="sxs-lookup"><span data-stu-id="3487e-129">Therefore, there are two modules, `Module1` and `Module2`.</span></span> <span data-ttu-id="3487e-130">In `Module1`werden ein privater Typ und ein interner Typ definiert.</span><span class="sxs-lookup"><span data-stu-id="3487e-130">A private type and an internal type are defined in `Module1`.</span></span> <span data-ttu-id="3487e-131">Der Zugriff `Module2`auf den privaten Typ ist nicht möglich, aber der interne Typ ist möglich.</span><span class="sxs-lookup"><span data-stu-id="3487e-131">The private type cannot be accessed from `Module2`, but the internal type can.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/access-control/snippet1.fs)]

<span data-ttu-id="3487e-132">Mit dem folgenden Code wird der Zugriff auf die Typen getestet `Module1.fs`, die in erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="3487e-132">The following code tests the accessibility of the types created in `Module1.fs`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/access-control/snippet2.fs)]

## <a name="see-also"></a><span data-ttu-id="3487e-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3487e-133">See also</span></span>

- [<span data-ttu-id="3487e-134">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="3487e-134">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="3487e-135">Signaturen</span><span class="sxs-lookup"><span data-stu-id="3487e-135">Signatures</span></span>](signatures.md)
