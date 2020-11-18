---
title: Enum-Entwurf
description: Entwurf für Enumerationswerte, die eine besondere Art von Werttyp sind. Einfache Enumerationen enthalten kleine, geschlossene Sätze von Optionen. Flag-Enumerationen unterstützen bitweise Vorgänge für Enumerationswerte.
ms.date: 10/22/2008
helpviewer_keywords:
- type design guidelines, enumerations
- simple enumerations
- enumerations [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], enumerations
- flags enumerations
ms.assetid: dd53c952-9d9a-4736-86ff-9540e815d545
ms.openlocfilehash: a2e19197b114daa2a0956a6fc87231a6a81de916
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821358"
---
# <a name="enum-design"></a><span data-ttu-id="0e814-105">Enum-Entwurf</span><span class="sxs-lookup"><span data-stu-id="0e814-105">Enum Design</span></span>

<span data-ttu-id="0e814-106">Enumerationswerte sind eine besondere Art von Werttyp.</span><span class="sxs-lookup"><span data-stu-id="0e814-106">Enums are a special kind of value type.</span></span> <span data-ttu-id="0e814-107">Es gibt zwei Arten von Aufständen: einfache Aufteilungs-und flagumerationszeichen.</span><span class="sxs-lookup"><span data-stu-id="0e814-107">There are two kinds of enums: simple enums and flag enums.</span></span>

<span data-ttu-id="0e814-108">Einfache Aufstellungen stellen kleine geschlossene Sätze von Auswahlmöglichkeiten dar.</span><span class="sxs-lookup"><span data-stu-id="0e814-108">Simple enums represent small closed sets of choices.</span></span> <span data-ttu-id="0e814-109">Ein gängiges Beispiel für die einfache-Enumeration ist ein Satz von Farben.</span><span class="sxs-lookup"><span data-stu-id="0e814-109">A common example of the simple enum is a set of colors.</span></span>

<span data-ttu-id="0e814-110">Flag-Enumerationen sind so konzipiert, dass bitweise Vorgänge für die Enumerationswerte unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="0e814-110">Flag enums are designed to support bitwise operations on the enum values.</span></span> <span data-ttu-id="0e814-111">Ein gängiges Beispiel für die Flags-Enumeration ist eine Liste von Optionen.</span><span class="sxs-lookup"><span data-stu-id="0e814-111">A common example of the flags enum is a list of options.</span></span>

<span data-ttu-id="0e814-112">✔️ eine Enumeration verwenden, um Parameter, Eigenschaften und Rückgabewerte, die Sätze von Werten darstellen, stark einzugeben.</span><span class="sxs-lookup"><span data-stu-id="0e814-112">✔️ DO use an enum to strongly type parameters, properties, and return values that represent sets of values.</span></span>

<span data-ttu-id="0e814-113">✔️ bevorzugen die Verwendung einer Enumeration anstelle von statischen Konstanten.</span><span class="sxs-lookup"><span data-stu-id="0e814-113">✔️ DO favor using an enum instead of static constants.</span></span>

<span data-ttu-id="0e814-114">❌ Verwenden Sie keine Enumeration für geöffnete Sätze (z. b. die Betriebssystemversion, die Namen der Freunde usw.).</span><span class="sxs-lookup"><span data-stu-id="0e814-114">❌ DO NOT use an enum for open sets (such as the operating system version, names of your friends, etc.).</span></span>

<span data-ttu-id="0e814-115">❌ Geben Sie keine reservierten Enumerationswerte an, die für die zukünftige Verwendung vorgesehen sind.</span><span class="sxs-lookup"><span data-stu-id="0e814-115">❌ DO NOT provide reserved enum values that are intended for future use.</span></span>

<span data-ttu-id="0e814-116">Sie können der vorhandenen Enumeration jederzeit einfach Werte hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0e814-116">You can always simply add values to the existing enum at a later stage.</span></span> <span data-ttu-id="0e814-117">Weitere Informationen zum Hinzufügen von Werten zu enumeraten finden [Sie unter Hinzufügen von Werten zu](#add_value) Enumerationswerten</span><span class="sxs-lookup"><span data-stu-id="0e814-117">See [Adding Values to Enums](#add_value) for more details on adding values to enums.</span></span> <span data-ttu-id="0e814-118">Reservierte Werte verschmutzen lediglich den Satz realer Werte und führen tendenziell zu Benutzerfehlern.</span><span class="sxs-lookup"><span data-stu-id="0e814-118">Reserved values just pollute the set of real values and tend to lead to user errors.</span></span>

<span data-ttu-id="0e814-119">❌ Vermeiden Sie die öffentliche Offenlegung von Enumerationswerten mit nur einem Wert</span><span class="sxs-lookup"><span data-stu-id="0e814-119">❌ AVOID publicly exposing enums with only one value.</span></span>

<span data-ttu-id="0e814-120">Eine gängige Vorgehensweise, um die zukünftige Erweiterbarkeit von C-APIs sicherzustellen, besteht darin, den Methoden Signaturen reservierte Parameter hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="0e814-120">A common practice for ensuring future extensibility of C APIs is to add reserved parameters to method signatures.</span></span> <span data-ttu-id="0e814-121">Solche reservierten Parameter können als Enumerationswerte mit einem einzelnen Standardwert ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="0e814-121">Such reserved parameters can be expressed as enums with a single default value.</span></span> <span data-ttu-id="0e814-122">Dies sollte nicht in verwalteten APIs erfolgen.</span><span class="sxs-lookup"><span data-stu-id="0e814-122">This should not be done in managed APIs.</span></span> <span data-ttu-id="0e814-123">Die Methoden Überladung ermöglicht das Hinzufügen von Parametern in zukünftigen Versionen.</span><span class="sxs-lookup"><span data-stu-id="0e814-123">Method overloading allows adding parameters in future releases.</span></span>

<span data-ttu-id="0e814-124">❌ Fügen Sie keine Sentinel-Werte in Enumerationswerte ein.</span><span class="sxs-lookup"><span data-stu-id="0e814-124">❌ DO NOT include sentinel values in enums.</span></span>

<span data-ttu-id="0e814-125">Obwohl Sie für Frameworkentwickler manchmal hilfreich sind, sind Sentinel-Werte für Benutzer des Frameworks verwirrend.</span><span class="sxs-lookup"><span data-stu-id="0e814-125">Although they are sometimes helpful to framework developers, sentinel values are confusing to users of the framework.</span></span> <span data-ttu-id="0e814-126">Sie werden verwendet, um den Zustand der Enumeration zu verfolgen, anstatt einen der Werte aus dem Satz zu verwenden, der durch die Enumeration repräsentiert wird.</span><span class="sxs-lookup"><span data-stu-id="0e814-126">They are used to track the state of the enum rather than being one of the values from the set represented by the enum.</span></span>

<span data-ttu-id="0e814-127">✔️ für einfache Enumerationswerte den Wert 0 (null) bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0e814-127">✔️ DO provide a value of zero on simple enums.</span></span>

<span data-ttu-id="0e814-128">Es empfiehlt sich, den Wert in etwa "None" zu aufrufen.</span><span class="sxs-lookup"><span data-stu-id="0e814-128">Consider calling the value something like "None."</span></span> <span data-ttu-id="0e814-129">Wenn ein solcher Wert für diese bestimmte Enumeration nicht geeignet ist, sollte dem am häufigsten voreingestellten Standardwert für die Enumeration der zugrunde liegende Wert 0 (null) zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="0e814-129">If such a value is not appropriate for this particular enum, the most common default value for the enum should be assigned the underlying value of zero.</span></span>

<span data-ttu-id="0e814-130">✔️ sollten Sie die Verwendung von <xref:System.Int32> (standardmäßig in den meisten Programmiersprachen) als zugrunde liegenden Typ einer-Aufzählung in Erwägung gezogen, es sei denn, eine der folgenden ist true</span><span class="sxs-lookup"><span data-stu-id="0e814-130">✔️ CONSIDER using <xref:System.Int32> (the default in most programming languages) as the underlying type of an enum unless any of the following is true:</span></span>

- <span data-ttu-id="0e814-131">Die Enumeration ist eine Flags-Enumeration, und Sie verfügen über mehr als 32 Flags oder erwarten, dass in der Zukunft mehr vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="0e814-131">The enum is a flags enum and you have more than 32 flags, or expect to have more in the future.</span></span>

- <span data-ttu-id="0e814-132">Der zugrunde liegende Typ muss sich von der <xref:System.Int32> einfacheren Interoperabilität mit nicht verwaltetem Code unterscheiden, der andere enums erwartet.</span><span class="sxs-lookup"><span data-stu-id="0e814-132">The underlying type needs to be different than <xref:System.Int32> for easier interoperability with unmanaged code expecting different-size enums.</span></span>

- <span data-ttu-id="0e814-133">Ein kleinerer zugrunde liegender Typ führt zu erheblichen Einsparungen im Bereich.</span><span class="sxs-lookup"><span data-stu-id="0e814-133">A smaller underlying type would result in substantial savings in space.</span></span> <span data-ttu-id="0e814-134">Wenn Sie davon ausgehen, dass die Aufzählung hauptsächlich als Argument für die Ablauf Steuerung verwendet werden soll, hat die Größe kaum einen Unterschied.</span><span class="sxs-lookup"><span data-stu-id="0e814-134">If you expect the enum to be used mainly as an argument for flow of control, the size makes little difference.</span></span> <span data-ttu-id="0e814-135">Die Größen Einsparungen können in folgenden Größen erheblich sein:</span><span class="sxs-lookup"><span data-stu-id="0e814-135">The size savings might be significant if:</span></span>

  - <span data-ttu-id="0e814-136">Sie erwarten, dass die Enumeration als Feld in einer sehr häufig instanziierten Struktur oder Klasse verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0e814-136">You expect the enum to be used as a field in a very frequently instantiated structure or class.</span></span>

  - <span data-ttu-id="0e814-137">Sie erwarten, dass Benutzer große Arrays oder Auflistungen der Enumeration-Instanzen erstellen.</span><span class="sxs-lookup"><span data-stu-id="0e814-137">You expect users to create large arrays or collections of the enum instances.</span></span>

  - <span data-ttu-id="0e814-138">Sie erwarten, dass eine große Anzahl von Instanzen der Enumeration serialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="0e814-138">You expect a large number of instances of the enum to be serialized.</span></span>

<span data-ttu-id="0e814-139">Beachten Sie bei der in-Memory-Verwendung, dass verwaltete Objekte immer `DWORD` ausgerichtet sind, sodass Sie in einer Instanz tatsächlich mehrere Enumerationen oder andere kleine Strukturen benötigen, um einen Unterschied zu erstellen, da die gesamte instanzgröße immer auf einen aufgerundet wird `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="0e814-139">For in-memory usage, be aware that managed objects are always `DWORD`-aligned, so you effectively need multiple enums or other small structures in an instance to pack a smaller enum with in order to make a difference, because the total instance size is always going to be rounded up to a `DWORD`.</span></span>

<span data-ttu-id="0e814-140">✔️ durch eine namensflag-Enumerationen mit Plural-Nomen oder nominalen Ausdrücken und einfachen Enumerationen mit Singular-Nomen oder Substantiv Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="0e814-140">✔️ DO name flag enums with plural nouns or noun phrases and simple enums with singular nouns or noun phrases.</span></span>

<span data-ttu-id="0e814-141">❌ Nicht direkt erweitern <xref:System.Enum?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="0e814-141">❌ DO NOT extend <xref:System.Enum?displayProperty=nameWithType> directly.</span></span>

<span data-ttu-id="0e814-142"><xref:System.Enum?displayProperty=nameWithType> ist ein spezieller Typ, der von der CLR verwendet wird, um benutzerdefinierte Enumerationen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0e814-142"><xref:System.Enum?displayProperty=nameWithType> is a special type used by the CLR to create user-defined enumerations.</span></span> <span data-ttu-id="0e814-143">Die meisten Programmiersprachen bieten ein Programmier Element, das Ihnen den Zugriff auf diese Funktionalität ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="0e814-143">Most programming languages provide a programming element that gives you access to this functionality.</span></span> <span data-ttu-id="0e814-144">Beispielsweise wird in c# das- `enum` Schlüsselwort verwendet, um eine Enumeration zu definieren.</span><span class="sxs-lookup"><span data-stu-id="0e814-144">For example, in C# the `enum` keyword is used to define an enumeration.</span></span>

<a name="design"></a>

### <a name="designing-flag-enums"></a><span data-ttu-id="0e814-145">Entwerfen von Flag-Aufständen</span><span class="sxs-lookup"><span data-stu-id="0e814-145">Designing Flag Enums</span></span>

<span data-ttu-id="0e814-146">✔️ anwenden, um auf-auf-auf-auf-auf- <xref:System.FlagsAttribute?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="0e814-146">✔️ DO apply the <xref:System.FlagsAttribute?displayProperty=nameWithType> to flag enums.</span></span> <span data-ttu-id="0e814-147">Wenden Sie dieses Attribut nicht auf einfache auffüge Aufgaben an.</span><span class="sxs-lookup"><span data-stu-id="0e814-147">Do not apply this attribute to simple enums.</span></span>

<span data-ttu-id="0e814-148">✔️ für die Flag-Enumerationswerte zwei Möglichkeiten verwenden, damit Sie mit der bitweisen OR-Operation frei kombiniert werden können.</span><span class="sxs-lookup"><span data-stu-id="0e814-148">✔️ DO use powers of two for the flag enum values so they can be freely combined using the bitwise OR operation.</span></span>

<span data-ttu-id="0e814-149">✔️ sollten besondere Enumerationswerte für häufig verwendete Kombinationen von Flags bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="0e814-149">✔️ CONSIDER providing special enum values for commonly used combinations of flags.</span></span>

<span data-ttu-id="0e814-150">Bitweise Vorgänge sind ein erweitertes Konzept, das für einfache Aufgaben nicht erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="0e814-150">Bitwise operations are an advanced concept and should not be required for simple tasks.</span></span> <span data-ttu-id="0e814-151"><xref:System.IO.FileAccess.ReadWrite> ein Beispiel für einen solchen besonderen Wert.</span><span class="sxs-lookup"><span data-stu-id="0e814-151"><xref:System.IO.FileAccess.ReadWrite> is an example of such a special value.</span></span>

<span data-ttu-id="0e814-152">❌ Vermeiden Sie das Erstellen von Flag-enumeraten, wenn bestimmte Kombinationen von Werten ungültig sind</span><span class="sxs-lookup"><span data-stu-id="0e814-152">❌ AVOID creating flag enums where certain combinations of values are invalid.</span></span>

<span data-ttu-id="0e814-153">❌ Vermeiden Sie die Verwendung von Flag-Enumerationswerten von 0 (null), es sei denn, der Wert steht für "alle Flags sind gelöscht" und entsprechend der Bezeichnung durch die nächste Richtlinie</span><span class="sxs-lookup"><span data-stu-id="0e814-153">❌ AVOID using flag enum values of zero unless the value represents "all flags are cleared" and is named appropriately, as prescribed by the next guideline.</span></span>

<span data-ttu-id="0e814-154">✔️ den Wert 0 (null) der Flag-Enumerationsnamen `None` .</span><span class="sxs-lookup"><span data-stu-id="0e814-154">✔️ DO name the zero value of flag enums `None`.</span></span> <span data-ttu-id="0e814-155">Bei einer Flag-Enumeration muss der Wert immer lauten, dass alle Flags gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="0e814-155">For a flag enum, the value must always mean "all flags are cleared."</span></span>

<a name="add_value"></a>

### <a name="adding-value-to-enums"></a><span data-ttu-id="0e814-156">Hinzufügen von Wert zu enumeraten</span><span class="sxs-lookup"><span data-stu-id="0e814-156">Adding Value to Enums</span></span>

<span data-ttu-id="0e814-157">Es kommt häufig vor, dass Sie einer Enumeration Werte hinzufügen müssen, nachdem Sie Sie bereits geliefert haben.</span><span class="sxs-lookup"><span data-stu-id="0e814-157">It is very common to discover that you need to add values to an enum after you have already shipped it.</span></span> <span data-ttu-id="0e814-158">Es gibt ein potenzielles Problem mit der Anwendungs Kompatibilität, wenn der neu hinzugefügte Wert von einer vorhandenen API zurückgegeben wird, da schlecht geschriebene Anwendungen den neuen Wert möglicherweise nicht ordnungsgemäß verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="0e814-158">There is a potential application compatibility problem when the newly added value is returned from an existing API, because poorly written applications might not handle the new value correctly.</span></span>

<span data-ttu-id="0e814-159">✔️ ggf. Werte zu Enumerationswerten hinzufügen, trotz eines geringen Kompatibilitäts Risikos.</span><span class="sxs-lookup"><span data-stu-id="0e814-159">✔️ CONSIDER adding values to enums, despite a small compatibility risk.</span></span>

<span data-ttu-id="0e814-160">Wenn Sie über echte Daten über Anwendungs Inkompatibilitäten verfügen, die durch Ergänzungen zu einer Enumeration verursacht werden, sollten Sie eine neue API hinzufügen, die die neuen und alten Werte zurückgibt, und die alte API als veraltet kennzeichnen, sodass nur die alten Werte zurückgegeben werden sollten.</span><span class="sxs-lookup"><span data-stu-id="0e814-160">If you have real data about application incompatibilities caused by additions to an enum, consider adding a new API that returns the new and old values, and deprecate the old API, which should continue returning just the old values.</span></span> <span data-ttu-id="0e814-161">Dadurch wird sichergestellt, dass Ihre vorhandenen Anwendungen kompatibel bleiben.</span><span class="sxs-lookup"><span data-stu-id="0e814-161">This will ensure that your existing applications remain compatible.</span></span>

<span data-ttu-id="0e814-162">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="0e814-162">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

<span data-ttu-id="0e814-163">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="0e814-163">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="0e814-164">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e814-164">See also</span></span>

- [<span data-ttu-id="0e814-165">Typentwurfs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="0e814-165">Type Design Guidelines</span></span>](type.md)
- [<span data-ttu-id="0e814-166">Framework-Entwurfs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="0e814-166">Framework Design Guidelines</span></span>](index.md)
