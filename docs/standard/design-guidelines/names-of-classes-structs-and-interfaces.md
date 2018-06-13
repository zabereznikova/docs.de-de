---
title: Namen von Klassen, Strukturen und Schnittstellen
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a1841fbfcb76d5b56681b63ec4b39e9a7418707f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33576141"
---
# <a name="names-of-classes-structs-and-interfaces"></a><span data-ttu-id="dda91-102">Namen von Klassen, Strukturen und Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="dda91-102">Names of Classes, Structs, and Interfaces</span></span>
<span data-ttu-id="dda91-103">Benennungskonventionen Richtlinien gelten für die Benennung von Typ "Allgemein".</span><span class="sxs-lookup"><span data-stu-id="dda91-103">The naming guidelines that follow apply to general type naming.</span></span>  
  
 <span data-ttu-id="dda91-104">**Führen Sie ✓** Benennen von Klassen und Strukturen Nomen und nominale Ausdrücke, die unter Verwendung von PascalCasing.</span><span class="sxs-lookup"><span data-stu-id="dda91-104">**✓ DO** name classes and structs with nouns or noun phrases, using PascalCasing.</span></span>  
  
 <span data-ttu-id="dda91-105">Dadurch unterscheidet Namen von Methoden, die mit Verb Ausdrücke benannt werden.</span><span class="sxs-lookup"><span data-stu-id="dda91-105">This distinguishes type names from methods, which are named with verb phrases.</span></span>  
  
 <span data-ttu-id="dda91-106">**Führen Sie ✓** Schnittstellen mit adjektivische Ausdrücke oder gelegentlich mit Nomen und nominale Ausdrücke benennen.</span><span class="sxs-lookup"><span data-stu-id="dda91-106">**✓ DO** name interfaces with adjective phrases, or occasionally with nouns or noun phrases.</span></span>  
  
 <span data-ttu-id="dda91-107">Nomen und nominale Ausdrücke sollte nur selten verwendet werden, und sie wird angegeben, dass der Typ eine abstrakte Klasse und keine Schnittstelle sein soll.</span><span class="sxs-lookup"><span data-stu-id="dda91-107">Nouns and noun phrases should be used rarely and they might indicate that the type should be an abstract class, and not an interface.</span></span>  
  
 <span data-ttu-id="dda91-108">**X nicht** Klassennamen ein Präfix (z. B. "C").</span><span class="sxs-lookup"><span data-stu-id="dda91-108">**X DO NOT** give class names a prefix (e.g., "C").</span></span>  
  
 <span data-ttu-id="dda91-109">**✓ GGF.** endet der Name der abgeleiteten Klassen mit dem Namen der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="dda91-109">**✓ CONSIDER** ending the name of derived classes with the name of the base class.</span></span>  
  
 <span data-ttu-id="dda91-110">Dies ist sehr gut lesbar und erklärt die Beziehung eindeutig.</span><span class="sxs-lookup"><span data-stu-id="dda91-110">This is very readable and explains the relationship clearly.</span></span> <span data-ttu-id="dda91-111">Beispiele hierzu finden Sie unter Code sind: `ArgumentOutOfRangeException`, also eine Art von `Exception`, und `SerializableAttribute`, also eine Art von `Attribute`.</span><span class="sxs-lookup"><span data-stu-id="dda91-111">Some examples of this in code are: `ArgumentOutOfRangeException`, which is a kind of `Exception`, and `SerializableAttribute`, which is a kind of `Attribute`.</span></span> <span data-ttu-id="dda91-112">Es ist jedoch mit angemessenen Urteil in diese Richtlinie anwenden; z. B. die `Button` Klasse ist eine Art von `Control` Ereignis, obwohl `Control` nicht in ihrem Namen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dda91-112">However, it is important to use reasonable judgment in applying this guideline; for example, the `Button` class is a kind of `Control` event, although `Control` doesn’t appear in its name.</span></span>  
  
 <span data-ttu-id="dda91-113">**Führen Sie ✓** Schnittstellennamen als Präfix mit dem Buchstaben I, um anzugeben, dass der Typ eine Schnittstelle ist.</span><span class="sxs-lookup"><span data-stu-id="dda91-113">**✓ DO** prefix interface names with the letter I, to indicate that the type is an interface.</span></span>  
  
 <span data-ttu-id="dda91-114">Beispielsweise `IComponent` (beschreibendes Nomen) `ICustomAttributeProvider` (nominaler Ausdruck), und `IPersistable` (Adjektiv) sind die Namen der entsprechenden Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="dda91-114">For example, `IComponent` (descriptive noun), `ICustomAttributeProvider` (noun phrase), and `IPersistable` (adjective) are appropriate interface names.</span></span> <span data-ttu-id="dda91-115">Vermeiden Sie wie bei anderen Typnamen Abkürzungen.</span><span class="sxs-lookup"><span data-stu-id="dda91-115">As with other type names, avoid abbreviations.</span></span>  
  
 <span data-ttu-id="dda91-116">**Führen Sie ✓** stellen Sie sicher, dass die Namen unterscheiden sich nur durch "I" auf der Schnittstellenname Präfix, wenn Sie ein paar Klassenschnittstelle – definieren, wenn die Klasse einer standardmäßigen Implementierung der Schnittstelle befindet.</span><span class="sxs-lookup"><span data-stu-id="dda91-116">**✓ DO** ensure that the names differ only by the "I" prefix on the interface name when you are defining a class–interface pair where the class is a standard implementation of the interface.</span></span>  
  
## <a name="names-of-generic-type-parameters"></a><span data-ttu-id="dda91-117">Namen von generischen Typparametern</span><span class="sxs-lookup"><span data-stu-id="dda91-117">Names of Generic Type Parameters</span></span>  
 <span data-ttu-id="dda91-118">.NET Framework 2.0 wurden Generika hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="dda91-118">Generics were added to .NET Framework 2.0.</span></span> <span data-ttu-id="dda91-119">Die Funktion eingeführt, eine neue Art von Bezeichner mit dem Namen *Typparameter*.</span><span class="sxs-lookup"><span data-stu-id="dda91-119">The feature introduced a new kind of identifier called *type parameter*.</span></span>  
  
 <span data-ttu-id="dda91-120">**Führen Sie ✓** generische Typparameter beschreibende Namen weisen Sie nur ein einzigen Buchstaben Namen vollständig selbsterklärend und ein aussagekräftigen Namen, würde kein Wert hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="dda91-120">**✓ DO** name generic type parameters with descriptive names unless a single-letter name is completely self-explanatory and a descriptive name would not add value.</span></span>  
  
 <span data-ttu-id="dda91-121">**✓ GGF.** mit `T` als der Typparametername für Typen mit einem einzelnen Buchstaben Typparameter.</span><span class="sxs-lookup"><span data-stu-id="dda91-121">**✓ CONSIDER** using `T` as the type parameter name for types with one single-letter type parameter.</span></span>  
  
```  
public int IComparer<T> { ... }  
public delegate bool Predicate<T>(T item);  
public struct Nullable<T> where T:struct { ... }  
```  
  
 <span data-ttu-id="dda91-122">**Führen Sie ✓** beschreibende Typparameternamen mit Präfix `T`.</span><span class="sxs-lookup"><span data-stu-id="dda91-122">**✓ DO** prefix descriptive type parameter names with `T`.</span></span>  
  
```  
public interface ISessionChannel<TSession> where TSession : ISession{  
    TSession Session { get; }  
}  
```  
  
 <span data-ttu-id="dda91-123">**✓ GGF.** , der angibt, Einschränkungen für einen Typparameter, den Namen der Parameter platziert.</span><span class="sxs-lookup"><span data-stu-id="dda91-123">**✓ CONSIDER** indicating constraints placed on a type parameter in the name of the parameter.</span></span>  
  
 <span data-ttu-id="dda91-124">Z. B. ein Parameter beschränkt auf `ISession` aufgerufen werden könnte `TSession`.</span><span class="sxs-lookup"><span data-stu-id="dda91-124">For example, a parameter constrained to `ISession` might be called `TSession`.</span></span>  
  
## <a name="names-of-common-types"></a><span data-ttu-id="dda91-125">Namen von allgemeinen Typen</span><span class="sxs-lookup"><span data-stu-id="dda91-125">Names of Common Types</span></span>  
 <span data-ttu-id="dda91-126">**Führen Sie ✓** beim Benennen von Typen abgeleitet wurde, oder implementieren bestimmte .NET Framework-Typen in der folgenden Tabelle beschriebenen Richtlinien folgen.</span><span class="sxs-lookup"><span data-stu-id="dda91-126">**✓ DO** follow the guidelines described in the following table when naming types derived from or implementing certain .NET Framework types.</span></span>  
  
|<span data-ttu-id="dda91-127">Basistyp</span><span class="sxs-lookup"><span data-stu-id="dda91-127">Base Type</span></span>|<span data-ttu-id="dda91-128">Typ-Richtlinie abgeleitet/implementieren</span><span class="sxs-lookup"><span data-stu-id="dda91-128">Derived/Implementing Type Guideline</span></span>|  
|---------------|------------------------------------------|  
|`System.Attribute`|<span data-ttu-id="dda91-129">**Führen Sie ✓** Namen von benutzerdefinierten Attributklassen das Suffix "Attribute" hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="dda91-129">**✓ DO** add the suffix "Attribute" to names of custom attribute classes.</span></span>|  
|`System.Delegate`|<span data-ttu-id="dda91-130">**Führen Sie ✓** fügen Sie das Suffix "EventHandler" in Namen von Delegaten, die in den Ereignissen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dda91-130">**✓ DO** add the suffix "EventHandler" to names of delegates that are used in events.</span></span><br /><br /> <span data-ttu-id="dda91-131">**Führen Sie ✓** fügen Sie das Suffix "Callback" in Namen von Delegaten, ausgenommen derer, die als Ereignishandler verwendet.</span><span class="sxs-lookup"><span data-stu-id="dda91-131">**✓ DO** add the suffix "Callback" to names of delegates other than those used as event handlers.</span></span><br /><br /> <span data-ttu-id="dda91-132">**X nicht** fügen Sie das Suffix "Delegat" an einen Delegaten.</span><span class="sxs-lookup"><span data-stu-id="dda91-132">**X DO NOT** add the suffix "Delegate" to a delegate.</span></span>|  
|`System.EventArgs`|<span data-ttu-id="dda91-133">**Führen Sie ✓** fügen Sie das Suffix "EventArgs".</span><span class="sxs-lookup"><span data-stu-id="dda91-133">**✓ DO** add the suffix "EventArgs."</span></span>|  
|`System.Enum`|<span data-ttu-id="dda91-134">**X nicht** von dieser Klasse abgeleitet werden; verwenden Sie das Schlüsselwort stattdessen von der Sprache unterstützt; beispielsweise in c# verwenden das `enum` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="dda91-134">**X DO NOT** derive from this class; use the keyword supported by your language instead; for example, in C#, use the `enum` keyword.</span></span><br /><br /> <span data-ttu-id="dda91-135">**X nicht** fügen Sie das Suffix "Enum" oder "Flag für"."</span><span class="sxs-lookup"><span data-stu-id="dda91-135">**X DO NOT** add the suffix "Enum" or "Flag."</span></span>|  
|`System.Exception`|<span data-ttu-id="dda91-136">**Führen Sie ✓** fügen Sie das Suffix "Ausnahme".</span><span class="sxs-lookup"><span data-stu-id="dda91-136">**✓ DO** add the suffix "Exception."</span></span>|  
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|<span data-ttu-id="dda91-137">**Führen Sie ✓** fügen Sie das Suffix "Wörterbuch".</span><span class="sxs-lookup"><span data-stu-id="dda91-137">**✓ DO** add the suffix "Dictionary."</span></span> <span data-ttu-id="dda91-138">Beachten Sie, dass `IDictionary` ist ein spezieller Typ einer Auflistung, aber diese Richtlinie hat Vorrang vor der allgemeineren Sammlungen-Richtlinie, die folgt.</span><span class="sxs-lookup"><span data-stu-id="dda91-138">Note that `IDictionary` is a specific type of collection, but this guideline takes precedence over the more general collections guideline that follows.</span></span>|  
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|<span data-ttu-id="dda91-139">**Führen Sie ✓** fügen Sie das Suffix "Collection".</span><span class="sxs-lookup"><span data-stu-id="dda91-139">**✓ DO** add the suffix "Collection."</span></span>|  
|`System.IO.Stream`|<span data-ttu-id="dda91-140">**Führen Sie ✓** fügen Sie das Suffix "Stream".</span><span class="sxs-lookup"><span data-stu-id="dda91-140">**✓ DO** add the suffix "Stream."</span></span>|  
|`CodeAccessPermission IPermission`|<span data-ttu-id="dda91-141">**Führen Sie ✓** fügen Sie das Suffix "Berechtigung".</span><span class="sxs-lookup"><span data-stu-id="dda91-141">**✓ DO** add the suffix "Permission."</span></span>|  
  
## <a name="naming-enumerations"></a><span data-ttu-id="dda91-142">Benennen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="dda91-142">Naming Enumerations</span></span>  
 <span data-ttu-id="dda91-143">Namen von Enumerationstypen (so genannte Enumerationen) sollte im Allgemeinen die Typ-Benennung Standardregeln (PascalCasing, usw.) entsprechen.</span><span class="sxs-lookup"><span data-stu-id="dda91-143">Names of enumeration types (also called enums) in general should follow the standard type-naming rules (PascalCasing, etc.).</span></span> <span data-ttu-id="dda91-144">Es gibt jedoch zusätzliche Richtlinien, die speziell für Enumerationen gelten.</span><span class="sxs-lookup"><span data-stu-id="dda91-144">However, there are additional guidelines that apply specifically to enums.</span></span>  
  
 <span data-ttu-id="dda91-145">**Führen Sie ✓** verwenden Sie einen Namen im singular für eine Enumeration, es sei denn, seine Werte Bitfelder sind.</span><span class="sxs-lookup"><span data-stu-id="dda91-145">**✓ DO** use a singular type name for an enumeration unless its values are bit fields.</span></span>  
  
 <span data-ttu-id="dda91-146">**Führen Sie ✓** verwenden Sie einen Namen im plural für eine Enumeration mit Bitfelder als Werte, die so genannte Flags-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="dda91-146">**✓ DO** use a plural type name for an enumeration with bit fields as values, also called flags enum.</span></span>  
  
 <span data-ttu-id="dda91-147">**X nicht** eine Suffix "Enum" im Namen der Enum-Typen verwenden.</span><span class="sxs-lookup"><span data-stu-id="dda91-147">**X DO NOT** use an "Enum" suffix in enum type names.</span></span>  
  
 <span data-ttu-id="dda91-148">**X nicht** verwenden "Flag" oder "Flags"-Suffixe in Enum-Typnamen.</span><span class="sxs-lookup"><span data-stu-id="dda91-148">**X DO NOT** use "Flag" or "Flags" suffixes in enum type names.</span></span>  
  
 <span data-ttu-id="dda91-149">**X nicht** ein Präfix auf Enumeration Wertnamen (z. B. "Ad" für ADO-Enumerationen.), "Rtf" für rich-Text-Enumerationen usw. verwenden.</span><span class="sxs-lookup"><span data-stu-id="dda91-149">**X DO NOT** use a prefix on enumeration value names (e.g., "ad" for ADO enums, "rtf" for rich text enums, etc.).</span></span>  
  
 <span data-ttu-id="dda91-150">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="dda91-150">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="dda91-151">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="dda91-151">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dda91-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dda91-152">See Also</span></span>  
 [<span data-ttu-id="dda91-153">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="dda91-153">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="dda91-154">Richtlinien für die Benennung</span><span class="sxs-lookup"><span data-stu-id="dda91-154">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
