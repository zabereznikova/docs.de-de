---
title: F#-Komponente Entwurfsrichtlinien
description: Erfahren Sie, die Richtlinien zum Schreiben von F#-Komponenten, die für die Nutzung durch andere Aufrufer vorgesehen.
ms.date: 05/14/2018
ms.openlocfilehash: 7e71710b1bc2fe3e8d7a5a091513a1432650dc04
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2018
ms.locfileid: "34458085"
---
# <a name="f-component-design-guidelines"></a><span data-ttu-id="9da9a-103">F#-Komponente Entwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="9da9a-103">F# component design guidelines</span></span>

<span data-ttu-id="9da9a-104">Dieses Dokument stellt einen Satz von Richtlinien zum Entwerfen einer Komponente für f#-Programmierung, basierend auf den F#-Komponente Entwurfsrichtlinien, 14, Microsoft Research und [eine andere Version](https://fsharp.org/specs/component-design-guidelines/) ursprünglich curated und von der F#-Software Foundation verwaltet.</span><span class="sxs-lookup"><span data-stu-id="9da9a-104">This document is a set of component design guidelines for F# programming, based on the F# Component Design Guidelines, v14, Microsoft Research, and [another version](https://fsharp.org/specs/component-design-guidelines/) originally curated and maintained by the F# Software Foundation.</span></span>

<span data-ttu-id="9da9a-105">Dieses Dokument wird davon ausgegangen, dass Sie mit der f#-Programmierung vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="9da9a-105">This document assumes you are familiar with F# programming.</span></span> <span data-ttu-id="9da9a-106">Vielen Dank für ihre Beiträge und hilfreiche Feedback auf verschiedenen Versionen dieses Handbuchs f#-Community.</span><span class="sxs-lookup"><span data-stu-id="9da9a-106">Many thanks to the F# community for their contributions and helpful feedback on various versions of this guide.</span></span>

## <a name="overview"></a><span data-ttu-id="9da9a-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="9da9a-107">Overview</span></span>

<span data-ttu-id="9da9a-108">Dieses Dokument untersucht die Probleme im Zusammenhang mit der F#-Komponentenentwurf und die sicherheitscodierung.</span><span class="sxs-lookup"><span data-stu-id="9da9a-108">This document looks at some of the issues related to F# component design and coding.</span></span> <span data-ttu-id="9da9a-109">Eine Komponente kann Folgendes bedeuten:</span><span class="sxs-lookup"><span data-stu-id="9da9a-109">A component can mean any of the following:</span></span>

* <span data-ttu-id="9da9a-110">Eine Ebene in f#-Projekts, das externe Consumer innerhalb dieses Projekts verfügt.</span><span class="sxs-lookup"><span data-stu-id="9da9a-110">A layer in your F# project that has external consumers within that project.</span></span>
* <span data-ttu-id="9da9a-111">Eine Bibliothek hinweg Assembly für die Verwendung von f#-Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-111">A library intended for consumption by F# code across assembly boundaries.</span></span>
* <span data-ttu-id="9da9a-112">Eine Bibliothek für die Nutzung von jeder Assembly hinweg vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-112">A library intended for consumption by any .NET language across assembly boundaries.</span></span>
* <span data-ttu-id="9da9a-113">Eine Bibliothek, die für die Verteilung über ein paketrepository gedacht sind, wie z. B. [NuGet](https://nuget.org).</span><span class="sxs-lookup"><span data-stu-id="9da9a-113">A library intended for distribution via a package repository, such as [NuGet](https://nuget.org).</span></span>

<span data-ttu-id="9da9a-114">Führen Sie die in diesem Artikel beschriebene Techniken der [fünf Prinzipien der gute f#-Code](index.md#five-principles-of-good-f-code), und daher beide funktionale nutzen und die Objekt-Programmierung nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="9da9a-114">Techniques described in this article follow the [Five principles of good F# code](index.md#five-principles-of-good-f-code), and thus utilize both functional and object programming as appropriate.</span></span>

<span data-ttu-id="9da9a-115">Unabhängig von der Methodik Flächen der Komponente und Bibliothek-Designer eine Reihe von praktische und prosaischen Problemen, beim Versuch, eine API zu erstellen, die von Entwicklern am einfachsten verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="9da9a-115">Regardless of the methodology, the component and library designer faces a number of practical and prosaic issues when trying to craft an API that is most easily usable by developers.</span></span> <span data-ttu-id="9da9a-116">Zudem Anwendung von der [Entwurfsrichtlinien von .NET Bibliothek](../../standard/design-guidelines/index.md) wird Sie beim Erstellen eines konsistenten Satz von APIs, nutzen angenehmeren sind, lenken.</span><span class="sxs-lookup"><span data-stu-id="9da9a-116">Conscientious application of the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md) will steer you towards creating a consistent set of APIs that are pleasant to consume.</span></span>

## <a name="general-guidelines"></a><span data-ttu-id="9da9a-117">Allgemeine Richtlinien</span><span class="sxs-lookup"><span data-stu-id="9da9a-117">General guidelines</span></span>

<span data-ttu-id="9da9a-118">Es gibt einige universelle Richtlinien, die für f#-Bibliotheken, unabhängig von der die Zielgruppe für die Bibliothek gelten.</span><span class="sxs-lookup"><span data-stu-id="9da9a-118">There are a few universal guidelines that apply to F# libraries, regardless of the intended audience for the library.</span></span>

### <a name="learn-the-net-library-design-guidelines"></a><span data-ttu-id="9da9a-119">Erfahren Sie, die Entwurfsrichtlinien für .NET-Bibliothek</span><span class="sxs-lookup"><span data-stu-id="9da9a-119">Learn the .NET Library Design Guidelines</span></span>

<span data-ttu-id="9da9a-120">Unabhängig von der Art der F#-codieren, Sie nehmen, ist es sinnvoll sein, eine ausreichende praktische Kenntnisse der [Entwurfsrichtlinien von .NET Bibliothek](../../standard/design-guidelines/index.md).</span><span class="sxs-lookup"><span data-stu-id="9da9a-120">Regardless of the kind of F# coding you are doing, it is valuable to have a working knowledge of the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md).</span></span> <span data-ttu-id="9da9a-121">Die meisten anderen f# und .NET Programmierer werden mit diesen Richtlinien vertraut sein, und .NET Code entsprechen, diese erwarten.</span><span class="sxs-lookup"><span data-stu-id="9da9a-121">Most other F# and .NET programmers will be familiar with these guidelines, and expect .NET code to conform to them.</span></span>

<span data-ttu-id="9da9a-122">Die Entwurfsrichtlinien von .NET Bibliothek bieten eine allgemeine Anleitung Bezug auf Benennung, Entwerfen von Klassen und Schnittstellen, Member-Entwurf (Eigenschaften, Methoden, Ereignisse usw.) und vieles mehr, und sind eine nützliche ersten Punkt des Verweises für eine Vielzahl von Leitfaden zum Design.</span><span class="sxs-lookup"><span data-stu-id="9da9a-122">The .NET Library Design Guidelines provide general guidance regarding naming, designing classes and interfaces, member design (properties, methods, events, etc.) and more, and are a useful first point of reference for a variety of design guidance.</span></span>

### <a name="add-xml-documentation-comments-to-your-code"></a><span data-ttu-id="9da9a-123">XML-Dokumentationskommentare in den Code hinzufügen</span><span class="sxs-lookup"><span data-stu-id="9da9a-123">Add XML documentation comments to your code</span></span>

<span data-ttu-id="9da9a-124">XML-Dokumentation von öffentlichen APIs stellen Sie sicher, dass Benutzer hervorragende Intellisense und den QuickInfos abrufen können, verwenden diese Typen und Member, und aktivieren erstellen Dokumentation für die Bibliothek von Dateien.</span><span class="sxs-lookup"><span data-stu-id="9da9a-124">XML documentation on public APIs ensure that users can get great Intellisense and Quickinfo when using these types and members, and enable building documentation files for the library.</span></span> <span data-ttu-id="9da9a-125">Finden Sie unter der [XML-Dokumentation](../language-reference/xml-documentation.md) über verschiedene XML‑Tags, die für zusätzliche Markup im Xmldoc Kommentare verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="9da9a-125">See the [XML Documentation](../language-reference/xml-documentation.md) about various xml tags that can be used for additional markup within xmldoc comments.</span></span>

```fsharp
/// A class for representing (x,y) coordinates
type Point =

    /// Computes the distance between this point and another
    member DistanceTo : otherPoint:Point -> float
```

<span data-ttu-id="9da9a-126">Sie können auch die Kurzform XML-Kommentare verwenden (`/// comment`), oder die standardmäßigen XML-Kommentare (`///<summary>comment</summary>`).</span><span class="sxs-lookup"><span data-stu-id="9da9a-126">You can use either the short form XML comments (`/// comment`), or standard XML comments (`///<summary>comment</summary>`).</span></span>

### <a name="consider-using-explicit-signature-files-fsi-for-stable-library-and-component-apis"></a><span data-ttu-id="9da9a-127">Erwägen Sie explizite Signaturdateien (".FSI") für stabile und APIs-Komponente</span><span class="sxs-lookup"><span data-stu-id="9da9a-127">Consider using explicit signature files (.fsi) for stable library and component APIs</span></span>

<span data-ttu-id="9da9a-128">Verwenden explizite Signaturen Dateien in F#-Bibliothek bietet eine kurze Zusammenfassung der öffentliche API, die jeweils sichergestellt wird, dass Sie wissen, die vollständigen öffentliche Oberfläche der Bibliothek als auch bietet eine saubere Trennung zwischen Dokumentation öffentliche und interne Details zur Implementierung.</span><span class="sxs-lookup"><span data-stu-id="9da9a-128">Using explicit signatures files in an F# library provides a succinct summary of public API, which both helps to ensure that you know the full public surface of your library, as well as provides a clean separation between public documentation and internal implementation details.</span></span> <span data-ttu-id="9da9a-129">Beachten Sie, dass die Signaturdateien Unstimmigkeiten hinzufügen, ändern die öffentliche API durch Anfordern von Änderungen, die in der Implementierung und die Signatur Dateien vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="9da9a-129">Note that signature files add friction to changing the public API, by requiring changes to be made in both the implementation and signature files.</span></span> <span data-ttu-id="9da9a-130">Daher sollten Signaturdateien in der Regel nur eingeführt werden, wenn eine API größtenteils durchgeführten Konsolidierung werden und ist nicht mehr erwartungsgemäß erheblich ändern.</span><span class="sxs-lookup"><span data-stu-id="9da9a-130">As a result, signature files should typically only be introduced when an API has become solidified and is no longer expected to change significantly.</span></span>

### <a name="always-follow-best-practices-for-using-strings-in-net"></a><span data-ttu-id="9da9a-131">Führen Sie immer die bewährte Methoden für die Verwendung von Zeichenfolgen in .NET</span><span class="sxs-lookup"><span data-stu-id="9da9a-131">Always follow best practices for using strings in .NET</span></span>

<span data-ttu-id="9da9a-132">Führen Sie die [bewährte Methoden für die Verwendung von Zeichenfolgen in .NET](../../standard/base-types/best-practices-strings.md) Anleitung.</span><span class="sxs-lookup"><span data-stu-id="9da9a-132">Follow [Best Practices for Using Strings in .NET](../../standard/base-types/best-practices-strings.md) guidance.</span></span> <span data-ttu-id="9da9a-133">Insbesondere immer explizit *kulturellen Absicht* in der Konvertierung und Vergleich von Zeichenfolgen (falls zutreffend).</span><span class="sxs-lookup"><span data-stu-id="9da9a-133">In particular, always explicitly state *cultural intent* in the conversion and comparison of strings (where applicable).</span></span>

## <a name="guidelines-for-f-facing-libraries"></a><span data-ttu-id="9da9a-134">Richtlinien für f#-Bibliotheken zugängliche</span><span class="sxs-lookup"><span data-stu-id="9da9a-134">Guidelines for F#-facing libraries</span></span>

<span data-ttu-id="9da9a-135">In diesem Abschnitt werden Empfehlungen für die Entwicklung von öffentlichen f#-Bibliotheken; zugängliche d. h. Bibliotheken Verfügbarmachen von öffentlichen APIs, die von F#-Entwicklern genutzt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-135">This section presents recommendations for developing public F#-facing libraries; that is, libraries exposing public APIs that are intended to be consumed by F# developers.</span></span> <span data-ttu-id="9da9a-136">Es gibt eine Vielzahl von Bibliotheksentwurf Empfehlungen gelten speziell für f#.</span><span class="sxs-lookup"><span data-stu-id="9da9a-136">There are a variety of library-design recommendations applicable specifically to F#.</span></span> <span data-ttu-id="9da9a-137">In Ermangelung der spezifischen Empfehlungen, die folgen, werden die Entwurfsrichtlinien von .NET Bibliothek fallback Anleitungen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-137">In the absence of the specific recommendations that follow, the .NET Library Design Guidelines are the fallback guidance.</span></span>

### <a name="naming-conventions"></a><span data-ttu-id="9da9a-138">Namenskonventionen </span><span class="sxs-lookup"><span data-stu-id="9da9a-138">Naming conventions</span></span>

#### <a name="use-net-naming-and-capitalization-conventions"></a><span data-ttu-id="9da9a-139">Verwenden Sie Benennungskonventionen für .NET benennen und Groß-/Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="9da9a-139">Use .NET naming and capitalization conventions</span></span>

<span data-ttu-id="9da9a-140">In der folgenden Tabelle folgt .NET benennen und Groß-/Kleinschreibung die Konventionen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-140">The following table follows .NET naming and capitalization conventions.</span></span> <span data-ttu-id="9da9a-141">Es sind kleine Ergänzungen auch f#-Konstrukte enthalten.</span><span class="sxs-lookup"><span data-stu-id="9da9a-141">There are small additions to also include F# constructs.</span></span>

| <span data-ttu-id="9da9a-142">Konstrukt</span><span class="sxs-lookup"><span data-stu-id="9da9a-142">Construct</span></span> | <span data-ttu-id="9da9a-143">Case</span><span class="sxs-lookup"><span data-stu-id="9da9a-143">Case</span></span> | <span data-ttu-id="9da9a-144">Segment</span><span class="sxs-lookup"><span data-stu-id="9da9a-144">Part</span></span> | <span data-ttu-id="9da9a-145">Beispiele</span><span class="sxs-lookup"><span data-stu-id="9da9a-145">Examples</span></span> | <span data-ttu-id="9da9a-146">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9da9a-146">Notes</span></span> |
|-----------|------|------|----------|-------|
| <span data-ttu-id="9da9a-147">Konkrete Typen</span><span class="sxs-lookup"><span data-stu-id="9da9a-147">Concrete types</span></span> | <span data-ttu-id="9da9a-148">"PascalCase"</span><span class="sxs-lookup"><span data-stu-id="9da9a-148">PascalCase</span></span> | <span data-ttu-id="9da9a-149">Nomen / adjektivische</span><span class="sxs-lookup"><span data-stu-id="9da9a-149">Noun/ adjective</span></span> | <span data-ttu-id="9da9a-150">Liste, Double, komplexe</span><span class="sxs-lookup"><span data-stu-id="9da9a-150">List, Double, Complex</span></span> | <span data-ttu-id="9da9a-151">Konkrete Typen sind Strukturen, Klassen, Enumerationen, Delegaten, Datensätze und Unions.</span><span class="sxs-lookup"><span data-stu-id="9da9a-151">Concrete types are structs, classes, enumerations, delegates, records, and unions.</span></span> <span data-ttu-id="9da9a-152">Obwohl Typnamen traditionell Kleinbuchstaben in mit OCaml handelt, hat f# das .NET Benennungsschema für Typen eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9da9a-152">Though type names are traditionally lowercase in OCaml, F# has adopted the .NET naming scheme for types.</span></span>
| <span data-ttu-id="9da9a-153">DLLs</span><span class="sxs-lookup"><span data-stu-id="9da9a-153">DLLs</span></span>           | <span data-ttu-id="9da9a-154">"PascalCase"</span><span class="sxs-lookup"><span data-stu-id="9da9a-154">PascalCase</span></span> |                 | <span data-ttu-id="9da9a-155">Fabrikam.Core.dll</span><span class="sxs-lookup"><span data-stu-id="9da9a-155">Fabrikam.Core.dll</span></span> |  |
| <span data-ttu-id="9da9a-156">Union-tags</span><span class="sxs-lookup"><span data-stu-id="9da9a-156">Union tags</span></span>     | <span data-ttu-id="9da9a-157">"PascalCase"</span><span class="sxs-lookup"><span data-stu-id="9da9a-157">PascalCase</span></span> | <span data-ttu-id="9da9a-158">Nomen</span><span class="sxs-lookup"><span data-stu-id="9da9a-158">Noun</span></span> | <span data-ttu-id="9da9a-159">Einige hinzuzufügen, Erfolg</span><span class="sxs-lookup"><span data-stu-id="9da9a-159">Some, Add, Success</span></span> | <span data-ttu-id="9da9a-160">Verwenden Sie ein Präfix nicht in öffentlichen APIs.</span><span class="sxs-lookup"><span data-stu-id="9da9a-160">Do not use a prefix in public APIs.</span></span> <span data-ttu-id="9da9a-161">Verwenden Sie optional ein Präfix, wenn interne, z. B. ''' Teams geben = TAlpha</span><span class="sxs-lookup"><span data-stu-id="9da9a-161">Optionally use a prefix when internal, such as \`\`\`type Teams = TAlpha</span></span> | <span data-ttu-id="9da9a-162">TBeta</span><span class="sxs-lookup"><span data-stu-id="9da9a-162">TBeta</span></span> | <span data-ttu-id="9da9a-163">TDelta. ""</span><span class="sxs-lookup"><span data-stu-id="9da9a-163">TDelta.\`\`\`</span></span> |
| <span data-ttu-id="9da9a-164">event</span><span class="sxs-lookup"><span data-stu-id="9da9a-164">Event</span></span>          | <span data-ttu-id="9da9a-165">"PascalCase"</span><span class="sxs-lookup"><span data-stu-id="9da9a-165">PascalCase</span></span> | <span data-ttu-id="9da9a-166">Verb</span><span class="sxs-lookup"><span data-stu-id="9da9a-166">Verb</span></span> | <span data-ttu-id="9da9a-167">ValueChanged / ValueChanging</span><span class="sxs-lookup"><span data-stu-id="9da9a-167">ValueChanged / ValueChanging</span></span> |  |
| <span data-ttu-id="9da9a-168">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="9da9a-168">Exceptions</span></span>     | <span data-ttu-id="9da9a-169">"PascalCase"</span><span class="sxs-lookup"><span data-stu-id="9da9a-169">PascalCase</span></span> |      | <span data-ttu-id="9da9a-170">WebException</span><span class="sxs-lookup"><span data-stu-id="9da9a-170">WebException</span></span> | <span data-ttu-id="9da9a-171">Name sollte mit "Ausnahme" enden.</span><span class="sxs-lookup"><span data-stu-id="9da9a-171">Name should end with “Exception”.</span></span> |
| <span data-ttu-id="9da9a-172">Feld</span><span class="sxs-lookup"><span data-stu-id="9da9a-172">Field</span></span>          | <span data-ttu-id="9da9a-173">"PascalCase"</span><span class="sxs-lookup"><span data-stu-id="9da9a-173">PascalCase</span></span> | <span data-ttu-id="9da9a-174">Nomen</span><span class="sxs-lookup"><span data-stu-id="9da9a-174">Noun</span></span> | <span data-ttu-id="9da9a-175">CurrentName</span><span class="sxs-lookup"><span data-stu-id="9da9a-175">CurrentName</span></span>  | |
| <span data-ttu-id="9da9a-176">Schnittstellentypen</span><span class="sxs-lookup"><span data-stu-id="9da9a-176">Interface types</span></span> |  <span data-ttu-id="9da9a-177">"PascalCase"</span><span class="sxs-lookup"><span data-stu-id="9da9a-177">PascalCase</span></span> | <span data-ttu-id="9da9a-178">Nomen / adjektivische</span><span class="sxs-lookup"><span data-stu-id="9da9a-178">Noun/ adjective</span></span> | <span data-ttu-id="9da9a-179">IDisposable</span><span class="sxs-lookup"><span data-stu-id="9da9a-179">IDisposable</span></span> | <span data-ttu-id="9da9a-180">Name sollte mit "I" beginnen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-180">Name should start with “I”.</span></span> |
| <span data-ttu-id="9da9a-181">Methode</span><span class="sxs-lookup"><span data-stu-id="9da9a-181">Method</span></span> |  <span data-ttu-id="9da9a-182">"PascalCase"</span><span class="sxs-lookup"><span data-stu-id="9da9a-182">PascalCase</span></span> |  <span data-ttu-id="9da9a-183">Verb</span><span class="sxs-lookup"><span data-stu-id="9da9a-183">Verb</span></span> | <span data-ttu-id="9da9a-184">ToString</span><span class="sxs-lookup"><span data-stu-id="9da9a-184">ToString</span></span> | |
| <span data-ttu-id="9da9a-185">Namespace</span><span class="sxs-lookup"><span data-stu-id="9da9a-185">Namespace</span></span> | <span data-ttu-id="9da9a-186">"PascalCase"</span><span class="sxs-lookup"><span data-stu-id="9da9a-186">PascalCase</span></span> | | <span data-ttu-id="9da9a-187">Microsoft.FSharp.Core</span><span class="sxs-lookup"><span data-stu-id="9da9a-187">Microsoft.FSharp.Core</span></span> | <span data-ttu-id="9da9a-188">Verwenden Sie in der Regel `<Organization>.<Technology>[.<Subnamespace>]`, obwohl die Organisation gelöscht werden, wenn die Technologie unabhängig von der Organisation ist.</span><span class="sxs-lookup"><span data-stu-id="9da9a-188">Generally use `<Organization>.<Technology>[.<Subnamespace>]`, though drop the organization if the technology is independent of organization.</span></span> |
| <span data-ttu-id="9da9a-189">Parameter</span><span class="sxs-lookup"><span data-stu-id="9da9a-189">Parameters</span></span> | <span data-ttu-id="9da9a-190">camelCase ändern möchten</span><span class="sxs-lookup"><span data-stu-id="9da9a-190">camelCase</span></span> | <span data-ttu-id="9da9a-191">Nomen</span><span class="sxs-lookup"><span data-stu-id="9da9a-191">Noun</span></span> |  <span data-ttu-id="9da9a-192">TypeName, Transform, Bereich</span><span class="sxs-lookup"><span data-stu-id="9da9a-192">typeName, transform, range</span></span> | |
| <span data-ttu-id="9da9a-193">Werte (intern)</span><span class="sxs-lookup"><span data-stu-id="9da9a-193">let values (internal)</span></span> | <span data-ttu-id="9da9a-194">camelCase ändern möchten oder "PascalCase"</span><span class="sxs-lookup"><span data-stu-id="9da9a-194">camelCase or PascalCase</span></span> | <span data-ttu-id="9da9a-195">Nomen / Verb</span><span class="sxs-lookup"><span data-stu-id="9da9a-195">Noun/ verb</span></span> |  <span data-ttu-id="9da9a-196">GetValue myTable</span><span class="sxs-lookup"><span data-stu-id="9da9a-196">getValue, myTable</span></span> |
| <span data-ttu-id="9da9a-197">Werte (extern)</span><span class="sxs-lookup"><span data-stu-id="9da9a-197">let values (external)</span></span> | <span data-ttu-id="9da9a-198">camelCase ändern möchten oder "PascalCase"</span><span class="sxs-lookup"><span data-stu-id="9da9a-198">camelCase or PascalCase</span></span> | <span data-ttu-id="9da9a-199">Nomen-verb</span><span class="sxs-lookup"><span data-stu-id="9da9a-199">Noun/verb</span></span>  | <span data-ttu-id="9da9a-200">List.Map Dates.Today</span><span class="sxs-lookup"><span data-stu-id="9da9a-200">List.map, Dates.Today</span></span> | <span data-ttu-id="9da9a-201">Let-Bindung Werte sind häufig öffentlich, beim traditionellen funktionale Entwurfsmuster stehenden.</span><span class="sxs-lookup"><span data-stu-id="9da9a-201">let-bound values are often public when following traditional functional design patterns.</span></span> <span data-ttu-id="9da9a-202">Allerdings verwenden Sie im Allgemeinen "PascalCase" Wenn der Bezeichner der anderen .NET-Sprachen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="9da9a-202">However, generally use PascalCase when the identifier can be used from other .NET languages.</span></span> |
| <span data-ttu-id="9da9a-203">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="9da9a-203">Property</span></span>  | <span data-ttu-id="9da9a-204">"PascalCase"</span><span class="sxs-lookup"><span data-stu-id="9da9a-204">PascalCase</span></span>  | <span data-ttu-id="9da9a-205">Nomen / adjektivische</span><span class="sxs-lookup"><span data-stu-id="9da9a-205">Noun/ adjective</span></span>  | <span data-ttu-id="9da9a-206">IsEndOfFile BackColor</span><span class="sxs-lookup"><span data-stu-id="9da9a-206">IsEndOfFile, BackColor</span></span>  | <span data-ttu-id="9da9a-207">Boolesche Eigenschaften, die in der Regel verwenden, und kann und abstimmungszeuge, wie in IsEndOfFile nicht IsNotEndOfFile sein.</span><span class="sxs-lookup"><span data-stu-id="9da9a-207">Boolean properties generally use Is and Can and should be affirmative, as in IsEndOfFile, not IsNotEndOfFile.</span></span>

#### <a name="avoid-abbreviations"></a><span data-ttu-id="9da9a-208">Vermeiden von Abkürzungen</span><span class="sxs-lookup"><span data-stu-id="9da9a-208">Avoid abbreviations</span></span>

<span data-ttu-id="9da9a-209">Die Richtlinien .NET abgeraten werden die Verwendung von Abkürzungen (z. B. "verwenden `OnButtonClick` statt `OnBtnClick`").</span><span class="sxs-lookup"><span data-stu-id="9da9a-209">The .NET guidelines discourage the use of abbreviations (for example, “use `OnButtonClick` rather than `OnBtnClick`”).</span></span> <span data-ttu-id="9da9a-210">Allgemeine Abkürzungen wie z. B. `Async` für "Asynchrone", toleriert werden.</span><span class="sxs-lookup"><span data-stu-id="9da9a-210">Common abbreviations, such as `Async` for “Asynchronous”, are tolerated.</span></span> <span data-ttu-id="9da9a-211">Diese Richtlinie ist für die funktionale Programmierung manchmal ignoriert. beispielsweise `List.iter` verwendet eine Abkürzung für "Iteration".</span><span class="sxs-lookup"><span data-stu-id="9da9a-211">This guideline is sometimes ignored for functional programming; for example, `List.iter` uses an abbreviation for “iterate”.</span></span> <span data-ttu-id="9da9a-212">Aus diesem Grund mithilfe von Abkürzungen tendenziell um eine genauere speichersteuerung in f# toleriert werden-zu-f#-Programmierung, aber immer noch in der Regel in öffentlichen Komponentenentwurf vermieden werden sollte.</span><span class="sxs-lookup"><span data-stu-id="9da9a-212">For this reason, using abbreviations tends to be tolerated to a greater degree in F#-to-F# programming, but should still generally be avoided in public component design.</span></span>

#### <a name="avoid-casing-name-collisions"></a><span data-ttu-id="9da9a-213">Vermeiden Sie die Groß-/Kleinschreibung Namenskonflikte</span><span class="sxs-lookup"><span data-stu-id="9da9a-213">Avoid casing name collisions</span></span>

<span data-ttu-id="9da9a-214">Die Richtlinien .NET sagen, dass die Groß-/Kleinschreibung allein verwendet werden, um Namenskonflikte, zu unterscheiden, da einige Clientsprachen (z. B. Visual Basic) sind, die Groß-/Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="9da9a-214">The .NET guidelines say that casing alone cannot be used to disambiguate name collisions, since some client languages (for example, Visual Basic) are case-insensitive.</span></span>

#### <a name="use-acronyms-where-appropriate"></a><span data-ttu-id="9da9a-215">Verwenden Sie bei Bedarf Akronyme</span><span class="sxs-lookup"><span data-stu-id="9da9a-215">Use acronyms where appropriate</span></span>

<span data-ttu-id="9da9a-216">Akronyme, wie z. B. XML sind keine Abkürzungen und werden häufig in .NET-Bibliotheken uncapitalized Format (Xml) verwendet.</span><span class="sxs-lookup"><span data-stu-id="9da9a-216">Acronyms such as XML are not abbreviations and are widely used in .NET libraries in uncapitalized form (Xml).</span></span> <span data-ttu-id="9da9a-217">Nur bekannte, bekannter Akronyme vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-217">Only well-known, widely recognized acronyms should be used.</span></span>

#### <a name="use-pascalcase-for-generic-parameter-names"></a><span data-ttu-id="9da9a-218">Verwenden Sie "PascalCase" für generische parameter</span><span class="sxs-lookup"><span data-stu-id="9da9a-218">Use PascalCase for generic parameter names</span></span>

<span data-ttu-id="9da9a-219">Verwenden Sie "PascalCase" für generische Parameternamen in öffentlichen APIs, einschließlich für f#-Bibliotheken nach.</span><span class="sxs-lookup"><span data-stu-id="9da9a-219">Do use PascalCase for generic parameter names in public APIs, including for F#-facing libraries.</span></span> <span data-ttu-id="9da9a-220">Insbesondere verwenden Sie Namen wie `T`, `U`, `T1`, `T2` für beliebige generische Parameter, und wenn bestimmte Namen Sinn, klicken Sie dann für f#-nach außen verfügbaren Bibliotheken verwenden Sie Namen wie `Key`, `Value`, `Arg`(aber nicht z. B. `TKey`).</span><span class="sxs-lookup"><span data-stu-id="9da9a-220">In particular, use names like `T`, `U`, `T1`, `T2` for arbitrary generic parameters, and when specific names make sense, then for F#-facing libraries use names like `Key`, `Value`, `Arg` (but not for example, `TKey`).</span></span>

#### <a name="use-either-pascalcase-or-camelcase-for-public-functions-and-values-in-f-modules"></a><span data-ttu-id="9da9a-221">Verwenden Sie "PascalCase" oder camelCase ändern möchten, für öffentliche Funktionen und die Werte in F#-Modulen</span><span class="sxs-lookup"><span data-stu-id="9da9a-221">Use either PascalCase or camelCase for public functions and values in F# modules</span></span>

<span data-ttu-id="9da9a-222">camelCase ändern möchten dient für öffentliche Funktionen, die darauf ausgelegt sind, verwendet werden, nicht qualifizierten (z. B. `invalidArg`), und für die "standard Auflistungsfunktionen" (z. B. List.map).</span><span class="sxs-lookup"><span data-stu-id="9da9a-222">camelCase is used for public functions that are designed to be used unqualified (for example, `invalidArg`), and for the “standard collection functions” (for example, List.map).</span></span> <span data-ttu-id="9da9a-223">In beiden Fällen verhalten sich die Funktionsnamen ähnlich wie Schlüsselwörter in der Sprache.</span><span class="sxs-lookup"><span data-stu-id="9da9a-223">In both these cases, the function names act much like keywords in the language.</span></span>

### <a name="object-type-and-module-design"></a><span data-ttu-id="9da9a-224">-Objekt, Typ und Modul Entwurf</span><span class="sxs-lookup"><span data-stu-id="9da9a-224">Object, Type, and Module design</span></span>

#### <a name="use-namespaces-or-modules-to-contain-your-types-and-modules"></a><span data-ttu-id="9da9a-225">Verwenden von Namespaces oder der Module, enthalten die Typen und die Module</span><span class="sxs-lookup"><span data-stu-id="9da9a-225">Use namespaces or modules to contain your types and modules</span></span>

<span data-ttu-id="9da9a-226">Jede f#-Datei in eine Komponente sollte eine Namespacedeklaration oder eine Moduldeklaration beginnen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-226">Each F# file in a component should begin with either a namespace declaration or a module declaration.</span></span>

```fsharp
namespace Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
     ...

module CommonOperations =
    ...
```

<span data-ttu-id="9da9a-227">oder</span><span class="sxs-lookup"><span data-stu-id="9da9a-227">or</span></span>

```fsharp
module Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
    ...

module CommonOperations =
    ...
```

<span data-ttu-id="9da9a-228">Die Unterschiede zwischen der Verwendung von Modulen und Namespaces zum Organisieren von Code auf der obersten Ebene sind wie folgt:</span><span class="sxs-lookup"><span data-stu-id="9da9a-228">The differences between using modules and namespaces to organize code at the top level are as follows:</span></span>

* <span data-ttu-id="9da9a-229">Namespaces können mehrere Dateien umfassen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-229">Namespaces can span multiple files</span></span>
* <span data-ttu-id="9da9a-230">Namespaces darf keine f#-Funktionen enthalten, es sei denn, sie in einem inneren-Modul</span><span class="sxs-lookup"><span data-stu-id="9da9a-230">Namespaces cannot contain F# functions unless they are within an inner module</span></span>
* <span data-ttu-id="9da9a-231">Der Code für ein beliebiges Modul angegebenen muss innerhalb einer einzelnen Datei enthalten sein</span><span class="sxs-lookup"><span data-stu-id="9da9a-231">The code for any given module must be contained within a single file</span></span>
* <span data-ttu-id="9da9a-232">Module der obersten Ebene können f#-Funktionen ohne die Notwendigkeit eines inneren Moduls enthalten.</span><span class="sxs-lookup"><span data-stu-id="9da9a-232">Top-level modules can contain F# functions without the need for an inner module</span></span>

<span data-ttu-id="9da9a-233">Die Wahl zwischen einem Namespace der obersten Ebene oder das Modul wirkt sich auf der kompilierten Form des Codes und daher wirken sich die Ansicht aus anderen Ihre API schließlich außerhalb von f#-Code verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-233">The choice between a top-level namespace or module affects the compiled form of the code, and thus will affect the view from other .NET languages should your API eventually be consumed outside of F# code.</span></span>

#### <a name="use-methods-and-properties-for-operations-intrinsic-to-object-types"></a><span data-ttu-id="9da9a-234">Verwenden von Methoden und Eigenschaften für Vorgänge für Objekte des Typs</span><span class="sxs-lookup"><span data-stu-id="9da9a-234">Use methods and properties for operations intrinsic to object types</span></span>

<span data-ttu-id="9da9a-235">Wenn Sie mit Objekten arbeiten, empfiehlt es sich um sicherzustellen, dass nutzbar Funktionalität als Methoden und Eigenschaften für diesen Typ implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="9da9a-235">When working with objects, it is best to ensure that consumable functionality is implemented as methods and properties on that type.</span></span>

```fsharp
type HardwareDevice() =

    member this.ID = ...

    member this.SupportedProtocols = ...

type HashTable<'Key,'Value>(comparer: IEqualityComparer<'Key>) =

    member this.Add(key, value) = ...

    member this.ContainsKey(key) = ...

    member this.ContainsValue(value) = ...
```

<span data-ttu-id="9da9a-236">Der Großteil der Funktionalität für ein bestimmtes Element muss unbedingt nicht in diesen Member implementiert werden, aber der nutzbar Teil dieser Funktionalität werden sollte.</span><span class="sxs-lookup"><span data-stu-id="9da9a-236">The bulk of functionality for a given member need not necessarily be implemented in that member, but the consumable piece of that functionality should be.</span></span>

#### <a name="use-classes-to-encapsulate-mutable-state"></a><span data-ttu-id="9da9a-237">Verwenden von Klassen zum Kapseln von veränderlichen Zustand</span><span class="sxs-lookup"><span data-stu-id="9da9a-237">Use classes to encapsulate mutable state</span></span>

<span data-ttu-id="9da9a-238">In F# erläutert werden muss dies nur, dass der Status nicht bereits von einem anderen Sprachkonstrukt, z. B. ein Abschluss, Sequenzausdruck oder asynchrone Berechnung gekapselt ist, in denen erfolgen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-238">In F#, this only needs to be done where that state is not already encapsulated by another language construct, such as a closure, sequence expression, or asynchronous computation.</span></span>

```fsharp
type Counter() =
    // let-bound values are private in classes.
    let mutable count = 0

    member this.Next() =
        count <- count + 1
        count
```

#### <a name="use-interfaces-to-group-related-operations"></a><span data-ttu-id="9da9a-239">Verwenden Sie Schnittstellen, um Gruppen verwandte Vorgänge</span><span class="sxs-lookup"><span data-stu-id="9da9a-239">Use interfaces to group related operations</span></span>

<span data-ttu-id="9da9a-240">Verwenden Sie Schnittstellentypen werden zur Darstellung von einer Reihe von Vorgängen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-240">Use interface types to represent a set of operations.</span></span> <span data-ttu-id="9da9a-241">Dies ist die bevorzugte zu anderen Optionen, z. B. Tupel von Funktionen oder Funktionen Datensätze.</span><span class="sxs-lookup"><span data-stu-id="9da9a-241">This is preferred to other options, such as tuples of functions or records of functions.</span></span>

```fsharp
type Serializer =
    abstract Serialize<'T> : preserveRefEq: bool -> value: 'T -> string
    abstract Deserialize<'T> : preserveRefEq: bool -> pickle: string -> 'T
```

<span data-ttu-id="9da9a-242">Vorzuziehen:</span><span class="sxs-lookup"><span data-stu-id="9da9a-242">In preference to:</span></span>

```fsharp
type Serializer<'T> = {
    Serialize : bool -> 'T -> string
    Deserialize : bool -> string -> 'T
}
```

<span data-ttu-id="9da9a-243">Schnittstellen sind erstrangige Konzepte in .NET, das Sie verwenden können, um zu erreichen, was Funktionselemente normalerweise Sie erlangen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-243">Interfaces are first-class concepts in .NET, which you can use to achieve what Functors would normally give you.</span></span> <span data-ttu-id="9da9a-244">Darüber hinaus können sie zum Codieren von existenzielle Typen in das Programm die Datensätze von Funktionen nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9da9a-244">Additionally, they can be used to encode existential types into your program, which records of functions cannot.</span></span>

#### <a name="use-a-module-to-group-functions-which-act-on-collections"></a><span data-ttu-id="9da9a-245">Verwenden Sie ein Modul, um die tätig Gruppenfunktionen Auflistungen</span><span class="sxs-lookup"><span data-stu-id="9da9a-245">Use a module to group functions which act on collections</span></span>

<span data-ttu-id="9da9a-246">Wenn Sie einen Auflistungstyp definieren, verwenden Sie möglicherweise ein Standardsatz von Vorgängen wie `CollectionType.map` und `CollectionType.iter`) für neuer Sammlungstypen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-246">When you define a collection type, consider providing a standard set of operations like `CollectionType.map` and `CollectionType.iter`) for new collection types.</span></span>

```fsharp
module CollectionType =
    let map f c =
        ...
    let iter f c =
        ...
```

<span data-ttu-id="9da9a-247">Wenn Sie solche ein Moduls enthalten, führen Sie die standardmäßigen Benennungskonventionen für FSharp.Core-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-247">If you include such a module, follow the standard naming conventions for functions found in FSharp.Core.</span></span>

#### <a name="use-a-module-to-group-functions-for-common-canonical-functions-especially-in-math-and-dsl-libraries"></a><span data-ttu-id="9da9a-248">Verwenden Sie ein Modul Gruppenfunktionen für allgemeine, kanonische Funktionen, insbesondere in mathematischen und DSL-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="9da9a-248">Use a module to group functions for common, canonical functions, especially in math and DSL libraries</span></span>

<span data-ttu-id="9da9a-249">Beispielsweise `Microsoft.FSharp.Core.Operators` ist eine Auflistung automatisch geöffnete, der Funktionen der obersten Ebene (z. B. `abs` und `sin`) von FSharp.Core.dll bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="9da9a-249">For example, `Microsoft.FSharp.Core.Operators` is an automatically opened collection of top-level functions (like `abs` and `sin`) provided by FSharp.Core.dll.</span></span>

<span data-ttu-id="9da9a-250">Entsprechend kann eine Bibliothek Statistiken ein Moduls mit Funktionen enthalten `erf` und `erfc`, wobei dieses Modul dient, explizit oder automatisch geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="9da9a-250">Likewise, a statistics library might include a module with functions `erf` and `erfc`, where this module is designed to be explicitly or automatically opened.</span></span>

#### <a name="consider-using-requirequalifiedaccess-and-carefully-apply-autoopen-attributes"></a><span data-ttu-id="9da9a-251">RequireQualifiedAccess in Betracht, und wenden sorgfältig AutoOpen-Attribute</span><span class="sxs-lookup"><span data-stu-id="9da9a-251">Consider using RequireQualifiedAccess and carefully apply AutoOpen attributes</span></span>

<span data-ttu-id="9da9a-252">Hinzufügen der `[<RequireQualifiedAccess>]` Attribut auf ein Modul gibt an, dass das Modul kann nicht geöffnet werden, dass Verweise auf die Elemente des Moduls explizite benötigen Zugriff qualifiziert.</span><span class="sxs-lookup"><span data-stu-id="9da9a-252">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="9da9a-253">Z. B. die `Microsoft.FSharp.Collections.List` -Modul ist dieses Attribut.</span><span class="sxs-lookup"><span data-stu-id="9da9a-253">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="9da9a-254">Dies ist hilfreich, wenn Funktionen und Werte im Modul Namen haben, die wahrscheinlich einen Konflikt mit Namen in anderen Modulen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9da9a-254">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="9da9a-255">Einen qualifizierten Zugriff erfordern, kann erheblich die langfristige Verwaltbarkeit und die Evolvability einer Bibliothek erhöhen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-255">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

<span data-ttu-id="9da9a-256">Hinzufügen der `[<AutoOpen>]` Attribut auf ein Modul bedeutet, dass das Modul wird geöffnet, wenn der übergeordnete Namespace geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="9da9a-256">Adding the `[<AutoOpen>]` attribute to a module means the module will be opened when the containing namespace is opened.</span></span> <span data-ttu-id="9da9a-257">Die `[<AutoOpen>]` Attribut möglicherweise auch zu einer Assembly an, dass ein Modul, das automatisch geöffnet wird, wenn die Assembly verwiesen wird, angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="9da9a-257">The `[<AutoOpen>]` attribute may also be applied to an assembly to indicate a module that is automatically opened when the assembly is referenced.</span></span>

<span data-ttu-id="9da9a-258">Angenommen, eine Statistik Bibliothek **MathsHeaven.Statistics** enthält möglicherweise eine `module MathsHeaven.Statistics.Operators` , die Funktionen enthalten `erf` und `erfc`.</span><span class="sxs-lookup"><span data-stu-id="9da9a-258">For example, a statistics library **MathsHeaven.Statistics** might contain a `module MathsHeaven.Statistics.Operators` containing functions `erf` and `erfc`.</span></span> <span data-ttu-id="9da9a-259">Es ist angemessen, markieren Sie dieses Modul als `[<AutoOpen>]`.</span><span class="sxs-lookup"><span data-stu-id="9da9a-259">It is reasonable to mark this module as `[<AutoOpen>]`.</span></span> <span data-ttu-id="9da9a-260">Dies bedeutet, dass `open MathsHeaven.Statistics` wird auch dieses Modul geöffnet, und schalten Sie die Namen `erf` und `erfc` einbinden.</span><span class="sxs-lookup"><span data-stu-id="9da9a-260">This means `open MathsHeaven.Statistics` will also open this module and bring the names `erf` and `erfc` into scope.</span></span> <span data-ttu-id="9da9a-261">Eine andere funktionierende nutzen `[<AutoOpen>]` für Module mit Erweiterungsmethoden ist.</span><span class="sxs-lookup"><span data-stu-id="9da9a-261">Another good use of `[<AutoOpen>]` is for modules containing extension methods.</span></span>

<span data-ttu-id="9da9a-262">Lösen von `[<AutoOpen>]` führt zu einem belasteten Namespaces und das Attribut sollte mit Vorsicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9da9a-262">Overuse of `[<AutoOpen>]` leads to polluted namespaces, and the attribute should be used with care.</span></span> <span data-ttu-id="9da9a-263">Für bestimmte Bibliotheken in bestimmten Domänen, zielgerichtete Verwendung von `[<AutoOpen>]` zu bessere Nutzbarkeit führen kann.</span><span class="sxs-lookup"><span data-stu-id="9da9a-263">For specific libraries in specific domains, judicious use of `[<AutoOpen>]` can lead to better usability.</span></span>

#### <a name="consider-defining-operator-members-on-classes-where-using-well-known-operators-is-appropriate"></a><span data-ttu-id="9da9a-264">Definieren Sie Operator Member für Klassen, die mithilfe von bekannter Operatoren geeignet ist</span><span class="sxs-lookup"><span data-stu-id="9da9a-264">Consider defining operator members on classes where using well-known operators is appropriate</span></span>

<span data-ttu-id="9da9a-265">In einigen Fällen werden Klassen verwendet, um mathematische Konstrukte wie Vektoren zu modellieren.</span><span class="sxs-lookup"><span data-stu-id="9da9a-265">Sometimes classes are used to model mathematical constructs such as Vectors.</span></span> <span data-ttu-id="9da9a-266">Bei der Domäne, die modelliert werden bekannte Operatoren sind, eignet sie als Mitglieder für die Klasse zu definieren.</span><span class="sxs-lookup"><span data-stu-id="9da9a-266">When the domain being modeled has well-known operators, defining them as members intrinsic to the class is helpful.</span></span>

```fsharp
type Vector(x:float) =

    member v.X = x

    static member (*) (vector:Vector, scalar:float) = Vector(vector.X * scalar)

    static member (+) (vector1:Vector, vector2:Vector) = Vector(vector1.X + vector2.X)

let v = Vector(5.0)

let u = v * 10.0
```

<span data-ttu-id="9da9a-267">In dieser Anleitung entspricht .NET Hilfestellungen für diese Typen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-267">This guidance corresponds to general .NET guidance for these types.</span></span> <span data-ttu-id="9da9a-268">Allerdings kann es wichtig sein, außerdem im F#-Code wie dies zulässt, dass diese Typen in Verbindung mit der f#-Funktionen und Methoden mit Membereinschränkungen, z. B. List.sumBy verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9da9a-268">However, it can be additionally important in F# coding as this allows these types to be used in conjunction with F# functions and methods with member constraints, such as List.sumBy.</span></span>

#### <a name="consider-using-compiledname-to-provide-a-net-friendly-name-for-other-net-language-consumers"></a><span data-ttu-id="9da9a-269">Erwägen Sie CompiledName bereitstellen ein. NET-Anzeigenamen für andere .NET Language-Consumer</span><span class="sxs-lookup"><span data-stu-id="9da9a-269">Consider using CompiledName to provide a .NET-friendly name for other .NET language consumers</span></span>

<span data-ttu-id="9da9a-270">In einigen Fällen möchten Sie Sie möglicherweise etwas in ein Format für F#-Consumer nennen (z. B. ein statischer Member in Kleinbuchstaben Kanton als handele es sich um ein Modul-gebundenen Funktionen), jedoch über einen anderen Stil für den Namen, wenn es in eine Assembly kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="9da9a-270">Sometimes you may wish to name something in one style for F# consumers (such as a static member in lower case so that it appears as if it were a module-bound function), but have a different style for the name when it is compiled into an assembly.</span></span> <span data-ttu-id="9da9a-271">Sie können die `[<CompiledName>]` Attribut nutzen die Assembly nicht f#-Code ein anderen Format bereit.</span><span class="sxs-lookup"><span data-stu-id="9da9a-271">You can use the `[<CompiledName>]` attribute to provide a different style for non F# code consuming the assembly.</span></span>

```fsharp
type Vector(x:float, y:float) =

    member v.X = x
    member v.Y = y

    [<CompiledName("Create")>]
    static member create x y = Vector (x, y)

let v = Vector.create 5.0 3.0
```

<span data-ttu-id="9da9a-272">Mithilfe von `[<CompiledName>]`, können Sie .NET Benennungskonventionen für nicht F#-Consumern der Assembly.</span><span class="sxs-lookup"><span data-stu-id="9da9a-272">By using `[<CompiledName>]`, you can use .NET naming conventions for non F# consumers of the assembly.</span></span>

#### <a name="use-method-overloading-for-member-functions-if-doing-so-provides-a-simpler-api"></a><span data-ttu-id="9da9a-273">Verwenden Sie Methode für Memberfunktionen zu überladen, wenn so eine einfachere-API bereitgestellt werden</span><span class="sxs-lookup"><span data-stu-id="9da9a-273">Use method overloading for member functions, if doing so provides a simpler API</span></span>

<span data-ttu-id="9da9a-274">Überladen von Methoden ist ein leistungsstarkes Tool zur Vereinfachung einer API, die ähnliche Funktionen ausführen muss, aber mit verschiedenen Optionen oder Argumente.</span><span class="sxs-lookup"><span data-stu-id="9da9a-274">Method overloading is a powerful tool for simplifying an API that may need to perform similar functionality, but with different options or arguments.</span></span>

```fsharp
type Logger() =

    member this.Log(message) =
        ...
    member this.Log(message, retryPolicy) =
        ...
```

<span data-ttu-id="9da9a-275">In F# erläutert werden ist es eher üblich, dass die Anzahl von Argumenten anstelle der Datentypen der Argumente überladen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-275">In F#, it is more common to overload on number of arguments rather than types of arguments.</span></span>

#### <a name="hide-the-representations-of-record-and-union-types-if-the-design-of-these-types-is-likely-to-evolve"></a><span data-ttu-id="9da9a-276">Blenden Sie die Darstellung des Datensatzes und union-Typen aus, wenn der Entwurf dieser Typen weiterentwickelt wird</span><span class="sxs-lookup"><span data-stu-id="9da9a-276">Hide the representations of record and union types if the design of these types is likely to evolve</span></span>

<span data-ttu-id="9da9a-277">Vermeiden Sie die konkrete Darstellungen von Objekten offenzulegen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-277">Avoid revealing concrete representations of objects.</span></span> <span data-ttu-id="9da9a-278">Z. B. die konkrete Darstellung des <xref:System.DateTime> Werte ist von der externen, öffentliche API des Entwurfs .NET Bibliothek nicht offen gelegt.</span><span class="sxs-lookup"><span data-stu-id="9da9a-278">For example, the concrete representation of <xref:System.DateTime> values is not revealed by the external, public API of the .NET library design.</span></span> <span data-ttu-id="9da9a-279">Zur Laufzeit weiß der Common Language Runtime die Commit-Implementierung, die in der gesamten Ausführung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9da9a-279">At run time, the Common Language Runtime knows the committed implementation that will be used throughout execution.</span></span> <span data-ttu-id="9da9a-280">Allerdings nicht kompilierter Code selbst Abhängigkeiten von den konkreten Darstellung zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-280">However, compiled code doesn't itself pick up dependencies on the concrete representation.</span></span>

#### <a name="avoid-the-use-of-implementation-inheritance-for-extensibility"></a><span data-ttu-id="9da9a-281">Vermeiden Sie die Verwendung von implementierungsvererbung für Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="9da9a-281">Avoid the use of implementation inheritance for extensibility</span></span>

<span data-ttu-id="9da9a-282">In F# erläutert werden ist die implementierungsvererbung selten verwendet.</span><span class="sxs-lookup"><span data-stu-id="9da9a-282">In F#, implementation inheritance is rarely used.</span></span> <span data-ttu-id="9da9a-283">Darüber hinaus sind Vererbungshierarchien häufig komplex und schwierig zu ändern, wenn neue Anforderungen eingehen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-283">Furthermore, inheritance hierarchies are often complex and difficult to change when new requirements arrive.</span></span> <span data-ttu-id="9da9a-284">Vererbung-Implementierung befindet sich noch in f# für Kompatibilität und seltenen Fällen, bei denen es die beste Lösung eines Problems, aber alternative Techniken sollten beim Entwerfen der Polymorphie, z. B.-Implementierung in F#-Programmen gesucht.</span><span class="sxs-lookup"><span data-stu-id="9da9a-284">Inheritance implementation still exists in F# for compatibility and rare cases where it is the best solution to a problem, but alternative techniques should be sought in your F# programs when designing for polymorphism, such as interface implementation.</span></span>

### <a name="function-and-member-signatures"></a><span data-ttu-id="9da9a-285">Funktion und Element-Signaturen</span><span class="sxs-lookup"><span data-stu-id="9da9a-285">Function and member signatures</span></span>

#### <a name="use-tuples-for-return-values-when-returning-a-small-number-of-multiple-unrelated-values"></a><span data-ttu-id="9da9a-286">Verwenden Sie Tupel für Rückgabewerte, wenn eine kleine Anzahl von mehreren nicht verknüpften Werten zurückgeben</span><span class="sxs-lookup"><span data-stu-id="9da9a-286">Use tuples for return values when returning a small number of multiple unrelated values</span></span>

<span data-ttu-id="9da9a-287">Hier ist ein gutes Beispiel für die Verwendung eines Tupels in einem Rückgabetyp:</span><span class="sxs-lookup"><span data-stu-id="9da9a-287">Here is a good example of using a tuple in a return type:</span></span>

```fsharp
val divrem : BigInteger -> BigInteger -> BigInteger * BigInteger
```

<span data-ttu-id="9da9a-288">Rückgabetypen Sie für die, die viele Komponenten enthält, oder wenn Komponenten mit einer einzelnen identifizierbaren Entität verknüpft sind, erwägen Sie, mithilfe eines benannten Typs statt eines tupelausdrucks.</span><span class="sxs-lookup"><span data-stu-id="9da9a-288">For return types containing many components, or where the components are related to a single identifiable entity, consider using a named type instead of a tuple.</span></span>

#### <a name="use-asynct-for-async-programming-at-f-api-boundaries"></a><span data-ttu-id="9da9a-289">Verwendung `Async<T>` für asynchrone Programmierung an den Begrenzungen der f#-API</span><span class="sxs-lookup"><span data-stu-id="9da9a-289">Use `Async<T>` for async programming at F# API boundaries</span></span>

<span data-ttu-id="9da9a-290">Es ist ein entsprechender synchronen Vorgang mit dem Namen `Operation` zurückgibt eine `T`, den Namen der asynchrone Vorgang sollte `AsyncOperation` zurückgibt `Async<T>` oder `OperationAsync` zurückgibt `Task<T>`.</span><span class="sxs-lookup"><span data-stu-id="9da9a-290">If there is a corresponding synchronous operation named `Operation` that returns a `T`, then the async operation should be named `AsyncOperation` if it returns `Async<T>` or `OperationAsync` if it returns `Task<T>`.</span></span> <span data-ttu-id="9da9a-291">Für häufig verwendete Typen von .NET Begin/End-Methoden verfügbar zu machen, die in Betracht `Async.FromBeginEnd` zum Schreiben von Erweiterungsmethoden als Fassade das f# asynchrone Programmiermodell für die .NET APIs bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-291">For commonly used .NET types that expose Begin/End methods, consider using `Async.FromBeginEnd` to write extension methods as a façade to provide the F# async programming model to those .NET APIs.</span></span>

```fsharp
type SomeType =
    member this.Compute(x:int) : int =
        ...
    member this.AsyncCompute(x:int) : Async<int> =
        ...

type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        ...
```

### <a name="exceptions"></a><span data-ttu-id="9da9a-292">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="9da9a-292">Exceptions</span></span>

<span data-ttu-id="9da9a-293">Ausnahmen sind in .NET herausragende; d. h., sollten sie nicht häufig zur Laufzeit auftreten.</span><span class="sxs-lookup"><span data-stu-id="9da9a-293">Exceptions are exceptional in .NET; that is, they should not occur frequently at runtime.</span></span> <span data-ttu-id="9da9a-294">Wenn dies der Fall, wird die darin enthaltenen Informationen nützlich.</span><span class="sxs-lookup"><span data-stu-id="9da9a-294">When they do, the information they contain is valuable.</span></span> <span data-ttu-id="9da9a-295">Ausnahmen sind ein Kern erstklassige Konzept von .NET. Daher IT folgt, die entsprechende Anwendung der Ausnahmen als Teil des Entwurfs der Schnittstelle einer Komponente verwendet werden sollten.</span><span class="sxs-lookup"><span data-stu-id="9da9a-295">Exceptions are a core first class concept of .NET; it hence follows that appropriate application of the Exceptions should be used as part of the design of the interface of a component.</span></span>

#### <a name="follow-the-net-guidelines-for-exceptions"></a><span data-ttu-id="9da9a-296">Befolgen Sie die .NET Richtlinien für Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="9da9a-296">Follow the .NET guidelines for exceptions</span></span>

<span data-ttu-id="9da9a-297">Die [Entwurfsrichtlinien von .NET Bibliothek](../../standard/design-guidelines/exceptions.md) hervorragende Ratschläge für die Verwendung von Ausnahmen im Kontext der Programmierung für alle .NET erteilen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-297">The [.NET Library Design Guidelines](../../standard/design-guidelines/exceptions.md) give excellent advice on the use of exceptions in the context of all .NET programming.</span></span> <span data-ttu-id="9da9a-298">Nachfolgend sind einige der folgenden Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="9da9a-298">Some of these guidelines are as follows:</span></span>

* <span data-ttu-id="9da9a-299">Verwenden Sie Ausnahmen nicht für normale ablaufsteuerung aus.</span><span class="sxs-lookup"><span data-stu-id="9da9a-299">Do not use exceptions for normal flow of control.</span></span> <span data-ttu-id="9da9a-300">Obwohl diese Technik in Sprachen wie z. B. mit OCaml häufig verwendet wird, ist fehleranfälliger und kann auf .NET ineffizient sein.</span><span class="sxs-lookup"><span data-stu-id="9da9a-300">Although this technique is often used in languages such as OCaml, it is bug-prone and can be inefficient on .NET.</span></span> <span data-ttu-id="9da9a-301">Stattdessen empfiehlt es sich, eine `None` Optionswert um einen Fehler anzugeben, dass eine gemeinsame oder erwarteten vorkommen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-301">Instead, consider returning a `None` option value to indicate a failure that is a common or expected occurrence.</span></span>

* <span data-ttu-id="9da9a-302">Dokumentieren Sie Ausnahmen, die von den Komponenten ausgelöst, wenn eine Funktion falsch verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9da9a-302">Document exceptions thrown by your components when a function is used incorrectly.</span></span>

* <span data-ttu-id="9da9a-303">Wenn möglich, nutzen Sie vorhandene Ausnahmen von den System-Namespaces.</span><span class="sxs-lookup"><span data-stu-id="9da9a-303">Where possible, employ existing exceptions from the System namespaces.</span></span> <span data-ttu-id="9da9a-304">Vermeiden Sie <xref:System.ApplicationException>, obwohl.</span><span class="sxs-lookup"><span data-stu-id="9da9a-304">Avoid <xref:System.ApplicationException>, though.</span></span>

* <span data-ttu-id="9da9a-305">Lösen Sie nicht <xref:System.Exception> Wenn es werden mit Escapezeichen versehen für Benutzercode.</span><span class="sxs-lookup"><span data-stu-id="9da9a-305">Do not throw <xref:System.Exception> when it will escape to user code.</span></span> <span data-ttu-id="9da9a-306">Dies schließt die Verwendung von vermeiden `failwith`, `failwithf`, die praktische Funktionen für die Verwendung in Skripts und Code in der Entwicklung sind, jedoch daraus f# Bibliothekscode zugunsten einen spezifischeren Ausnahmetyp auslösen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-306">This includes avoiding the use of `failwith`, `failwithf`, which are handy functions for use in scripting and for code under development, but should be removed from F# library code in favor of throwing a more specific exception type.</span></span>

* <span data-ttu-id="9da9a-307">Verwendung `nullArg`, `invalidArg`, und `invalidOp` als Mechanismus zum lösen <xref:System.ArgumentNullException>, <xref:System.ArgumentException>, und <xref:System.InvalidOperationException> gegebenenfalls.</span><span class="sxs-lookup"><span data-stu-id="9da9a-307">Use `nullArg`, `invalidArg`, and `invalidOp` as the mechanism to throw <xref:System.ArgumentNullException>, <xref:System.ArgumentException>, and <xref:System.InvalidOperationException> when appropriate.</span></span>

#### <a name="consider-using-option-values-for-return-types-when-failure-is-not-an-exceptional-scenario"></a><span data-ttu-id="9da9a-308">Erwägen Sie Optionswerte für Rückgabetypen Wenn war keiner außergewöhnlichen Szenario</span><span class="sxs-lookup"><span data-stu-id="9da9a-308">Consider using option values for return types when failure is not an exceptional scenario</span></span>

<span data-ttu-id="9da9a-309">Der Ansatz .NET Ausnahmen ist, dass sie "herausragende;" werden soll Sie sollten also relativ selten auftreten.</span><span class="sxs-lookup"><span data-stu-id="9da9a-309">The .NET approach to exceptions is that they should be “exceptional”; that is, they should occur relatively infrequently.</span></span> <span data-ttu-id="9da9a-310">Einige Vorgänge (z. B. eine Tabelle suchen) können jedoch häufig fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-310">However, some operations (for example, searching a table) may fail frequently.</span></span> <span data-ttu-id="9da9a-311">F#-Optionswerte sind eine ausgezeichnete Möglichkeit, die Rückgabetypen dieser Vorgänge darstellen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-311">F# option values are an excellent way to represent the return types of these operations.</span></span> <span data-ttu-id="9da9a-312">Diese Vorgänge werden konventionell mit dem Präfix "Try" starten:</span><span class="sxs-lookup"><span data-stu-id="9da9a-312">These operations conventionally start with the name prefix “try”:</span></span>

```fsharp
// bad: throws exception if no element meets criteria
member this.FindFirstIndex(pred : 'T -> bool) : int =
    ...

// bad: returns -1 if no element meets criteria
member this.FindFirstIndex(pred : 'T -> bool) : int =
    ...

// good: returns None if no element meets criteria
member this.TryFindFirstIndex(pred : 'T -> bool) : int option =
    ...
```

### <a name="extension-members"></a><span data-ttu-id="9da9a-313">Erweiterungsmember</span><span class="sxs-lookup"><span data-stu-id="9da9a-313">Extension Members</span></span>

#### <a name="carefully-apply-f-extension-members-in-f-to-f-components"></a><span data-ttu-id="9da9a-314">Sorgfältig gelten f# Erweiterungsmember in f#-zu-Komponenten [F#]</span><span class="sxs-lookup"><span data-stu-id="9da9a-314">Carefully apply F# extension members in F#-to-F# components</span></span>

<span data-ttu-id="9da9a-315">F#-Erweiterungsmember sollte im Allgemeinen nur für Vorgänge verwendet werden, die den Abschluss von systeminternen Vorgänge, die einen Typ in den meisten ihrer Arten der Verwendung zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="9da9a-315">F# extension members should generally only be used for operations that are in the closure of intrinsic operations associated with a type in the majority of its modes of use.</span></span> <span data-ttu-id="9da9a-316">Eine allgemeine Verwendung ist APIs ermöglichen die idiomatische für f# für verschiedene .NET Datentypen sind:</span><span class="sxs-lookup"><span data-stu-id="9da9a-316">One common use is to provide APIs that are more idiomatic to F# for various .NET types:</span></span>

```fsharp
type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        Async.FromBeginEnd(this.BeginReceive, this.EndReceive)

type System.Collections.Generic.IDictionary<'Key,'Value> with
    member this.TryGet key =
        let ok, v = this.TryGetValue key
        if ok then Some v else None
```

### <a name="union-types"></a><span data-ttu-id="9da9a-317">Union-Typen</span><span class="sxs-lookup"><span data-stu-id="9da9a-317">Union Types</span></span>

#### <a name="use-discriminated-unions-instead-of-class-hierarchies-for-tree-structured-data"></a><span data-ttu-id="9da9a-318">Verwenden von Unterscheidungs-Unions statt Klassenhierarchien für Strukturbaums Daten</span><span class="sxs-lookup"><span data-stu-id="9da9a-318">Use discriminated unions instead of class hierarchies for tree-structured data</span></span>

<span data-ttu-id="9da9a-319">Baumähnlichen Strukturen sind rekursiv definiert.</span><span class="sxs-lookup"><span data-stu-id="9da9a-319">Tree-like structures are recursively defined.</span></span> <span data-ttu-id="9da9a-320">Dies ist mit Vererbung umständliche aber elegante mit Unterscheidungs-Unions.</span><span class="sxs-lookup"><span data-stu-id="9da9a-320">This is awkward with inheritance, but elegant with Discriminated Unions.</span></span>

```fsharp
type BST<'T> =
    | Empty
    | Node of 'T * BST<'T> * BST<'T>
```

<span data-ttu-id="9da9a-321">Darstellen von baumähnlichen Daten mit Unterscheidungs-Unions können Sie auch Exhaustiveness Mustervergleich profitieren.</span><span class="sxs-lookup"><span data-stu-id="9da9a-321">Representing tree-like data with Discriminated Unions also allows you to benefit from exhaustiveness in pattern matching.</span></span>

#### <a name="use-requirequalifiedaccess-on-union-types-whose-case-names-are-not-sufficiently-unique"></a><span data-ttu-id="9da9a-322">Verwendung `[<RequireQualifiedAccess>]` auf union-Typen, deren Namen mit Groß-/Kleinschreibung nicht ausreichend eindeutig sind.</span><span class="sxs-lookup"><span data-stu-id="9da9a-322">Use `[<RequireQualifiedAccess>]` on union types whose case names are not sufficiently unique</span></span>

<span data-ttu-id="9da9a-323">Sie können selbst in einer Domäne gefunden werden, in dem gleichnamigen jede Funktion einen Namen für unterschiedliche Dinge, wie z. B. Unterscheidungs-Union-Fälle.</span><span class="sxs-lookup"><span data-stu-id="9da9a-323">You may find yourself in a domain where the same name is the best name for different things, such as Discriminated Union cases.</span></span> <span data-ttu-id="9da9a-324">Sie können `[<RequireQualifiedAccess>]` um Groß-/Kleinschreibung Namen zu unterscheiden, um zu vermeiden, verwirrend Fehler aufgrund von shadowing von abhängt, die die Reihenfolge der Auslösung `open` Anweisungen</span><span class="sxs-lookup"><span data-stu-id="9da9a-324">You can use `[<RequireQualifiedAccess>]` to disambiguate case names in order to avoid triggering confusing errors due to shadowing dependent on the ordering of `open` statements</span></span>

#### <a name="hide-the-representations-of-discriminated-unions-for-binary-compatible-apis-if-the-design-of-these-types-is-likely-to-evolve"></a><span data-ttu-id="9da9a-325">Blenden Sie die Darstellung der Unterscheidungs-Unions für binäre kompatibel APIs, wenn der Entwurf dieser Typen weiterentwickelt wird</span><span class="sxs-lookup"><span data-stu-id="9da9a-325">Hide the representations of discriminated unions for binary compatible APIs if the design of these types is likely to evolve</span></span>

<span data-ttu-id="9da9a-326">Unions-Typen beruhen auf f# Mustervergleich Forms für eine kompakte Programmiermodell.</span><span class="sxs-lookup"><span data-stu-id="9da9a-326">Unions types rely on F# pattern-matching forms for a succinct programming model.</span></span> <span data-ttu-id="9da9a-327">Wie bereits erwähnt, sollten Sie vermeiden, Darstellungen konkreter Daten offenzulegen, wenn der Entwurf dieser Typen weiterentwickelt wird.</span><span class="sxs-lookup"><span data-stu-id="9da9a-327">As mentioned previously, you should avoid revealing concrete data representations if the design of these types is likely to evolve.</span></span>

<span data-ttu-id="9da9a-328">Z. B. die Darstellung des eine Unterscheidungs-Union kann ausgeblendet werden, mit einer privaten oder internen-Deklaration, oder indem Sie eine Signaturdatei.</span><span class="sxs-lookup"><span data-stu-id="9da9a-328">For example, the representation of a discriminated union can be hidden using a private or internal declaration, or by using a signature file.</span></span>

```fsharp
type Union =
    private
    | CaseA of int
    | CaseB of string
```

<span data-ttu-id="9da9a-329">Wenn Sie Unterscheidungs-Unions wahllos offenlegen, möglicherweise finden Sie es schwer zu Version die Bibliothek ohne Unterbrechung von Benutzercode.</span><span class="sxs-lookup"><span data-stu-id="9da9a-329">If you reveal discriminated unions indiscriminately, you may find it hard to version your library without breaking user code.</span></span> <span data-ttu-id="9da9a-330">Erwägen Sie stattdessen eine oder mehrere aktive Muster gestatten Mustervergleich über Werte des Typs offenzulegen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-330">Instead, consider revealing one or more active patterns to permit pattern matching over values of your type.</span></span>

<span data-ttu-id="9da9a-331">Aktive Muster bieten eine alternative Möglichkeit zum Bereitstellen f# Consumer Musterabgleich Verfügbarmachen von F#-Union-Typen direkt zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="9da9a-331">Active patterns provide an alternate way to provide F# consumers with pattern matching while avoiding exposing F# Union Types directly.</span></span>

### <a name="inline-functions-and-member-constraints"></a><span data-ttu-id="9da9a-332">Inlinefunktionen und Membereinschränkungen</span><span class="sxs-lookup"><span data-stu-id="9da9a-332">Inline Functions and Member Constraints</span></span>

#### <a name="define-generic-numeric-algorithms-using-inline-functions-with-implied-member-constraints-and-statically-resolved-generic-types"></a><span data-ttu-id="9da9a-333">Definieren von generischen numerischen Algorithmen, die Verwendung von Inlinefunktionen mit impliziten Membereinschränkungen und statisch aufgelösten generischen Typen</span><span class="sxs-lookup"><span data-stu-id="9da9a-333">Define generic numeric algorithms using inline functions with implied member constraints and statically resolved generic types</span></span>

<span data-ttu-id="9da9a-334">Arithmetische Member und F#-Vergleich Einschränkungen sind ein Standard für f#-Programmierung.</span><span class="sxs-lookup"><span data-stu-id="9da9a-334">Arithmetic member constraints and F# comparison constraints are a standard for F# programming.</span></span> <span data-ttu-id="9da9a-335">Beachten Sie z. B. folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="9da9a-335">For example, consider the following code:</span></span>

```fsharp
let inline highestCommonFactor a b =
    let rec loop a b =
        if a = LanguagePrimitives.GenericZero<_> then b
        elif a < b then loop a (b - a)
        else loop (a - b) b
    loop a b
```

<span data-ttu-id="9da9a-336">Der Typ dieser Funktion lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="9da9a-336">The type of this function is as follows:</span></span>

```fsharp
val inline highestCommonFactor : ^T -> ^T -> ^T
                when ^T : (static member Zero : ^T)
                and ^T : (static member ( - ) : ^T * ^T -> ^T)
                and ^T : equality
                and ^T : comparison
```

<span data-ttu-id="9da9a-337">Dies ist eine passende Funktion für eine öffentliche API in einer mathematischen Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="9da9a-337">This is a suitable function for a public API in a mathematical library.</span></span>

#### <a name="avoid-using-member-constraints-to-simulate-type-classes-and-duck-typing"></a><span data-ttu-id="9da9a-338">Vermeiden Sie die Verwendung von Membereinschränkungen um zu simulieren, Klassen und Ente eingeben</span><span class="sxs-lookup"><span data-stu-id="9da9a-338">Avoid using member constraints to simulate type classes and duck typing</span></span>

<span data-ttu-id="9da9a-339">Es ist möglich, simulieren "Wildenten eingeben" mit der F#-Member-Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-339">It is possible to simulate “duck typing” using F# member constraints.</span></span> <span data-ttu-id="9da9a-340">Allerdings Elemente, die Stellen mithilfe dieses sollten nicht im Allgemeinen in f# verwendet-zu-Entwürfe für f#-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="9da9a-340">However, members that make use of this should not in general be used in F#-to-F# library designs.</span></span> <span data-ttu-id="9da9a-341">Dies ist da Bibliothek Entwürfe anhand von unbekannten oder nicht standardmäßigen implizite Einschränkungen eher dazu führen, dass der Benutzercode unflexibel und an einem bestimmten Framework-Muster gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="9da9a-341">This is because library designs based on unfamiliar or non-standard implicit constraints tend to cause user code to become inflexible and tied to one particular framework pattern.</span></span>

<span data-ttu-id="9da9a-342">Darüber hinaus ist eine gute Chance, die starke Nutzung von Membereinschränkungen auf diese Weise zu sehr langen kompilierzeiten führen kann.</span><span class="sxs-lookup"><span data-stu-id="9da9a-342">Additionally, there is a good chance that heavy use of member constraints in this manner can result in very long compile times.</span></span>

### <a name="operator-definitions"></a><span data-ttu-id="9da9a-343">Operatordefinitionen</span><span class="sxs-lookup"><span data-stu-id="9da9a-343">Operator Definitions</span></span>

#### <a name="avoid-defining-custom-symbolic-operators"></a><span data-ttu-id="9da9a-344">Vermeiden Sie definieren von benutzerdefinierten symbolischen Operatoren</span><span class="sxs-lookup"><span data-stu-id="9da9a-344">Avoid defining custom symbolic operators</span></span>

<span data-ttu-id="9da9a-345">Benutzerdefinierte Operatoren sind in einigen Situationen wichtig und höchst Hilfereiche Schreibweisen Geräten innerhalb einer große Text der Implementierungscode.</span><span class="sxs-lookup"><span data-stu-id="9da9a-345">Custom operators are essential in some situations and are highly useful notational devices within a large body of implementation code.</span></span> <span data-ttu-id="9da9a-346">Für neue Benutzer einer Bibliothek sind benannte Funktionen häufig einfacher zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9da9a-346">For new users of a library, named functions are often easier to use.</span></span> <span data-ttu-id="9da9a-347">Darüber hinaus benutzerdefinierte symbolische Operatoren Dokument schwer sein, und Benutzer gefunden schwieriger, um Hilfe für Operatoren, die aufgrund von vorhandenen Einschränkungen bei der IDE und suchen Sie Module zu suchen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-347">In addition, custom symbolic operators can be hard to document, and users find it more difficult to look up help on operators, due to existing limitations in IDE and search engines.</span></span>

<span data-ttu-id="9da9a-348">Daher ist es am besten, veröffentlichen Sie Ihre Funktionalität wie benannten Funktionen und Elemente, und nur, wenn die notationsvorteile überwiegen, die Dokumentation und cognitive Kosten müssen sie außerdem die Operatoren für diese Funktionalität verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-348">As a result, it is best to publish your functionality as named functions and members, and additionally expose operators for this functionality only if the notational benefits outweigh the documentation and cognitive cost of having them.</span></span>

### <a name="units-of-measure"></a><span data-ttu-id="9da9a-349">Maßeinheiten</span><span class="sxs-lookup"><span data-stu-id="9da9a-349">Units of Measure</span></span>

#### <a name="carefully-use-units-of-measure-for-added-type-safety-in-f-code"></a><span data-ttu-id="9da9a-350">Verwenden Sie sorgfältig Maßeinheiten für hinzugefügte typsicherheit in f#-code</span><span class="sxs-lookup"><span data-stu-id="9da9a-350">Carefully use units of measure for added type safety in F# code</span></span>

<span data-ttu-id="9da9a-351">Zusätzliche typisierungsinformationen Einheiten des Measures wird gelöscht, wenn Sie von anderen .NET-Programmiersprachen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9da9a-351">Additional typing information for units of measure is erased when viewed by other .NET languages.</span></span> <span data-ttu-id="9da9a-352">Denken Sie daran, dass Visual Studio .NET Komponenten, Tools und Reflektion Typen sans Einheiten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9da9a-352">Be aware that .NET components, tools, and reflection will see types-sans-units.</span></span> <span data-ttu-id="9da9a-353">C#-Consumer werden angezeigt, z. B. `float` statt `float<kg>`.</span><span class="sxs-lookup"><span data-stu-id="9da9a-353">For example, C# consumers will see `float` rather than `float<kg>`.</span></span>

### <a name="type-abbreviations"></a><span data-ttu-id="9da9a-354">Typabkürzungen</span><span class="sxs-lookup"><span data-stu-id="9da9a-354">Type Abbreviations</span></span>

#### <a name="carefully-use-type-abbreviations-to-simplify-f-code"></a><span data-ttu-id="9da9a-355">Typabkürzungen bedacht zu verwenden, um f#-Code zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-355">Carefully use type abbreviations to simplify F# code</span></span>

<span data-ttu-id="9da9a-356">Visual Studio .NET Komponenten, Tools und Reflektion werden nicht auf die abgekürzte Namen für Typen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9da9a-356">.NET components, tools, and reflection will not see abbreviated names for types.</span></span> <span data-ttu-id="9da9a-357">Bedeutender Verwendung von typabkürzungen kann auch eine Domäne angezeigt, je komplexer als es tatsächlich ist die konnte Consumer zu verwechseln, vornehmen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-357">Significant usage of type abbreviations can also make a domain appear more complex than it actually is, which could confuse consumers.</span></span>

#### <a name="avoid-type-abbreviations-for-public-types-whose-members-and-properties-should-be-intrinsically-different-to-those-available-on-the-type-being-abbreviated"></a><span data-ttu-id="9da9a-358">Vermeiden Sie typabkürzungen für öffentliche Typen, deren Elemente und Eigenschaften verfügbar sind, auf den Typ wird abgekürzt systemintern verschiedene werden soll</span><span class="sxs-lookup"><span data-stu-id="9da9a-358">Avoid type abbreviations for public types whose members and properties should be intrinsically different to those available on the type being abbreviated</span></span>

<span data-ttu-id="9da9a-359">In diesem Fall wird der Typ wird abgekürzt viel über die Darstellung des aktuellen Typs definiert wird.</span><span class="sxs-lookup"><span data-stu-id="9da9a-359">In this case, the type being abbreviated reveals too much about the representation of the actual type being defined.</span></span> <span data-ttu-id="9da9a-360">Stattdessen umschließen Sie die Abkürzung in einen Klassentyp oder einen einzelnen Fall Unterscheidungs-Union (oder, wenn Leistung wichtig ist, erwägen Sie einen Strukturtyp um zu umschließen die Abkürzung).</span><span class="sxs-lookup"><span data-stu-id="9da9a-360">Instead, consider wrapping the abbreviation in a class type or a single-case discriminated union (or, when performance is essential, consider using a struct type to wrap the abbreviation).</span></span>

<span data-ttu-id="9da9a-361">Beispielsweise ist es verlockend, um eine Zuordnung mit mehreren als Sonderfall einer F#-Zuordnung, z. B. zu definieren:</span><span class="sxs-lookup"><span data-stu-id="9da9a-361">For example, it is tempting to define a multi-map as a special case of an F# map, for example:</span></span>

```fsharp
type MultiMap<'Key,'Value> = Map<'Key,'Value list>
```

<span data-ttu-id="9da9a-362">Allerdings die logischen Punktnotation Vorgänge für diesen Typ sind nicht identisch mit der Vorgänge auf einer Karte, – beispielsweise ist es sinnvoll, ordnen Sie die Lookup-Operator. [Key] Rückgabe der leere Liste, wenn der Schlüssel nicht im Wörterbuch, anstatt durch das Auslösen einer Ausnahme ist.</span><span class="sxs-lookup"><span data-stu-id="9da9a-362">However, the logical dot-notation operations on this type are not the same as the operations on a Map – for example, it is reasonable that the lookup operator map.[key] return the empty list if the key is not in the dictionary, rather than raising an exception.</span></span>

## <a name="guidelines-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="9da9a-363">Richtlinien für die Bibliotheken für die Verwendung der anderen .NET-Sprachen</span><span class="sxs-lookup"><span data-stu-id="9da9a-363">Guidelines for libraries for Use from other .NET Languages</span></span>

<span data-ttu-id="9da9a-364">Bei Bibliotheken für die Verwendung anderer Sprachen .NET zu entwerfen, ist es wichtig, entsprechen die [Entwurfsrichtlinien von .NET Bibliothek](../../standard/design-guidelines/index.md).</span><span class="sxs-lookup"><span data-stu-id="9da9a-364">When designing libraries for use from other .NET languages, it is important to adhere to the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md).</span></span> <span data-ttu-id="9da9a-365">In diesem Dokument diese Bibliotheken herkömmlichen .NET Bibliotheken, im Gegensatz zu f# beschriftet-zugängliche Bibliotheken, die f# verwenden ohne Einschränkung erstellt.</span><span class="sxs-lookup"><span data-stu-id="9da9a-365">In this document, these libraries are labeled as vanilla .NET libraries, as opposed to F#-facing libraries that use F# constructs without restriction.</span></span> <span data-ttu-id="9da9a-366">Entwerfen von herkömmlichen .NET Bibliotheken bedeutet Bereitstellen von vertraut sind und idiomatische-APIs, die konsistent mit dem Rest des .NET Framework minimieren die Verwendung von f#-spezifische Konstrukte in der öffentlichen API.</span><span class="sxs-lookup"><span data-stu-id="9da9a-366">Designing vanilla .NET libraries means providing familiar and idiomatic APIs consistent with the rest of the .NET Framework by minimizing the use of F#-specific constructs in the public API.</span></span> <span data-ttu-id="9da9a-367">Die Regeln werden in den folgenden Abschnitten erläutert.</span><span class="sxs-lookup"><span data-stu-id="9da9a-367">The rules are explained in the following sections.</span></span>

### <a name="namespace-and-type-design-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="9da9a-368">Namespace und Typ Entwurf (für Bibliotheken für die Verwendung anderer Sprachen .NET)</span><span class="sxs-lookup"><span data-stu-id="9da9a-368">Namespace and Type design (for libraries for use from other .NET Languages)</span></span>

#### <a name="apply-the-net-naming-conventions-to-the-public-api-of-your-components"></a><span data-ttu-id="9da9a-369">Übernehmen Sie die .NET-Namenskonventionen, um die öffentliche API-Komponenten</span><span class="sxs-lookup"><span data-stu-id="9da9a-369">Apply the .NET naming conventions to the public API of your components</span></span>

<span data-ttu-id="9da9a-370">Achten Sie besonders auf die Verwendung von abgekürzten Namen und die .NET Groß-/Kleinschreibung Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="9da9a-370">Pay special attention to the use of abbreviated names and the .NET capitalization guidelines.</span></span>

```fsharp
type pCoord = ...
    member this.theta = ...

type PolarCoordinate = ...
    member this.Theta = ...
```

#### <a name="use-namespaces-types-and-members-as-the-primary-organizational-structure-for-your-components"></a><span data-ttu-id="9da9a-371">Verwenden von Namespaces, Typen und Membern als die primäre Organisationsstruktur für Ihre Komponenten</span><span class="sxs-lookup"><span data-stu-id="9da9a-371">Use namespaces, types, and members as the primary organizational structure for your components</span></span>

<span data-ttu-id="9da9a-372">Alle Dateien, die mit öffentlichen Funktionen sollten beginnen mit einer `namespace` Deklaration und die nur öffentliche Entitäten in Namespaces Typen werden sollte.</span><span class="sxs-lookup"><span data-stu-id="9da9a-372">All files containing public functionality should begin with a `namespace` declaration, and the only public-facing entities in namespaces should be types.</span></span> <span data-ttu-id="9da9a-373">Verwenden Sie F#-Module nicht.</span><span class="sxs-lookup"><span data-stu-id="9da9a-373">Do not use F# modules.</span></span>

<span data-ttu-id="9da9a-374">Verwenden Sie nicht öffentlich Module, um Implementierungscode Hilfsprogramm Typen und Hilfsfunktionen aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-374">Use non-public modules to hold implementation code, utility types, and utility functions.</span></span>

<span data-ttu-id="9da9a-375">Statische Typen sollte bevorzugte mit Modulen, sie können für die zukünftige Evolution der API Überladen von Operatoren und anderer .NET API Entwurfskonzepte verwenden, die nicht in F#-Modulen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="9da9a-375">Static types should be preferred over modules, as they allow for future evolution of the API to use overloading and other .NET API design concepts that may not be used within F# modules.</span></span>

<span data-ttu-id="9da9a-376">Beispielsweise anstelle der folgenden öffentlichen API:</span><span class="sxs-lookup"><span data-stu-id="9da9a-376">For example, in place of the following public API:</span></span>

```fsharp
module Fabrikam

module Utilities =
    let Name = "Bob"
    let Add2 x y = x + y
    let Add3 x y z = x + y + z
```

<span data-ttu-id="9da9a-377">Erwägen Sie stattdessen die:</span><span class="sxs-lookup"><span data-stu-id="9da9a-377">Consider instead:</span></span>

```fsharp
namespace Fabrikam

[<AbstractClass; Sealed>]
type Utilities =
    static member Name = "Bob"
    static member Add(x,y) = x + y
    static member Add(x,y,z) = x + y + z
```

#### <a name="use-f-record-types-in-vanilla-net-apis-if-the-design-of-the-types-wont-evolve"></a><span data-ttu-id="9da9a-378">Verwenden Sie f# Datensatztypen in Vanille .NET APIs, wenn der Entwurf der Typen weiterentwickelt wird nicht</span><span class="sxs-lookup"><span data-stu-id="9da9a-378">Use F# record types in vanilla .NET APIs if the design of the types won't evolve</span></span>

<span data-ttu-id="9da9a-379">F#-Datensatztypen, die in einer einfachen .NET Klasse kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="9da9a-379">F# record types compile to a simple .NET class.</span></span> <span data-ttu-id="9da9a-380">Diese sind für einige einfachen, stabilen Typen in APIs geeignet.</span><span class="sxs-lookup"><span data-stu-id="9da9a-380">These are suitable for some simple, stable types in APIs.</span></span> <span data-ttu-id="9da9a-381">Verwenden Sie die `[<NoEquality>]` und `[<NoComparison>]` Attribute, um die automatische Generierung von Schnittstellen zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="9da9a-381">You should consider using the `[<NoEquality>]` and `[<NoComparison>]` attributes to suppress the automatic generation of interfaces.</span></span> <span data-ttu-id="9da9a-382">Vermeiden Sie auch die Verwendung von änderbare Datensatzfelder in Vanille-.NET APIs als diese macht eines öffentlichen Felds.</span><span class="sxs-lookup"><span data-stu-id="9da9a-382">Also avoid using mutable record fields in vanilla .NET APIs as these exposes a public field.</span></span> <span data-ttu-id="9da9a-383">In Betracht gezogen Sie, ob eine Klasse eine flexiblere Option für die Entwicklung der API bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="9da9a-383">Always consider whether a class would provide a more flexible option for future evolution of the API.</span></span>

<span data-ttu-id="9da9a-384">Beispielsweise macht die folgenden f#-Code die öffentliche API für einen Consumer, c# verfügbar:</span><span class="sxs-lookup"><span data-stu-id="9da9a-384">For example, the following F# code exposes the public API to a C# consumer:</span></span>

<span data-ttu-id="9da9a-385">F# ERLÄUTERT WERDEN:</span><span class="sxs-lookup"><span data-stu-id="9da9a-385">F#:</span></span>

```fsharp
[<NoEquality; NoComparison>]
type MyRecord =
    { FirstThing : int
        SecondThing : string }
```

<span data-ttu-id="9da9a-386">C#:</span><span class="sxs-lookup"><span data-stu-id="9da9a-386">C#:</span></span>

```csharp
public sealed class MyRecord
{
    public MyRecord(int firstThing, string secondThing);
    public int FirstThing { get; }
    public string SecondThing { get; }
}
```

#### <a name="hide-the-representation-of-f-union-types-in-vanilla-net-apis"></a><span data-ttu-id="9da9a-387">Die Darstellung der union f#-Typen in Vanille-.NET APIs ausblenden</span><span class="sxs-lookup"><span data-stu-id="9da9a-387">Hide the representation of F# union types in vanilla .NET APIs</span></span>

<span data-ttu-id="9da9a-388">F#-union-Typen werden im Allgemeinen nicht verwendet über komponentenbegrenzungen hinweg, sogar für f#-zu-F#-Programmierung.</span><span class="sxs-lookup"><span data-stu-id="9da9a-388">F# union types are not commonly used across component boundaries, even for F#-to-F# coding.</span></span> <span data-ttu-id="9da9a-389">Sie sind eine ausgezeichnete Implementierung Gerät intern für Komponenten und -Bibliotheken verwendet.</span><span class="sxs-lookup"><span data-stu-id="9da9a-389">They are an excellent implementation device when used internally within components and libraries.</span></span>

<span data-ttu-id="9da9a-390">Beim Entwerfen eines herkömmlichen .NET API sollten Sie die Darstellung eines union-Typs mit einem privaten Deklaration oder eine Signaturdatei ausblenden.</span><span class="sxs-lookup"><span data-stu-id="9da9a-390">When designing a vanilla .NET API, consider hiding the representation of a union type by using either a private declaration or a signature file.</span></span>

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True
```

<span data-ttu-id="9da9a-391">Sie können auch Typen erweitern, die intern eine union Darstellung mit Elementen verwenden, um eine gewünschte bereitzustellen. NET-verbundene-API.</span><span class="sxs-lookup"><span data-stu-id="9da9a-391">You may also augment types that use a union representation internally with members to provide a desired .NET-facing API.</span></span>

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True

    /// A public member for use from C#
    member x.Evaluate =
        match x with
        | And(a,b) -> a.Evaluate && b.Evaluate
        | Not a -> not a.Evaluate
        | True -> true

    /// A public member for use from C#
    static member CreateAnd(a,b) = And(a,b)
```

#### <a name="design-gui-and-other-components-using-the-design-patterns-of-the-framework"></a><span data-ttu-id="9da9a-392">Design-GUI und andere Komponenten, die mit den Entwurfsmustern von framework</span><span class="sxs-lookup"><span data-stu-id="9da9a-392">Design GUI and other components using the design patterns of the framework</span></span>

<span data-ttu-id="9da9a-393">Es sind viele verschiedene Frameworks im .NET, z. B. WinForms, WPF und ASP.NET verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9da9a-393">There are many different frameworks available within .NET, such as WinForms, WPF, and ASP.NET.</span></span> <span data-ttu-id="9da9a-394">Benennen und Entwurf Konventionen für die einzelnen sollte verwendet werden, wenn Sie Komponenten für die Verwendung in diesen Frameworks entwerfen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-394">Naming and design conventions for each should be used if you are designing components for use in these frameworks.</span></span> <span data-ttu-id="9da9a-395">Übernehmen Sie für WPF-Programmierung, z. B. WPF-Entwurfsmuster für die Klassen, mit denen, die Sie entwerfen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-395">For example, for WPF programming, adopt WPF design patterns for the classes you are designing.</span></span> <span data-ttu-id="9da9a-396">Verwenden Sie für Modelle im Programmierung der Benutzeroberfläche, Entwurfsmuster, z. B. Ereignisse, und Sammlungen benachrichtigungsbasierter, z. B. die finden Sie in <xref:System.Collections.ObjectModel>.</span><span class="sxs-lookup"><span data-stu-id="9da9a-396">For models in user interface programming, use design patterns such as events and notification-based collections such as those found in <xref:System.Collections.ObjectModel>.</span></span>

### <a name="object-and-member-design-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="9da9a-397">Objekt und Element-Entwurf (für Bibliotheken für die Verwendung anderer Sprachen .NET)</span><span class="sxs-lookup"><span data-stu-id="9da9a-397">Object and Member design (for libraries for use from other .NET Languages)</span></span>

#### <a name="use-the-clievent-attribute-to-expose-net-events"></a><span data-ttu-id="9da9a-398">Verwenden Sie das CLIEvent-Attribut .NET Ereignisse verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-398">Use the CLIEvent attribute to expose .NET events</span></span>

<span data-ttu-id="9da9a-399">Erstellen einer `DelegateEvent` mit einer bestimmten .NET Delegattyp, der ein Objekt akzeptiert und `EventArgs` (anstelle einer `Event`, die gerade verwendet die `FSharpHandler` standardmäßig Typ), damit die Ereignisse auf die vertraute Weise für andere Sprachen .NET veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="9da9a-399">Construct a `DelegateEvent` with a specific .NET delegate type that takes an object and `EventArgs` (rather than an `Event`, which just uses the `FSharpHandler` type by default) so that the events are published in the familiar way to other .NET languages.</span></span>

```fsharp
type MyBadType() =
    let myEv = new Event<int>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish

type MyEventArgs(x:int) =
    inherit System.EventArgs()
    member this.X = x

    /// A type in a component designed for use from other .NET languages
type MyGoodType() =
    let myEv = new DelegateEvent<EventHandler<MyEventArgs>>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish
```

#### <a name="expose-asynchronous-operations-as-methods-which-return-net-tasks"></a><span data-ttu-id="9da9a-400">Asynchrone Vorgänge als Methoden, die .NET Aufgaben zurückzugeben verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="9da9a-400">Expose asynchronous operations as methods which return .NET tasks</span></span>

<span data-ttu-id="9da9a-401">Aufgaben werden in .NET zum aktive asynchrone Berechnungen darstellen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-401">Tasks are used in .NET to represent active asynchronous computations.</span></span> <span data-ttu-id="9da9a-402">Aufgaben sind im Allgemeinen weniger als f# festgelegte `Async<T>` Objekte, da sie die Aufgaben "bereits ausgeführt" darstellen und nicht zusammen Möglichkeiten bestehen können, parallele Komposition ausführen oder das Ausblenden der Weitergabe von Abbruch Signale und andere, kontextbezogene Parameter.</span><span class="sxs-lookup"><span data-stu-id="9da9a-402">Tasks are in general less compositional than F# `Async<T>` objects, since they represent “already executing” tasks and can’t be composed together in ways that perform parallel composition, or which hide the propagation of cancellation signals and other contextual parameters.</span></span>

<span data-ttu-id="9da9a-403">Allerdings sind Methoden, die Aufgaben zurückzugeben, ungeachtet der standarddarstellung der asynchronen Programmierung in .NET.</span><span class="sxs-lookup"><span data-stu-id="9da9a-403">However, despite this, methods which return Tasks are the standard representation of asynchronous programming on .NET.</span></span>

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =

    let compute (x: int) : Async<int> = async { ... }

    member this.ComputeAsync(x) = compute x |> Async.StartAsTask
```

<span data-ttu-id="9da9a-404">Sie werden häufig auch als explizites Abbruchtoken akzeptieren möchten:</span><span class="sxs-lookup"><span data-stu-id="9da9a-404">You will frequently also want to accept an explicit cancellation token:</span></span>

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =
    let compute(x:int) : Async<int> = async { ... }
    member this.ComputeAsTask(x, cancellationToken) = Async.StartAsTask(compute x, cancellationToken)
```

#### <a name="use-net-delegate-types-instead-of-f-function-types"></a><span data-ttu-id="9da9a-405">Verwenden von .NET Delegattypen anstelle von f#-Typen-Funktion</span><span class="sxs-lookup"><span data-stu-id="9da9a-405">Use .NET delegate types instead of F# function types</span></span>

<span data-ttu-id="9da9a-406">Hier "f# Funktionstypen" bedeutet "Pfeil"-Typen wie `int -> int`.</span><span class="sxs-lookup"><span data-stu-id="9da9a-406">Here “F# function types” mean “arrow” types like `int -> int`.</span></span>

<span data-ttu-id="9da9a-407">Statt diesen:</span><span class="sxs-lookup"><span data-stu-id="9da9a-407">Instead of this:</span></span>

```fsharp
member this.Transform(f:int->int) =
    ...
```

<span data-ttu-id="9da9a-408">Vorgehensweise:</span><span class="sxs-lookup"><span data-stu-id="9da9a-408">Do this:</span></span>

```fsharp
member this.Transform(f:Func<int,int>) =
    ...
```

<span data-ttu-id="9da9a-409">Der f#-Funktionstyps wird als `class FSharpFunc<T,U>` für andere Sprachen .NET und eignet sich weniger für die Sprachfeatures und Tools, die Delegattypen kennen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-409">The F# function type appears as `class FSharpFunc<T,U>` to other .NET languages, and is less suitable for language features and tooling that understand delegate types.</span></span> <span data-ttu-id="9da9a-410">Beim Erstellen einer .NET Framework 3.5 oder höher abzielt höherer Ordnung-Methode der `System.Func` und `System.Action` Delegaten sind die richtigen APIs veröffentlichen, damit .NET Entwickler diese APIs in einer Weise niedrig problemlose nutzen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-410">When authoring a higher-order method targeting .NET Framework 3.5 or higher, the `System.Func` and `System.Action` delegates are the right APIs to publish to enable .NET developers to consume these APIs in a low-friction manner.</span></span> <span data-ttu-id="9da9a-411">(Wenn .NET Framework 2.0 abzielen, werden systemdefinierte Delegattypen mehr beschränkt. das bedeutet, mithilfe von vordefinierten Delegattypen wie z. B. `System.Converter<T,U>` oder einen bestimmten Delegattyp zu definieren.)</span><span class="sxs-lookup"><span data-stu-id="9da9a-411">(When targeting .NET Framework 2.0, the system-defined delegate types are more limited; consider using predefined delegate types such as `System.Converter<T,U>` or defining a specific delegate type.)</span></span>

<span data-ttu-id="9da9a-412">Auf der Seite kippen .NET Delegaten sind nicht für f# natürliche-zugängliche Bibliotheken (finden Sie im nächsten Abschnitt in f#-Bibliotheken nach).</span><span class="sxs-lookup"><span data-stu-id="9da9a-412">On the flip side, .NET delegates are not natural for F#-facing libraries (see the next Section on F#-facing libraries).</span></span> <span data-ttu-id="9da9a-413">Daher ist eine verbreitete Implementierungsstrategie beim Entwickeln von höherer Ordnung Methoden für herkömmlichen .NET-Bibliotheken, erstellen alle die Implementierung mit f#-Typen-Funktion, und klicken Sie dann der öffentlichen API mithilfe von Delegaten als dünne Fassade über die tatsächliche f# -Implementierung.</span><span class="sxs-lookup"><span data-stu-id="9da9a-413">As a result, a common implementation strategy when developing higher-order methods for vanilla .NET libraries is to author all the implementation using F# function types, and then create the public API using delegates as a thin façade atop the actual F# implementation.</span></span>

#### <a name="use-the-trygetvalue-pattern-instead-of-returning-f-option-values-and-prefer-method-overloading-to-taking-f-option-values-as-arguments"></a><span data-ttu-id="9da9a-414">Verwenden Sie das TryGetValue-Muster, anstatt von f#-Optionswerte und bevorzugen Sie Überladen von Methoden mit dem Erstellen der Optionswerte f# als Argumente</span><span class="sxs-lookup"><span data-stu-id="9da9a-414">Use the TryGetValue pattern instead of returning F# option values, and prefer method overloading to taking F# option values as arguments</span></span>

<span data-ttu-id="9da9a-415">Häufige Muster von der Verwendung für den F#-Option-Typ in-APIs sind besser in Vanille implementiert .NET APIs, die mit standardmäßigen .NET entwerfen Techniken.</span><span class="sxs-lookup"><span data-stu-id="9da9a-415">Common patterns of use for the F# option type in APIs are better implemented in vanilla .NET APIs using standard .NET design techniques.</span></span> <span data-ttu-id="9da9a-416">Anstatt einen f#-Wert, erwägen Sie den Rückgabetyp Bool plus ein Out-Parameter wie das Muster "TryGetValue".</span><span class="sxs-lookup"><span data-stu-id="9da9a-416">Instead of returning an F# option value, consider using the bool return type plus an out parameter as in the "TryGetValue" pattern.</span></span> <span data-ttu-id="9da9a-417">Und statt f# Optionswerte als Parameter zu verwenden, bietet sich das Überladen von Methoden oder optionale Argumente.</span><span class="sxs-lookup"><span data-stu-id="9da9a-417">And instead of taking F# option values as parameters, consider using method overloading or optional arguments.</span></span>

```fsharp
member this.ReturnOption() = Some 3

member this.ReturnBoolAndOut(outVal : byref<int>) =
    outVal <- 3
    true

member this.ParamOption(x : int, y : int option) =
    match y with
    | Some y2 -> x + y2
    | None -> x

member this.ParamOverload(x : int) = x

member this.ParamOverload(x : int, y : int) = x + y
```

#### <a name="use-the-net-collection-interface-types-ienumerablet-and-idictionarykeyvalue-for-parameters-and-return-values"></a><span data-ttu-id="9da9a-418">Verwenden Sie die .NET sammlungsschnittstelle Typen IEnumerable\<T\> und IDictionary\<Schlüssel, Wert\> für Parameter und Rückgabewerte</span><span class="sxs-lookup"><span data-stu-id="9da9a-418">Use the .NET collection interface types IEnumerable\<T\> and IDictionary\<Key,Value\> for parameters and return values</span></span>

<span data-ttu-id="9da9a-419">Vermeiden Sie die Verwendung der konkreten Auflistungstypen, z. B. .NET Arrays `T[]`, f#-Typen `list<T>`, `Map<Key,Value>` und `Set<T>`, und .NET konkreten Auflistungstypen wie `Dictionary<Key,Value>`.</span><span class="sxs-lookup"><span data-stu-id="9da9a-419">Avoid the use of concrete collection types such as .NET arrays `T[]`, F# types `list<T>`, `Map<Key,Value>` and `Set<T>`, and .NET concrete collection types such as `Dictionary<Key,Value>`.</span></span> <span data-ttu-id="9da9a-420">Die Entwurfsrichtlinien von .NET Bibliothek haben gut Bezug auf das Verwenden von unterschiedlichen Auflistungstypen, z. B. `IEnumerable<T>`.</span><span class="sxs-lookup"><span data-stu-id="9da9a-420">The .NET Library Design Guidelines have good advice regarding when to use various collection types like `IEnumerable<T>`.</span></span> <span data-ttu-id="9da9a-421">Einige verwenden von Arrays (`T[]`) in einigen Fällen aus Gründen, die Leistung akzeptabel ist.</span><span class="sxs-lookup"><span data-stu-id="9da9a-421">Some use of arrays (`T[]`) is acceptable in some circumstances, on performance grounds.</span></span> <span data-ttu-id="9da9a-422">Beachten Sie insbesondere, dass `seq<T>` wird nur der F#-alias für `IEnumerable<T>`, und daher Seq ist häufig für eines herkömmlichen .NET API einen entsprechenden Typ.</span><span class="sxs-lookup"><span data-stu-id="9da9a-422">Note especially that `seq<T>` is just the F# alias for `IEnumerable<T>`, and thus seq is often an appropriate type for a vanilla .NET API.</span></span>

<span data-ttu-id="9da9a-423">Stattdessen führt der F#:</span><span class="sxs-lookup"><span data-stu-id="9da9a-423">Instead of F# lists:</span></span>

```fsharp
member this.PrintNames(names : string list) =
    ...
```

<span data-ttu-id="9da9a-424">Verwenden Sie F#-Sequenzen:</span><span class="sxs-lookup"><span data-stu-id="9da9a-424">Use F# sequences:</span></span>

```fsharp
member this.PrintNames(names : seq<string>) =
    ...
```

#### <a name="use-the-unit-type-as-the-only-input-type-of-a-method-to-define-a-zero-argument-method-or-as-the-only-return-type-to-define-a-void-returning-method"></a><span data-ttu-id="9da9a-425">Unit-Typ als des einzigen Typs der Eingabe einer Methode verwenden, definieren Sie die Methode eine NULL-Argument, oder als die einzige Rückgabetyp definieren eine "void" zurückgebende-Methode</span><span class="sxs-lookup"><span data-stu-id="9da9a-425">Use the unit type as the only input type of a method to define a zero-argument method, or as the only return type to define a void-returning method</span></span>

<span data-ttu-id="9da9a-426">Vermeiden Sie andere Verwendungen des Typs der.</span><span class="sxs-lookup"><span data-stu-id="9da9a-426">Avoid other uses of the unit type.</span></span> <span data-ttu-id="9da9a-427">Dies sind gute:</span><span class="sxs-lookup"><span data-stu-id="9da9a-427">These are good:</span></span>

```fsharp
✔ member this.NoArguments() = 3

✔ member this.ReturnVoid(x : int) = ()
```

<span data-ttu-id="9da9a-428">Dies ist ungültig:</span><span class="sxs-lookup"><span data-stu-id="9da9a-428">This is bad:</span></span>

```fsharp
member this.WrongUnit( x:unit, z:int) = ((), ())
```

#### <a name="check-for-null-values-on-vanilla-net-api-boundaries"></a><span data-ttu-id="9da9a-429">Überprüfen Sie null-Werte auf herkömmlichen .NET API-Grenzen</span><span class="sxs-lookup"><span data-stu-id="9da9a-429">Check for null values on vanilla .NET API boundaries</span></span>

<span data-ttu-id="9da9a-430">F#-Implementierungscode tendenziell weniger null-Werte, aufgrund der unveränderliche Entwurfsmuster und Einschränkungen bei der Verwendung des null-Literale für f#-Typen enthalten.</span><span class="sxs-lookup"><span data-stu-id="9da9a-430">F# implementation code tends to have fewer null values, due to immutable design patterns and restrictions on use of null literals for F# types.</span></span> <span data-ttu-id="9da9a-431">Anderssprachige .NET verwenden häufig sehr viel häufiger null als Wert.</span><span class="sxs-lookup"><span data-stu-id="9da9a-431">Other .NET languages often use null as a value much more frequently.</span></span> <span data-ttu-id="9da9a-432">Aus diesem Grund sollten F#-Code, der ein herkömmlichen .NET API verfügbar macht, ist Überprüfen der Parameter für Null-Zeichen an der Grenze der API und verhindern, dass diese Werte fließen tiefer in den f#-Code-Implementierung.</span><span class="sxs-lookup"><span data-stu-id="9da9a-432">Because of this, F# code that is exposing a vanilla .NET API should check parameters for null at the API boundary, and prevent these values from flowing deeper into the F# implementation code.</span></span> <span data-ttu-id="9da9a-433">Die `isNull` Funktion oder einen Mustervergleich für die `null` Muster kann verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9da9a-433">The `isNull` function or pattern matching on the `null` pattern can be used.</span></span>

```fsharp
let checkNonNull argName (arg: obj) =
    match arg with
    | null -> nullArg argName
    | _ -> ()

let checkNonNull` argName (arg: obj) =
    if isNull arg then nullArg argName
    else ()
```

#### <a name="avoid-using-tuples-as-return-values"></a><span data-ttu-id="9da9a-434">Vermeiden Sie die Verwendung von Tupeln als Rückgabewerte</span><span class="sxs-lookup"><span data-stu-id="9da9a-434">Avoid using tuples as return values</span></span>

<span data-ttu-id="9da9a-435">Bevorzugen Sie stattdessen einen benannten Typ die aggregierten Daten enthalten oder mit dem out-Parameter mehrere Werte zurückgeben zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="9da9a-435">Instead, prefer returning a named type holding the aggregate data, or using out parameters to return multiple values.</span></span> <span data-ttu-id="9da9a-436">Trotz Tupel und Tupel Struktur in .NET geben (einschließlich der C#-sprachunterstützung für die Struktur Tupel), häufig nicht die ideale und die erforderliche-API für .NET-Entwickler sie.</span><span class="sxs-lookup"><span data-stu-id="9da9a-436">Although tuples and struct tuples exist in .NET (including C# language support for struct tuples), they will most often not provide the ideal and expected API for .NET developers.</span></span>

#### <a name="avoid-the-use-of-currying-of-parameters"></a><span data-ttu-id="9da9a-437">Vermeiden Sie die Verwendung von currying von Parametern</span><span class="sxs-lookup"><span data-stu-id="9da9a-437">Avoid the use of currying of parameters</span></span>

<span data-ttu-id="9da9a-438">Verwenden Sie stattdessen .NET Aufrufkonventionen ``Method(arg1,arg2,…,argN)``.</span><span class="sxs-lookup"><span data-stu-id="9da9a-438">Instead, use .NET calling conventions ``Method(arg1,arg2,…,argN)``.</span></span>

```fsharp
member this.TupledArguments(str, num) = String.replicate num str
```

<span data-ttu-id="9da9a-439">Tipp: Wenn Sie Bibliotheken zur Verwendung in jeder .NET-Sprache entwerfen, besteht kein Ersatz für tatsächlich auf diese Weise einige experimentellen (c# und Visual Basic Programmieren um sicherzustellen, dass Ihre Bibliotheken "Verhalten nach rechts" aus, aus dieser Sprachen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-439">Tip: If you’re designing libraries for use from any .NET language, then there’s no substitute for actually doing some experimental C# and Visual Basic programming to ensure that your libraries "feel right" from these languages.</span></span> <span data-ttu-id="9da9a-440">Sie können auch Tools, z. B. Reflector .NET und Visual Studio-Objektkatalog verwenden, um sicherzustellen, dass Bibliotheken und deren Dokumentation, wie Entwickler erwartet angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9da9a-440">You can also use tools such as .NET Reflector and the Visual Studio Object Browser to ensure that libraries and their documentation appear as expected to developers.</span></span>

## <a name="appendix"></a><span data-ttu-id="9da9a-441">Anhang</span><span class="sxs-lookup"><span data-stu-id="9da9a-441">Appendix</span></span>

### <a name="end-to-end-example-of-designing-f-code-for-use-by-other-net-languages"></a><span data-ttu-id="9da9a-442">Entwerfen von f#-Code für die Verwendung von anderen .NET-Programmiersprachen End-to-End-Beispiel</span><span class="sxs-lookup"><span data-stu-id="9da9a-442">End-to-end example of designing F# code for use by other .NET languages</span></span>

<span data-ttu-id="9da9a-443">Betrachten Sie die folgende Klasse:</span><span class="sxs-lookup"><span data-stu-id="9da9a-443">Consider the following class:</span></span>

```fsharp
open System

type Point1(angle,radius) =
    new() = Point1(angle=0.0, radius=0.0)
    member x.Angle = angle
    member x.Radius = radius
    member x.Stretch(l) = Point1(angle=x.Angle, radius=x.Radius * l)
    member x.Warp(f) = Point1(angle=f(x.Angle), radius=x.Radius)
    static member Circle(n) =
        [ for i in 1..n -> Point1(angle=2.0*Math.PI/float(n), radius=1.0) ]
```

<span data-ttu-id="9da9a-444">Der abgeleitete f#-Typ dieser Klasse lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="9da9a-444">The inferred F# type of this class is as follows:</span></span>

```fsharp
type Point1 =
    new : unit -> Point1
    new : angle:double * radius:double -> Point1
    static member Circle : n:int -> Point1 list
    member Stretch : l:double -> Point1
    member Warp : f:(double -> double) -> Point1
    member Angle : double
    member Radius : double
```

<span data-ttu-id="9da9a-445">Wir sehen Sie sich wie ein Programmierer, die unter Verwendung einer anderen .NET-Programmiersprache dieser f#-Typ angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="9da9a-445">Let’s take a look at how this F# type appears to a programmer using another .NET language.</span></span> <span data-ttu-id="9da9a-446">Beispielsweise ist die ungefähre c# "Signatur" wie folgt:</span><span class="sxs-lookup"><span data-stu-id="9da9a-446">For example, the approximate C# “signature” is as follows:</span></span>

```csharp
// C# signature for the unadjusted Point1 class
public class Point1
{
    public Point1();

    public Point1(double angle, double radius);

    public static Microsoft.FSharp.Collections.List<Point1> Circle(int count);

    public Point1 Stretch(double factor);

    public Point1 Warp(Microsoft.FSharp.Core.FastFunc<double,double> transform);

    public double Angle { get; }

    public double Radius { get; }
}
```

<span data-ttu-id="9da9a-447">Es gibt einige wichtige Punkte zu beachten, über wie F#-Konstrukte hier darstellt.</span><span class="sxs-lookup"><span data-stu-id="9da9a-447">There are some important points to notice about how F# represents constructs here.</span></span> <span data-ttu-id="9da9a-448">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9da9a-448">For example:</span></span>

* <span data-ttu-id="9da9a-449">Metadaten, z. B. Argumentnamen wurde beibehalten.</span><span class="sxs-lookup"><span data-stu-id="9da9a-449">Metadata such as argument names has been preserved.</span></span>

* <span data-ttu-id="9da9a-450">F#-Methoden, die zwei Argumente werden C#-Methoden, die zwei Argumente.</span><span class="sxs-lookup"><span data-stu-id="9da9a-450">F# methods that take two arguments become C# methods that take two arguments.</span></span>

* <span data-ttu-id="9da9a-451">Funktionen und Listen werden Verweise auf die entsprechenden Typen in der f#-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="9da9a-451">Functions and lists become references to corresponding types in the F# library.</span></span>

<span data-ttu-id="9da9a-452">Der folgende Code zeigt, wie zum Anpassen dieses Codes, um Folgendes zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-452">The following code shows how to adjust this code to take these things into account.</span></span>

```fsharp
namespace SuperDuperFSharpLibrary.Types

type RadialPoint(angle:double, radius:double) =

    /// Return a point at the origin
    new() = RadialPoint(angle=0.0, radius=0.0)

    /// The angle to the point, from the x-axis
    member x.Angle = angle

    /// The distance to the point, from the origin
    member x.Radius = radius

    /// Return a new point, with radius multiplied by the given factor
    member x.Stretch(factor) =
        RadialPoint(angle=angle, radius=radius * factor)

    /// Return a new point, with angle transformed by the function
    member x.Warp(transform:Func<_,_>) =
        RadialPoint(angle=transform.Invoke angle, radius=radius)

    /// Return a sequence of points describing an approximate circle using
    /// the given count of points
    static member Circle(count) =
        seq { for i in 1..count ->
                RadialPoint(angle=2.0*Math.PI/float(count), radius=1.0) }
```

<span data-ttu-id="9da9a-453">Der abgeleitete f#-Typ des Codes lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="9da9a-453">The inferred F# type of the code is as follows:</span></span>

```fsharp
type RadialPoint =
    new : unit -> RadialPoint
    new : angle:double * radius:double -> RadialPoint
    static member Circle : count:int -> seq<RadialPoint>
    member Stretch : factor:double -> RadialPoint
    member Warp : transform:System.Func<double,double> -> RadialPoint
    member Angle : double
    member Radius : double
```

<span data-ttu-id="9da9a-454">Die C#-Signatur ist jetzt wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="9da9a-454">The C# signature is now as follows:</span></span>

```csharp
public class RadialPoint
{
    public RadialPoint();

    public RadialPoint(double angle, double radius);

    public static System.Collections.Generic.IEnumerable<RadialPoint> Circle(int count);

    public RadialPoint Stretch(double factor);

    public RadialPoint Warp(System.Func<double,double> transform);

    public double Angle { get; }

    public double Radius { get; }
}
```

<span data-ttu-id="9da9a-455">Fehlerbehebungen vorgenommen, um diesen Typ für die Verwendung vorbereiten, als Teil einer herkömmlichen .NET Bibliothek sind wie folgt:</span><span class="sxs-lookup"><span data-stu-id="9da9a-455">The fixes made to prepare this type for use as part of a vanilla .NET library are as follows:</span></span>

* <span data-ttu-id="9da9a-456">Mehrere Namen angepasst: `Point1`, `n`, `l`, und `f` ist seit `RadialPoint`, `count`, `factor`, und `transform`zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="9da9a-456">Adjusted several names: `Point1`, `n`, `l`, and `f` became `RadialPoint`, `count`, `factor`, and `transform`, respectively.</span></span>

* <span data-ttu-id="9da9a-457">Verwendet einen Rückgabetyp von `seq<RadialPoint>` anstelle von `RadialPoint list` durch Ändern einer Liste der Erstellung mit `[ ... ]` einer Sequenz Konstruktion mit `IEnumerable<RadialPoint>`.</span><span class="sxs-lookup"><span data-stu-id="9da9a-457">Used a return type of `seq<RadialPoint>` instead of `RadialPoint list` by changing a list construction using `[ ... ]` to a sequence construction using `IEnumerable<RadialPoint>`.</span></span>

* <span data-ttu-id="9da9a-458">Verwendet den Delegattyp .NET `System.Func` anstelle eines f#-Funktionstyps.</span><span class="sxs-lookup"><span data-stu-id="9da9a-458">Used the .NET delegate type `System.Func` instead of an F# function type.</span></span>

<span data-ttu-id="9da9a-459">Dies macht es viel nützlicher in C#-Code nutzen.</span><span class="sxs-lookup"><span data-stu-id="9da9a-459">This makes it far nicer to consume in C# code.</span></span>
