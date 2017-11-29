---
title: Member (F#)
description: Erfahren Sie Member des Objekts in der Programmiersprache f#.
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: e472f50a-4939-4e62-abbc-471f8f265790
ms.openlocfilehash: ca34c8d073594791ec268a85ad56f50cc6d9e435
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="members"></a><span data-ttu-id="1736e-104">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="1736e-104">Members</span></span>

<span data-ttu-id="1736e-105">Dieser Abschnitt beschreibt Member von F#-Objekttypen.</span><span class="sxs-lookup"><span data-stu-id="1736e-105">This section describes members of F# object types.</span></span>


## <a name="remarks"></a><span data-ttu-id="1736e-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1736e-106">Remarks</span></span>
<span data-ttu-id="1736e-107">*Member* sind Funktionen, die Teil einer Typdefinition sind und mit dem Schlüsselwort `member` deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="1736e-107">*Members* are features that are part of a type definition and are declared with the `member` keyword.</span></span> <span data-ttu-id="1736e-108">F#-Objekttypen, z.B. Datensätze, Klassen, Unterscheidbare Unions, Schnittstellen und Strukturen,Klasse, unterstützen Elemente.</span><span class="sxs-lookup"><span data-stu-id="1736e-108">F# object types such as records, classes, discriminated unions, interfaces, and structures support members.</span></span> <span data-ttu-id="1736e-109">Weitere Informationen finden Sie unter [Datensätze](../records.md), [Klassen](../classes.md), [Unterscheidungs-Unions](../discriminated-Unions.md), [Schnittstellen](../interfaces.md) und [Strukturen](../structures.md).</span><span class="sxs-lookup"><span data-stu-id="1736e-109">For more information, see [Records](../records.md), [Classes](../classes.md), [Discriminated Unions](../discriminated-Unions.md), [Interfaces](../interfaces.md), and [Structures](../structures.md).</span></span>

<span data-ttu-id="1736e-110">Elemente bilden in der Regel die öffentliche Schnittstelle für einen Typ, weshalb diese öffentlich sind, sofern nicht anders angegeben.</span><span class="sxs-lookup"><span data-stu-id="1736e-110">Members typically make up the public interface for a type, which is why they are public unless otherwise specified.</span></span> <span data-ttu-id="1736e-111">Member können auch privat oder intern deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="1736e-111">Members can also be declared private or internal.</span></span> <span data-ttu-id="1736e-112">Weitere Informationen finden Sie unter [Zugriffssteuerung](../access-Control.md).</span><span class="sxs-lookup"><span data-stu-id="1736e-112">For more information, see [Access Control](../access-Control.md).</span></span> <span data-ttu-id="1736e-113">Signaturen für Typen können auch verwendet werden, um bestimmte Member eines Typs verfügbar bzw. nicht verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="1736e-113">Signatures for types can also be used to expose or not expose certain members of a type.</span></span> <span data-ttu-id="1736e-114">Weitere Informationen finden Sie unter [Signaturen](../signatures.md).</span><span class="sxs-lookup"><span data-stu-id="1736e-114">For more information, see [Signatures](../signatures.md).</span></span>

<span data-ttu-id="1736e-115">Private Felder und `do`-Bindungen, die nur mit Klassen verwendet werden, sind keine richtigen Member, da sie nicht teil der öffentlichen Schnittstelle eines Typs sind und nicht mit dem Schlüsselwort `member` deklariert sind. Sie werden jedoch auch in diesem Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1736e-115">Private fields and `do` bindings, which are used only with classes, are not true members, because they are never part of the public interface of a type and are not declared with the `member` keyword, but they are described in this section also.</span></span>


## <a name="related-topics"></a><span data-ttu-id="1736e-116">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="1736e-116">Related Topics</span></span>


|<span data-ttu-id="1736e-117">Thema</span><span class="sxs-lookup"><span data-stu-id="1736e-117">Topic</span></span>|<span data-ttu-id="1736e-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1736e-118">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="1736e-119">`let`-Bindungen in Klassen</span><span class="sxs-lookup"><span data-stu-id="1736e-119">`let` Bindings in Classes</span></span>](let-bindings-in-classes.md)|<span data-ttu-id="1736e-120">Beschreibt die Definition der privaten Felder und Funktionen in Klassen.</span><span class="sxs-lookup"><span data-stu-id="1736e-120">Describes the definition of private fields and functions in classes.</span></span>|
|[<span data-ttu-id="1736e-121">`do`-Bindungen in Klassen</span><span class="sxs-lookup"><span data-stu-id="1736e-121">`do` Bindings in Classes</span></span>](do-bindings-in-classes.md)|<span data-ttu-id="1736e-122">Beschreibt die Spezifikation des Initialisierungscodes für Objekte.</span><span class="sxs-lookup"><span data-stu-id="1736e-122">Describes the specification of object initialization code.</span></span>|
|[<span data-ttu-id="1736e-123">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1736e-123">Properties</span></span>](properties.md)|<span data-ttu-id="1736e-124">Beschreibt Eigenschaftenmember in Klassen und anderen Typen.</span><span class="sxs-lookup"><span data-stu-id="1736e-124">Describes property members in classes and other types.</span></span>|
|[<span data-ttu-id="1736e-125">Indizierte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1736e-125">Indexed Properties</span></span>](indexed-properties.md)|<span data-ttu-id="1736e-126">Beschreibt arrayähnliche Eigenschaften in Klassen und anderen Typen.</span><span class="sxs-lookup"><span data-stu-id="1736e-126">Describes array-like properties in classes and other types.</span></span>|
|[<span data-ttu-id="1736e-127">Methoden</span><span class="sxs-lookup"><span data-stu-id="1736e-127">Methods</span></span>](methods.md)|<span data-ttu-id="1736e-128">Beschreibt Funktionen, die Member eines Typs sind.</span><span class="sxs-lookup"><span data-stu-id="1736e-128">Describes functions that are members of a type.</span></span>|
|[<span data-ttu-id="1736e-129">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="1736e-129">Constructors</span></span>](constructors.md)|<span data-ttu-id="1736e-130">Beschreibt spezielle Funktionen, die Objekte eines Typs initialisieren.</span><span class="sxs-lookup"><span data-stu-id="1736e-130">Describes special functions that initialize objects of a type.</span></span>|
|[<span data-ttu-id="1736e-131">Operatorüberladung</span><span class="sxs-lookup"><span data-stu-id="1736e-131">Operator Overloading</span></span>](../operator-overloading.md)|<span data-ttu-id="1736e-132">Beschreibt die Definition benutzerdefinierter Operatoren für Typen.</span><span class="sxs-lookup"><span data-stu-id="1736e-132">Describes the definition of customized operators for types.</span></span>|
|[<span data-ttu-id="1736e-133">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="1736e-133">Events</span></span>](events.md)|<span data-ttu-id="1736e-134">Beschreibt die Definition von Ereignissen und Unterstützung für die Ereignisbehandlung in F#.</span><span class="sxs-lookup"><span data-stu-id="1736e-134">Describes the definition of events and event handling support in F#.</span></span>|
|[<span data-ttu-id="1736e-135">Explizite Felder: Das `val`-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="1736e-135">Explicit Fields: The `val` Keyword</span></span>](explicit-fields-the-val-keyword.md)|<span data-ttu-id="1736e-136">Beschreibt die Definition von nicht initialisierten Feldern in einem Typ.</span><span class="sxs-lookup"><span data-stu-id="1736e-136">Describes the definition of uninitialized fields in a type.</span></span>|
