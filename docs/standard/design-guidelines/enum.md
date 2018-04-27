---
title: Enum-Entwurf
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- type design guidelines, enumerations
- simple enumerations
- enumerations [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], enumerations
- flags enumerations
ms.assetid: dd53c952-9d9a-4736-86ff-9540e815d545
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c3e89567761367ddcd67078b138c15b982a0d666
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="enum-design"></a><span data-ttu-id="03dfd-102">Enum-Entwurf</span><span class="sxs-lookup"><span data-stu-id="03dfd-102">Enum Design</span></span>
<span data-ttu-id="03dfd-103">Enumerationen sind eine besondere Art von Werttyp.</span><span class="sxs-lookup"><span data-stu-id="03dfd-103">Enums are a special kind of value type.</span></span> <span data-ttu-id="03dfd-104">Es gibt zwei Arten von Enumerationen: Einfache Enumerationen und Flags-Enumerationen.</span><span class="sxs-lookup"><span data-stu-id="03dfd-104">There are two kinds of enums: simple enums and flag enums.</span></span>  
  
 <span data-ttu-id="03dfd-105">Einfache Enumerationen stellen kleine geschlossene Sätze von Optionen dar.</span><span class="sxs-lookup"><span data-stu-id="03dfd-105">Simple enums represent small closed sets of choices.</span></span> <span data-ttu-id="03dfd-106">Ein gängiges Beispiel der einfachen Enumeration ist ein Satz von Farben.</span><span class="sxs-lookup"><span data-stu-id="03dfd-106">A common example of the simple enum is a set of colors.</span></span>  
  
 <span data-ttu-id="03dfd-107">Flags-Enumerationen dienen zur Unterstützung von bitweiser Operations für den Enum-Werte.</span><span class="sxs-lookup"><span data-stu-id="03dfd-107">Flag enums are designed to support bitwise operations on the enum values.</span></span> <span data-ttu-id="03dfd-108">Ein gängiges Beispiel Flags-Enumeration wird eine Liste der Optionen an.</span><span class="sxs-lookup"><span data-stu-id="03dfd-108">A common example of the flags enum is a list of options.</span></span>  
  
 <span data-ttu-id="03dfd-109">**Führen Sie ✓** mit, dass eine Enumeration typisieren Parameter, Eigenschaften und Rückgabewerte, die Sätze von Werten darstellen.</span><span class="sxs-lookup"><span data-stu-id="03dfd-109">**✓ DO** use an enum to strongly type parameters, properties, and return values that represent sets of values.</span></span>  
  
 <span data-ttu-id="03dfd-110">**Führen Sie ✓** statische Konstanten anstelle einer Enumeration begünstigen.</span><span class="sxs-lookup"><span data-stu-id="03dfd-110">**✓ DO** favor using an enum instead of static constants.</span></span>  
  
 <span data-ttu-id="03dfd-111">**X nicht** Enum für offene Gruppen (z. B. die Version des Betriebssystems, Namen von Ihrer Freunde usw.) verwenden.</span><span class="sxs-lookup"><span data-stu-id="03dfd-111">**X DO NOT** use an enum for open sets (such as the operating system version, names of your friends, etc.).</span></span>  
  
 <span data-ttu-id="03dfd-112">**X nicht** Geben Sie für die zukünftige Verwendung reservierte Enumerationswerte, die vorgesehen sind.</span><span class="sxs-lookup"><span data-stu-id="03dfd-112">**X DO NOT** provide reserved enum values that are intended for future use.</span></span>  
  
 <span data-ttu-id="03dfd-113">Sie können Werte immer einfach der vorhandenen Enumeration zu einem späteren Zeitpunkt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="03dfd-113">You can always simply add values to the existing enum at a later stage.</span></span> <span data-ttu-id="03dfd-114">Finden Sie unter [Hinzufügen von Werten für Enumerationen](#add_value) detaillierte Informationen zum Hinzufügen von Werten für Enumerationen.</span><span class="sxs-lookup"><span data-stu-id="03dfd-114">See [Adding Values to Enums](#add_value) for more details on adding values to enums.</span></span> <span data-ttu-id="03dfd-115">Reservierten Werte einfach dadurch die echte Wertemenge und tendenziell zu Benutzerfehler führen.</span><span class="sxs-lookup"><span data-stu-id="03dfd-115">Reserved values just pollute the set of real values and tend to lead to user errors.</span></span>  
  
 <span data-ttu-id="03dfd-116">**X vermeiden** öffentlich verfügbar machen Enumerationen mit nur einem Wert.</span><span class="sxs-lookup"><span data-stu-id="03dfd-116">**X AVOID** publicly exposing enums with only one value.</span></span>  
  
 <span data-ttu-id="03dfd-117">Üblicherweise für zukünftige Erweiterungen der C-APIs sichergestellt wird Methodensignaturen reservierte Parameter hinzu.</span><span class="sxs-lookup"><span data-stu-id="03dfd-117">A common practice for ensuring future extensibility of C APIs is to add reserved parameters to method signatures.</span></span> <span data-ttu-id="03dfd-118">Solche reservierte Parameter können als Enumerationen mit einem einzelnen Wert ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="03dfd-118">Such reserved parameters can be expressed as enums with a single default value.</span></span> <span data-ttu-id="03dfd-119">Dies sollte nicht in der verwalteten APIs erfolgen.</span><span class="sxs-lookup"><span data-stu-id="03dfd-119">This should not be done in managed APIs.</span></span> <span data-ttu-id="03dfd-120">Überladen von Methoden ermöglicht das Hinzufügen von Parametern in zukünftigen Versionen.</span><span class="sxs-lookup"><span data-stu-id="03dfd-120">Method overloading allows adding parameters in future releases.</span></span>  
  
 <span data-ttu-id="03dfd-121">**X nicht** Sentinel Werte in Enumerationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="03dfd-121">**X DO NOT** include sentinel values in enums.</span></span>  
  
 <span data-ttu-id="03dfd-122">Obwohl sie manchmal hilfreich, Frameworkentwickler sind, sind Sentinel Werte für Benutzer von Framework verwirrend.</span><span class="sxs-lookup"><span data-stu-id="03dfd-122">Although they are sometimes helpful to framework developers, sentinel values are confusing to users of the framework.</span></span> <span data-ttu-id="03dfd-123">Sie werden verwendet, den Status der Enumeration, statt wird einer der Werte aus der Gruppe, dargestellt durch die Enumeration zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="03dfd-123">They are used to track the state of the enum rather than being one of the values from the set represented by the enum.</span></span>  
  
 <span data-ttu-id="03dfd-124">**Führen Sie ✓** Geben Sie einen Wert von 0 zu einfachen Enumerationen.</span><span class="sxs-lookup"><span data-stu-id="03dfd-124">**✓ DO** provide a value of zero on simple enums.</span></span>  
  
 <span data-ttu-id="03dfd-125">Rufen Sie den Wert etwa "None".</span><span class="sxs-lookup"><span data-stu-id="03dfd-125">Consider calling the value something like "None."</span></span> <span data-ttu-id="03dfd-126">Wenn ein solcher Wert nicht für diese bestimmte Enumeration geeignet ist, sollte der am häufigsten verwendete Standardwert für die Enumeration den zugrunde liegenden Wert von 0 (null) zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="03dfd-126">If such a value is not appropriate for this particular enum, the most common default value for the enum should be assigned the underlying value of zero.</span></span>  
  
 <span data-ttu-id="03dfd-127">**✓ GGF.** mit <xref:System.Int32> (die Standardeinstellung in den meisten Programmiersprachen) als zugrunde liegende Typ einer Enumeration, wenn eine der folgenden Aussagen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="03dfd-127">**✓ CONSIDER** using <xref:System.Int32> (the default in most programming languages) as the underlying type of an enum unless any of the following is true:</span></span>  
  
-   <span data-ttu-id="03dfd-128">Die Enumeration ist eine Flags-Enumeration, und Sie haben mehr als 32 Flags, oder voraussichtlich mehr in der Zukunft verbunden.</span><span class="sxs-lookup"><span data-stu-id="03dfd-128">The enum is a flags enum and you have more than 32 flags, or expect to have more in the future.</span></span>  
  
-   <span data-ttu-id="03dfd-129">Der zugrunde liegende Typ benötigt werden, anders als <xref:System.Int32> für Interoperabilität mit nicht verwaltetem Code erwartet andere Größe Enumerationen erleichtern.</span><span class="sxs-lookup"><span data-stu-id="03dfd-129">The underlying type needs to be different than <xref:System.Int32> for easier interoperability with unmanaged code expecting different-size enums.</span></span>  
  
-   <span data-ttu-id="03dfd-130">Eine kleinere zugrunde liegenden Typs führt zu erheblichen einsparungen im Raum.</span><span class="sxs-lookup"><span data-stu-id="03dfd-130">A smaller underlying type would result in substantial savings in space.</span></span> <span data-ttu-id="03dfd-131">Wenn Sie erwarten, dass ein Enum hauptsächlich als ein Argument für den steuerungsverlauf verwendet werden soll, wird die Größe nur ein geringer Unterschied.</span><span class="sxs-lookup"><span data-stu-id="03dfd-131">If you expect the enum to be used mainly as an argument for flow of control, the size makes little difference.</span></span> <span data-ttu-id="03dfd-132">Die Größe einsparungen können erheblich sein wenn:</span><span class="sxs-lookup"><span data-stu-id="03dfd-132">The size savings might be significant if:</span></span>  
  
    -   <span data-ttu-id="03dfd-133">Sie erwarten, dass die Enumeration als Feld in einer sehr häufig instanziierten Struktur oder Klasse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="03dfd-133">You expect the enum to be used as a field in a very frequently instantiated structure or class.</span></span>  
  
    -   <span data-ttu-id="03dfd-134">Sie erwarten, dass Benutzer große Arrays oder Auflistungen von Enum-Instanzen erstellen.</span><span class="sxs-lookup"><span data-stu-id="03dfd-134">You expect users to create large arrays or collections of the enum instances.</span></span>  
  
    -   <span data-ttu-id="03dfd-135">Sie erwarten, dass eine große Anzahl von Instanzen der Enumeration serialisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="03dfd-135">You expect a large number of instances of the enum to be serialized.</span></span>  
  
 <span data-ttu-id="03dfd-136">Für die Verwendung im Arbeitsspeicher, Bedenken Sie, dass verwaltete Objekte immer sind `DWORD`-ausgerichtet, sodass effektiv mehrere Enumerationen oder andere kleineren Strukturen in einer Instanz auf eine kleinere Aufzählung mit pack um einen Unterschied machen, da immer die gesamte Instanzgröße ist erforderlich zu rundende bis zu einem `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="03dfd-136">For in-memory usage, be aware that managed objects are always `DWORD`-aligned, so you effectively need multiple enums or other small structures in an instance to pack a smaller enum with in order to make a difference, because the total instance size is always going to be rounded up to a `DWORD`.</span></span>  
  
 <span data-ttu-id="03dfd-137">**Führen Sie ✓** benennen Flags-Enumerationen mit Nomen im plural oder Substantivausdrücke und einfache Enumerationen mit Nomen im singular oder nominale Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="03dfd-137">**✓ DO** name flag enums with plural nouns or noun phrases and simple enums with singular nouns or noun phrases.</span></span>  
  
 <span data-ttu-id="03dfd-138">**X nicht** erweitern <xref:System.Enum?displayProperty=nameWithType> direkt.</span><span class="sxs-lookup"><span data-stu-id="03dfd-138">**X DO NOT** extend <xref:System.Enum?displayProperty=nameWithType> directly.</span></span>  
  
 <span data-ttu-id="03dfd-139"><xref:System.Enum?displayProperty=nameWithType> eine besondere Art ist von der CLR zum Erstellen von benutzerdefinierten Enumerationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="03dfd-139"><xref:System.Enum?displayProperty=nameWithType> is a special type used by the CLR to create user-defined enumerations.</span></span> <span data-ttu-id="03dfd-140">Die meisten Programmiersprachen bieten ein Programmierelement, das Ihnen den Zugriff auf diese Funktionalität bietet.</span><span class="sxs-lookup"><span data-stu-id="03dfd-140">Most programming languages provide a programming element that gives you access to this functionality.</span></span> <span data-ttu-id="03dfd-141">Beispielsweise ist in c# die `enum` Schlüsselwort wird verwendet, um eine Enumeration zu definieren.</span><span class="sxs-lookup"><span data-stu-id="03dfd-141">For example, in C# the `enum` keyword is used to define an enumeration.</span></span>  
  
<a name="design"></a>   
### <a name="designing-flag-enums"></a><span data-ttu-id="03dfd-142">Entwerfen von Flags-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="03dfd-142">Designing Flag Enums</span></span>  
 <span data-ttu-id="03dfd-143">**Führen Sie ✓** gelten die <xref:System.FlagsAttribute?displayProperty=nameWithType> Flags-Enumerationen.</span><span class="sxs-lookup"><span data-stu-id="03dfd-143">**✓ DO** apply the <xref:System.FlagsAttribute?displayProperty=nameWithType> to flag enums.</span></span> <span data-ttu-id="03dfd-144">Dieses Attribut nicht auf einfache Enumerationen anwenden.</span><span class="sxs-lookup"><span data-stu-id="03dfd-144">Do not apply this attribute to simple enums.</span></span>  
  
 <span data-ttu-id="03dfd-145">**Führen Sie ✓** Potenzen von 2 für die Kennzeichnung Enum-Werte verwenden, damit diese problemlos kombiniert werden, können mit dem bitweisen OR-Operation.</span><span class="sxs-lookup"><span data-stu-id="03dfd-145">**✓ DO** use powers of two for the flag enum values so they can be freely combined using the bitwise OR operation.</span></span>  
  
 <span data-ttu-id="03dfd-146">**✓ GGF.** Kombinationen der Flags verwendet spezielle Enumerationswerte für häufig bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="03dfd-146">**✓ CONSIDER** providing special enum values for commonly used combinations of flags.</span></span>  
  
 <span data-ttu-id="03dfd-147">Bitweise Operationen sollte sind ein Konzept, das erweitert und nicht für einfache Aufgaben erforderlich.</span><span class="sxs-lookup"><span data-stu-id="03dfd-147">Bitwise operations are an advanced concept and should not be required for simple tasks.</span></span> <span data-ttu-id="03dfd-148"><xref:System.IO.FileAccess.ReadWrite> ist ein Beispiel eines speziellen Werts.</span><span class="sxs-lookup"><span data-stu-id="03dfd-148"><xref:System.IO.FileAccess.ReadWrite> is an example of such a special value.</span></span>  
  
 <span data-ttu-id="03dfd-149">**X vermeiden** Erstellen von Flags-Enumerationen, in denen bestimmte Kombinationen von Werten ungültig sind.</span><span class="sxs-lookup"><span data-stu-id="03dfd-149">**X AVOID** creating flag enums where certain combinations of values are invalid.</span></span>  
  
 <span data-ttu-id="03dfd-150">**X vermeiden** mit Flagwerten Enum 0 (null), wenn der Wert "deaktiviert sind alle Flags" darstellt und Sie heißt entsprechend, wie der nächsten Richtlinie vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="03dfd-150">**X AVOID** using flag enum values of zero unless the value represents "all flags are cleared" and is named appropriately, as prescribed by the next guideline.</span></span>  
  
 <span data-ttu-id="03dfd-151">**Führen Sie ✓** benennen Sie den Wert 0 (null) von Flags-Enumerationen `None`.</span><span class="sxs-lookup"><span data-stu-id="03dfd-151">**✓ DO** name the zero value of flag enums `None`.</span></span> <span data-ttu-id="03dfd-152">Für eine Flags-Enumeration muss der Wert immer bedeuten, dass "alle Flags gelöscht werden."</span><span class="sxs-lookup"><span data-stu-id="03dfd-152">For a flag enum, the value must always mean "all flags are cleared."</span></span>  
  
<a name="add_value"></a>   
### <a name="adding-value-to-enums"></a><span data-ttu-id="03dfd-153">Enumerationen Wert hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="03dfd-153">Adding Value to Enums</span></span>  
 <span data-ttu-id="03dfd-154">Es ist üblich, um zu ermitteln, müssen Sie Werte einer Enumeration hinzufügen, nachdem Sie bereits versendet habe.</span><span class="sxs-lookup"><span data-stu-id="03dfd-154">It is very common to discover that you need to add values to an enum after you have already shipped it.</span></span> <span data-ttu-id="03dfd-155">Ein potenzieller Anwendung Kompatibilitätsproblem vorliegt, wenn der neu hinzugefügte Wert aus einer vorhandenen API zurückgegeben wird da schlecht geschriebene Anwendungen den neuen Wert nicht ordnungsgemäß verarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="03dfd-155">There is a potential application compatibility problem when the newly added value is returned from an existing API, because poorly written applications might not handle the new value correctly.</span></span>  
  
 <span data-ttu-id="03dfd-156">**✓ GGF.** Enumerationen, die trotz eines geringen Kompatibilitätsproblems Werte hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="03dfd-156">**✓ CONSIDER** adding values to enums, despite a small compatibility risk.</span></span>  
  
 <span data-ttu-id="03dfd-157">Wenn Sie sich um echte Daten zur Anwendungsinkompatibilitäten durch Hinzufügen einer Enumeration verursacht haben, erwägen Sie eine neue API, die den alten und neuen Werte zurückgibt, und als veraltet markiert die alten API, die fortgesetzt werden nur die alten Werte zurückgeben soll.</span><span class="sxs-lookup"><span data-stu-id="03dfd-157">If you have real data about application incompatibilities caused by additions to an enum, consider adding a new API that returns the new and old values, and deprecate the old API, which should continue returning just the old values.</span></span> <span data-ttu-id="03dfd-158">Dadurch wird sichergestellt, dass Ihre vorhandenen Anwendungen kompatibel bleiben.</span><span class="sxs-lookup"><span data-stu-id="03dfd-158">This will ensure that your existing applications remain compatible.</span></span>  
  
 <span data-ttu-id="03dfd-159">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="03dfd-159">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="03dfd-160">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="03dfd-160">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03dfd-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03dfd-161">See Also</span></span>  
 [<span data-ttu-id="03dfd-162">Richtlinien für den Entwurf von Typen</span><span class="sxs-lookup"><span data-stu-id="03dfd-162">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 [<span data-ttu-id="03dfd-163">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="03dfd-163">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
