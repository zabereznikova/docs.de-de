---
title: Namen von Klassen, Strukturen und Schnittstellen
description: Verwenden Sie diese Richtlinien zum Benennen von Klassen, Strukturen und Schnittstellen als Teil der Richtlinien zum Entwerfen von Bibliotheken, die .NET-Bibliotheken erweitern und interagieren.
ms.date: 10/22/2008
helpviewer_keywords:
- type names, guidelines
- classes [.NET Framework], names
- enumerations [.NET Framework], names
- names [.NET Framework], interfaces
- common type names
- names [.NET Framework], type names
- names [.NET Framework], classes
- interfaces [.NET Framework], names
- generic type parameters
ms.assetid: 87a4b0da-ed64-43b1-ac43-968576c444ce
ms.openlocfilehash: 49bafda0d5c362fa02313c5304436069d054cfd9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706514"
---
# <a name="names-of-classes-structs-and-interfaces"></a><span data-ttu-id="d55d1-103">Namen von Klassen, Strukturen und Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d55d1-103">Names of Classes, Structs, and Interfaces</span></span>

<span data-ttu-id="d55d1-104">Die folgenden Benennungs Richtlinien gelten für die allgemeine Typbenennung.</span><span class="sxs-lookup"><span data-stu-id="d55d1-104">The naming guidelines that follow apply to general type naming.</span></span>

 <span data-ttu-id="d55d1-105">mit der Pass-/Schreibweise von ✔️ Klassen und Strukturen mit Nomen oder nominalen Ausdrücken benannt.</span><span class="sxs-lookup"><span data-stu-id="d55d1-105">✔️ DO name classes and structs with nouns or noun phrases, using PascalCasing.</span></span>

 <span data-ttu-id="d55d1-106">Dies unterscheidet Typnamen von Methoden, die mit Verb Ausdrücken benannt werden.</span><span class="sxs-lookup"><span data-stu-id="d55d1-106">This distinguishes type names from methods, which are named with verb phrases.</span></span>

 <span data-ttu-id="d55d1-107">✔️ Namen Schnittstellen mit Adjektiv Ausdrücken oder gelegentlich mit Nomen oder nominalen Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="d55d1-107">✔️ DO name interfaces with adjective phrases, or occasionally with nouns or noun phrases.</span></span>

 <span data-ttu-id="d55d1-108">Nomen und nominale Ausdrücke sollten in seltenen Fällen verwendet werden, und Sie können darauf hinweisen, dass der Typ eine abstrakte Klasse und keine Schnittstelle sein sollte.</span><span class="sxs-lookup"><span data-stu-id="d55d1-108">Nouns and noun phrases should be used rarely and they might indicate that the type should be an abstract class, and not an interface.</span></span>

 <span data-ttu-id="d55d1-109">❌ Nennen Sie keine Klassennamen als Präfix (z. b. "C").</span><span class="sxs-lookup"><span data-stu-id="d55d1-109">❌ DO NOT give class names a prefix (e.g., "C").</span></span>

 <span data-ttu-id="d55d1-110">✔️ sollten den Namen abgeleiteter Klassen mit dem Namen der Basisklasse beenden.</span><span class="sxs-lookup"><span data-stu-id="d55d1-110">✔️ CONSIDER ending the name of derived classes with the name of the base class.</span></span>

 <span data-ttu-id="d55d1-111">Dies ist sehr lesbar und erläutert die Beziehung eindeutig.</span><span class="sxs-lookup"><span data-stu-id="d55d1-111">This is very readable and explains the relationship clearly.</span></span> <span data-ttu-id="d55d1-112">Einige Beispiele hierfür sind: `ArgumentOutOfRangeException` , eine Art von `Exception` und `SerializableAttribute` , die eine Art von ist `Attribute` .</span><span class="sxs-lookup"><span data-stu-id="d55d1-112">Some examples of this in code are: `ArgumentOutOfRangeException`, which is a kind of `Exception`, and `SerializableAttribute`, which is a kind of `Attribute`.</span></span> <span data-ttu-id="d55d1-113">Es ist jedoch wichtig, bei der Anwendung dieser Richtlinie ein vernünftiges Urteil zu verwenden. Beispielsweise ist die- `Button` Klasse eine Art von `Control` Ereignis, obwohl `Control` nicht im Namen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d55d1-113">However, it is important to use reasonable judgment in applying this guideline; for example, the `Button` class is a kind of `Control` event, although `Control` doesn’t appear in its name.</span></span>

 <span data-ttu-id="d55d1-114">✔️ Geben Sie Schnittstellennamen mit dem Buchstaben I an, um anzugeben, dass der Typ eine Schnittstelle ist.</span><span class="sxs-lookup"><span data-stu-id="d55d1-114">✔️ DO prefix interface names with the letter I, to indicate that the type is an interface.</span></span>

 <span data-ttu-id="d55d1-115">Beispielsweise `IComponent` sind (beschreibende Substantiv), `ICustomAttributeProvider` (Substantiv Phrase) und `IPersistable` (Adjektiv) geeignete Schnittstellennamen.</span><span class="sxs-lookup"><span data-stu-id="d55d1-115">For example, `IComponent` (descriptive noun), `ICustomAttributeProvider` (noun phrase), and `IPersistable` (adjective) are appropriate interface names.</span></span> <span data-ttu-id="d55d1-116">Vermeiden Sie Abkürzungen wie andere Typnamen.</span><span class="sxs-lookup"><span data-stu-id="d55d1-116">As with other type names, avoid abbreviations.</span></span>

 <span data-ttu-id="d55d1-117">Stellen Sie ✔️ sicher, dass sich die Namen nur durch das Präfix "I" für den Schnittstellennamen unterscheiden, wenn Sie ein Klassen –-Schnittstellen Paar definieren, bei dem die Klasse eine Standard Implementierung der Schnittstelle ist.</span><span class="sxs-lookup"><span data-stu-id="d55d1-117">✔️ DO ensure that the names differ only by the "I" prefix on the interface name when you are defining a class–interface pair where the class is a standard implementation of the interface.</span></span>

## <a name="names-of-generic-type-parameters"></a><span data-ttu-id="d55d1-118">Namen von generischen Typparametern</span><span class="sxs-lookup"><span data-stu-id="d55d1-118">Names of Generic Type Parameters</span></span>

 <span data-ttu-id="d55d1-119">Generika wurden .NET Framework 2,0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d55d1-119">Generics were added to .NET Framework 2.0.</span></span> <span data-ttu-id="d55d1-120">Mit der Funktion wurde eine neue Art von Bezeichner namens *Typparameter* eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d55d1-120">The feature introduced a new kind of identifier called *type parameter*.</span></span>

 <span data-ttu-id="d55d1-121">✔️ Namen generischer Typparameter mit beschreibenden Namen verwenden, es sei denn, ein einzelner Buchstabe ist vollständig selbsterklärend, und ein beschreibender Name würde keinen Wert hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d55d1-121">✔️ DO name generic type parameters with descriptive names unless a single-letter name is completely self-explanatory and a descriptive name would not add value.</span></span>

 <span data-ttu-id="d55d1-122">✔️ die Verwendung `T` von als Typparameter Name für Typen mit einem Typparameter mit einem einzelnen Buchstaben in Erwägung gezogen.</span><span class="sxs-lookup"><span data-stu-id="d55d1-122">✔️ CONSIDER using `T` as the type parameter name for types with one single-letter type parameter.</span></span>

```csharp
public int IComparer<T> { ... }
public delegate bool Predicate<T>(T item);
public struct Nullable<T> where T:struct { ... }
```

 <span data-ttu-id="d55d1-123">✔️ machen beschreibende Typparameter Namen mit Präfix `T` .</span><span class="sxs-lookup"><span data-stu-id="d55d1-123">✔️ DO prefix descriptive type parameter names with `T`.</span></span>

```csharp
public interface ISessionChannel<TSession> where TSession : ISession {
    TSession Session { get; }
}
```

 <span data-ttu-id="d55d1-124">✔️ in Erwägung gezogen, dass Einschränkungen für einen Typparameter im Namen des Parameters eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="d55d1-124">✔️ CONSIDER indicating constraints placed on a type parameter in the name of the parameter.</span></span>

 <span data-ttu-id="d55d1-125">Beispielsweise kann ein Parameter, der auf eingeschränkt ist, `ISession` aufgerufen werden `TSession` .</span><span class="sxs-lookup"><span data-stu-id="d55d1-125">For example, a parameter constrained to `ISession` might be called `TSession`.</span></span>

## <a name="names-of-common-types"></a><span data-ttu-id="d55d1-126">Namen allgemeiner Typen</span><span class="sxs-lookup"><span data-stu-id="d55d1-126">Names of Common Types</span></span>

 <span data-ttu-id="d55d1-127">✔️ Befolgen Sie die in der folgenden Tabelle beschriebenen Richtlinien, wenn Sie Typen benennen, die von abgeleitet sind oder bestimmte .NET Framework Typen implementieren.</span><span class="sxs-lookup"><span data-stu-id="d55d1-127">✔️ DO follow the guidelines described in the following table when naming types derived from or implementing certain .NET Framework types.</span></span>

|<span data-ttu-id="d55d1-128">Basistyp</span><span class="sxs-lookup"><span data-stu-id="d55d1-128">Base Type</span></span>|<span data-ttu-id="d55d1-129">Abgeleitete/implementierende typrichtlinie</span><span class="sxs-lookup"><span data-stu-id="d55d1-129">Derived/Implementing Type Guideline</span></span>|
|---------------|------------------------------------------|
|`System.Attribute`|<span data-ttu-id="d55d1-130">Fügen Sie den Namen von benutzerdefinierten Attribut Klassen ✔️ das Suffix "Attribute" hinzu.</span><span class="sxs-lookup"><span data-stu-id="d55d1-130">✔️ DO add the suffix "Attribute" to names of custom attribute classes.</span></span>|
|`System.Delegate`|<span data-ttu-id="d55d1-131">✔️ Fügen Sie das Suffix "EventHandler" den Namen von Delegaten hinzu, die in Ereignissen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d55d1-131">✔️ DO add the suffix "EventHandler" to names of delegates that are used in events.</span></span><br /><br /> <span data-ttu-id="d55d1-132">✔️ fügen das Suffix "Callback" Namen von Delegaten hinzu, die nicht als Ereignishandler verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d55d1-132">✔️ DO add the suffix "Callback" to names of delegates other than those used as event handlers.</span></span><br /><br /> <span data-ttu-id="d55d1-133">❌ Fügen Sie das Suffix "Delegat" nicht zu einem Delegaten hinzu.</span><span class="sxs-lookup"><span data-stu-id="d55d1-133">❌ DO NOT add the suffix "Delegate" to a delegate.</span></span>|
|`System.EventArgs`|<span data-ttu-id="d55d1-134">Fügen Sie ✔️ das Suffix "EventArgs" hinzu.</span><span class="sxs-lookup"><span data-stu-id="d55d1-134">✔️ DO add the suffix "EventArgs."</span></span>|
|`System.Enum`|<span data-ttu-id="d55d1-135">❌ Nicht von dieser Klasse ableiten; Verwenden Sie stattdessen das von Ihrer Sprache unterstützte Schlüsselwort; Verwenden Sie z. b. in c# das- `enum` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="d55d1-135">❌ DO NOT derive from this class; use the keyword supported by your language instead; for example, in C#, use the `enum` keyword.</span></span><br /><br /> <span data-ttu-id="d55d1-136">❌ Fügen Sie das Suffix "Enum" oder "Flag" nicht hinzu.</span><span class="sxs-lookup"><span data-stu-id="d55d1-136">❌ DO NOT add the suffix "Enum" or "Flag."</span></span>|
|`System.Exception`|<span data-ttu-id="d55d1-137">Fügen Sie ✔️ das Suffix "Exception" hinzu.</span><span class="sxs-lookup"><span data-stu-id="d55d1-137">✔️ DO add the suffix "Exception."</span></span>|
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|<span data-ttu-id="d55d1-138">Fügen Sie ✔️ das Suffix "Dictionary" hinzu.</span><span class="sxs-lookup"><span data-stu-id="d55d1-138">✔️ DO add the suffix "Dictionary."</span></span> <span data-ttu-id="d55d1-139">Beachten Sie, dass es `IDictionary` sich um einen bestimmten Sammlungstyp handelt. diese Richtlinie hat jedoch Vorrang vor den folgenden allgemeinen Auflistungs Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="d55d1-139">Note that `IDictionary` is a specific type of collection, but this guideline takes precedence over the more general collections guideline that follows.</span></span>|
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|<span data-ttu-id="d55d1-140">Fügen Sie ✔️ das Suffix "Collection" hinzu.</span><span class="sxs-lookup"><span data-stu-id="d55d1-140">✔️ DO add the suffix "Collection."</span></span>|
|`System.IO.Stream`|<span data-ttu-id="d55d1-141">Fügen Sie ✔️ das Suffix "Stream" hinzu.</span><span class="sxs-lookup"><span data-stu-id="d55d1-141">✔️ DO add the suffix "Stream."</span></span>|
|`CodeAccessPermission IPermission`|<span data-ttu-id="d55d1-142">✔️ Fügen Sie das Suffix "Berechtigung" hinzu.</span><span class="sxs-lookup"><span data-stu-id="d55d1-142">✔️ DO add the suffix "Permission."</span></span>|

## <a name="naming-enumerations"></a><span data-ttu-id="d55d1-143">Benennen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="d55d1-143">Naming Enumerations</span></span>

 <span data-ttu-id="d55d1-144">Namen von Enumerationstypen (auch als Enumerationen bezeichnet) sollten im Allgemeinen den standardmäßigen typbenennungs Regeln (pascalnaming, usw.) entsprechen.</span><span class="sxs-lookup"><span data-stu-id="d55d1-144">Names of enumeration types (also called enums) in general should follow the standard type-naming rules (PascalCasing, etc.).</span></span> <span data-ttu-id="d55d1-145">Es gibt jedoch weitere Richtlinien, die speziell für-aufzählen gelten.</span><span class="sxs-lookup"><span data-stu-id="d55d1-145">However, there are additional guidelines that apply specifically to enums.</span></span>

 <span data-ttu-id="d55d1-146">✔️ einen eindeutigen Typnamen für eine Enumeration verwenden, es sei denn, die Werte sind Bitfelder.</span><span class="sxs-lookup"><span data-stu-id="d55d1-146">✔️ DO use a singular type name for an enumeration unless its values are bit fields.</span></span>

 <span data-ttu-id="d55d1-147">✔️ einen Plural Typnamen für eine Enumeration mit Bitfeldern als Werte verwenden, die auch als Flags-Enumeration bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="d55d1-147">✔️ DO use a plural type name for an enumeration with bit fields as values, also called flags enum.</span></span>

 <span data-ttu-id="d55d1-148">❌ Verwenden Sie kein "Enumeration"-Suffix in Enumeration-Typnamen.</span><span class="sxs-lookup"><span data-stu-id="d55d1-148">❌ DO NOT use an "Enum" suffix in enum type names.</span></span>

 <span data-ttu-id="d55d1-149">❌ Verwenden Sie keine "Flag"-oder "Flags"-Suffixe in Enumeration-Typnamen.</span><span class="sxs-lookup"><span data-stu-id="d55d1-149">❌ DO NOT use "Flag" or "Flags" suffixes in enum type names.</span></span>

 <span data-ttu-id="d55d1-150">❌ Verwenden Sie kein Präfix für enumerationswertnamen (z. b. "AD" für ADO-Enumerationen, "RTF" für Rich-Text-Enumerationen usw.).</span><span class="sxs-lookup"><span data-stu-id="d55d1-150">❌ DO NOT use a prefix on enumeration value names (e.g., "ad" for ADO enums, "rtf" for rich text enums, etc.).</span></span>

 <span data-ttu-id="d55d1-151">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="d55d1-151">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="d55d1-152">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="d55d1-152">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="d55d1-153">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d55d1-153">See also</span></span>

- [<span data-ttu-id="d55d1-154">Framework-Entwurfs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="d55d1-154">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="d55d1-155">Benennungs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="d55d1-155">Naming Guidelines</span></span>](naming-guidelines.md)
