---
title: Namen von Klassen, Strukturen und Schnittstellen
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
ms.openlocfilehash: 2c528348c0e84037a80df9797c56f03b51c73adc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401238"
---
# <a name="names-of-classes-structs-and-interfaces"></a><span data-ttu-id="b621e-102">Namen von Klassen, Strukturen und Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b621e-102">Names of Classes, Structs, and Interfaces</span></span>
<span data-ttu-id="b621e-103">Die folgenden Benennungsrichtlinien gelten für die allgemeine Typbenennung.</span><span class="sxs-lookup"><span data-stu-id="b621e-103">The naming guidelines that follow apply to general type naming.</span></span>

 <span data-ttu-id="b621e-104">✔️ DO-Namensklassen und -Strukturen mit Substantiven oder Nomenphrasen mit PascalCasing.</span><span class="sxs-lookup"><span data-stu-id="b621e-104">✔️ DO name classes and structs with nouns or noun phrases, using PascalCasing.</span></span>

 <span data-ttu-id="b621e-105">Dadurch werden Typnamen von Methoden unterschieden, die mit Verbausdrücken benannt werden.</span><span class="sxs-lookup"><span data-stu-id="b621e-105">This distinguishes type names from methods, which are named with verb phrases.</span></span>

 <span data-ttu-id="b621e-106">✔️ DO-Namensschnittstellen mit Adjektivphrasen oder gelegentlich mit Substantiven oder Substantiven.</span><span class="sxs-lookup"><span data-stu-id="b621e-106">✔️ DO name interfaces with adjective phrases, or occasionally with nouns or noun phrases.</span></span>

 <span data-ttu-id="b621e-107">Nomen und Nomenphrasen sollten selten verwendet werden, und sie können darauf hinweisen, dass der Typ eine abstrakte Klasse und keine Schnittstelle sein sollte.</span><span class="sxs-lookup"><span data-stu-id="b621e-107">Nouns and noun phrases should be used rarely and they might indicate that the type should be an abstract class, and not an interface.</span></span>

 <span data-ttu-id="b621e-108">❌Geben Sie Klassennamen KEIN Präfix (z. B. "C").</span><span class="sxs-lookup"><span data-stu-id="b621e-108">❌ DO NOT give class names a prefix (e.g., "C").</span></span>

 <span data-ttu-id="b621e-109">✔️ CONSIDER, der den Namen abgeleiteter Klassen mit dem Namen der Basisklasse beendet.</span><span class="sxs-lookup"><span data-stu-id="b621e-109">✔️ CONSIDER ending the name of derived classes with the name of the base class.</span></span>

 <span data-ttu-id="b621e-110">Dies ist sehr lesbar und erklärt die Beziehung deutlich.</span><span class="sxs-lookup"><span data-stu-id="b621e-110">This is very readable and explains the relationship clearly.</span></span> <span data-ttu-id="b621e-111">Einige Beispiele dafür im `ArgumentOutOfRangeException`Code sind: , `Exception`was `SerializableAttribute`eine Art von `Attribute`ist, und , das ist eine Art von .</span><span class="sxs-lookup"><span data-stu-id="b621e-111">Some examples of this in code are: `ArgumentOutOfRangeException`, which is a kind of `Exception`, and `SerializableAttribute`, which is a kind of `Attribute`.</span></span> <span data-ttu-id="b621e-112">Es ist jedoch wichtig, bei der Anwendung dieser Richtlinie ein vernünftiges Urteilsvermögen zu verwenden; Beispielsweise ist `Button` die Klasse eine `Control` Art `Control` Ereignis, obwohl sie nicht in ihrem Namen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b621e-112">However, it is important to use reasonable judgment in applying this guideline; for example, the `Button` class is a kind of `Control` event, although `Control` doesn’t appear in its name.</span></span>

 <span data-ttu-id="b621e-113">✔️ DO-Präfixschnittstellennamen mit dem Buchstaben I, um anzugeben, dass der Typ eine Schnittstelle ist.</span><span class="sxs-lookup"><span data-stu-id="b621e-113">✔️ DO prefix interface names with the letter I, to indicate that the type is an interface.</span></span>

 <span data-ttu-id="b621e-114">Beispielsweise `IComponent` sind (deskriptives `ICustomAttributeProvider` Nounon), (Nounphrase) und `IPersistable` (Adjektiv) geeignete Schnittstellennamen.</span><span class="sxs-lookup"><span data-stu-id="b621e-114">For example, `IComponent` (descriptive noun), `ICustomAttributeProvider` (noun phrase), and `IPersistable` (adjective) are appropriate interface names.</span></span> <span data-ttu-id="b621e-115">Vermeiden Sie wie bei anderen Typnamen Abkürzungen.</span><span class="sxs-lookup"><span data-stu-id="b621e-115">As with other type names, avoid abbreviations.</span></span>

 <span data-ttu-id="b621e-116">✔️ stellen Sie sicher, dass sich die Namen nur durch das Präfix "I" im Schnittstellennamen unterscheiden, wenn Sie ein Klassen-Schnittstellenpaar definieren, bei dem die Klasse eine Standardimplementierung der Schnittstelle ist.</span><span class="sxs-lookup"><span data-stu-id="b621e-116">✔️ DO ensure that the names differ only by the "I" prefix on the interface name when you are defining a class–interface pair where the class is a standard implementation of the interface.</span></span>

## <a name="names-of-generic-type-parameters"></a><span data-ttu-id="b621e-117">Namen generischer Typparameter</span><span class="sxs-lookup"><span data-stu-id="b621e-117">Names of Generic Type Parameters</span></span>
 <span data-ttu-id="b621e-118">Generics wurden zu .NET Framework 2.0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b621e-118">Generics were added to .NET Framework 2.0.</span></span> <span data-ttu-id="b621e-119">Die Funktion führte eine neue Art von Bezeichner namens *Typparameter*ein.</span><span class="sxs-lookup"><span data-stu-id="b621e-119">The feature introduced a new kind of identifier called *type parameter*.</span></span>

 <span data-ttu-id="b621e-120">✔️ DO-Namen generische Typparameter mit beschreibenden Namen, es sei denn, ein Name mit einem Buchstaben ist vollständig selbsterklärend und ein beschreibender Name würde keinen Wert hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b621e-120">✔️ DO name generic type parameters with descriptive names unless a single-letter name is completely self-explanatory and a descriptive name would not add value.</span></span>

 <span data-ttu-id="b621e-121">✔️ CONSIDER `T` als Typparametername für Typen mit einem Einzelbuchstabentypparameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="b621e-121">✔️ CONSIDER using `T` as the type parameter name for types with one single-letter type parameter.</span></span>

```csharp
public int IComparer<T> { ... }
public delegate bool Predicate<T>(T item);
public struct Nullable<T> where T:struct { ... }
```

 <span data-ttu-id="b621e-122">✔️ DO präskriptiven Typparameternamen mit `T`.</span><span class="sxs-lookup"><span data-stu-id="b621e-122">✔️ DO prefix descriptive type parameter names with `T`.</span></span>

```csharp
public interface ISessionChannel<TSession> where TSession : ISession {
    TSession Session { get; }
}
```

 <span data-ttu-id="b621e-123">✔️ CONSIDER, die Einschränkungen angibt, die für einen Typparameter im Namen des Parameters platziert werden.</span><span class="sxs-lookup"><span data-stu-id="b621e-123">✔️ CONSIDER indicating constraints placed on a type parameter in the name of the parameter.</span></span>

 <span data-ttu-id="b621e-124">Beispielsweise kann ein Parameter, der eingeschränkt `ISession` ist, aufgerufen `TSession`werden.</span><span class="sxs-lookup"><span data-stu-id="b621e-124">For example, a parameter constrained to `ISession` might be called `TSession`.</span></span>

## <a name="names-of-common-types"></a><span data-ttu-id="b621e-125">Namen gängiger Typen</span><span class="sxs-lookup"><span data-stu-id="b621e-125">Names of Common Types</span></span>
 <span data-ttu-id="b621e-126">✔️ befolgen Sie die in der folgenden Tabelle beschriebenen Richtlinien, wenn Sie Typen benennen, die von bestimmten .NET Framework-Typen abgeleitet sind oder diese implementieren.</span><span class="sxs-lookup"><span data-stu-id="b621e-126">✔️ DO follow the guidelines described in the following table when naming types derived from or implementing certain .NET Framework types.</span></span>

|<span data-ttu-id="b621e-127">Basistyp</span><span class="sxs-lookup"><span data-stu-id="b621e-127">Base Type</span></span>|<span data-ttu-id="b621e-128">Abgeleitete/Implementierenvon Typleitlinie</span><span class="sxs-lookup"><span data-stu-id="b621e-128">Derived/Implementing Type Guideline</span></span>|
|---------------|------------------------------------------|
|`System.Attribute`|<span data-ttu-id="b621e-129">✔️ das Suffix "Attribut" zu Namen benutzerdefinierter Attributklassen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b621e-129">✔️ DO add the suffix "Attribute" to names of custom attribute classes.</span></span>|
|`System.Delegate`|<span data-ttu-id="b621e-130">✔️ das Suffix "EventHandler" zu den Namen von Delegaten hinzufügen, die in Ereignissen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b621e-130">✔️ DO add the suffix "EventHandler" to names of delegates that are used in events.</span></span><br /><br /> <span data-ttu-id="b621e-131">✔️ das Suffix "Callback" zu Namen anderer Delegaten als der als Ereignishandler verwendeten Hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b621e-131">✔️ DO add the suffix "Callback" to names of delegates other than those used as event handlers.</span></span><br /><br /> <span data-ttu-id="b621e-132">❌Fügen Sie einem Delegaten NICHT das Suffix "Delegate" hinzu.</span><span class="sxs-lookup"><span data-stu-id="b621e-132">❌ DO NOT add the suffix "Delegate" to a delegate.</span></span>|
|`System.EventArgs`|<span data-ttu-id="b621e-133">✔️ das Suffix "EventArgs" hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b621e-133">✔️ DO add the suffix "EventArgs."</span></span>|
|`System.Enum`|<span data-ttu-id="b621e-134">❌Nicht von dieser Klasse ableiten; verwenden Sie stattdessen das von Ihrer Sprache unterstützte Schlüsselwort; Verwenden Sie z. B. `enum` das Schlüsselwort in C.</span><span class="sxs-lookup"><span data-stu-id="b621e-134">❌ DO NOT derive from this class; use the keyword supported by your language instead; for example, in C#, use the `enum` keyword.</span></span><br /><br /> <span data-ttu-id="b621e-135">❌Fügen Sie NICHT das Suffix "Enum" oder "Flag" hinzu.</span><span class="sxs-lookup"><span data-stu-id="b621e-135">❌ DO NOT add the suffix "Enum" or "Flag."</span></span>|
|`System.Exception`|<span data-ttu-id="b621e-136">✔️ das Suffix "Ausnahme" hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b621e-136">✔️ DO add the suffix "Exception."</span></span>|
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|<span data-ttu-id="b621e-137">✔️ das Suffix "Wörterbuch" hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b621e-137">✔️ DO add the suffix "Dictionary."</span></span> <span data-ttu-id="b621e-138">Beachten `IDictionary` Sie, dass es sich um einen bestimmten Auflistungstyp handelt, aber diese Richtlinie hat Vorrang vor der allgemeineren Auflistungsrichtlinie, die folgt.</span><span class="sxs-lookup"><span data-stu-id="b621e-138">Note that `IDictionary` is a specific type of collection, but this guideline takes precedence over the more general collections guideline that follows.</span></span>|
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|<span data-ttu-id="b621e-139">✔️ das Suffix "Collection" hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b621e-139">✔️ DO add the suffix "Collection."</span></span>|
|`System.IO.Stream`|<span data-ttu-id="b621e-140">✔️ das Suffix "Stream" hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b621e-140">✔️ DO add the suffix "Stream."</span></span>|
|`CodeAccessPermission IPermission`|<span data-ttu-id="b621e-141">✔️ das Suffix "Berechtigung" hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b621e-141">✔️ DO add the suffix "Permission."</span></span>|

## <a name="naming-enumerations"></a><span data-ttu-id="b621e-142">Benennen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="b621e-142">Naming Enumerations</span></span>
 <span data-ttu-id="b621e-143">Namen von Enumerationstypen (auch Enumerationen genannt) sollten im Allgemeinen den Standardregeln für die Typbenennung (PascalCasing usw.) folgen.</span><span class="sxs-lookup"><span data-stu-id="b621e-143">Names of enumeration types (also called enums) in general should follow the standard type-naming rules (PascalCasing, etc.).</span></span> <span data-ttu-id="b621e-144">Es gibt jedoch zusätzliche Richtlinien, die speziell für Enumerungen gelten.</span><span class="sxs-lookup"><span data-stu-id="b621e-144">However, there are additional guidelines that apply specifically to enums.</span></span>

 <span data-ttu-id="b621e-145">✔️ verwenden einen eindeutigen Typnamen für eine Enumeration, es sei denn, seine Werte sind Bitfelder.</span><span class="sxs-lookup"><span data-stu-id="b621e-145">✔️ DO use a singular type name for an enumeration unless its values are bit fields.</span></span>

 <span data-ttu-id="b621e-146">✔️ DO einen Pluraltypnamen für eine Enumeration mit Bitfeldern als Werte verwenden, die auch als Flags enum bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="b621e-146">✔️ DO use a plural type name for an enumeration with bit fields as values, also called flags enum.</span></span>

 <span data-ttu-id="b621e-147">❌Verwenden Sie NICHT ein "Enum"-Suffix in Enumerumtypnamen.</span><span class="sxs-lookup"><span data-stu-id="b621e-147">❌ DO NOT use an "Enum" suffix in enum type names.</span></span>

 <span data-ttu-id="b621e-148">❌Verwenden Sie NICHT die Suffixe "Flag" oder "Flags" in Enumerumtypnamen.</span><span class="sxs-lookup"><span data-stu-id="b621e-148">❌ DO NOT use "Flag" or "Flags" suffixes in enum type names.</span></span>

 <span data-ttu-id="b621e-149">❌Verwenden Sie NICHT ein Präfix für Enumerationswertnamen (z. B. "ad" für ADO-Enumerationen, "rtf" für Rich-Text-Enumerationen usw.).</span><span class="sxs-lookup"><span data-stu-id="b621e-149">❌ DO NOT use a prefix on enumeration value names (e.g., "ad" for ADO enums, "rtf" for rich text enums, etc.).</span></span>

 <span data-ttu-id="b621e-150">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="b621e-150">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="b621e-151">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="b621e-151">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="b621e-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b621e-152">See also</span></span>

- [<span data-ttu-id="b621e-153">Framework Design-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="b621e-153">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="b621e-154">Richtlinien für die Benennung</span><span class="sxs-lookup"><span data-stu-id="b621e-154">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
