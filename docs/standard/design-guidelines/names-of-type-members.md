---
title: Namen von Typmembern
ms.date: 10/22/2008
ms.technology: dotnet-standard
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
ms.openlocfilehash: 81c837bd045992043208a59f6ee16803c1d6eb3c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744176"
---
# <a name="names-of-type-members"></a><span data-ttu-id="04b04-102">Namen von Typmembern</span><span class="sxs-lookup"><span data-stu-id="04b04-102">Names of Type Members</span></span>
<span data-ttu-id="04b04-103">Typen bestehen aus Membern: Methoden, Eigenschaften, Ereignisse, Konstruktoren und Felder.</span><span class="sxs-lookup"><span data-stu-id="04b04-103">Types are made of members: methods, properties, events, constructors, and fields.</span></span> <span data-ttu-id="04b04-104">In den folgenden Abschnitten werden die Richtlinien zum Benennen von Typmembern beschrieben.</span><span class="sxs-lookup"><span data-stu-id="04b04-104">The following sections describe guidelines for naming type members.</span></span>

## <a name="names-of-methods"></a><span data-ttu-id="04b04-105">Namen von Methoden</span><span class="sxs-lookup"><span data-stu-id="04b04-105">Names of Methods</span></span>
 <span data-ttu-id="04b04-106">Da Methoden das Ausführen von Aktionen ermöglichen, erfordern die Entwurfsrichtlinien, dass Methodennamen Verben oder Verbalphrasen sind.</span><span class="sxs-lookup"><span data-stu-id="04b04-106">Because methods are the means of taking action, the design guidelines require that method names be verbs or verb phrases.</span></span> <span data-ttu-id="04b04-107">Mit dieser Richtlinie ist es auch möglich, Methodennamen von Eigenschafts- und Typnamen zu unterscheiden, die Nominal- oder Adjektivphrasen sind.</span><span class="sxs-lookup"><span data-stu-id="04b04-107">Following this guideline also serves to distinguish method names from property and type names, which are noun or adjective phrases.</span></span>

 <span data-ttu-id="04b04-108">✔️ Methodennamen, bei denen es sich um Verben oder Verb Ausdrücke handelt.</span><span class="sxs-lookup"><span data-stu-id="04b04-108">✔️ DO give methods names that are verbs or verb phrases.</span></span>

```csharp
public class String {
    public int CompareTo(...);
    public string[] Split(...);
    public string Trim();
}
```

## <a name="names-of-properties"></a><span data-ttu-id="04b04-109">Namen von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="04b04-109">Names of Properties</span></span>
 <span data-ttu-id="04b04-110">Anders als andere Member sollten Eigenschaften mit Substantivphrasen oder Adjektivnamen benannt werden.</span><span class="sxs-lookup"><span data-stu-id="04b04-110">Unlike other members, properties should be given noun phrase or adjective names.</span></span> <span data-ttu-id="04b04-111">Das liegt daran, dass eine Eigenschaft auf Daten verweist, und der Name der Eigenschaft gibt dies wieder.</span><span class="sxs-lookup"><span data-stu-id="04b04-111">That is because a property refers to data, and the name of the property reflects that.</span></span> <span data-ttu-id="04b04-112">Für Eigenschaftsnamen wird immer PascalCasing verwendet.</span><span class="sxs-lookup"><span data-stu-id="04b04-112">PascalCasing is always used for property names.</span></span>

 <span data-ttu-id="04b04-113">✔️ Sie namens Eigenschaften mit einem Substantiv, nominalen Ausdruck oder Adjektiv.</span><span class="sxs-lookup"><span data-stu-id="04b04-113">✔️ DO name properties using a noun, noun phrase, or adjective.</span></span>

 <span data-ttu-id="04b04-114">❌ haben keine Eigenschaften, die mit dem Namen der Get-Methoden identisch sind, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="04b04-114">❌ DO NOT have properties that match the name of "Get" methods as in the following example:</span></span>

 <span data-ttu-id="04b04-115">`public string TextWriter { get {...} set {...} }` `public string GetTextWriter(int value) { ... }`</span><span class="sxs-lookup"><span data-stu-id="04b04-115">`public string TextWriter { get {...} set {...} }` `public string GetTextWriter(int value) { ... }`</span></span>

 <span data-ttu-id="04b04-116">Dieses Muster gibt normalerweise an, dass die Eigenschaft eigentlich eine Methode sein soll.</span><span class="sxs-lookup"><span data-stu-id="04b04-116">This pattern typically indicates that the property should really be a method.</span></span>

 <span data-ttu-id="04b04-117">✔️ namens Sammlungs Eigenschaften mit einem Plural Ausdruck, der die Elemente in der Auflistung beschreibt, anstatt einen Singular Ausdruck, gefolgt von "List" oder "Collection" zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="04b04-117">✔️ DO name collection properties with a plural phrase describing the items in the collection instead of using a singular phrase followed by "List" or "Collection".</span></span>

 <span data-ttu-id="04b04-118">✔️ die boolesche Eigenschaften mit einem positiven Ausdruck (`CanSeek` anstelle `CantSeek`) benennen.</span><span class="sxs-lookup"><span data-stu-id="04b04-118">✔️ DO name Boolean properties with an affirmative phrase (`CanSeek` instead of `CantSeek`).</span></span> <span data-ttu-id="04b04-119">Optional können Sie auch boolesche Eigenschaften mit "is", "Can" oder "has" versehen, aber nur an der Stelle, an der der Wert hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="04b04-119">Optionally, you can also prefix Boolean properties with "Is", "Can", or "Has", but only where it adds value.</span></span>

 <span data-ttu-id="04b04-120">✔️ sollten Sie eine Eigenschaft mit dem gleichen Namen wie der Typ eingeben.</span><span class="sxs-lookup"><span data-stu-id="04b04-120">✔️ CONSIDER giving a property the same name as its type.</span></span>

 <span data-ttu-id="04b04-121">Die folgende Eigenschaft ruft ordnungsgemäß einen Enumerationswert namens `Color` ab und legt ihn fest. Die Eigenschaft heißt also `Color`:</span><span class="sxs-lookup"><span data-stu-id="04b04-121">For example, the following property correctly gets and sets an enum value named `Color`, so the property is named `Color`:</span></span>

```csharp
public enum Color {...}
public class Control {
    public Color Color { get {...} set {...} }
}
```

## <a name="names-of-events"></a><span data-ttu-id="04b04-122">Namen von Ereignissen</span><span class="sxs-lookup"><span data-stu-id="04b04-122">Names of Events</span></span>
 <span data-ttu-id="04b04-123">Ereignisse beziehen sich immer auf Aktionen, also entweder auf eine Aktion, die gerade passiert oder eine, die in der Vergangenheit liegt.</span><span class="sxs-lookup"><span data-stu-id="04b04-123">Events always refer to some action, either one that is happening or one that has occurred.</span></span> <span data-ttu-id="04b04-124">Deshalb werden Ereignisse mit Verben benannt (wie Methoden auch), und die Verbkonjugation wird genutzt, um den Zeitpunkt anzugeben, wann das Ereignis ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="04b04-124">Therefore, as with methods, events are named with verbs, and verb tense is used to indicate the time when the event is raised.</span></span>

 <span data-ttu-id="04b04-125">✔️ Ereignisse mit einem Verb oder einem Verb Ausdruck zu benennen.</span><span class="sxs-lookup"><span data-stu-id="04b04-125">✔️ DO name events with a verb or a verb phrase.</span></span>

 <span data-ttu-id="04b04-126">Beispiele dafür sind `Clicked`, `Painting`, `DroppedDown` usw.</span><span class="sxs-lookup"><span data-stu-id="04b04-126">Examples include `Clicked`, `Painting`, `DroppedDown`, and so on.</span></span>

 <span data-ttu-id="04b04-127">✔️ die Namen von Ereignissen mit einem Konzept von before und After zu versehen, wobei die vorhandenen und vergangenen Mandanten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="04b04-127">✔️ DO give events names with a concept of before and after, using the present and past tenses.</span></span>

 <span data-ttu-id="04b04-128">Beispielsweise wird ein Schließereignis, das ausgelöst wird, bevor ein Fenster geschlossen wird, als `Closing` bezeichnet. Ein Ereignis, das nach dem Schließen des Fensters ausgelöst wird, wird als `Closed` bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="04b04-128">For example, a close event that is raised before a window is closed would be called `Closing`, and one that is raised after the window is closed would be called `Closed`.</span></span>

 <span data-ttu-id="04b04-129">❌ nicht die Präfixe oder postfixes "Before" oder "After" verwenden, um Pre-und Post-Ereignisse anzugeben.</span><span class="sxs-lookup"><span data-stu-id="04b04-129">❌ DO NOT use "Before" or "After" prefixes or postfixes to indicate pre- and post-events.</span></span> <span data-ttu-id="04b04-130">Verwenden Sie wie oben beschrieben die Gegenwarts- und Vergangenheitsformen.</span><span class="sxs-lookup"><span data-stu-id="04b04-130">Use present and past tenses as just described.</span></span>

 <span data-ttu-id="04b04-131">✔️ Do-Ereignishandler (Delegaten, die als Typen von Ereignissen verwendet werden) mit dem Suffix "EventHandler", wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="04b04-131">✔️ DO name event handlers (delegates used as types of events) with the "EventHandler" suffix, as shown in the following example:</span></span>

 `public delegate void ClickedEventHandler(object sender, ClickedEventArgs e);`

 <span data-ttu-id="04b04-132">✔️ Verwenden Sie zwei Parameter mit dem Namen `sender` und `e` in Ereignis Handlern.</span><span class="sxs-lookup"><span data-stu-id="04b04-132">✔️ DO use two parameters named `sender` and `e` in event handlers.</span></span>

 <span data-ttu-id="04b04-133">Der sender-Parameter stellt das Objekt dar, das das Ereignis ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="04b04-133">The sender parameter represents the object that raised the event.</span></span> <span data-ttu-id="04b04-134">Der sender-Parameter ist in der Regel vom Typ `object`, auch wenn es möglich ist, einen spezifischeren Typ zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="04b04-134">The sender parameter is typically of type `object`, even if it is possible to employ a more specific type.</span></span>

 <span data-ttu-id="04b04-135">✔️ Do Event Argument-Klassen mit dem Suffix "EventArgs".</span><span class="sxs-lookup"><span data-stu-id="04b04-135">✔️ DO name event argument classes with the "EventArgs" suffix.</span></span>

## <a name="names-of-fields"></a><span data-ttu-id="04b04-136">Feldnamen</span><span class="sxs-lookup"><span data-stu-id="04b04-136">Names of Fields</span></span>
 <span data-ttu-id="04b04-137">Die Richtlinien für die Benennung von Feldern gelten für statische öffentliche und geschützte Felder.</span><span class="sxs-lookup"><span data-stu-id="04b04-137">The field-naming guidelines apply to static public and protected fields.</span></span> <span data-ttu-id="04b04-138">Interne und private Felder sind nicht Gegenstand von Richtlinien, und öffentliche oder geschützte Instanzfelder sind laut den [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md) nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="04b04-138">Internal and private fields are not covered by guidelines, and public or protected instance fields are not allowed by the [member design guidelines](../../../docs/standard/design-guidelines/member.md).</span></span>

 <span data-ttu-id="04b04-139">✔️ Verwenden Sie die pascalschreibweise in Feldnamen.</span><span class="sxs-lookup"><span data-stu-id="04b04-139">✔️ DO use PascalCasing in field names.</span></span>

 <span data-ttu-id="04b04-140">✔️ Felder mit einem Substantiv, Substantiv Ausdruck oder Adjektiv benennen.</span><span class="sxs-lookup"><span data-stu-id="04b04-140">✔️ DO name fields using a noun, noun phrase, or adjective.</span></span>

 <span data-ttu-id="04b04-141">❌ kein Präfix für Feldnamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="04b04-141">❌ DO NOT use a prefix for field names.</span></span>

 <span data-ttu-id="04b04-142">Verwenden Sie beispielsweise nicht „g_“ oder „s_“, um statische Felder anzugeben.</span><span class="sxs-lookup"><span data-stu-id="04b04-142">For example, do not use "g_" or "s_" to indicate static fields.</span></span>

 <span data-ttu-id="04b04-143">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="04b04-143">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="04b04-144">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="04b04-144">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="04b04-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="04b04-145">See also</span></span>

- [<span data-ttu-id="04b04-146">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="04b04-146">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="04b04-147">Richtlinien für die Benennung</span><span class="sxs-lookup"><span data-stu-id="04b04-147">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
