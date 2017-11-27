---
title: Zugriffssteuerung (F#)
description: Informationen Sie zum Steuern des Zugriffs auf Programmierelemente wie Typen, Methoden und Funktionen, die in der Programmiersprache f#.
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 955b06fe-d1cd-431d-8db6-93e83b697453
ms.openlocfilehash: a02e20a585a0456577901f2762a0eeb0e3ecd2f0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="access-control"></a><span data-ttu-id="b3051-104">Zugriffssteuerung</span><span class="sxs-lookup"><span data-stu-id="b3051-104">Access Control</span></span>

<span data-ttu-id="b3051-105">*Steuerung des Zugriffs* bezieht sich auf deklarieren, welche Clients bestimmte Programmelemente, wie Typen, Methoden und Funktionen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="b3051-105">*Access control* refers to declaring which clients can use certain program elements, such as types, methods, and functions.</span></span>


## <a name="basics-of-access-control"></a><span data-ttu-id="b3051-106">Grundlagen der Zugriffssteuerung</span><span class="sxs-lookup"><span data-stu-id="b3051-106">Basics of Access Control</span></span>
<span data-ttu-id="b3051-107">In F# erläutert werden, die Zugriff steuern Spezifizierer `public`, `internal`, und `private` für Module, Typen, Methoden, Wertdefinitionen, Funktionen, Eigenschaften und explizite Felder angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="b3051-107">In F#, the access control specifiers `public`, `internal`, and `private` can be applied to modules, types, methods, value definitions, functions, properties, and explicit fields.</span></span>


- <span data-ttu-id="b3051-108">`public`Gibt an, dass die Entität, die von allen Aufrufern zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="b3051-108">`public` indicates that the entity can be accessed by all callers.</span></span>

- <span data-ttu-id="b3051-109">`internal`Gibt an, dass die Entität, die nur aus der gleichen Assembly zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="b3051-109">`internal` indicates that the entity can be accessed only from the same assembly.</span></span>

- <span data-ttu-id="b3051-110">`private`Gibt an, dass die Entität, die nur aus dem einschließenden Typ oder Modul zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="b3051-110">`private` indicates that the entity can be accessed only from the enclosing type or module.</span></span>


>[!NOTE] 
<span data-ttu-id="b3051-111">Der Zugriffsspezifizierer `protected` wird nicht in f# verwendet, obwohl es akzeptabel ist, bei Verwendung von Typen, die in Sprachen, unterstützen erstellte `protected` Zugriff.</span><span class="sxs-lookup"><span data-stu-id="b3051-111">The access specifier `protected` is not used in F#, although it is acceptable if you are using types authored in languages that do support `protected` access.</span></span> <span data-ttu-id="b3051-112">Wenn Sie eine geschützte Methode überschreiben, bleibt die Methode daher nur innerhalb der Klasse und die zugehörigen Nachfolgerelemente zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="b3051-112">Therefore, if you override a protected method, your method remains accessible only within the class and its descendents.</span></span>

<span data-ttu-id="b3051-113">Im Allgemeinen wird der Spezifizierer vor den Namen der Entität, außer wenn versetzt einen `mutable` oder `inline` Formatbezeichner verwendet, die nach dem Steuerelement Zugriffsspezifizierer angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b3051-113">In general, the specifier is put in front of the name of the entity, except when a `mutable` or `inline` specifier is used, which appear after the access control specifier.</span></span>

<span data-ttu-id="b3051-114">Wenn keine Zugriffsspezifizierer verwendet wird, ist die Standardeinstellung `public`, mit Ausnahme von `let` Bindungen, die in einem Typ immer sind `private` in den Typ.</span><span class="sxs-lookup"><span data-stu-id="b3051-114">If no access specifier is used, the default is `public`, except for `let` bindings in a type, which are always `private` to the type.</span></span>

<span data-ttu-id="b3051-115">Signaturen in F# erläutert werden. Geben Sie einen anderen Mechanismus zum Steuern des Zugriffs auf f#-Programmelementen.</span><span class="sxs-lookup"><span data-stu-id="b3051-115">Signatures in F# provide another mechanism for controlling access to F# program elements.</span></span> <span data-ttu-id="b3051-116">Signaturen sind nicht für die Zugriffssteuerung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b3051-116">Signatures are not required for access control.</span></span> <span data-ttu-id="b3051-117">Weitere Informationen finden Sie unter [Signaturen](signatures.md).</span><span class="sxs-lookup"><span data-stu-id="b3051-117">For more information, see [Signatures](signatures.md).</span></span>


## <a name="rules-for-access-control"></a><span data-ttu-id="b3051-118">Regeln für die Zugriffssteuerung</span><span class="sxs-lookup"><span data-stu-id="b3051-118">Rules for Access Control</span></span>
<span data-ttu-id="b3051-119">Die Zugriffssteuerung ist gemäß den folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="b3051-119">Access control is subject to the following rules:</span></span>


- <span data-ttu-id="b3051-120">Vererbungsdeklarationen (d. h. die Verwendung von `inherit` eine Basisklasse für eine Klasse angeben) Schnittstellendeklarationen (das ist, gibt an, dass eine Klasse eine Schnittstelle implementiert) und abstrakte Member verfügen immer über den gleichen Zugriff wie der einschließende Typ.</span><span class="sxs-lookup"><span data-stu-id="b3051-120">Inheritance declarations (that is, the use of `inherit` to specify a base class for a class), interface declarations (that is, specifying that a class implements an interface), and abstract members always have the same accessibility as the enclosing type.</span></span> <span data-ttu-id="b3051-121">Aus diesem Grund kann ein Steuerelement Zugriffsspezifizierer auf diese Konstrukte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b3051-121">Therefore, an access control specifier cannot be used on these constructs.</span></span>

- <span data-ttu-id="b3051-122">Einzelne Fälle, in eine Unterscheidungs-Union sind keine eigene Steuerelement-Zugriffsmodifizierer, die getrennt von den union-Typ.</span><span class="sxs-lookup"><span data-stu-id="b3051-122">Individual cases in a discriminated union cannot have their own access control modifiers separate from the union type.</span></span>

- <span data-ttu-id="b3051-123">Einzelne Felder eines Datensatztyps sind keine eigene Steuerelement-Zugriffsmodifizierer, die getrennt von den Datensatztyp.</span><span class="sxs-lookup"><span data-stu-id="b3051-123">Individual fields of a record type cannot have their own access control modifiers separate from the record type.</span></span>


## <a name="example"></a><span data-ttu-id="b3051-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b3051-124">Example</span></span>
<span data-ttu-id="b3051-125">Der folgende Code veranschaulicht die Verwendung der Zugriffsspezifizierer-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="b3051-125">The following code illustrates the use of access control specifiers.</span></span> <span data-ttu-id="b3051-126">Es gibt zwei Dateien im Projekt `Module1.fs` und `Module2.fs`.</span><span class="sxs-lookup"><span data-stu-id="b3051-126">There are two files in the project, `Module1.fs` and `Module2.fs`.</span></span> <span data-ttu-id="b3051-127">Jede Datei ist implizit ein Modul.</span><span class="sxs-lookup"><span data-stu-id="b3051-127">Each file is implicitly a module.</span></span> <span data-ttu-id="b3051-128">Aus diesem Grund sind die beiden Module `Module1` und `Module2`.</span><span class="sxs-lookup"><span data-stu-id="b3051-128">Therefore, there are two modules, `Module1` and `Module2`.</span></span> <span data-ttu-id="b3051-129">Einen privaten Typ und einen internen Typ sind in definiert `Module1`.</span><span class="sxs-lookup"><span data-stu-id="b3051-129">A private type and an internal type are defined in `Module1`.</span></span> <span data-ttu-id="b3051-130">Die private Typ kann nicht zugegriffen werden, aus `Module2`, aber Sie können der interne Typ.</span><span class="sxs-lookup"><span data-stu-id="b3051-130">The private type cannot be accessed from `Module2`, but the internal type can.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet1.fs)]
    
<span data-ttu-id="b3051-131">Der folgende Code überprüft, den Zugriff auf die Typen im erstellten `Module1.fs`.</span><span class="sxs-lookup"><span data-stu-id="b3051-131">The following code tests the accessibility of the types created in `Module1.fs`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet2.fs)]
    
## <a name="see-also"></a><span data-ttu-id="b3051-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3051-132">See Also</span></span>
[<span data-ttu-id="b3051-133">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="b3051-133">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="b3051-134">Signaturen</span><span class="sxs-lookup"><span data-stu-id="b3051-134">Signatures</span></span>](signatures.md)
