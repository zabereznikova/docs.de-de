---
title: Member (F#)
description: Erfahren Sie Member des Objekts in der Programmiersprache f#.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: a37f14d138cc017cf78e3a0ff1d5b5bba2f09020
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="members"></a><span data-ttu-id="654e8-103">Member</span><span class="sxs-lookup"><span data-stu-id="654e8-103">Members</span></span>

<span data-ttu-id="654e8-104">Dieser Abschnitt beschreibt Member von F#-Objekttypen.</span><span class="sxs-lookup"><span data-stu-id="654e8-104">This section describes members of F# object types.</span></span>


## <a name="remarks"></a><span data-ttu-id="654e8-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="654e8-105">Remarks</span></span>
<span data-ttu-id="654e8-106">*Member* sind Funktionen, die Teil einer Typdefinition sind und mit dem Schlüsselwort `member` deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="654e8-106">*Members* are features that are part of a type definition and are declared with the `member` keyword.</span></span> <span data-ttu-id="654e8-107">F#-Objekttypen, z.B. Datensätze, Klassen, Unterscheidbare Unions, Schnittstellen und Strukturen,Klasse, unterstützen Elemente.</span><span class="sxs-lookup"><span data-stu-id="654e8-107">F# object types such as records, classes, discriminated unions, interfaces, and structures support members.</span></span> <span data-ttu-id="654e8-108">Weitere Informationen finden Sie unter [Datensätze](../records.md), [Klassen](../classes.md), [Unterscheidungs-Unions](../discriminated-Unions.md), [Schnittstellen](../interfaces.md) und [Strukturen](../structures.md).</span><span class="sxs-lookup"><span data-stu-id="654e8-108">For more information, see [Records](../records.md), [Classes](../classes.md), [Discriminated Unions](../discriminated-Unions.md), [Interfaces](../interfaces.md), and [Structures](../structures.md).</span></span>

<span data-ttu-id="654e8-109">Elemente bilden in der Regel die öffentliche Schnittstelle für einen Typ, weshalb diese öffentlich sind, sofern nicht anders angegeben.</span><span class="sxs-lookup"><span data-stu-id="654e8-109">Members typically make up the public interface for a type, which is why they are public unless otherwise specified.</span></span> <span data-ttu-id="654e8-110">Member können auch privat oder intern deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="654e8-110">Members can also be declared private or internal.</span></span> <span data-ttu-id="654e8-111">Weitere Informationen finden Sie unter [Zugriffssteuerung](../access-Control.md).</span><span class="sxs-lookup"><span data-stu-id="654e8-111">For more information, see [Access Control](../access-Control.md).</span></span> <span data-ttu-id="654e8-112">Signaturen für Typen können auch verwendet werden, um bestimmte Member eines Typs verfügbar bzw. nicht verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="654e8-112">Signatures for types can also be used to expose or not expose certain members of a type.</span></span> <span data-ttu-id="654e8-113">Weitere Informationen finden Sie unter [Signaturen](../signatures.md).</span><span class="sxs-lookup"><span data-stu-id="654e8-113">For more information, see [Signatures](../signatures.md).</span></span>

<span data-ttu-id="654e8-114">Private Felder und `do`-Bindungen, die nur mit Klassen verwendet werden, sind keine richtigen Member, da sie nicht teil der öffentlichen Schnittstelle eines Typs sind und nicht mit dem Schlüsselwort `member` deklariert sind. Sie werden jedoch auch in diesem Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="654e8-114">Private fields and `do` bindings, which are used only with classes, are not true members, because they are never part of the public interface of a type and are not declared with the `member` keyword, but they are described in this section also.</span></span>


## <a name="related-topics"></a><span data-ttu-id="654e8-115">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="654e8-115">Related Topics</span></span>


|<span data-ttu-id="654e8-116">Thema</span><span class="sxs-lookup"><span data-stu-id="654e8-116">Topic</span></span>|<span data-ttu-id="654e8-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="654e8-117">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="654e8-118">`let`-Bindungen in Klassen</span><span class="sxs-lookup"><span data-stu-id="654e8-118">`let` Bindings in Classes</span></span>](let-bindings-in-classes.md)|<span data-ttu-id="654e8-119">Beschreibt die Definition der privaten Felder und Funktionen in Klassen.</span><span class="sxs-lookup"><span data-stu-id="654e8-119">Describes the definition of private fields and functions in classes.</span></span>|
|[<span data-ttu-id="654e8-120">`do`-Bindungen in Klassen</span><span class="sxs-lookup"><span data-stu-id="654e8-120">`do` Bindings in Classes</span></span>](do-bindings-in-classes.md)|<span data-ttu-id="654e8-121">Beschreibt die Spezifikation des Initialisierungscodes für Objekte.</span><span class="sxs-lookup"><span data-stu-id="654e8-121">Describes the specification of object initialization code.</span></span>|
|[<span data-ttu-id="654e8-122">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="654e8-122">Properties</span></span>](properties.md)|<span data-ttu-id="654e8-123">Beschreibt Eigenschaftenmember in Klassen und anderen Typen.</span><span class="sxs-lookup"><span data-stu-id="654e8-123">Describes property members in classes and other types.</span></span>|
|[<span data-ttu-id="654e8-124">Indizierte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="654e8-124">Indexed Properties</span></span>](indexed-properties.md)|<span data-ttu-id="654e8-125">Beschreibt arrayähnliche Eigenschaften in Klassen und anderen Typen.</span><span class="sxs-lookup"><span data-stu-id="654e8-125">Describes array-like properties in classes and other types.</span></span>|
|[<span data-ttu-id="654e8-126">Methoden</span><span class="sxs-lookup"><span data-stu-id="654e8-126">Methods</span></span>](methods.md)|<span data-ttu-id="654e8-127">Beschreibt Funktionen, die Member eines Typs sind.</span><span class="sxs-lookup"><span data-stu-id="654e8-127">Describes functions that are members of a type.</span></span>|
|[<span data-ttu-id="654e8-128">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="654e8-128">Constructors</span></span>](constructors.md)|<span data-ttu-id="654e8-129">Beschreibt spezielle Funktionen, die Objekte eines Typs initialisieren.</span><span class="sxs-lookup"><span data-stu-id="654e8-129">Describes special functions that initialize objects of a type.</span></span>|
|[<span data-ttu-id="654e8-130">Operatorüberladung</span><span class="sxs-lookup"><span data-stu-id="654e8-130">Operator Overloading</span></span>](../operator-overloading.md)|<span data-ttu-id="654e8-131">Beschreibt die Definition benutzerdefinierter Operatoren für Typen.</span><span class="sxs-lookup"><span data-stu-id="654e8-131">Describes the definition of customized operators for types.</span></span>|
|[<span data-ttu-id="654e8-132">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="654e8-132">Events</span></span>](events.md)|<span data-ttu-id="654e8-133">Beschreibt die Definition von Ereignissen und Unterstützung für die Ereignisbehandlung in F#.</span><span class="sxs-lookup"><span data-stu-id="654e8-133">Describes the definition of events and event handling support in F#.</span></span>|
|[<span data-ttu-id="654e8-134">Explizite Felder: Das `val`-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="654e8-134">Explicit Fields: The `val` Keyword</span></span>](explicit-fields-the-val-keyword.md)|<span data-ttu-id="654e8-135">Beschreibt die Definition von nicht initialisierten Feldern in einem Typ.</span><span class="sxs-lookup"><span data-stu-id="654e8-135">Describes the definition of uninitialized fields in a type.</span></span>|
