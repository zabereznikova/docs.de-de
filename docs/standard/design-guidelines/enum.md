---
title: Enum-Entwurf
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, enumerations
- simple enumerations
- enumerations [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], enumerations
- flags enumerations
ms.assetid: dd53c952-9d9a-4736-86ff-9540e815d545
author: KrzysztofCwalina
ms.openlocfilehash: 36e1f62ab1b236d48a55f7c255ed406cc0efa488
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64615251"
---
# <a name="enum-design"></a><span data-ttu-id="4c531-102">Enum-Entwurf</span><span class="sxs-lookup"><span data-stu-id="4c531-102">Enum Design</span></span>
<span data-ttu-id="4c531-103">Enumerationen sind eine besondere Art von Werttyp.</span><span class="sxs-lookup"><span data-stu-id="4c531-103">Enums are a special kind of value type.</span></span> <span data-ttu-id="4c531-104">Es gibt zwei Arten von Enumerationen: Einfache Enumerationen und Flags-Enumerationen.</span><span class="sxs-lookup"><span data-stu-id="4c531-104">There are two kinds of enums: simple enums and flag enums.</span></span>  
  
 <span data-ttu-id="4c531-105">Einfache Enumerationen stellen kleine geschlossene Sätze von Optionen dar.</span><span class="sxs-lookup"><span data-stu-id="4c531-105">Simple enums represent small closed sets of choices.</span></span> <span data-ttu-id="4c531-106">Ein allgemeines Beispiel für die einfache Enumeration ist ein Satz von Farben.</span><span class="sxs-lookup"><span data-stu-id="4c531-106">A common example of the simple enum is a set of colors.</span></span>  
  
 <span data-ttu-id="4c531-107">Flags-Enumerationen dienen zur Unterstützung von bitweiser Operations für Enum-Werte.</span><span class="sxs-lookup"><span data-stu-id="4c531-107">Flag enums are designed to support bitwise operations on the enum values.</span></span> <span data-ttu-id="4c531-108">Ein allgemeines Beispiel für die Bitflags-Enum ist eine Liste von Optionen an.</span><span class="sxs-lookup"><span data-stu-id="4c531-108">A common example of the flags enum is a list of options.</span></span>  
  
 <span data-ttu-id="4c531-109">**✓ DO** mit, dass eine Enumeration typisieren Parameter, Eigenschaften und Rückgabewerte, die Sätze von Werten darstellen.</span><span class="sxs-lookup"><span data-stu-id="4c531-109">**✓ DO** use an enum to strongly type parameters, properties, and return values that represent sets of values.</span></span>  
  
 <span data-ttu-id="4c531-110">**✓ DO** statische Konstanten anstelle einer Enumeration begünstigen.</span><span class="sxs-lookup"><span data-stu-id="4c531-110">**✓ DO** favor using an enum instead of static constants.</span></span>  
  
 <span data-ttu-id="4c531-111">**X DO NOT** Enum für offene Gruppen (z. B. die Version des Betriebssystems, Namen von Ihrer Freunde usw.) verwenden.</span><span class="sxs-lookup"><span data-stu-id="4c531-111">**X DO NOT** use an enum for open sets (such as the operating system version, names of your friends, etc.).</span></span>  
  
 <span data-ttu-id="4c531-112">**X DO NOT** Geben Sie für die zukünftige Verwendung reservierte Enumerationswerte, die vorgesehen sind.</span><span class="sxs-lookup"><span data-stu-id="4c531-112">**X DO NOT** provide reserved enum values that are intended for future use.</span></span>  
  
 <span data-ttu-id="4c531-113">Sie können Werte immer der vorhandenen-Enumeration zu einem späteren Zeitpunkt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="4c531-113">You can always simply add values to the existing enum at a later stage.</span></span> <span data-ttu-id="4c531-114">Finden Sie unter [hinzufügen Werte zu Enumerationen](#add_value) ausführliche Informationen zum Hinzufügen von Werten für Enumerationen.</span><span class="sxs-lookup"><span data-stu-id="4c531-114">See [Adding Values to Enums](#add_value) for more details on adding values to enums.</span></span> <span data-ttu-id="4c531-115">Reservierten Werte einfach, verunreinigen den Satz von tatsächlichen Werten und tendenziell zu Benutzerfehlern führen.</span><span class="sxs-lookup"><span data-stu-id="4c531-115">Reserved values just pollute the set of real values and tend to lead to user errors.</span></span>  
  
 <span data-ttu-id="4c531-116">**X AVOID** öffentlich verfügbar machen Enumerationen mit nur einem Wert.</span><span class="sxs-lookup"><span data-stu-id="4c531-116">**X AVOID** publicly exposing enums with only one value.</span></span>  
  
 <span data-ttu-id="4c531-117">Üblicherweise zum Sicherstellen der zukünftige Erweiterbarkeit von C-APIs wird, um Methodensignaturen reservierte Parameter hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="4c531-117">A common practice for ensuring future extensibility of C APIs is to add reserved parameters to method signatures.</span></span> <span data-ttu-id="4c531-118">Diese reservierte Parameter können als Enumerationen mit einem einzigen Standardwert ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="4c531-118">Such reserved parameters can be expressed as enums with a single default value.</span></span> <span data-ttu-id="4c531-119">Dies sollte nicht in der verwalteten APIs ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4c531-119">This should not be done in managed APIs.</span></span> <span data-ttu-id="4c531-120">Überladen von Methoden ermöglicht das Hinzufügen von Parametern in zukünftigen Versionen.</span><span class="sxs-lookup"><span data-stu-id="4c531-120">Method overloading allows adding parameters in future releases.</span></span>  
  
 <span data-ttu-id="4c531-121">**X DO NOT** Sentinel Werte in Enumerationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="4c531-121">**X DO NOT** include sentinel values in enums.</span></span>  
  
 <span data-ttu-id="4c531-122">Obwohl sie manchmal hilfreich, Framework-Entwickler sind, sind die Werte der Sentinel für Benutzer von Framework verwirrend.</span><span class="sxs-lookup"><span data-stu-id="4c531-122">Although they are sometimes helpful to framework developers, sentinel values are confusing to users of the framework.</span></span> <span data-ttu-id="4c531-123">Sie werden zum Nachverfolgen des Zustands anstelle von wird einer der Werte der Enumeration aus der Gruppe, die durch die Enumeration dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="4c531-123">They are used to track the state of the enum rather than being one of the values from the set represented by the enum.</span></span>  
  
 <span data-ttu-id="4c531-124">**✓ DO** Geben Sie einen Wert von 0 zu einfachen Enumerationen.</span><span class="sxs-lookup"><span data-stu-id="4c531-124">**✓ DO** provide a value of zero on simple enums.</span></span>  
  
 <span data-ttu-id="4c531-125">Rufen Sie den Wert beispielsweise "None".</span><span class="sxs-lookup"><span data-stu-id="4c531-125">Consider calling the value something like "None."</span></span> <span data-ttu-id="4c531-126">Wenn solche Werte nicht für diese bestimmte Enumeration geeignet ist, sollte der am häufigsten verwendete Standardwert für die Enumeration den zugrunde liegenden Wert von 0 (null) zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="4c531-126">If such a value is not appropriate for this particular enum, the most common default value for the enum should be assigned the underlying value of zero.</span></span>  
  
 <span data-ttu-id="4c531-127">**✓ CONSIDER** mit <xref:System.Int32> (die Standardeinstellung in den meisten Programmiersprachen) als zugrunde liegende Typ einer Enumeration, wenn eine der folgenden Aussagen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="4c531-127">**✓ CONSIDER** using <xref:System.Int32> (the default in most programming languages) as the underlying type of an enum unless any of the following is true:</span></span>  
  
- <span data-ttu-id="4c531-128">Die Enumeration ist eine Flags-Enumeration, und Sie haben mehr als 32-Flags oder erwarten, dass zukünftig mehr.</span><span class="sxs-lookup"><span data-stu-id="4c531-128">The enum is a flags enum and you have more than 32 flags, or expect to have more in the future.</span></span>  
  
- <span data-ttu-id="4c531-129">Der zugrunde liegende Typ muss anders als <xref:System.Int32> für Interoperabilität mit nicht verwaltetem Code erwartet andere Größe Enumerationen erleichtern.</span><span class="sxs-lookup"><span data-stu-id="4c531-129">The underlying type needs to be different than <xref:System.Int32> for easier interoperability with unmanaged code expecting different-size enums.</span></span>  
  
- <span data-ttu-id="4c531-130">Ein kleinerer zugrunde liegender Typ führt zu beträchtlichen einsparungen beim Speicherplatz.</span><span class="sxs-lookup"><span data-stu-id="4c531-130">A smaller underlying type would result in substantial savings in space.</span></span> <span data-ttu-id="4c531-131">Wenn Sie erwarten, die Enumeration dass, die hauptsächlich als Argument für die ablaufsteuerung verwendet werden, ist die Größe kaum einen Unterschied.</span><span class="sxs-lookup"><span data-stu-id="4c531-131">If you expect the enum to be used mainly as an argument for flow of control, the size makes little difference.</span></span> <span data-ttu-id="4c531-132">Die einsparungen können erheblich sein wenn:</span><span class="sxs-lookup"><span data-stu-id="4c531-132">The size savings might be significant if:</span></span>  
  
    - <span data-ttu-id="4c531-133">Sie erwarten, dass die Enumeration als ein Feld in einer sehr häufig instanziierten Struktur oder Klasse verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4c531-133">You expect the enum to be used as a field in a very frequently instantiated structure or class.</span></span>  
  
    - <span data-ttu-id="4c531-134">Sie erwarten, dass Benutzer große Arrays oder Auflistungen der Enum-Instanzen erstellen.</span><span class="sxs-lookup"><span data-stu-id="4c531-134">You expect users to create large arrays or collections of the enum instances.</span></span>  
  
    - <span data-ttu-id="4c531-135">Sie erwarten, dass eine große Anzahl von Instanzen der Enumeration serialisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="4c531-135">You expect a large number of instances of the enum to be serialized.</span></span>  
  
 <span data-ttu-id="4c531-136">Für die speicherauslastung, denken Sie daran, dass verwaltete Objekte immer `DWORD`-ausgerichtet, weshalb Sie effektiv mehrere Enumerationen oder andere kleineren Strukturen in einer Instanz mit eine kleineren Enumeration zu platzieren, um einen Unterschied machen, da die Größe der gesamten Instanz immer jetzt bis zu rundende eine `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="4c531-136">For in-memory usage, be aware that managed objects are always `DWORD`-aligned, so you effectively need multiple enums or other small structures in an instance to pack a smaller enum with in order to make a difference, because the total instance size is always going to be rounded up to a `DWORD`.</span></span>  
  
 <span data-ttu-id="4c531-137">**✓ DO** benennen Flags-Enumerationen mit Nomen im plural oder Substantivausdrücke und einfache Enumerationen mit Nomen im singular oder nominale Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="4c531-137">**✓ DO** name flag enums with plural nouns or noun phrases and simple enums with singular nouns or noun phrases.</span></span>  
  
 <span data-ttu-id="4c531-138">**X DO NOT** erweitern <xref:System.Enum?displayProperty=nameWithType> direkt.</span><span class="sxs-lookup"><span data-stu-id="4c531-138">**X DO NOT** extend <xref:System.Enum?displayProperty=nameWithType> directly.</span></span>  
  
 <span data-ttu-id="4c531-139"><xref:System.Enum?displayProperty=nameWithType> ein spezieller Typ wird von der CLR zum Erstellen von benutzerdefinierten Enumerationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4c531-139"><xref:System.Enum?displayProperty=nameWithType> is a special type used by the CLR to create user-defined enumerations.</span></span> <span data-ttu-id="4c531-140">Die meisten Programmiersprachen bieten ein Programmierelement, das Zugriff auf diese Funktionalität bietet.</span><span class="sxs-lookup"><span data-stu-id="4c531-140">Most programming languages provide a programming element that gives you access to this functionality.</span></span> <span data-ttu-id="4c531-141">Z. B. in c# die `enum` Schlüsselwort wird verwendet, um eine Enumeration zu definieren.</span><span class="sxs-lookup"><span data-stu-id="4c531-141">For example, in C# the `enum` keyword is used to define an enumeration.</span></span>  
  
<a name="design"></a>   
### <a name="designing-flag-enums"></a><span data-ttu-id="4c531-142">Entwerfen von Flags-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="4c531-142">Designing Flag Enums</span></span>  
 <span data-ttu-id="4c531-143">**✓ DO** gelten die <xref:System.FlagsAttribute?displayProperty=nameWithType> Flags-Enumerationen.</span><span class="sxs-lookup"><span data-stu-id="4c531-143">**✓ DO** apply the <xref:System.FlagsAttribute?displayProperty=nameWithType> to flag enums.</span></span> <span data-ttu-id="4c531-144">Dieses Attribut nicht auf einfache Enumerationen anwenden.</span><span class="sxs-lookup"><span data-stu-id="4c531-144">Do not apply this attribute to simple enums.</span></span>  
  
 <span data-ttu-id="4c531-145">**✓ DO** Potenzen von 2 für die Kennzeichnung Enum-Werte verwenden, damit diese problemlos kombiniert werden, können mit dem bitweisen OR-Operation.</span><span class="sxs-lookup"><span data-stu-id="4c531-145">**✓ DO** use powers of two for the flag enum values so they can be freely combined using the bitwise OR operation.</span></span>  
  
 <span data-ttu-id="4c531-146">**✓ CONSIDER** Kombinationen der Flags verwendet spezielle Enumerationswerte für häufig bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4c531-146">**✓ CONSIDER** providing special enum values for commonly used combinations of flags.</span></span>  
  
 <span data-ttu-id="4c531-147">Bitweise Operationen sind ein Konzept, das erweiterte und sollte nicht für einfache Aufgaben erforderlich sein.</span><span class="sxs-lookup"><span data-stu-id="4c531-147">Bitwise operations are an advanced concept and should not be required for simple tasks.</span></span> <span data-ttu-id="4c531-148"><xref:System.IO.FileAccess.ReadWrite> ist ein Beispiel für solche ein spezieller Wert.</span><span class="sxs-lookup"><span data-stu-id="4c531-148"><xref:System.IO.FileAccess.ReadWrite> is an example of such a special value.</span></span>  
  
 <span data-ttu-id="4c531-149">**X AVOID** Erstellen von Flags-Enumerationen, in denen bestimmte Kombinationen von Werten ungültig sind.</span><span class="sxs-lookup"><span data-stu-id="4c531-149">**X AVOID** creating flag enums where certain combinations of values are invalid.</span></span>  
  
 <span data-ttu-id="4c531-150">**X AVOID** mit Flagwerten Enum 0 (null), wenn der Wert "deaktiviert sind alle Flags" darstellt und Sie heißt entsprechend, wie der nächsten Richtlinie vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="4c531-150">**X AVOID** using flag enum values of zero unless the value represents "all flags are cleared" and is named appropriately, as prescribed by the next guideline.</span></span>  
  
 <span data-ttu-id="4c531-151">**✓ DO** benennen Sie den Wert 0 (null) von Flags-Enumerationen `None`.</span><span class="sxs-lookup"><span data-stu-id="4c531-151">**✓ DO** name the zero value of flag enums `None`.</span></span> <span data-ttu-id="4c531-152">Für eine Flags-Enumeration muss der Wert immer bedeutet, dass "alle Flags deaktiviert werden."</span><span class="sxs-lookup"><span data-stu-id="4c531-152">For a flag enum, the value must always mean "all flags are cleared."</span></span>  
  
<a name="add_value"></a>   
### <a name="adding-value-to-enums"></a><span data-ttu-id="4c531-153">Enumerationen Wert hinzufügen</span><span class="sxs-lookup"><span data-stu-id="4c531-153">Adding Value to Enums</span></span>  
 <span data-ttu-id="4c531-154">Es ist üblich, feststellen, dass Sie eine Enumeration Werte hinzufügen, nachdem Sie bereits geliefert haben möchten.</span><span class="sxs-lookup"><span data-stu-id="4c531-154">It is very common to discover that you need to add values to an enum after you have already shipped it.</span></span> <span data-ttu-id="4c531-155">Es liegt einer potenziellen Problems "Anwendungskompatibilität" bei der neu hinzugefügte Wert, über eine vorhandene API zurückgegeben wird, schlecht geschriebene Anwendungen den neuen Wert nicht ordnungsgemäß verarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="4c531-155">There is a potential application compatibility problem when the newly added value is returned from an existing API, because poorly written applications might not handle the new value correctly.</span></span>  
  
 <span data-ttu-id="4c531-156">**✓ CONSIDER** Enumerationen, die trotz eines geringen Kompatibilitätsproblems Werte hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4c531-156">**✓ CONSIDER** adding values to enums, despite a small compatibility risk.</span></span>  
  
 <span data-ttu-id="4c531-157">Wenn Sie echte Daten über Anwendungsinkompatibilitäten durch Hinzufügungen zu einer Enumeration verursacht haben, erwägen Sie eine neue API, die die alten und neuen Werte zurückgibt, und Beenden der alten API, die fortgesetzt werden nur die alten Werte zurückgeben soll.</span><span class="sxs-lookup"><span data-stu-id="4c531-157">If you have real data about application incompatibilities caused by additions to an enum, consider adding a new API that returns the new and old values, and deprecate the old API, which should continue returning just the old values.</span></span> <span data-ttu-id="4c531-158">Dadurch wird sichergestellt, dass Ihre vorhandenen Anwendungen kompatibel bleiben.</span><span class="sxs-lookup"><span data-stu-id="4c531-158">This will ensure that your existing applications remain compatible.</span></span>  
  
 <span data-ttu-id="4c531-159">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="4c531-159">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="4c531-160">*Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*</span><span class="sxs-lookup"><span data-stu-id="4c531-160">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c531-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4c531-161">See also</span></span>

- [<span data-ttu-id="4c531-162">Richtlinien für den Entwurf von Typen</span><span class="sxs-lookup"><span data-stu-id="4c531-162">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="4c531-163">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="4c531-163">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
