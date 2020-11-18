---
title: Namen von Typmembern
description: Erfahren Sie mehr über die Richtlinien für die Benennung von Typmembern in .net, z. b. Methoden, Eigenschaften, Ereignisse und Felder.
ms.date: 10/22/2008
helpviewer_keywords:
- events [.NET Framework], names
- methods [.NET Framework], names
- type members
- properties [.NET Framework], names
- fields, names
- field names
- names [.NET Framework], type members
- members [.NET Framework], type
ms.assetid: af5a0903-36af-4c2a-b848-cf959affeaa5
ms.openlocfilehash: 85f3137b4a8d75de92b12d6535415743395db890
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94820912"
---
# <a name="names-of-type-members"></a><span data-ttu-id="10e0f-103">Namen von Typmembern</span><span class="sxs-lookup"><span data-stu-id="10e0f-103">Names of Type Members</span></span>
<span data-ttu-id="10e0f-104">Typen bestehen aus Membern: Methoden, Eigenschaften, Ereignisse, Konstruktoren und Felder.</span><span class="sxs-lookup"><span data-stu-id="10e0f-104">Types are made of members: methods, properties, events, constructors, and fields.</span></span> <span data-ttu-id="10e0f-105">In den folgenden Abschnitten werden die Richtlinien zum Benennen von Typmembern beschrieben.</span><span class="sxs-lookup"><span data-stu-id="10e0f-105">The following sections describe guidelines for naming type members.</span></span>

## <a name="names-of-methods"></a><span data-ttu-id="10e0f-106">Namen von Methoden</span><span class="sxs-lookup"><span data-stu-id="10e0f-106">Names of Methods</span></span>
 <span data-ttu-id="10e0f-107">Da Methoden das Ausführen von Aktionen ermöglichen, erfordern die Entwurfsrichtlinien, dass Methodennamen Verben oder Verbalphrasen sind.</span><span class="sxs-lookup"><span data-stu-id="10e0f-107">Because methods are the means of taking action, the design guidelines require that method names be verbs or verb phrases.</span></span> <span data-ttu-id="10e0f-108">Mit dieser Richtlinie ist es auch möglich, Methodennamen von Eigenschafts- und Typnamen zu unterscheiden, die Nominal- oder Adjektivphrasen sind.</span><span class="sxs-lookup"><span data-stu-id="10e0f-108">Following this guideline also serves to distinguish method names from property and type names, which are noun or adjective phrases.</span></span>

 <span data-ttu-id="10e0f-109">✔️ Methodennamen, bei denen es sich um Verben oder Verb Ausdrücke handelt.</span><span class="sxs-lookup"><span data-stu-id="10e0f-109">✔️ DO give methods names that are verbs or verb phrases.</span></span>

```csharp
public class String {
    public int CompareTo(...);
    public string[] Split(...);
    public string Trim();
}
```

## <a name="names-of-properties"></a><span data-ttu-id="10e0f-110">Namen von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="10e0f-110">Names of Properties</span></span>
 <span data-ttu-id="10e0f-111">Anders als bei anderen Membern sollten Sie Eigenschaften einen Namen geben, der eine Nominal- oder Adjektivphrase ist.</span><span class="sxs-lookup"><span data-stu-id="10e0f-111">Unlike other members, properties should be given noun phrase or adjective names.</span></span> <span data-ttu-id="10e0f-112">Der Grund dafür ist, dass sich eine Eigenschaft auf Daten bezieht, und der Name der Eigenschaft dies widerspiegelt.</span><span class="sxs-lookup"><span data-stu-id="10e0f-112">That is because a property refers to data, and the name of the property reflects that.</span></span> <span data-ttu-id="10e0f-113">Eigenschaftennamen werden immer in Pascal-Schreibweise geschrieben.</span><span class="sxs-lookup"><span data-stu-id="10e0f-113">PascalCasing is always used for property names.</span></span>

 <span data-ttu-id="10e0f-114">✔️ Sie namens Eigenschaften mit einem Substantiv, nominalen Ausdruck oder Adjektiv.</span><span class="sxs-lookup"><span data-stu-id="10e0f-114">✔️ DO name properties using a noun, noun phrase, or adjective.</span></span>

 <span data-ttu-id="10e0f-115">❌ Verwenden Sie keine Eigenschaften, die mit dem Namen der Get-Methoden identisch sind, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="10e0f-115">❌ DO NOT have properties that match the name of "Get" methods as in the following example:</span></span>

 <span data-ttu-id="10e0f-116">`public string TextWriter { get {...} set {...} }` `public string GetTextWriter(int value) { ... }`</span><span class="sxs-lookup"><span data-stu-id="10e0f-116">`public string TextWriter { get {...} set {...} }` `public string GetTextWriter(int value) { ... }`</span></span>

 <span data-ttu-id="10e0f-117">Dieses Muster gibt normalerweise an, dass die Eigenschaft eigentlich eine Methode sein soll.</span><span class="sxs-lookup"><span data-stu-id="10e0f-117">This pattern typically indicates that the property should really be a method.</span></span>

 <span data-ttu-id="10e0f-118">✔️ namens Sammlungs Eigenschaften mit einem Plural Ausdruck, der die Elemente in der Auflistung beschreibt, anstatt einen Singular Ausdruck, gefolgt von "List" oder "Collection" zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="10e0f-118">✔️ DO name collection properties with a plural phrase describing the items in the collection instead of using a singular phrase followed by "List" or "Collection".</span></span>

 <span data-ttu-id="10e0f-119">✔️ die boolesche Eigenschaften mit einem positiven Ausdruck ( `CanSeek` anstelle von `CantSeek` ) benennen.</span><span class="sxs-lookup"><span data-stu-id="10e0f-119">✔️ DO name Boolean properties with an affirmative phrase (`CanSeek` instead of `CantSeek`).</span></span> <span data-ttu-id="10e0f-120">Optional können Sie auch boolesche Eigenschaften mit "is", "Can" oder "has" versehen, aber nur an der Stelle, an der der Wert hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="10e0f-120">Optionally, you can also prefix Boolean properties with "Is", "Can", or "Has", but only where it adds value.</span></span>

 <span data-ttu-id="10e0f-121">✔️ sollten Sie eine Eigenschaft mit dem gleichen Namen wie der Typ eingeben.</span><span class="sxs-lookup"><span data-stu-id="10e0f-121">✔️ CONSIDER giving a property the same name as its type.</span></span>

 <span data-ttu-id="10e0f-122">Die folgende Eigenschaft ruft ordnungsgemäß einen Enumerationswert namens `Color` ab und legt ihn fest. Die Eigenschaft heißt also `Color`:</span><span class="sxs-lookup"><span data-stu-id="10e0f-122">For example, the following property correctly gets and sets an enum value named `Color`, so the property is named `Color`:</span></span>

```csharp
public enum Color {...}
public class Control {
    public Color Color { get {...} set {...} }
}
```

## <a name="names-of-events"></a><span data-ttu-id="10e0f-123">Namen von Ereignissen</span><span class="sxs-lookup"><span data-stu-id="10e0f-123">Names of Events</span></span>
 <span data-ttu-id="10e0f-124">Ereignisse beziehen sich immer auf Aktionen, also entweder auf eine Aktion, die gerade passiert oder eine, die in der Vergangenheit liegt.</span><span class="sxs-lookup"><span data-stu-id="10e0f-124">Events always refer to some action, either one that is happening or one that has occurred.</span></span> <span data-ttu-id="10e0f-125">Deshalb werden Ereignisse mit Verben benannt (wie Methoden auch), und die Verbkonjugation wird genutzt, um den Zeitpunkt anzugeben, wann das Ereignis ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="10e0f-125">Therefore, as with methods, events are named with verbs, and verb tense is used to indicate the time when the event is raised.</span></span>

 <span data-ttu-id="10e0f-126">✔️ Ereignisse mit einem Verb oder einem Verb Ausdruck zu benennen.</span><span class="sxs-lookup"><span data-stu-id="10e0f-126">✔️ DO name events with a verb or a verb phrase.</span></span>

 <span data-ttu-id="10e0f-127">Beispiele dafür sind `Clicked`, `Painting`, `DroppedDown` usw.</span><span class="sxs-lookup"><span data-stu-id="10e0f-127">Examples include `Clicked`, `Painting`, `DroppedDown`, and so on.</span></span>

 <span data-ttu-id="10e0f-128">✔️ die Namen von Ereignissen mit einem Konzept von before und After zu versehen, wobei die vorhandenen und vergangenen Mandanten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="10e0f-128">✔️ DO give events names with a concept of before and after, using the present and past tenses.</span></span>

 <span data-ttu-id="10e0f-129">Beispielsweise wird ein Schließereignis, das ausgelöst wird, bevor ein Fenster geschlossen wird, als `Closing` bezeichnet. Ein Ereignis, das nach dem Schließen des Fensters ausgelöst wird, wird als `Closed` bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="10e0f-129">For example, a close event that is raised before a window is closed would be called `Closing`, and one that is raised after the window is closed would be called `Closed`.</span></span>

 <span data-ttu-id="10e0f-130">❌ Verwenden Sie nicht die Präfixe "Before" oder "After" oder postfixes, um Pre-und Post-Ereignisse anzugeben.</span><span class="sxs-lookup"><span data-stu-id="10e0f-130">❌ DO NOT use "Before" or "After" prefixes or postfixes to indicate pre- and post-events.</span></span> <span data-ttu-id="10e0f-131">Verwenden Sie wie oben beschrieben die Gegenwarts- und Vergangenheitsformen.</span><span class="sxs-lookup"><span data-stu-id="10e0f-131">Use present and past tenses as just described.</span></span>

 <span data-ttu-id="10e0f-132">✔️ Do-Ereignishandler (Delegaten, die als Typen von Ereignissen verwendet werden) mit dem Suffix "EventHandler", wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="10e0f-132">✔️ DO name event handlers (delegates used as types of events) with the "EventHandler" suffix, as shown in the following example:</span></span>

 `public delegate void ClickedEventHandler(object sender, ClickedEventArgs e);`

 <span data-ttu-id="10e0f-133">in ✔️ werden zwei Parameter mit dem Namen `sender` und `e` in Ereignis Handlern verwendet.</span><span class="sxs-lookup"><span data-stu-id="10e0f-133">✔️ DO use two parameters named `sender` and `e` in event handlers.</span></span>

 <span data-ttu-id="10e0f-134">Der sender-Parameter stellt das Objekt dar, das das Ereignis ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="10e0f-134">The sender parameter represents the object that raised the event.</span></span> <span data-ttu-id="10e0f-135">Der sender-Parameter ist in der Regel vom Typ `object`, auch wenn es möglich ist, einen spezifischeren Typ zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="10e0f-135">The sender parameter is typically of type `object`, even if it is possible to employ a more specific type.</span></span>

 <span data-ttu-id="10e0f-136">✔️ Do Event Argument-Klassen mit dem Suffix "EventArgs".</span><span class="sxs-lookup"><span data-stu-id="10e0f-136">✔️ DO name event argument classes with the "EventArgs" suffix.</span></span>

## <a name="names-of-fields"></a><span data-ttu-id="10e0f-137">Feldnamen</span><span class="sxs-lookup"><span data-stu-id="10e0f-137">Names of Fields</span></span>
 <span data-ttu-id="10e0f-138">Die Richtlinien für die Benennung von Feldern gelten für statische öffentliche und geschützte Felder.</span><span class="sxs-lookup"><span data-stu-id="10e0f-138">The field-naming guidelines apply to static public and protected fields.</span></span> <span data-ttu-id="10e0f-139">Interne und private Felder sind nicht Gegenstand von Richtlinien, und öffentliche oder geschützte Instanzfelder sind laut den [Entwurfsrichtlinien für Member](member.md) nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="10e0f-139">Internal and private fields are not covered by guidelines, and public or protected instance fields are not allowed by the [member design guidelines](member.md).</span></span>

 <span data-ttu-id="10e0f-140">✔️ Verwenden Sie die pascalschreibweise in Feldnamen.</span><span class="sxs-lookup"><span data-stu-id="10e0f-140">✔️ DO use PascalCasing in field names.</span></span>

 <span data-ttu-id="10e0f-141">✔️ Felder mit einem Substantiv, Substantiv Ausdruck oder Adjektiv benennen.</span><span class="sxs-lookup"><span data-stu-id="10e0f-141">✔️ DO name fields using a noun, noun phrase, or adjective.</span></span>

 <span data-ttu-id="10e0f-142">❌ Verwenden Sie kein Präfix für Feldnamen.</span><span class="sxs-lookup"><span data-stu-id="10e0f-142">❌ DO NOT use a prefix for field names.</span></span>

 <span data-ttu-id="10e0f-143">Verwenden Sie beispielsweise nicht „g_“ oder „s_“, um statische Felder anzugeben.</span><span class="sxs-lookup"><span data-stu-id="10e0f-143">For example, do not use "g_" or "s_" to indicate static fields.</span></span>

 <span data-ttu-id="10e0f-144">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="10e0f-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="10e0f-145">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="10e0f-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="10e0f-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10e0f-146">See also</span></span>

- [<span data-ttu-id="10e0f-147">Framework-Entwurfs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="10e0f-147">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="10e0f-148">Benennungs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="10e0f-148">Naming Guidelines</span></span>](naming-guidelines.md)
