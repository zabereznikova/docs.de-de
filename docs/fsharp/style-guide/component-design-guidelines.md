---
title: F#Richtlinien zum Entwerfen der Komponente
description: Erfahren Sie, die Richtlinien für das Schreiben von F# Komponenten, die für die Nutzung durch andere Aufrufer vorgesehen.
ms.date: 05/14/2018
ms.openlocfilehash: c61e4cd9098388b356c71c325d66c760fa866cf0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61902160"
---
# <a name="f-component-design-guidelines"></a><span data-ttu-id="ddddd-103">F#Richtlinien zum Entwerfen der Komponente</span><span class="sxs-lookup"><span data-stu-id="ddddd-103">F# component design guidelines</span></span>

<span data-ttu-id="ddddd-104">In diesem Dokument ist ein Satz von Komponente-Entwurfsrichtlinien für F#-Programmierung, basierend auf den F#-Komponente Entwurfsrichtlinien, v14, Microsoft Research und [eine andere Version](https://fsharp.org/specs/component-design-guidelines/) ursprünglich kuratierten und von der F# Software Foundation verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="ddddd-104">This document is a set of component design guidelines for F# programming, based on the F# Component Design Guidelines, v14, Microsoft Research, and [another version](https://fsharp.org/specs/component-design-guidelines/) originally curated and maintained by the F# Software Foundation.</span></span>

<span data-ttu-id="ddddd-105">In diesem Dokument wird vorausgesetzt, Sie sind vertraut mit F# programmieren.</span><span class="sxs-lookup"><span data-stu-id="ddddd-105">This document assumes you are familiar with F# programming.</span></span> <span data-ttu-id="ddddd-106">Vielen Dank an die F# Community für ihre Beiträge und hilfreiche Feedback an den verschiedenen Versionen dieses Handbuchs.</span><span class="sxs-lookup"><span data-stu-id="ddddd-106">Many thanks to the F# community for their contributions and helpful feedback on various versions of this guide.</span></span>

## <a name="overview"></a><span data-ttu-id="ddddd-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="ddddd-107">Overview</span></span>

<span data-ttu-id="ddddd-108">In diesem Dokument untersucht einige der Probleme im Zusammenhang mit F# Komponente entwerfen und Programmieren.</span><span class="sxs-lookup"><span data-stu-id="ddddd-108">This document looks at some of the issues related to F# component design and coding.</span></span> <span data-ttu-id="ddddd-109">Eine Komponente kann Folgendes bedeuten:</span><span class="sxs-lookup"><span data-stu-id="ddddd-109">A component can mean any of the following:</span></span>

* <span data-ttu-id="ddddd-110">Eine Ebene in Ihrer F# -Projekts, externe Consumer innerhalb dieses Projekts verfügt.</span><span class="sxs-lookup"><span data-stu-id="ddddd-110">A layer in your F# project that has external consumers within that project.</span></span>
* <span data-ttu-id="ddddd-111">Eine Bibliothek, für die Nutzung von F# Code über assemblygrenzen hinweg.</span><span class="sxs-lookup"><span data-stu-id="ddddd-111">A library intended for consumption by F# code across assembly boundaries.</span></span>
* <span data-ttu-id="ddddd-112">Eine Bibliothek, die für die Nutzung von jeder .NET-Sprache nichtüber assemblygrenzen hinweg vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="ddddd-112">A library intended for consumption by any .NET language across assembly boundaries.</span></span>
* <span data-ttu-id="ddddd-113">Eine Bibliothek, für die Verteilung über ein paketrepository, z. B. [NuGet](https://nuget.org).</span><span class="sxs-lookup"><span data-stu-id="ddddd-113">A library intended for distribution via a package repository, such as [NuGet](https://nuget.org).</span></span>

<span data-ttu-id="ddddd-114">In diesem Artikel beschriebene Verfahren führen Sie die [fünf Prinzipien guten F# Code](index.md#five-principles-of-good-f-code), und daher sowohl funktionale als nutzen und Objekt nach Bedarf programmieren.</span><span class="sxs-lookup"><span data-stu-id="ddddd-114">Techniques described in this article follow the [Five principles of good F# code](index.md#five-principles-of-good-f-code), and thus utilize both functional and object programming as appropriate.</span></span>

<span data-ttu-id="ddddd-115">Unabhängig von der Methodik steht der Designer-Komponente und die Bibliothek eine Reihe von praktischen und prosaischen Problemen an, beim Versuch, eine API erstellen, die problemlos von Entwicklern verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="ddddd-115">Regardless of the methodology, the component and library designer faces a number of practical and prosaic issues when trying to craft an API that is most easily usable by developers.</span></span> <span data-ttu-id="ddddd-116">Gewissenhaft Anwendung von der [.NET Klassenbibliotheken – Entwurfsrichtlinien](../../standard/design-guidelines/index.md) werden Sie beim Erstellen eines konsistenten Satz von APIs, nutzen angenehme sind, nach steuern.</span><span class="sxs-lookup"><span data-stu-id="ddddd-116">Conscientious application of the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md) will steer you towards creating a consistent set of APIs that are pleasant to consume.</span></span>

## <a name="general-guidelines"></a><span data-ttu-id="ddddd-117">Allgemeine Richtlinien</span><span class="sxs-lookup"><span data-stu-id="ddddd-117">General guidelines</span></span>

<span data-ttu-id="ddddd-118">Es gibt einige universelle Richtlinien, die für F#-Bibliotheken, unabhängig davon, die Zielgruppe für die Bibliothek gelten.</span><span class="sxs-lookup"><span data-stu-id="ddddd-118">There are a few universal guidelines that apply to F# libraries, regardless of the intended audience for the library.</span></span>

### <a name="learn-the-net-library-design-guidelines"></a><span data-ttu-id="ddddd-119">Erfahren Sie, die .NET Klassenbibliotheken – Entwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="ddddd-119">Learn the .NET Library Design Guidelines</span></span>

<span data-ttu-id="ddddd-120">Unabhängig von der Art der F# codieren Sie durchführen, es ist sinnvoll, eine ausreichende praktische Kenntnisse in der [.NET Klassenbibliotheken – Entwurfsrichtlinien](../../standard/design-guidelines/index.md).</span><span class="sxs-lookup"><span data-stu-id="ddddd-120">Regardless of the kind of F# coding you are doing, it is valuable to have a working knowledge of the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md).</span></span> <span data-ttu-id="ddddd-121">Die meisten anderen F# und .NET Programmierer werden mit diesen Richtlinien vertraut sein und erwarten, dass .NET Code, um sie zu entsprechen.</span><span class="sxs-lookup"><span data-stu-id="ddddd-121">Most other F# and .NET programmers will be familiar with these guidelines, and expect .NET code to conform to them.</span></span>

<span data-ttu-id="ddddd-122">Die .NET Klassenbibliotheken – Entwurfsrichtlinien enthalten eine allgemeine Anleitung zur Benennung, Entwerfen von Klassen und Schnittstellen, Member-Entwurf (Eigenschaften, Methoden, Ereignisse usw.) und vieles mehr, und sind eine nützliche erste Anlaufpunkt für eine Vielzahl von Entwurfsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="ddddd-122">The .NET Library Design Guidelines provide general guidance regarding naming, designing classes and interfaces, member design (properties, methods, events, etc.) and more, and are a useful first point of reference for a variety of design guidance.</span></span>

### <a name="add-xml-documentation-comments-to-your-code"></a><span data-ttu-id="ddddd-123">Hinzufügen von XML-Dokumentationskommentare zu code</span><span class="sxs-lookup"><span data-stu-id="ddddd-123">Add XML documentation comments to your code</span></span>

<span data-ttu-id="ddddd-124">XML-Dokumentation in öffentlichen APIs stellen Sie sicher, dass Benutzer erhalten können, hervorragende Intellisense und den QuickInfos beim Verwenden dieser Typen und Member, und aktivieren, Erstellen von Dokumentation für die Bibliothek von Dateien.</span><span class="sxs-lookup"><span data-stu-id="ddddd-124">XML documentation on public APIs ensure that users can get great Intellisense and Quickinfo when using these types and members, and enable building documentation files for the library.</span></span> <span data-ttu-id="ddddd-125">Finden Sie unter den [XML-Dokumentation](../language-reference/xml-documentation.md) über verschiedene XML‑Tags, die für zusätzliches Markup in Xmldoc Kommentare verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="ddddd-125">See the [XML Documentation](../language-reference/xml-documentation.md) about various xml tags that can be used for additional markup within xmldoc comments.</span></span>

```fsharp
/// A class for representing (x,y) coordinates
type Point =

    /// Computes the distance between this point and another
    member DistanceTo: otherPoint:Point -> float
```

<span data-ttu-id="ddddd-126">Sie können entweder die kurze Form von XML-Kommentare verwenden (`/// comment`), oder die standard-XML-Kommentaren (`///<summary>comment</summary>`).</span><span class="sxs-lookup"><span data-stu-id="ddddd-126">You can use either the short form XML comments (`/// comment`), or standard XML comments (`///<summary>comment</summary>`).</span></span>

### <a name="consider-using-explicit-signature-files-fsi-for-stable-library-and-component-apis"></a><span data-ttu-id="ddddd-127">Erwägen Sie die Verwendung von expliziten Signaturdateien (".FSI") für stabile und Komponenten-APIs</span><span class="sxs-lookup"><span data-stu-id="ddddd-127">Consider using explicit signature files (.fsi) for stable library and component APIs</span></span>

<span data-ttu-id="ddddd-128">Verwendung von expliziten Signaturen-Dateien in ein F# -Bibliothek bietet eine kurze Zusammenfassung der öffentliche API nutzen, die jeweils sichergestellt wird, dass Sie wissen, dass die vollständige öffentliche Oberfläche Ihrer Bibliothek bietet eine saubere Trennung zwischen öffentlichen Dokumentation und interne Details zur Implementierung.</span><span class="sxs-lookup"><span data-stu-id="ddddd-128">Using explicit signatures files in an F# library provides a succinct summary of public API, which both helps to ensure that you know the full public surface of your library, as well as provides a clean separation between public documentation and internal implementation details.</span></span> <span data-ttu-id="ddddd-129">Beachten Sie, dass die Signaturdateien Reibung hinzufügen, ändern die öffentliche API nutzen, durch das Anfordern von Änderungen, die in der Implementierung und den Signatur-Dateien vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="ddddd-129">Note that signature files add friction to changing the public API, by requiring changes to be made in both the implementation and signature files.</span></span> <span data-ttu-id="ddddd-130">Daher sollten Signaturdateien in der Regel nur eingeführt werden, wenn eine API größtenteils durchgeführten Konsolidierung werden und muss nicht mehr ändern.</span><span class="sxs-lookup"><span data-stu-id="ddddd-130">As a result, signature files should typically only be introduced when an API has become solidified and is no longer expected to change significantly.</span></span>

### <a name="always-follow-best-practices-for-using-strings-in-net"></a><span data-ttu-id="ddddd-131">Befolgen Sie stets die bewährte Methoden für die Verwendung von Zeichenfolgen in .NET</span><span class="sxs-lookup"><span data-stu-id="ddddd-131">Always follow best practices for using strings in .NET</span></span>

<span data-ttu-id="ddddd-132">Führen Sie [bewährte Methoden für die Verwendung von Zeichenfolgen in .NET](../../standard/base-types/best-practices-strings.md) Anleitungen.</span><span class="sxs-lookup"><span data-stu-id="ddddd-132">Follow [Best Practices for Using Strings in .NET](../../standard/base-types/best-practices-strings.md) guidance.</span></span> <span data-ttu-id="ddddd-133">Insbesondere immer explizit *kulturellen Absicht* in die Konvertierung und Vergleich von Zeichenfolgen (falls zutreffend).</span><span class="sxs-lookup"><span data-stu-id="ddddd-133">In particular, always explicitly state *cultural intent* in the conversion and comparison of strings (where applicable).</span></span>

## <a name="guidelines-for-f-facing-libraries"></a><span data-ttu-id="ddddd-134">Richtlinien für F#-Bibliotheken für</span><span class="sxs-lookup"><span data-stu-id="ddddd-134">Guidelines for F#-facing libraries</span></span>

<span data-ttu-id="ddddd-135">In diesem Abschnitt werden die Empfehlungen für die Entwicklung von öffentlichen F#-Bibliotheken für d. h. Bibliotheken Verfügbarmachen von öffentlichen APIs, die von F#-Entwickler verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ddddd-135">This section presents recommendations for developing public F#-facing libraries; that is, libraries exposing public APIs that are intended to be consumed by F# developers.</span></span> <span data-ttu-id="ddddd-136">Es gibt eine Vielzahl von Empfehlungen für den Bibliothek-Entwurf gelten speziell für F#.</span><span class="sxs-lookup"><span data-stu-id="ddddd-136">There are a variety of library-design recommendations applicable specifically to F#.</span></span> <span data-ttu-id="ddddd-137">Keine spezifischen Empfehlungen, die folgen, sind die .NET Klassenbibliotheken – Entwurfsrichtlinien die fallback-Anleitung.</span><span class="sxs-lookup"><span data-stu-id="ddddd-137">In the absence of the specific recommendations that follow, the .NET Library Design Guidelines are the fallback guidance.</span></span>

### <a name="naming-conventions"></a><span data-ttu-id="ddddd-138">Namenskonventionen </span><span class="sxs-lookup"><span data-stu-id="ddddd-138">Naming conventions</span></span>

#### <a name="use-net-naming-and-capitalization-conventions"></a><span data-ttu-id="ddddd-139">Verwenden Sie .NET benennen und Groß-/Kleinschreibung die Konventionen</span><span class="sxs-lookup"><span data-stu-id="ddddd-139">Use .NET naming and capitalization conventions</span></span>

<span data-ttu-id="ddddd-140">In der folgende Tabelle werden die .NET benennen und Groß-/Kleinschreibung-Konventionen befolgt.</span><span class="sxs-lookup"><span data-stu-id="ddddd-140">The following table follows .NET naming and capitalization conventions.</span></span> <span data-ttu-id="ddddd-141">Es gibt kleine Erweiterungen auch F#-Konstrukte enthalten.</span><span class="sxs-lookup"><span data-stu-id="ddddd-141">There are small additions to also include F# constructs.</span></span>

| <span data-ttu-id="ddddd-142">Konstrukt</span><span class="sxs-lookup"><span data-stu-id="ddddd-142">Construct</span></span> | <span data-ttu-id="ddddd-143">Case</span><span class="sxs-lookup"><span data-stu-id="ddddd-143">Case</span></span> | <span data-ttu-id="ddddd-144">Segment</span><span class="sxs-lookup"><span data-stu-id="ddddd-144">Part</span></span> | <span data-ttu-id="ddddd-145">Beispiele</span><span class="sxs-lookup"><span data-stu-id="ddddd-145">Examples</span></span> | <span data-ttu-id="ddddd-146">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ddddd-146">Notes</span></span> |
|-----------|------|------|----------|-------|
| <span data-ttu-id="ddddd-147">Konkrete Typen</span><span class="sxs-lookup"><span data-stu-id="ddddd-147">Concrete types</span></span> | <span data-ttu-id="ddddd-148">PascalCase</span><span class="sxs-lookup"><span data-stu-id="ddddd-148">PascalCase</span></span> | <span data-ttu-id="ddddd-149">Nomen / adjektivische</span><span class="sxs-lookup"><span data-stu-id="ddddd-149">Noun/ adjective</span></span> | <span data-ttu-id="ddddd-150">Liste, Double, komplexe</span><span class="sxs-lookup"><span data-stu-id="ddddd-150">List, Double, Complex</span></span> | <span data-ttu-id="ddddd-151">Konkrete Typen sind Strukturen, Klassen, Enumerationen, Delegaten, Datensätze und Unions.</span><span class="sxs-lookup"><span data-stu-id="ddddd-151">Concrete types are structs, classes, enumerations, delegates, records, and unions.</span></span> <span data-ttu-id="ddddd-152">Obwohl Typnamen traditionell in mit OCaml Kleinbuchstaben sind, hat F# das Benennungsschema für .NET für Typen übernommen.</span><span class="sxs-lookup"><span data-stu-id="ddddd-152">Though type names are traditionally lowercase in OCaml, F# has adopted the .NET naming scheme for types.</span></span>
| <span data-ttu-id="ddddd-153">DLLs</span><span class="sxs-lookup"><span data-stu-id="ddddd-153">DLLs</span></span>           | <span data-ttu-id="ddddd-154">PascalCase</span><span class="sxs-lookup"><span data-stu-id="ddddd-154">PascalCase</span></span> |                 | <span data-ttu-id="ddddd-155">Fabrikam.Core.dll</span><span class="sxs-lookup"><span data-stu-id="ddddd-155">Fabrikam.Core.dll</span></span> |  |
| <span data-ttu-id="ddddd-156">Union-tags</span><span class="sxs-lookup"><span data-stu-id="ddddd-156">Union tags</span></span>     | <span data-ttu-id="ddddd-157">PascalCase</span><span class="sxs-lookup"><span data-stu-id="ddddd-157">PascalCase</span></span> | <span data-ttu-id="ddddd-158">Nomen</span><span class="sxs-lookup"><span data-stu-id="ddddd-158">Noun</span></span> | <span data-ttu-id="ddddd-159">Einige hinzuzufügen, Erfolg</span><span class="sxs-lookup"><span data-stu-id="ddddd-159">Some, Add, Success</span></span> | <span data-ttu-id="ddddd-160">Verwenden Sie ein Präfix nicht in öffentlichen APIs aus.</span><span class="sxs-lookup"><span data-stu-id="ddddd-160">Do not use a prefix in public APIs.</span></span> <span data-ttu-id="ddddd-161">Verwenden Sie optional ein Präfix, bei der internen, z. B. `type Teams = TAlpha | TBeta | TDelta.`</span><span class="sxs-lookup"><span data-stu-id="ddddd-161">Optionally use a prefix when internal, such as `type Teams = TAlpha | TBeta | TDelta.`</span></span> |
| <span data-ttu-id="ddddd-162">event</span><span class="sxs-lookup"><span data-stu-id="ddddd-162">Event</span></span>          | <span data-ttu-id="ddddd-163">PascalCase</span><span class="sxs-lookup"><span data-stu-id="ddddd-163">PascalCase</span></span> | <span data-ttu-id="ddddd-164">Verb</span><span class="sxs-lookup"><span data-stu-id="ddddd-164">Verb</span></span> | <span data-ttu-id="ddddd-165">ValueChanged / ValueChanging</span><span class="sxs-lookup"><span data-stu-id="ddddd-165">ValueChanged / ValueChanging</span></span> |  |
| <span data-ttu-id="ddddd-166">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="ddddd-166">Exceptions</span></span>     | <span data-ttu-id="ddddd-167">PascalCase</span><span class="sxs-lookup"><span data-stu-id="ddddd-167">PascalCase</span></span> |      | <span data-ttu-id="ddddd-168">WebException</span><span class="sxs-lookup"><span data-stu-id="ddddd-168">WebException</span></span> | <span data-ttu-id="ddddd-169">Name sollte mit "Exception" enden.</span><span class="sxs-lookup"><span data-stu-id="ddddd-169">Name should end with “Exception”.</span></span> |
| <span data-ttu-id="ddddd-170">Feld</span><span class="sxs-lookup"><span data-stu-id="ddddd-170">Field</span></span>          | <span data-ttu-id="ddddd-171">PascalCase</span><span class="sxs-lookup"><span data-stu-id="ddddd-171">PascalCase</span></span> | <span data-ttu-id="ddddd-172">Nomen</span><span class="sxs-lookup"><span data-stu-id="ddddd-172">Noun</span></span> | <span data-ttu-id="ddddd-173">CurrentName</span><span class="sxs-lookup"><span data-stu-id="ddddd-173">CurrentName</span></span>  | |
| <span data-ttu-id="ddddd-174">Schnittstellentypen</span><span class="sxs-lookup"><span data-stu-id="ddddd-174">Interface types</span></span> |  <span data-ttu-id="ddddd-175">PascalCase</span><span class="sxs-lookup"><span data-stu-id="ddddd-175">PascalCase</span></span> | <span data-ttu-id="ddddd-176">Nomen / adjektivische</span><span class="sxs-lookup"><span data-stu-id="ddddd-176">Noun/ adjective</span></span> | <span data-ttu-id="ddddd-177">IDisposable</span><span class="sxs-lookup"><span data-stu-id="ddddd-177">IDisposable</span></span> | <span data-ttu-id="ddddd-178">Name sollte mit "I" beginnen.</span><span class="sxs-lookup"><span data-stu-id="ddddd-178">Name should start with “I”.</span></span> |
| <span data-ttu-id="ddddd-179">Methode</span><span class="sxs-lookup"><span data-stu-id="ddddd-179">Method</span></span> |  <span data-ttu-id="ddddd-180">PascalCase</span><span class="sxs-lookup"><span data-stu-id="ddddd-180">PascalCase</span></span> |  <span data-ttu-id="ddddd-181">Verb</span><span class="sxs-lookup"><span data-stu-id="ddddd-181">Verb</span></span> | <span data-ttu-id="ddddd-182">ToString</span><span class="sxs-lookup"><span data-stu-id="ddddd-182">ToString</span></span> | |
| <span data-ttu-id="ddddd-183">Namespace</span><span class="sxs-lookup"><span data-stu-id="ddddd-183">Namespace</span></span> | <span data-ttu-id="ddddd-184">PascalCase</span><span class="sxs-lookup"><span data-stu-id="ddddd-184">PascalCase</span></span> | | <span data-ttu-id="ddddd-185">Microsoft.FSharp.Core</span><span class="sxs-lookup"><span data-stu-id="ddddd-185">Microsoft.FSharp.Core</span></span> | <span data-ttu-id="ddddd-186">In der Regel `<Organization>.<Technology>[.<Subnamespace>]`, jedoch nicht die Organisation löschen, wenn die Technologie unabhängig von der Organisation ist.</span><span class="sxs-lookup"><span data-stu-id="ddddd-186">Generally use `<Organization>.<Technology>[.<Subnamespace>]`, though drop the organization if the technology is independent of organization.</span></span> |
| <span data-ttu-id="ddddd-187">Parameter</span><span class="sxs-lookup"><span data-stu-id="ddddd-187">Parameters</span></span> | <span data-ttu-id="ddddd-188">camelCase</span><span class="sxs-lookup"><span data-stu-id="ddddd-188">camelCase</span></span> | <span data-ttu-id="ddddd-189">Nomen</span><span class="sxs-lookup"><span data-stu-id="ddddd-189">Noun</span></span> |  <span data-ttu-id="ddddd-190">typeName, transform, range</span><span class="sxs-lookup"><span data-stu-id="ddddd-190">typeName, transform, range</span></span> | |
| <span data-ttu-id="ddddd-191">Lassen Sie die Werte (intern)</span><span class="sxs-lookup"><span data-stu-id="ddddd-191">let values (internal)</span></span> | <span data-ttu-id="ddddd-192">CamelCase oder PascalCase</span><span class="sxs-lookup"><span data-stu-id="ddddd-192">camelCase or PascalCase</span></span> | <span data-ttu-id="ddddd-193">Nomen / Verb</span><span class="sxs-lookup"><span data-stu-id="ddddd-193">Noun/ verb</span></span> |  <span data-ttu-id="ddddd-194">getValue, myTable</span><span class="sxs-lookup"><span data-stu-id="ddddd-194">getValue, myTable</span></span> |
| <span data-ttu-id="ddddd-195">Lassen Sie die Werte (extern)</span><span class="sxs-lookup"><span data-stu-id="ddddd-195">let values (external)</span></span> | <span data-ttu-id="ddddd-196">CamelCase oder PascalCase</span><span class="sxs-lookup"><span data-stu-id="ddddd-196">camelCase or PascalCase</span></span> | <span data-ttu-id="ddddd-197">Substantiv Verb /</span><span class="sxs-lookup"><span data-stu-id="ddddd-197">Noun/verb</span></span>  | <span data-ttu-id="ddddd-198">List.map, Dates.Today</span><span class="sxs-lookup"><span data-stu-id="ddddd-198">List.map, Dates.Today</span></span> | <span data-ttu-id="ddddd-199">Let gebundenen Werte sind oft öffentlich, wenn herkömmliche funktionale Entwurfsmuster zu befolgen.</span><span class="sxs-lookup"><span data-stu-id="ddddd-199">let-bound values are often public when following traditional functional design patterns.</span></span> <span data-ttu-id="ddddd-200">Im Allgemeinen verwenden Sie jedoch PascalCase, wenn der Bezeichner, die von anderen .NET-Sprachen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="ddddd-200">However, generally use PascalCase when the identifier can be used from other .NET languages.</span></span> |
| <span data-ttu-id="ddddd-201">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="ddddd-201">Property</span></span>  | <span data-ttu-id="ddddd-202">PascalCase</span><span class="sxs-lookup"><span data-stu-id="ddddd-202">PascalCase</span></span>  | <span data-ttu-id="ddddd-203">Nomen / adjektivische</span><span class="sxs-lookup"><span data-stu-id="ddddd-203">Noun/ adjective</span></span>  | <span data-ttu-id="ddddd-204">IsEndOfFile, BackColor</span><span class="sxs-lookup"><span data-stu-id="ddddd-204">IsEndOfFile, BackColor</span></span>  | <span data-ttu-id="ddddd-205">Boolesche Eigenschaften, die in der Regel verwendet wird und können und sollten positive, wie IsEndOfFile, nicht IsNotEndOfFile.</span><span class="sxs-lookup"><span data-stu-id="ddddd-205">Boolean properties generally use Is and Can and should be affirmative, as in IsEndOfFile, not IsNotEndOfFile.</span></span>

#### <a name="avoid-abbreviations"></a><span data-ttu-id="ddddd-206">Vermeiden Sie Abkürzungen</span><span class="sxs-lookup"><span data-stu-id="ddddd-206">Avoid abbreviations</span></span>

<span data-ttu-id="ddddd-207">Die .NET Richtlinien davon abhalten, die Verwendung von Abkürzungen (z. B. "verwenden `OnButtonClick` statt `OnBtnClick`").</span><span class="sxs-lookup"><span data-stu-id="ddddd-207">The .NET guidelines discourage the use of abbreviations (for example, “use `OnButtonClick` rather than `OnBtnClick`”).</span></span> <span data-ttu-id="ddddd-208">Allgemeine Abkürzungen, z. B. `Async` für "Asynchron", werden toleriert.</span><span class="sxs-lookup"><span data-stu-id="ddddd-208">Common abbreviations, such as `Async` for “Asynchronous”, are tolerated.</span></span> <span data-ttu-id="ddddd-209">Diese Richtlinie wird für die funktionale Programmierung manchmal ignoriert. z. B. `List.iter` verwendet eine Abkürzung für "durchlaufen".</span><span class="sxs-lookup"><span data-stu-id="ddddd-209">This guideline is sometimes ignored for functional programming; for example, `List.iter` uses an abbreviation for “iterate”.</span></span> <span data-ttu-id="ddddd-210">Aus diesem Grund mit Abkürzungen tendenziell in höherem Maß in F# toleriert werden-zu-F#-Programmierung, aber immer noch in der Regel in öffentlichen Komponentenentwurf vermieden werden sollte.</span><span class="sxs-lookup"><span data-stu-id="ddddd-210">For this reason, using abbreviations tends to be tolerated to a greater degree in F#-to-F# programming, but should still generally be avoided in public component design.</span></span>

#### <a name="avoid-casing-name-collisions"></a><span data-ttu-id="ddddd-211">Vermeiden Sie die Groß-/Kleinschreibung von Namenskonflikten</span><span class="sxs-lookup"><span data-stu-id="ddddd-211">Avoid casing name collisions</span></span>

<span data-ttu-id="ddddd-212">Die Richtlinien für die .NET sagen, dass die Groß-/Kleinschreibung allein verwendet werden kann, Namenskonflikte, zu unterscheiden, da einige Clientsprachen (z. B. Visual Basic), Groß-/Kleinschreibung sind.</span><span class="sxs-lookup"><span data-stu-id="ddddd-212">The .NET guidelines say that casing alone cannot be used to disambiguate name collisions, since some client languages (for example, Visual Basic) are case-insensitive.</span></span>

#### <a name="use-acronyms-where-appropriate"></a><span data-ttu-id="ddddd-213">Verwenden Sie bei Bedarf Akronyme</span><span class="sxs-lookup"><span data-stu-id="ddddd-213">Use acronyms where appropriate</span></span>

<span data-ttu-id="ddddd-214">Akronyme, wie z. B. XML sind keine Abkürzungen und werden häufig in .NET-Bibliotheken uncapitalized Format (Xml) verwendet.</span><span class="sxs-lookup"><span data-stu-id="ddddd-214">Acronyms such as XML are not abbreviations and are widely used in .NET libraries in uncapitalized form (Xml).</span></span> <span data-ttu-id="ddddd-215">Nur sollte bekannte und weithin anerkannter Akronyme verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ddddd-215">Only well-known, widely recognized acronyms should be used.</span></span>

#### <a name="use-pascalcase-for-generic-parameter-names"></a><span data-ttu-id="ddddd-216">Verwendung von PascalCase für generischen Parameternamen</span><span class="sxs-lookup"><span data-stu-id="ddddd-216">Use PascalCase for generic parameter names</span></span>

<span data-ttu-id="ddddd-217">Verwenden Sie PascalCase für den generischen Parameternamen in öffentlichen APIs, einschließlich für F#-Bibliotheken nach.</span><span class="sxs-lookup"><span data-stu-id="ddddd-217">Do use PascalCase for generic parameter names in public APIs, including for F#-facing libraries.</span></span> <span data-ttu-id="ddddd-218">Insbesondere verwenden Sie Namen wie `T`, `U`, `T1`, `T2` für beliebige generische Parameter, und wenn bestimmte Namen sinnvoll, klicken Sie dann für F#-zugängliche Bibliotheken verwenden Sie Namen wie `Key`, `Value`, `Arg`(aber nicht z. B. `TKey`).</span><span class="sxs-lookup"><span data-stu-id="ddddd-218">In particular, use names like `T`, `U`, `T1`, `T2` for arbitrary generic parameters, and when specific names make sense, then for F#-facing libraries use names like `Key`, `Value`, `Arg` (but not for example, `TKey`).</span></span>

#### <a name="use-either-pascalcase-or-camelcase-for-public-functions-and-values-in-f-modules"></a><span data-ttu-id="ddddd-219">Verwenden Sie entweder "PascalCase" oder "CamelCase für öffentliche Funktionen und die Werte in F# Module</span><span class="sxs-lookup"><span data-stu-id="ddddd-219">Use either PascalCase or camelCase for public functions and values in F# modules</span></span>

<span data-ttu-id="ddddd-220">CamelCase dient für öffentliche Funktionen, die verwendet werden, dienen nicht qualifizierten (z. B. `invalidArg`), und für die "Standardsammlung Functions" (z. B. List.map).</span><span class="sxs-lookup"><span data-stu-id="ddddd-220">camelCase is used for public functions that are designed to be used unqualified (for example, `invalidArg`), and for the “standard collection functions” (for example, List.map).</span></span> <span data-ttu-id="ddddd-221">In beiden Fällen verhalten sich die Namen der Funktionen ähnlich wie Schlüsselwörter in der Sprache.</span><span class="sxs-lookup"><span data-stu-id="ddddd-221">In both these cases, the function names act much like keywords in the language.</span></span>

### <a name="object-type-and-module-design"></a><span data-ttu-id="ddddd-222">-Objekt, Typ und Modul-Entwurf</span><span class="sxs-lookup"><span data-stu-id="ddddd-222">Object, Type, and Module design</span></span>

#### <a name="use-namespaces-or-modules-to-contain-your-types-and-modules"></a><span data-ttu-id="ddddd-223">Verwenden von Namespaces oder Module, Ihre Typen und Module enthalten</span><span class="sxs-lookup"><span data-stu-id="ddddd-223">Use namespaces or modules to contain your types and modules</span></span>

<span data-ttu-id="ddddd-224">Jede F#-Datei in eine Komponente, die mit einer Namespacedeklaration oder eine Moduldeklaration beginnen soll.</span><span class="sxs-lookup"><span data-stu-id="ddddd-224">Each F# file in a component should begin with either a namespace declaration or a module declaration.</span></span>

```fsharp
namespace Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
     ...

module CommonOperations =
    ...
```

<span data-ttu-id="ddddd-225">oder</span><span class="sxs-lookup"><span data-stu-id="ddddd-225">or</span></span>

```fsharp
module Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
    ...

module CommonOperations =
    ...
```

<span data-ttu-id="ddddd-226">Die Unterschiede zwischen der Verwendung von Modulen und Namespaces zum Organisieren von Code auf der obersten Ebene sind wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="ddddd-226">The differences between using modules and namespaces to organize code at the top level are as follows:</span></span>

* <span data-ttu-id="ddddd-227">Namespaces können mehrere Dateien umfassen.</span><span class="sxs-lookup"><span data-stu-id="ddddd-227">Namespaces can span multiple files</span></span>
* <span data-ttu-id="ddddd-228">Namespaces darf keine F#-Funktionen enthalten, es sei denn, sie in einem inneren Modul</span><span class="sxs-lookup"><span data-stu-id="ddddd-228">Namespaces cannot contain F# functions unless they are within an inner module</span></span>
* <span data-ttu-id="ddddd-229">Der Code für jedes angegebene Modul muss innerhalb einer einzelnen Datei enthalten sein</span><span class="sxs-lookup"><span data-stu-id="ddddd-229">The code for any given module must be contained within a single file</span></span>
* <span data-ttu-id="ddddd-230">Module auf oberster Ebene können F#-Funktionen ohne die Notwendigkeit eines inneren Moduls enthalten.</span><span class="sxs-lookup"><span data-stu-id="ddddd-230">Top-level modules can contain F# functions without the need for an inner module</span></span>

<span data-ttu-id="ddddd-231">Die Wahl zwischen einem der obersten Ebene Namespace oder Modul wirkt sich auf die kompilierte Form des Codes und daher wirken sich die Ansicht von anderen .NET-Sprachen Ihrer API schließlich genutzt werden sollen außerhalb von F# Code.</span><span class="sxs-lookup"><span data-stu-id="ddddd-231">The choice between a top-level namespace or module affects the compiled form of the code, and thus will affect the view from other .NET languages should your API eventually be consumed outside of F# code.</span></span>

#### <a name="use-methods-and-properties-for-operations-intrinsic-to-object-types"></a><span data-ttu-id="ddddd-232">Verwenden von Methoden und Eigenschaften für Vorgänge, die systeminterne Objekte des Typs</span><span class="sxs-lookup"><span data-stu-id="ddddd-232">Use methods and properties for operations intrinsic to object types</span></span>

<span data-ttu-id="ddddd-233">Bei der Arbeit mit Objekten empfiehlt es sich um sicherzustellen, dass genutzt werden Funktionen wie Methoden und Eigenschaften für diesen Typ implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="ddddd-233">When working with objects, it is best to ensure that consumable functionality is implemented as methods and properties on that type.</span></span>

```fsharp
type HardwareDevice() =

    member this.ID = ...

    member this.SupportedProtocols = ...

type HashTable<'Key,'Value>(comparer: IEqualityComparer<'Key>) =

    member this.Add(key, value) = ...

    member this.ContainsKey(key) = ...

    member this.ContainsValue(value) = ...
```

<span data-ttu-id="ddddd-234">Der Großteil der Funktionalität für ein bestimmtes Element muss unbedingt nicht in diesen Member implementiert werden, aber die Information, diese Funktionalität genutzt werden muss.</span><span class="sxs-lookup"><span data-stu-id="ddddd-234">The bulk of functionality for a given member need not necessarily be implemented in that member, but the consumable piece of that functionality should be.</span></span>

#### <a name="use-classes-to-encapsulate-mutable-state"></a><span data-ttu-id="ddddd-235">Verwenden von Klassen zum Kapseln von veränderlichen Zustands</span><span class="sxs-lookup"><span data-stu-id="ddddd-235">Use classes to encapsulate mutable state</span></span>

<span data-ttu-id="ddddd-236">In F#, dies nur, dass der Status nicht bereits von einem anderen Sprachkonstrukt, z. B. eine Closure, Sequenzausdruck oder asynchrone Berechnung gekapselt ist, in denen erfolgen muss.</span><span class="sxs-lookup"><span data-stu-id="ddddd-236">In F#, this only needs to be done where that state is not already encapsulated by another language construct, such as a closure, sequence expression, or asynchronous computation.</span></span>

```fsharp
type Counter() =
    // let-bound values are private in classes.
    let mutable count = 0

    member this.Next() =
        count <- count + 1
        count
```

#### <a name="use-interfaces-to-group-related-operations"></a><span data-ttu-id="ddddd-237">Verwenden Sie Schnittstellen gruppiert verwandte Vorgänge</span><span class="sxs-lookup"><span data-stu-id="ddddd-237">Use interfaces to group related operations</span></span>

<span data-ttu-id="ddddd-238">Verwenden Sie Schnittstellentypen, um eine Reihe von Vorgängen darzustellen.</span><span class="sxs-lookup"><span data-stu-id="ddddd-238">Use interface types to represent a set of operations.</span></span> <span data-ttu-id="ddddd-239">Dies wird zu anderen Optionen, wie Tupel von Funktionen oder Datensätze Funktionen bevorzugt.</span><span class="sxs-lookup"><span data-stu-id="ddddd-239">This is preferred to other options, such as tuples of functions or records of functions.</span></span>

```fsharp
type Serializer =
    abstract Serialize<'T>: preserveRefEq: bool -> value: 'T -> string
    abstract Deserialize<'T>: preserveRefEq: bool -> pickle: string -> 'T
```

<span data-ttu-id="ddddd-240">Vorzuziehen:</span><span class="sxs-lookup"><span data-stu-id="ddddd-240">In preference to:</span></span>

```fsharp
type Serializer<'T> = {
    Serialize: bool -> 'T -> string
    Deserialize: bool -> string -> 'T
}
```

<span data-ttu-id="ddddd-241">Schnittstellen sind erstklassige Konzepte in .NET, die Sie verwenden können, um zu erreichen, was Funktionselemente normalerweise Sie erhalten.</span><span class="sxs-lookup"><span data-stu-id="ddddd-241">Interfaces are first-class concepts in .NET, which you can use to achieve what Functors would normally give you.</span></span> <span data-ttu-id="ddddd-242">Darüber hinaus können sie um existenzielle Typen in das Programm zu codieren, der Datensätze von Funktionen können nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ddddd-242">Additionally, they can be used to encode existential types into your program, which records of functions cannot.</span></span>

#### <a name="use-a-module-to-group-functions-which-act-on-collections"></a><span data-ttu-id="ddddd-243">Verwenden eines Moduls, das die dienen Funktionen für Sammlungen</span><span class="sxs-lookup"><span data-stu-id="ddddd-243">Use a module to group functions which act on collections</span></span>

<span data-ttu-id="ddddd-244">Wenn Sie einen Auflistungstyp definieren, geben Sie ggf. ein standardmäßigen Satz von Vorgängen wie `CollectionType.map` und `CollectionType.iter`) für die neue Sammlungstypen.</span><span class="sxs-lookup"><span data-stu-id="ddddd-244">When you define a collection type, consider providing a standard set of operations like `CollectionType.map` and `CollectionType.iter`) for new collection types.</span></span>

```fsharp
module CollectionType =
    let map f c =
        ...
    let iter f c =
        ...
```

<span data-ttu-id="ddddd-245">Wenn Sie ein solches Modul einschließen, führen Sie die standardmäßigen Benennungskonventionen für Funktionen in FSharp.Core gefunden.</span><span class="sxs-lookup"><span data-stu-id="ddddd-245">If you include such a module, follow the standard naming conventions for functions found in FSharp.Core.</span></span>

#### <a name="use-a-module-to-group-functions-for-common-canonical-functions-especially-in-math-and-dsl-libraries"></a><span data-ttu-id="ddddd-246">Verwenden eines Moduls, das Funktionen für allgemeine, kanonische Funktionen, insbesondere in Mathematik und DSL-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="ddddd-246">Use a module to group functions for common, canonical functions, especially in math and DSL libraries</span></span>

<span data-ttu-id="ddddd-247">Z. B. `Microsoft.FSharp.Core.Operators` ist eine automatisch geöffnete Sammlung von Funktionen der obersten Ebene (z. B. `abs` und `sin`) von FSharp.Core.dll bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ddddd-247">For example, `Microsoft.FSharp.Core.Operators` is an automatically opened collection of top-level functions (like `abs` and `sin`) provided by FSharp.Core.dll.</span></span>

<span data-ttu-id="ddddd-248">Entsprechend kann eine Statistik-Bibliothek ein Modul mit Funktionen enthalten `erf` und `erfc`, wo dieses Modul dient, explizit oder automatisch geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="ddddd-248">Likewise, a statistics library might include a module with functions `erf` and `erfc`, where this module is designed to be explicitly or automatically opened.</span></span>

#### <a name="consider-using-requirequalifiedaccess-and-carefully-apply-autoopen-attributes"></a><span data-ttu-id="ddddd-249">RequireQualifiedAccess in Betracht, und wenden Sie sorgfältig AutoOpen-Attribute</span><span class="sxs-lookup"><span data-stu-id="ddddd-249">Consider using RequireQualifiedAccess and carefully apply AutoOpen attributes</span></span>

<span data-ttu-id="ddddd-250">Hinzufügen der `[<RequireQualifiedAccess>]` Attribut auf ein Modul gibt an, dass das Modul kann nicht geöffnet werden, dass Verweise auf die Elemente des Moduls explizite benötigen Zugriff qualifizierten.</span><span class="sxs-lookup"><span data-stu-id="ddddd-250">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="ddddd-251">Z. B. die `Microsoft.FSharp.Collections.List` Modul verfügt über dieses Attribut.</span><span class="sxs-lookup"><span data-stu-id="ddddd-251">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="ddddd-252">Dies ist nützlich, wenn Funktionen und Werte im Modul Namen haben, die einen Konflikt mit den Namen in anderen Modulen wahrscheinlich sind.</span><span class="sxs-lookup"><span data-stu-id="ddddd-252">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="ddddd-253">Qualifizierten Zugriff erfordern, kann erheblich die langfristige wartbarkeit und Evolvability einer Bibliothek erhöhen.</span><span class="sxs-lookup"><span data-stu-id="ddddd-253">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

<span data-ttu-id="ddddd-254">Hinzufügen der `[<AutoOpen>]` Attribut auf ein Modul bedeutet, dass das Modul wird geöffnet, wenn der übergeordnete Namespace geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="ddddd-254">Adding the `[<AutoOpen>]` attribute to a module means the module will be opened when the containing namespace is opened.</span></span> <span data-ttu-id="ddddd-255">Die `[<AutoOpen>]` Attribut kann auch auf eine Assembly an, die automatisch geöffnet wird, wenn die Assembly verwiesen wird, ist ein Modul angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="ddddd-255">The `[<AutoOpen>]` attribute may also be applied to an assembly to indicate a module that is automatically opened when the assembly is referenced.</span></span>

<span data-ttu-id="ddddd-256">Beispielsweise eine Statistik Bibliothek **MathsHeaven.Statistics** enthält möglicherweise eine `module MathsHeaven.Statistics.Operators` , das Funktionen enthält `erf` und `erfc`.</span><span class="sxs-lookup"><span data-stu-id="ddddd-256">For example, a statistics library **MathsHeaven.Statistics** might contain a `module MathsHeaven.Statistics.Operators` containing functions `erf` and `erfc`.</span></span> <span data-ttu-id="ddddd-257">Es ist sinnvoll, markieren Sie dieses Modul als `[<AutoOpen>]`.</span><span class="sxs-lookup"><span data-stu-id="ddddd-257">It is reasonable to mark this module as `[<AutoOpen>]`.</span></span> <span data-ttu-id="ddddd-258">Dies bedeutet, dass `open MathsHeaven.Statistics` außerdem öffnen Sie dieses Modul, und schalten Sie die Namen `erf` und `erfc` in den Bereich.</span><span class="sxs-lookup"><span data-stu-id="ddddd-258">This means `open MathsHeaven.Statistics` will also open this module and bring the names `erf` and `erfc` into scope.</span></span> <span data-ttu-id="ddddd-259">Verwenden Sie einen anderen funktionierenden von `[<AutoOpen>]` für Module mit Erweiterungsmethoden bereit ist.</span><span class="sxs-lookup"><span data-stu-id="ddddd-259">Another good use of `[<AutoOpen>]` is for modules containing extension methods.</span></span>

<span data-ttu-id="ddddd-260">Der übermäßigen Verwendung `[<AutoOpen>]` Leads auf belasteten Namespaces und das Attribut sollte mit Vorsicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ddddd-260">Overuse of `[<AutoOpen>]` leads to polluted namespaces, and the attribute should be used with care.</span></span> <span data-ttu-id="ddddd-261">Für bestimmte Bibliotheken in bestimmten Domänen, zielgerichtete Verwendung von `[<AutoOpen>]` zu besserer benutzerfreundlichkeit führen kann.</span><span class="sxs-lookup"><span data-stu-id="ddddd-261">For specific libraries in specific domains, judicious use of `[<AutoOpen>]` can lead to better usability.</span></span>

#### <a name="consider-defining-operator-members-on-classes-where-using-well-known-operators-is-appropriate"></a><span data-ttu-id="ddddd-262">Betrachten Sie die Definition von Operator Member für Klassen, die mit bekannten Operatoren geeignet ist</span><span class="sxs-lookup"><span data-stu-id="ddddd-262">Consider defining operator members on classes where using well-known operators is appropriate</span></span>

<span data-ttu-id="ddddd-263">Manchmal werden Klassen zum Modellieren von mathematischer Konstrukten, z. B. Vektoren verwendet.</span><span class="sxs-lookup"><span data-stu-id="ddddd-263">Sometimes classes are used to model mathematical constructs such as Vectors.</span></span> <span data-ttu-id="ddddd-264">Wenn die Domäne, die modelliert werden bekannte Operatoren verfügt, ist das Definieren sie als Member der Klasse systeminterne hilfreich.</span><span class="sxs-lookup"><span data-stu-id="ddddd-264">When the domain being modeled has well-known operators, defining them as members intrinsic to the class is helpful.</span></span>

```fsharp
type Vector(x: float) =

    member v.X = x

    static member (*) (vector: Vector, scalar: float) = Vector(vector.X * scalar)

    static member (+) (vector1: Vector, vector2: Vector) = Vector(vector1.X + vector2.X)

let v = Vector(5.0)

let u = v * 10.0
```

<span data-ttu-id="ddddd-265">Diese Anleitung entspricht .NET Hilfestellungen für diese Typen.</span><span class="sxs-lookup"><span data-stu-id="ddddd-265">This guidance corresponds to general .NET guidance for these types.</span></span> <span data-ttu-id="ddddd-266">Allerdings kann es außerdem wichtig sein in F#-Programmierung, da dadurch diese Typen, die in Verbindung mit der F#-Funktionen und Methoden mit Membereinschränkungen, z. B. List.sumBy verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="ddddd-266">However, it can be additionally important in F# coding as this allows these types to be used in conjunction with F# functions and methods with member constraints, such as List.sumBy.</span></span>

#### <a name="consider-using-compiledname-to-provide-a-net-friendly-name-for-other-net-language-consumers"></a><span data-ttu-id="ddddd-267">Erwägen Sie die Verwendung von CompiledName bereitstellen ein. NET-Anzeigenamen für andere .NET Language-Consumer</span><span class="sxs-lookup"><span data-stu-id="ddddd-267">Consider using CompiledName to provide a .NET-friendly name for other .NET language consumers</span></span>

<span data-ttu-id="ddddd-268">In einigen Fällen möglicherweise möchten Sie ein Element in ein Format für Namen F# Consumern (z. B. ein statischer Member in Kleinbuchstaben, damit er angezeigt wird als handele es sich um eine Modul-Bound-Funktion), aber haben Sie einen anderen Stil für den Namen ein, wenn sie in eine Assembly kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="ddddd-268">Sometimes you may wish to name something in one style for F# consumers (such as a static member in lower case so that it appears as if it were a module-bound function), but have a different style for the name when it is compiled into an assembly.</span></span> <span data-ttu-id="ddddd-269">Können Sie die `[<CompiledName>]` Attribut geben Sie einen anderen Stil für nicht F# Code, in der Assemblys.</span><span class="sxs-lookup"><span data-stu-id="ddddd-269">You can use the `[<CompiledName>]` attribute to provide a different style for non F# code consuming the assembly.</span></span>

```fsharp
type Vector(x:float, y:float) =

    member v.X = x
    member v.Y = y

    [<CompiledName("Create")>]
    static member create x y = Vector (x, y)

let v = Vector.create 5.0 3.0
```

<span data-ttu-id="ddddd-270">Mithilfe von `[<CompiledName>]`, können Sie Konventionen für .NET nicht F# Consumern der Assembly.</span><span class="sxs-lookup"><span data-stu-id="ddddd-270">By using `[<CompiledName>]`, you can use .NET naming conventions for non F# consumers of the assembly.</span></span>

#### <a name="use-method-overloading-for-member-functions-if-doing-so-provides-a-simpler-api"></a><span data-ttu-id="ddddd-271">Verwenden Sie Überladen von Methoden für Memberfunktionen, wenn so eine einfachere API bereitgestellt werden</span><span class="sxs-lookup"><span data-stu-id="ddddd-271">Use method overloading for member functions, if doing so provides a simpler API</span></span>

<span data-ttu-id="ddddd-272">Überladen von Methoden ist ein leistungsfähiges Tool für die Vereinfachung einer API, die ähnliche Funktionen ausführen muss, aber mit verschiedenen Optionen oder Argumente.</span><span class="sxs-lookup"><span data-stu-id="ddddd-272">Method overloading is a powerful tool for simplifying an API that may need to perform similar functionality, but with different options or arguments.</span></span>

```fsharp
type Logger() =

    member this.Log(message) =
        ...
    member this.Log(message, retryPolicy) =
        ...
```

<span data-ttu-id="ddddd-273">In F# ist es eher üblich, dass die Anzahl von Argumenten statt Typen der Argumente zu überladen.</span><span class="sxs-lookup"><span data-stu-id="ddddd-273">In F#, it is more common to overload on number of arguments rather than types of arguments.</span></span>

#### <a name="hide-the-representations-of-record-and-union-types-if-the-design-of-these-types-is-likely-to-evolve"></a><span data-ttu-id="ddddd-274">Blenden Sie die Darstellung des Datensatzes und union-Typen aus, wenn das Design dieser Typen voraussichtlich weiterentwickelt werden</span><span class="sxs-lookup"><span data-stu-id="ddddd-274">Hide the representations of record and union types if the design of these types is likely to evolve</span></span>

<span data-ttu-id="ddddd-275">Vermeiden Sie die konkrete Darstellungen von Objekten offenzulegen.</span><span class="sxs-lookup"><span data-stu-id="ddddd-275">Avoid revealing concrete representations of objects.</span></span> <span data-ttu-id="ddddd-276">Z. B. die konkrete Repräsentation der <xref:System.DateTime> Werte von der externen, öffentliche API des Entwurfs .NET Bibliothek nicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ddddd-276">For example, the concrete representation of <xref:System.DateTime> values is not revealed by the external, public API of the .NET library design.</span></span> <span data-ttu-id="ddddd-277">Zur Laufzeit weiß der Common Language Runtime die Commit-Implementierung, die in der gesamten Ausführung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ddddd-277">At run time, the Common Language Runtime knows the committed implementation that will be used throughout execution.</span></span> <span data-ttu-id="ddddd-278">Allerdings nicht kompilierter Code selbst abhängig von der konkrete Repräsentation übernommen.</span><span class="sxs-lookup"><span data-stu-id="ddddd-278">However, compiled code doesn't itself pick up dependencies on the concrete representation.</span></span>

#### <a name="avoid-the-use-of-implementation-inheritance-for-extensibility"></a><span data-ttu-id="ddddd-279">Vermeiden Sie die Verwendung der implementierungsvererbung für die Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="ddddd-279">Avoid the use of implementation inheritance for extensibility</span></span>

<span data-ttu-id="ddddd-280">In F# wird die implementierungsvererbung selten verwendet.</span><span class="sxs-lookup"><span data-stu-id="ddddd-280">In F#, implementation inheritance is rarely used.</span></span> <span data-ttu-id="ddddd-281">Darüber hinaus sind Vererbungshierarchien häufig komplex und schwierig zu ändern, wenn neue Anforderungen eingehen.</span><span class="sxs-lookup"><span data-stu-id="ddddd-281">Furthermore, inheritance hierarchies are often complex and difficult to change when new requirements arrive.</span></span> <span data-ttu-id="ddddd-282">Implementierung der Vererbung noch vorhanden ist, im F# für Kompatibilität und seltenen Fällen, in denen die beste Lösung für ein Problem aufgetreten ist, aber die alternative Techniken gesucht werden soll, in, Ihre F# Programme beim Entwerfen der Polymorphie, wie z. B. Schnittstelle -Implementierung.</span><span class="sxs-lookup"><span data-stu-id="ddddd-282">Inheritance implementation still exists in F# for compatibility and rare cases where it is the best solution to a problem, but alternative techniques should be sought in your F# programs when designing for polymorphism, such as interface implementation.</span></span>

### <a name="function-and-member-signatures"></a><span data-ttu-id="ddddd-283">Funktion und Element-Signaturen</span><span class="sxs-lookup"><span data-stu-id="ddddd-283">Function and member signatures</span></span>

#### <a name="use-tuples-for-return-values-when-returning-a-small-number-of-multiple-unrelated-values"></a><span data-ttu-id="ddddd-284">Verwenden Sie Tupel für die Rückgabe von Werten, wenn eine kleine Anzahl von mehreren nicht verknüpften Werten zurückgibt</span><span class="sxs-lookup"><span data-stu-id="ddddd-284">Use tuples for return values when returning a small number of multiple unrelated values</span></span>

<span data-ttu-id="ddddd-285">Hier ist ein gutes Beispiel für die Verwendung eines Tupels in einem Rückgabetyp:</span><span class="sxs-lookup"><span data-stu-id="ddddd-285">Here is a good example of using a tuple in a return type:</span></span>

```fsharp
val divrem: BigInteger -> BigInteger -> BigInteger * BigInteger
```

<span data-ttu-id="ddddd-286">Für zurückgeben Sie, die viele Komponenten enthält, oder wenn es sich bei die Komponenten mit einer einzelnen identifizierbaren Entität verknüpft sind, sollten Sie einen benannten Typ anstelle eines Tupels verwenden.</span><span class="sxs-lookup"><span data-stu-id="ddddd-286">For return types containing many components, or where the components are related to a single identifiable entity, consider using a named type instead of a tuple.</span></span>

#### <a name="use-asynct-for-async-programming-at-f-api-boundaries"></a><span data-ttu-id="ddddd-287">Verwendung `Async<T>` für asynchrone Programmierung an den Begrenzungen der F#-API</span><span class="sxs-lookup"><span data-stu-id="ddddd-287">Use `Async<T>` for async programming at F# API boundaries</span></span>

<span data-ttu-id="ddddd-288">Es ist ein entsprechender synchroner Vorgang, der mit dem Namen `Operation` zurückgibt eine `T`, und klicken Sie dann der asynchronen Vorgang benannt werden sollen `AsyncOperation` zurückgegeben `Async<T>` oder `OperationAsync` zurückgegeben `Task<T>`.</span><span class="sxs-lookup"><span data-stu-id="ddddd-288">If there is a corresponding synchronous operation named `Operation` that returns a `T`, then the async operation should be named `AsyncOperation` if it returns `Async<T>` or `OperationAsync` if it returns `Task<T>`.</span></span> <span data-ttu-id="ddddd-289">Für häufig verwendete .NET Typen, die Begin/End-Methoden verfügbar machen können Sie mithilfe von `Async.FromBeginEnd` zum Schreiben von Erweiterungsmethoden bereit, die als eine Fassade zum Bereitstellen der F# asynchrone Programmiermodell, das auf diese .NET APIs.</span><span class="sxs-lookup"><span data-stu-id="ddddd-289">For commonly used .NET types that expose Begin/End methods, consider using `Async.FromBeginEnd` to write extension methods as a façade to provide the F# async programming model to those .NET APIs.</span></span>

```fsharp
type SomeType =
    member this.Compute(x:int): int =
        ...
    member this.AsyncCompute(x:int): Async<int> =
        ...

type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        ...
```

### <a name="exceptions"></a><span data-ttu-id="ddddd-290">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="ddddd-290">Exceptions</span></span>

<span data-ttu-id="ddddd-291">Finden Sie unter [Fehlerverwaltung](conventions.md#error-management) angemessene Verwendung von Ausnahmen, Ergebnisse und Optionen zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="ddddd-291">See [Error Management](conventions.md#error-management) to learn about appropriate use of exceptions, results, and options.</span></span>

### <a name="extension-members"></a><span data-ttu-id="ddddd-292">Erweiterungsmember</span><span class="sxs-lookup"><span data-stu-id="ddddd-292">Extension Members</span></span>

#### <a name="carefully-apply-f-extension-members-in-f-to-f-components"></a><span data-ttu-id="ddddd-293">Sorgfältig anwenden F# Erweiterungsmember in F#-zu-F#-Komponenten</span><span class="sxs-lookup"><span data-stu-id="ddddd-293">Carefully apply F# extension members in F#-to-F# components</span></span>

<span data-ttu-id="ddddd-294">F#Erweiterungsmember sollte in der Regel nur für Vorgänge verwendet werden, die in der Closure systeminterne Vorgänge, die einem Typ in den meisten ihrer Arten der Verwendung zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="ddddd-294">F# extension members should generally only be used for operations that are in the closure of intrinsic operations associated with a type in the majority of its modes of use.</span></span> <span data-ttu-id="ddddd-295">Eine übliche Verwendung besteht darin, APIs bereit, die idiomatische F# für verschiedene .NET Datentypen sind:</span><span class="sxs-lookup"><span data-stu-id="ddddd-295">One common use is to provide APIs that are more idiomatic to F# for various .NET types:</span></span>

```fsharp
type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        Async.FromBeginEnd(this.BeginReceive, this.EndReceive)

type System.Collections.Generic.IDictionary<'Key,'Value> with
    member this.TryGet key =
        let ok, v = this.TryGetValue key
        if ok then Some v else None
```

### <a name="union-types"></a><span data-ttu-id="ddddd-296">Union-Typen</span><span class="sxs-lookup"><span data-stu-id="ddddd-296">Union Types</span></span>

#### <a name="use-discriminated-unions-instead-of-class-hierarchies-for-tree-structured-data"></a><span data-ttu-id="ddddd-297">Verwenden von Unterscheidungs-Unions statt Klassenhierarchien strukturierten Daten</span><span class="sxs-lookup"><span data-stu-id="ddddd-297">Use discriminated unions instead of class hierarchies for tree-structured data</span></span>

<span data-ttu-id="ddddd-298">Baumähnliche Strukturen sind rekursiv definiert.</span><span class="sxs-lookup"><span data-stu-id="ddddd-298">Tree-like structures are recursively defined.</span></span> <span data-ttu-id="ddddd-299">Dies ist ganz einfach mit Vererbung, jedoch mit Unterscheidungs-Unions elegant.</span><span class="sxs-lookup"><span data-stu-id="ddddd-299">This is awkward with inheritance, but elegant with Discriminated Unions.</span></span>

```fsharp
type BST<'T> =
    | Empty
    | Node of 'T * BST<'T> * BST<'T>
```

<span data-ttu-id="ddddd-300">Darstellen von baumähnliche-Daten mit Unterscheidungs-Unions können Sie auch Exhaustiveness Musterabgleich profitieren.</span><span class="sxs-lookup"><span data-stu-id="ddddd-300">Representing tree-like data with Discriminated Unions also allows you to benefit from exhaustiveness in pattern matching.</span></span>

#### <a name="use-requirequalifiedaccess-on-union-types-whose-case-names-are-not-sufficiently-unique"></a><span data-ttu-id="ddddd-301">Verwendung `[<RequireQualifiedAccess>]` auf union-Typen, deren Namen mit Groß-und Kleinschreibung nicht ausreichend eindeutig sind,</span><span class="sxs-lookup"><span data-stu-id="ddddd-301">Use `[<RequireQualifiedAccess>]` on union types whose case names are not sufficiently unique</span></span>

<span data-ttu-id="ddddd-302">Selbst in einer Domäne möglicherweise steht der gleiche Namen auf Namen fest. für unterschiedliche Dinge, wie z. B. Unterscheidungs-Union-Fälle.</span><span class="sxs-lookup"><span data-stu-id="ddddd-302">You may find yourself in a domain where the same name is the best name for different things, such as Discriminated Union cases.</span></span> <span data-ttu-id="ddddd-303">Sie können `[<RequireQualifiedAccess>]` um Groß-/Kleinschreibung von Namen zu unterscheiden, um zu vermeiden, verwirrend Fehler aufgrund von shadowing abhängig, die Reihenfolge der Auslösung `open` Anweisungen</span><span class="sxs-lookup"><span data-stu-id="ddddd-303">You can use `[<RequireQualifiedAccess>]` to disambiguate case names in order to avoid triggering confusing errors due to shadowing dependent on the ordering of `open` statements</span></span>

#### <a name="hide-the-representations-of-discriminated-unions-for-binary-compatible-apis-if-the-design-of-these-types-is-likely-to-evolve"></a><span data-ttu-id="ddddd-304">Blenden Sie die Darstellung der Unterscheidungs-Unions für binäre kompatiblen APIs aus, wenn das Design dieser Typen voraussichtlich weiterentwickelt werden</span><span class="sxs-lookup"><span data-stu-id="ddddd-304">Hide the representations of discriminated unions for binary compatible APIs if the design of these types is likely to evolve</span></span>

<span data-ttu-id="ddddd-305">Unions-Typen basieren auf F# Mustervergleichs-Formulare für eine kurze Programmiermodell.</span><span class="sxs-lookup"><span data-stu-id="ddddd-305">Unions types rely on F# pattern-matching forms for a succinct programming model.</span></span> <span data-ttu-id="ddddd-306">Wie bereits erwähnt, sollten Sie konkrete datendarstellungen offenzulegen, wenn das Design dieser Typen voraussichtlich weiterentwickelt wird.</span><span class="sxs-lookup"><span data-stu-id="ddddd-306">As mentioned previously, you should avoid revealing concrete data representations if the design of these types is likely to evolve.</span></span>

<span data-ttu-id="ddddd-307">Z. B. die Darstellung einer Unterscheidungs-Union kann ausgeblendet werden, mit einer privaten oder internen-Deklaration, oder indem Sie eine Signaturdatei.</span><span class="sxs-lookup"><span data-stu-id="ddddd-307">For example, the representation of a discriminated union can be hidden using a private or internal declaration, or by using a signature file.</span></span>

```fsharp
type Union =
    private
    | CaseA of int
    | CaseB of string
```

<span data-ttu-id="ddddd-308">Wenn Sie eine Unterscheidungs-Unions wahllos anzeigen, es schwierig, Version Ihrer Bibliothek möglicherweise ohne Benutzercode.</span><span class="sxs-lookup"><span data-stu-id="ddddd-308">If you reveal discriminated unions indiscriminately, you may find it hard to version your library without breaking user code.</span></span> <span data-ttu-id="ddddd-309">Erwägen Sie stattdessen eine oder mehrere aktive Muster zum Musterabgleich gegenüber Werte des Typs zulassen offenzulegen.</span><span class="sxs-lookup"><span data-stu-id="ddddd-309">Instead, consider revealing one or more active patterns to permit pattern matching over values of your type.</span></span>

<span data-ttu-id="ddddd-310">Aktive Muster stellen eine Alternative zu F# Kunden mit Musterabgleich zugleich Verfügbarmachen von F# Union-Typen direkt.</span><span class="sxs-lookup"><span data-stu-id="ddddd-310">Active patterns provide an alternate way to provide F# consumers with pattern matching while avoiding exposing F# Union Types directly.</span></span>

### <a name="inline-functions-and-member-constraints"></a><span data-ttu-id="ddddd-311">Inline-Funktionen und Member-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="ddddd-311">Inline Functions and Member Constraints</span></span>

#### <a name="define-generic-numeric-algorithms-using-inline-functions-with-implied-member-constraints-and-statically-resolved-generic-types"></a><span data-ttu-id="ddddd-312">Definieren von generischen numerischen Algorithmen, die Verwendung von Inlinefunktionen mit impliziten Member-Einschränkungen und statisch aufgelösten generischen Typen</span><span class="sxs-lookup"><span data-stu-id="ddddd-312">Define generic numeric algorithms using inline functions with implied member constraints and statically resolved generic types</span></span>

<span data-ttu-id="ddddd-313">Arithmetische Member und F#-Vergleichs-Einschränkungen sind ein Standard für F#-Programmierung.</span><span class="sxs-lookup"><span data-stu-id="ddddd-313">Arithmetic member constraints and F# comparison constraints are a standard for F# programming.</span></span> <span data-ttu-id="ddddd-314">Beachten Sie z. B. folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="ddddd-314">For example, consider the following code:</span></span>

```fsharp
let inline highestCommonFactor a b =
    let rec loop a b =
        if a = LanguagePrimitives.GenericZero<_> then b
        elif a < b then loop a (b - a)
        else loop (a - b) b
    loop a b
```

<span data-ttu-id="ddddd-315">Der Typ dieser Funktion lautet wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="ddddd-315">The type of this function is as follows:</span></span>

```fsharp
val inline highestCommonFactor : ^T -> ^T -> ^T
                when ^T : (static member Zero : ^T)
                and ^T : (static member ( - ) : ^T * ^T -> ^T)
                and ^T : equality
                and ^T : comparison
```

<span data-ttu-id="ddddd-316">Dies ist eine passende Funktion für eine öffentliche API in einer mathematischen Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="ddddd-316">This is a suitable function for a public API in a mathematical library.</span></span>

#### <a name="avoid-using-member-constraints-to-simulate-type-classes-and-duck-typing"></a><span data-ttu-id="ddddd-317">Vermeiden Sie die Verwendung der Member-Einschränkungen, Klassen und beim Duck-typing zu simulieren</span><span class="sxs-lookup"><span data-stu-id="ddddd-317">Avoid using member constraints to simulate type classes and duck typing</span></span>

<span data-ttu-id="ddddd-318">Es ist möglich, mithilfe von "Duck typing" simulieren F# Member-Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="ddddd-318">It is possible to simulate “duck typing” using F# member constraints.</span></span> <span data-ttu-id="ddddd-319">Allerdings Elemente, die Stellen verwenden dieses sollte nicht im Allgemeinen in F# verwendet-zu-Entwürfe für F#-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="ddddd-319">However, members that make use of this should not in general be used in F#-to-F# library designs.</span></span> <span data-ttu-id="ddddd-320">Dies ist, da die Bibliothek-Designs, die basierend auf implizite nicht vertraut sind oder nicht dem standard-Einschränkungen in der Regel dazu führen, dass der Benutzercode unflexibel und an einem bestimmten Framework-Muster gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="ddddd-320">This is because library designs based on unfamiliar or non-standard implicit constraints tend to cause user code to become inflexible and tied to one particular framework pattern.</span></span>

<span data-ttu-id="ddddd-321">Darüber hinaus besteht eine hohe Wahrscheinlichkeit, die intensiven Gebrauch von der Membereinschränkungen auf diese Weise sehr lange kompilierzeiten führen kann.</span><span class="sxs-lookup"><span data-stu-id="ddddd-321">Additionally, there is a good chance that heavy use of member constraints in this manner can result in very long compile times.</span></span>

### <a name="operator-definitions"></a><span data-ttu-id="ddddd-322">Operatordefinitionen</span><span class="sxs-lookup"><span data-stu-id="ddddd-322">Operator Definitions</span></span>

#### <a name="avoid-defining-custom-symbolic-operators"></a><span data-ttu-id="ddddd-323">Vermeiden Sie das Festlegen von benutzerdefinierter symbolische Operatoren</span><span class="sxs-lookup"><span data-stu-id="ddddd-323">Avoid defining custom symbolic operators</span></span>

<span data-ttu-id="ddddd-324">Benutzerdefinierte Operatoren sind in einigen Situationen wichtig und überaus nützliche Schreibweisen Geräte in eine große Menge Code zur Implementierung.</span><span class="sxs-lookup"><span data-stu-id="ddddd-324">Custom operators are essential in some situations and are highly useful notational devices within a large body of implementation code.</span></span> <span data-ttu-id="ddddd-325">Benannte Funktionen sind für neue Benutzer von einer Bibliothek häufig einfacher zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ddddd-325">For new users of a library, named functions are often easier to use.</span></span> <span data-ttu-id="ddddd-326">Darüber hinaus benutzerdefinierte symbolische Operatoren können schwierig sein, Dokument, und Benutzer finden es schwieriger, um Hilfe für Operatoren, die aufgrund von vorhandenen Einschränkungen in der IDE, und suchen Sie Module zu suchen.</span><span class="sxs-lookup"><span data-stu-id="ddddd-326">In addition, custom symbolic operators can be hard to document, and users find it more difficult to look up help on operators, due to existing limitations in IDE and search engines.</span></span>

<span data-ttu-id="ddddd-327">Daher ist es am besten, veröffentlichen Sie Ihre Funktionalität wie die benannten Funktionen und Member, und nur dann, wenn die notationsvorteile überwiegen, Dokumentation und kognitive Kosten für Sie außerdem die Operatoren für diese Funktionalität verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="ddddd-327">As a result, it is best to publish your functionality as named functions and members, and additionally expose operators for this functionality only if the notational benefits outweigh the documentation and cognitive cost of having them.</span></span>

### <a name="units-of-measure"></a><span data-ttu-id="ddddd-328">Maßeinheiten</span><span class="sxs-lookup"><span data-stu-id="ddddd-328">Units of Measure</span></span>

#### <a name="carefully-use-units-of-measure-for-added-type-safety-in-f-code"></a><span data-ttu-id="ddddd-329">Maßeinheiten für die hinzugefügte typsicherheit mit Vorsicht verwenden F# Code</span><span class="sxs-lookup"><span data-stu-id="ddddd-329">Carefully use units of measure for added type safety in F# code</span></span>

<span data-ttu-id="ddddd-330">Zusätzliche typisierungsinformationen für Einheiten des Measures wird gelöscht, wenn Sie von anderen .NET-Programmiersprachen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ddddd-330">Additional typing information for units of measure is erased when viewed by other .NET languages.</span></span> <span data-ttu-id="ddddd-331">Denken Sie daran, dass .NET Komponenten, Tools und Reflektion Typen-sans-Einheiten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ddddd-331">Be aware that .NET components, tools, and reflection will see types-sans-units.</span></span> <span data-ttu-id="ddddd-332">C#-Kunden werden angezeigt, z. B. `float` statt `float<kg>`.</span><span class="sxs-lookup"><span data-stu-id="ddddd-332">For example, C# consumers will see `float` rather than `float<kg>`.</span></span>

### <a name="type-abbreviations"></a><span data-ttu-id="ddddd-333">Typabkürzungen</span><span class="sxs-lookup"><span data-stu-id="ddddd-333">Type Abbreviations</span></span>

#### <a name="carefully-use-type-abbreviations-to-simplify-f-code"></a><span data-ttu-id="ddddd-334">Typabkürzungen sorgfältig zu verwenden, um F#-Code zu vereinfachen</span><span class="sxs-lookup"><span data-stu-id="ddddd-334">Carefully use type abbreviations to simplify F# code</span></span>

<span data-ttu-id="ddddd-335">.NET Komponenten, Tools und Reflektion werden nicht abgekürzte Namen für Typen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ddddd-335">.NET components, tools, and reflection will not see abbreviated names for types.</span></span> <span data-ttu-id="ddddd-336">Nennenswerte Nutzung von typabkürzungen kann auch eine Domäne, die angezeigt werden, viel komplexer, als sie tatsächlich ist die könnte Kunden verwirren, vornehmen.</span><span class="sxs-lookup"><span data-stu-id="ddddd-336">Significant usage of type abbreviations can also make a domain appear more complex than it actually is, which could confuse consumers.</span></span>

#### <a name="avoid-type-abbreviations-for-public-types-whose-members-and-properties-should-be-intrinsically-different-to-those-available-on-the-type-being-abbreviated"></a><span data-ttu-id="ddddd-337">Vermeiden Sie typabkürzungen für öffentliche Typen, deren Elemente und Eigenschaften ganz anderes eingabeparadigma nahe zur Verfügung stehen, für den Typ wird abgekürzt werden soll</span><span class="sxs-lookup"><span data-stu-id="ddddd-337">Avoid type abbreviations for public types whose members and properties should be intrinsically different to those available on the type being abbreviated</span></span>

<span data-ttu-id="ddddd-338">In diesem Fall zeigt den abgekürzt werden zu viele Informationen über die Darstellung des aktuellen Typs definiert wird.</span><span class="sxs-lookup"><span data-stu-id="ddddd-338">In this case, the type being abbreviated reveals too much about the representation of the actual type being defined.</span></span> <span data-ttu-id="ddddd-339">Stattdessen sollten Sie die Abkürzung in einen Klassentyp oder eine einzelne Fall Unterscheidungs-Union zu umschließen (oder, wenn Leistung wichtig ist, erwägen Sie die Verwendung eines Strukturtyps, umschließen die Abkürzung).</span><span class="sxs-lookup"><span data-stu-id="ddddd-339">Instead, consider wrapping the abbreviation in a class type or a single-case discriminated union (or, when performance is essential, consider using a struct type to wrap the abbreviation).</span></span>

<span data-ttu-id="ddddd-340">Angenommen, es ist verlockend, definieren Sie eine Zuordnung mit mehreren als Sonderfall von einem F# zuordnen, z.B.:</span><span class="sxs-lookup"><span data-stu-id="ddddd-340">For example, it is tempting to define a multi-map as a special case of an F# map, for example:</span></span>

```fsharp
type MultiMap<'Key,'Value> = Map<'Key,'Value list>
```

<span data-ttu-id="ddddd-341">Allerdings die logische Punktnotation-Vorgänge für diesen Typ sind nicht identisch mit die Vorgänge auf einer Karte – beispielsweise ist es plausibel, dass die Lookup-Operator zugeordnet. [Schlüssel] Rückgabe der leeren Liste, wenn der Schlüssel nicht in das Wörterbuch, anstatt eine Ausnahme auszulösen.</span><span class="sxs-lookup"><span data-stu-id="ddddd-341">However, the logical dot-notation operations on this type are not the same as the operations on a Map – for example, it is reasonable that the lookup operator map.[key] return the empty list if the key is not in the dictionary, rather than raising an exception.</span></span>

## <a name="guidelines-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="ddddd-342">Richtlinien für die Bibliotheken für die Verwendung von anderen .NET-Sprachen</span><span class="sxs-lookup"><span data-stu-id="ddddd-342">Guidelines for libraries for Use from other .NET Languages</span></span>

<span data-ttu-id="ddddd-343">Beim Entwerfen der Bibliotheken für die Verwendung von anderen .NET-Sprachen ist es wichtig, entsprechen die [.NET Klassenbibliotheken – Entwurfsrichtlinien](../../standard/design-guidelines/index.md).</span><span class="sxs-lookup"><span data-stu-id="ddddd-343">When designing libraries for use from other .NET languages, it is important to adhere to the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md).</span></span> <span data-ttu-id="ddddd-344">In diesem Dokument werden diese Bibliotheken bezeichnet, als einfaches .NET Bibliotheken, im Gegensatz zu F#-Bibliotheken, mit denen F#-facing ohne Einschränkungen erstellt.</span><span class="sxs-lookup"><span data-stu-id="ddddd-344">In this document, these libraries are labeled as vanilla .NET libraries, as opposed to F#-facing libraries that use F# constructs without restriction.</span></span> <span data-ttu-id="ddddd-345">Entwerfen einfache Bibliotheken für .NET bedeutet, dass vertraut und idiomatische-APIs, die konsistent mit dem Rest des .NET Framework durch minimieren die Verwendung von bereitstellen F#-spezifische Konstrukte in der öffentlichen API.</span><span class="sxs-lookup"><span data-stu-id="ddddd-345">Designing vanilla .NET libraries means providing familiar and idiomatic APIs consistent with the rest of the .NET Framework by minimizing the use of F#-specific constructs in the public API.</span></span> <span data-ttu-id="ddddd-346">Die Regeln werden in den folgenden Abschnitten erläutert.</span><span class="sxs-lookup"><span data-stu-id="ddddd-346">The rules are explained in the following sections.</span></span>

### <a name="namespace-and-type-design-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="ddddd-347">Namespace und Typ-Entwurf (für die Bibliotheken für die Verwendung von anderen .NET-Sprachen)</span><span class="sxs-lookup"><span data-stu-id="ddddd-347">Namespace and Type design (for libraries for use from other .NET Languages)</span></span>

#### <a name="apply-the-net-naming-conventions-to-the-public-api-of-your-components"></a><span data-ttu-id="ddddd-348">Übernehmen Sie die .NET-Namenskonventionen, um die öffentliche API des Ihre Komponenten</span><span class="sxs-lookup"><span data-stu-id="ddddd-348">Apply the .NET naming conventions to the public API of your components</span></span>

<span data-ttu-id="ddddd-349">Achten Sie besonders auf die Verwendung der abgekürzten Namen und die Groß-/Kleinschreibung-Richtlinien von .NET.</span><span class="sxs-lookup"><span data-stu-id="ddddd-349">Pay special attention to the use of abbreviated names and the .NET capitalization guidelines.</span></span>

```fsharp
type pCoord = ...
    member this.theta = ...

type PolarCoordinate = ...
    member this.Theta = ...
```

#### <a name="use-namespaces-types-and-members-as-the-primary-organizational-structure-for-your-components"></a><span data-ttu-id="ddddd-350">Verwenden von Namespaces, Typen und Membern als die primäre Organisationsstruktur für Ihre Komponenten</span><span class="sxs-lookup"><span data-stu-id="ddddd-350">Use namespaces, types, and members as the primary organizational structure for your components</span></span>

<span data-ttu-id="ddddd-351">Alle Dateien mit öffentlichen Funktionen sollten beginnen mit einer `namespace` Deklaration und die einzigen öffentlichen Entitäten in Namespaces sollten Typen sein.</span><span class="sxs-lookup"><span data-stu-id="ddddd-351">All files containing public functionality should begin with a `namespace` declaration, and the only public-facing entities in namespaces should be types.</span></span> <span data-ttu-id="ddddd-352">Verwenden Sie keine F# Module.</span><span class="sxs-lookup"><span data-stu-id="ddddd-352">Do not use F# modules.</span></span>

<span data-ttu-id="ddddd-353">Verwenden Sie nicht öffentliche Module, um Code zur Implementierung, Hilfsprogramm Typen und Hilfsprogrammfunktionen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="ddddd-353">Use non-public modules to hold implementation code, utility types, and utility functions.</span></span>

<span data-ttu-id="ddddd-354">Statische Typen sollten bevorzugt werden über Module, sie können für die zukünftige Entwicklung der API zum Überladen von Operatoren und andere .NET API-Entwurfskonzepte verwenden, die nicht innerhalb von verwendet werden kann F# Module.</span><span class="sxs-lookup"><span data-stu-id="ddddd-354">Static types should be preferred over modules, as they allow for future evolution of the API to use overloading and other .NET API design concepts that may not be used within F# modules.</span></span>

<span data-ttu-id="ddddd-355">Beispielsweise anstelle der folgenden öffentlichen API:</span><span class="sxs-lookup"><span data-stu-id="ddddd-355">For example, in place of the following public API:</span></span>

```fsharp
module Fabrikam

module Utilities =
    let Name = "Bob"
    let Add2 x y = x + y
    let Add3 x y z = x + y + z
```

<span data-ttu-id="ddddd-356">Erwägen Sie stattdessen ein:</span><span class="sxs-lookup"><span data-stu-id="ddddd-356">Consider instead:</span></span>

```fsharp
namespace Fabrikam

[<AbstractClass; Sealed>]
type Utilities =
    static member Name = "Bob"
    static member Add(x,y) = x + y
    static member Add(x,y,z) = x + y + z
```

#### <a name="use-f-record-types-in-vanilla-net-apis-if-the-design-of-the-types-wont-evolve"></a><span data-ttu-id="ddddd-357">Verwendung F# Eintragstypen in Vanille .NET APIs, wenn der Entwurf der Typen weiterentwickelt wird nicht</span><span class="sxs-lookup"><span data-stu-id="ddddd-357">Use F# record types in vanilla .NET APIs if the design of the types won't evolve</span></span>

<span data-ttu-id="ddddd-358">F#Record-Typen, die in einer einfachen .NET Klasse kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="ddddd-358">F# record types compile to a simple .NET class.</span></span> <span data-ttu-id="ddddd-359">Diese sind für einige einfachen, stabile-Typen in APIs geeignet.</span><span class="sxs-lookup"><span data-stu-id="ddddd-359">These are suitable for some simple, stable types in APIs.</span></span> <span data-ttu-id="ddddd-360">Erwägen Sie die `[<NoEquality>]` und `[<NoComparison>]` Attribute, um die automatische Generierung von Schnittstellen zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="ddddd-360">You should consider using the `[<NoEquality>]` and `[<NoComparison>]` attributes to suppress the automatic generation of interfaces.</span></span> <span data-ttu-id="ddddd-361">Außerdem verwenden Sie änderbare Datensatzfelder in Vanille .NET APIs als diese macht ein öffentliches Feld.</span><span class="sxs-lookup"><span data-stu-id="ddddd-361">Also avoid using mutable record fields in vanilla .NET APIs as these exposes a public field.</span></span> <span data-ttu-id="ddddd-362">Berücksichtigen Sie immer, ob es sich bei eine Klasse eine flexiblere Option für die zukünftige Entwicklung der API bieten würde.</span><span class="sxs-lookup"><span data-stu-id="ddddd-362">Always consider whether a class would provide a more flexible option for future evolution of the API.</span></span>

<span data-ttu-id="ddddd-363">Beispielsweise die folgenden F# Code verfügbar macht, die öffentliche API zu einem C# Consumer:</span><span class="sxs-lookup"><span data-stu-id="ddddd-363">For example, the following F# code exposes the public API to a C# consumer:</span></span>

<span data-ttu-id="ddddd-364">F#:</span><span class="sxs-lookup"><span data-stu-id="ddddd-364">F#:</span></span>

```fsharp
[<NoEquality; NoComparison>]
type MyRecord =
    { FirstThing: int
        SecondThing: string }
```

<span data-ttu-id="ddddd-365">C#:</span><span class="sxs-lookup"><span data-stu-id="ddddd-365">C#:</span></span>

```csharp
public sealed class MyRecord
{
    public MyRecord(int firstThing, string secondThing);
    public int FirstThing { get; }
    public string SecondThing { get; }
}
```

#### <a name="hide-the-representation-of-f-union-types-in-vanilla-net-apis"></a><span data-ttu-id="ddddd-366">Blenden Sie die Darstellung der F# union-Typen in Vanille .NET APIs</span><span class="sxs-lookup"><span data-stu-id="ddddd-366">Hide the representation of F# union types in vanilla .NET APIs</span></span>

<span data-ttu-id="ddddd-367">F#-union-Typen nicht dienen meist über komponentenbegrenzungen hinweg, sogar für F#-zu-F#-Programmierung.</span><span class="sxs-lookup"><span data-stu-id="ddddd-367">F# union types are not commonly used across component boundaries, even for F#-to-F# coding.</span></span> <span data-ttu-id="ddddd-368">Sie sind eine ausgezeichnete Implementierung Gerät intern innerhalb der Komponenten und Bibliotheken verwendet.</span><span class="sxs-lookup"><span data-stu-id="ddddd-368">They are an excellent implementation device when used internally within components and libraries.</span></span>

<span data-ttu-id="ddddd-369">Beim Entwerfen eines herkömmlichen .NET API sollten Sie die Darstellung eines union-Typs mit einer privaten Deklaration oder eine Signaturdatei ausblenden.</span><span class="sxs-lookup"><span data-stu-id="ddddd-369">When designing a vanilla .NET API, consider hiding the representation of a union type by using either a private declaration or a signature file.</span></span>

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True
```

<span data-ttu-id="ddddd-370">Sie können auch Typen erweitern, die intern eine union Darstellung mit Membern verwenden, um eine gewünschte bereitzustellen. NET-Facing-API.</span><span class="sxs-lookup"><span data-stu-id="ddddd-370">You may also augment types that use a union representation internally with members to provide a desired .NET-facing API.</span></span>

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

#### <a name="design-gui-and-other-components-using-the-design-patterns-of-the-framework"></a><span data-ttu-id="ddddd-371">Design-GUI und andere Komponenten, die mit den Entwurfsmustern von framework</span><span class="sxs-lookup"><span data-stu-id="ddddd-371">Design GUI and other components using the design patterns of the framework</span></span>

<span data-ttu-id="ddddd-372">Viele verschiedene Frameworks sind in .NET, z. B. WPF, WinForms und ASP.NET verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ddddd-372">There are many different frameworks available within .NET, such as WinForms, WPF, and ASP.NET.</span></span> <span data-ttu-id="ddddd-373">Benennen und Design-Konventionen für die einzelnen sollte verwendet werden, wenn Sie Komponenten für die Verwendung in diesen Frameworks entwerfen.</span><span class="sxs-lookup"><span data-stu-id="ddddd-373">Naming and design conventions for each should be used if you are designing components for use in these frameworks.</span></span> <span data-ttu-id="ddddd-374">Übernehmen Sie für WPF-Programmierung, z. B. WPF-Entwurfsmuster für die Klassen, die Sie entwerfen.</span><span class="sxs-lookup"><span data-stu-id="ddddd-374">For example, for WPF programming, adopt WPF design patterns for the classes you are designing.</span></span> <span data-ttu-id="ddddd-375">Verwenden Sie für die Modelle in der Programmierung der Benutzeroberfläche, Entwurfsmuster, wie Ereignisse und benachrichtigungsbasierte Auflistungen, z. B. unter <xref:System.Collections.ObjectModel>.</span><span class="sxs-lookup"><span data-stu-id="ddddd-375">For models in user interface programming, use design patterns such as events and notification-based collections such as those found in <xref:System.Collections.ObjectModel>.</span></span>

### <a name="object-and-member-design-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="ddddd-376">-Objekt und Element-Entwurf (für die Bibliotheken für die Verwendung von anderen .NET-Sprachen)</span><span class="sxs-lookup"><span data-stu-id="ddddd-376">Object and Member design (for libraries for use from other .NET Languages)</span></span>

#### <a name="use-the-clievent-attribute-to-expose-net-events"></a><span data-ttu-id="ddddd-377">Verwenden Sie das CLIEvent-Attribut, Ereignisse verfügbar zu machen</span><span class="sxs-lookup"><span data-stu-id="ddddd-377">Use the CLIEvent attribute to expose .NET events</span></span>

<span data-ttu-id="ddddd-378">Erstellen einer `DelegateEvent` mit einer bestimmten .NET Delegattyp, der ein Objekt akzeptiert und `EventArgs` (anstelle einer `Event`, die gerade verwendet die `FSharpHandler` standardmäßig Typ), damit die Ereignisse in der vertrauten Verfahren können Sie anderen veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="ddddd-378">Construct a `DelegateEvent` with a specific .NET delegate type that takes an object and `EventArgs` (rather than an `Event`, which just uses the `FSharpHandler` type by default) so that the events are published in the familiar way to other .NET languages.</span></span>

```fsharp
type MyBadType() =
    let myEv = new Event<int>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish

type MyEventArgs(x: int) =
    inherit System.EventArgs()
    member this.X = x

    /// A type in a component designed for use from other .NET languages
type MyGoodType() =
    let myEv = new DelegateEvent<EventHandler<MyEventArgs>>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish
```

#### <a name="expose-asynchronous-operations-as-methods-which-return-net-tasks"></a><span data-ttu-id="ddddd-379">Bereitstellen Sie asynchroner Vorgänge als Methoden, die .NET Aufgaben zurückgeben</span><span class="sxs-lookup"><span data-stu-id="ddddd-379">Expose asynchronous operations as methods which return .NET tasks</span></span>

<span data-ttu-id="ddddd-380">Aufgaben sind in .NET verwendet, um aktive asynchrone Berechnungen darzustellen.</span><span class="sxs-lookup"><span data-stu-id="ddddd-380">Tasks are used in .NET to represent active asynchronous computations.</span></span> <span data-ttu-id="ddddd-381">Aufgaben sind im Allgemeinen weniger als F# kompositionell `Async<T>` Objekte, da sie die Aufgaben "bereits ausgeführt" darstellen und nicht zusammengesetzte zusammen, es gibt Möglichkeiten, parallele Kombination ausführen oder das Ausblenden der Weitergabe von Abbruch signalisiert und andere, kontextbezogene Parameter.</span><span class="sxs-lookup"><span data-stu-id="ddddd-381">Tasks are in general less compositional than F# `Async<T>` objects, since they represent “already executing” tasks and can’t be composed together in ways that perform parallel composition, or which hide the propagation of cancellation signals and other contextual parameters.</span></span>

<span data-ttu-id="ddddd-382">Dennoch sind Methoden, die Aufgaben zurückgeben jedoch die standarddarstellung der asynchronen Programmierung in .NET.</span><span class="sxs-lookup"><span data-stu-id="ddddd-382">However, despite this, methods which return Tasks are the standard representation of asynchronous programming on .NET.</span></span>

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =

    let compute (x: int): Async<int> = async { ... }

    member this.ComputeAsync(x) = compute x |> Async.StartAsTask
```

<span data-ttu-id="ddddd-383">Sie werden häufig auch als explizites Abbruchtoken akzeptieren möchten:</span><span class="sxs-lookup"><span data-stu-id="ddddd-383">You will frequently also want to accept an explicit cancellation token:</span></span>

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =
    let compute(x: int): Async<int> = async { ... }
    member this.ComputeAsTask(x, cancellationToken) = Async.StartAsTask(compute x, cancellationToken)
```

#### <a name="use-net-delegate-types-instead-of-f-function-types"></a><span data-ttu-id="ddddd-384">Verwenden Sie .NET Delegattypen anstelle von F#-Typen-Funktion</span><span class="sxs-lookup"><span data-stu-id="ddddd-384">Use .NET delegate types instead of F# function types</span></span>

<span data-ttu-id="ddddd-385">Hier "F# Funktionstypen" bedeutet, dass "Pfeil"-Typen wie `int -> int`.</span><span class="sxs-lookup"><span data-stu-id="ddddd-385">Here “F# function types” mean “arrow” types like `int -> int`.</span></span>

<span data-ttu-id="ddddd-386">Statt dies:</span><span class="sxs-lookup"><span data-stu-id="ddddd-386">Instead of this:</span></span>

```fsharp
member this.Transform(f: int->int) =
    ...
```

<span data-ttu-id="ddddd-387">Vorgehensweise:</span><span class="sxs-lookup"><span data-stu-id="ddddd-387">Do this:</span></span>

```fsharp
member this.Transform(f: Func<int,int>) =
    ...
```

<span data-ttu-id="ddddd-388">Die F# Funktionstyp wird als `class FSharpFunc<T,U>` in andere .NET-Sprachen und eignet sich weniger für die Sprachfeatures und Tools, die Delegattypen zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="ddddd-388">The F# function type appears as `class FSharpFunc<T,U>` to other .NET languages, and is less suitable for language features and tooling that understand delegate types.</span></span> <span data-ttu-id="ddddd-389">Beim Erstellen einer höherer Ordnung-Methode, die für .NET Framework 3.5 oder höher, die `System.Func` und `System.Action` Delegaten sind die richtigen APIs veröffentlichen möchten, .NET Entwickler diese APIs in einer Weise reibungsarme verwenden können.</span><span class="sxs-lookup"><span data-stu-id="ddddd-389">When authoring a higher-order method targeting .NET Framework 3.5 or higher, the `System.Func` and `System.Action` delegates are the right APIs to publish to enable .NET developers to consume these APIs in a low-friction manner.</span></span> <span data-ttu-id="ddddd-390">(Bei .NET Framework 2.0 abzielen, sind die vom System definierte Delegattypen mehr beschränkt, erwägen Sie die Verwendung von vordefinierten Delegattypen wie z. B. `System.Converter<T,U>` oder einen bestimmten Delegattyp definieren.)</span><span class="sxs-lookup"><span data-stu-id="ddddd-390">(When targeting .NET Framework 2.0, the system-defined delegate types are more limited; consider using predefined delegate types such as `System.Converter<T,U>` or defining a specific delegate type.)</span></span>

<span data-ttu-id="ddddd-391">Auf der Seite kippen .NET Delegaten sind nicht für F# natürliche-Bibliotheken für (finden Sie im nächsten Abschnitt F#-Bibliotheken für).</span><span class="sxs-lookup"><span data-stu-id="ddddd-391">On the flip side, .NET delegates are not natural for F#-facing libraries (see the next Section on F#-facing libraries).</span></span> <span data-ttu-id="ddddd-392">Daher ist eine verbreitete Implementierungsstrategie, bei der Entwicklung von höherer Ordnung-Methoden für einfache Bibliotheken für .NET alle die Implementierung mithilfe von F#-Funktion-Typen zu erstellen, und erstellen Sie die öffentliche API, die mithilfe von Delegaten als thin Fassade auf die tatsächliche F# -Implementierung.</span><span class="sxs-lookup"><span data-stu-id="ddddd-392">As a result, a common implementation strategy when developing higher-order methods for vanilla .NET libraries is to author all the implementation using F# function types, and then create the public API using delegates as a thin façade atop the actual F# implementation.</span></span>

#### <a name="use-the-trygetvalue-pattern-instead-of-returning-f-option-values-and-prefer-method-overloading-to-taking-f-option-values-as-arguments"></a><span data-ttu-id="ddddd-393">Verwenden Sie das TryGetValue-Muster, anstatt die Rückgabe von Werten für F#-Option aus, und es vorziehen Sie, Überladen von Methoden mit dem Erstellen von F#-Werte als Argumente</span><span class="sxs-lookup"><span data-stu-id="ddddd-393">Use the TryGetValue pattern instead of returning F# option values, and prefer method overloading to taking F# option values as arguments</span></span>

<span data-ttu-id="ddddd-394">Allgemeine Muster für die Verwendung für die F# Optionstyp APIs sind besser in Vanille implementiert .NET APIs, die mit standardmäßigen .NET entwerfen Techniken.</span><span class="sxs-lookup"><span data-stu-id="ddddd-394">Common patterns of use for the F# option type in APIs are better implemented in vanilla .NET APIs using standard .NET design techniques.</span></span> <span data-ttu-id="ddddd-395">Anstatt einen F#-Wert, erwägen Sie den Rückgabetyp "bool" sowie einen Out-Parameter wie das Muster "TryGetValue".</span><span class="sxs-lookup"><span data-stu-id="ddddd-395">Instead of returning an F# option value, consider using the bool return type plus an out parameter as in the "TryGetValue" pattern.</span></span> <span data-ttu-id="ddddd-396">Und anstelle der Instanz F# Optionswerte als Parameter, Überladen von Operatoren oder optionalen Argumenten in Betracht.</span><span class="sxs-lookup"><span data-stu-id="ddddd-396">And instead of taking F# option values as parameters, consider using method overloading or optional arguments.</span></span>

```fsharp
member this.ReturnOption() = Some 3

member this.ReturnBoolAndOut(outVal: byref<int>) =
    outVal <- 3
    true

member this.ParamOption(x: int, y: int option) =
    match y with
    | Some y2 -> x + y2
    | None -> x

member this.ParamOverload(x: int) = x

member this.ParamOverload(x: int, y: int) = x + y
```

#### <a name="use-the-net-collection-interface-types-ienumerablet-and-idictionarykeyvalue-for-parameters-and-return-values"></a><span data-ttu-id="ddddd-397">Verwenden Sie die .NET sammlungsschnittstelle Typen "IEnumerable"\<T\> und IDictionary\<Schlüssel, Wert\> für Parameter und Rückgabewerte</span><span class="sxs-lookup"><span data-stu-id="ddddd-397">Use the .NET collection interface types IEnumerable\<T\> and IDictionary\<Key,Value\> for parameters and return values</span></span>

<span data-ttu-id="ddddd-398">Vermeiden Sie die Verwendung der konkreten Auflistungstypen, z. B. .NET Arrays `T[]`, F#-Typen `list<T>`, `Map<Key,Value>` und `Set<T>`, und .NET konkreten Auflistungstypen wie z. B. `Dictionary<Key,Value>`.</span><span class="sxs-lookup"><span data-stu-id="ddddd-398">Avoid the use of concrete collection types such as .NET arrays `T[]`, F# types `list<T>`, `Map<Key,Value>` and `Set<T>`, and .NET concrete collection types such as `Dictionary<Key,Value>`.</span></span> <span data-ttu-id="ddddd-399">Die .NET Klassenbibliotheken – Entwurfsrichtlinien haben gute Ratschläge in Bezug auf die unterschiedlichen Auflistungstypen, z. B. verwenden `IEnumerable<T>`.</span><span class="sxs-lookup"><span data-stu-id="ddddd-399">The .NET Library Design Guidelines have good advice regarding when to use various collection types like `IEnumerable<T>`.</span></span> <span data-ttu-id="ddddd-400">Einige verwenden von Arrays (`T[]`) in einigen Fällen aus Gründen, die Leistung akzeptabel ist.</span><span class="sxs-lookup"><span data-stu-id="ddddd-400">Some use of arrays (`T[]`) is acceptable in some circumstances, on performance grounds.</span></span> <span data-ttu-id="ddddd-401">Beachten Sie insbesondere, dass `seq<T>` ist nur für die F# alias für `IEnumerable<T>`, und so Seq ist häufig einen geeigneten Typ für eine Vanille .NET API.</span><span class="sxs-lookup"><span data-stu-id="ddddd-401">Note especially that `seq<T>` is just the F# alias for `IEnumerable<T>`, and thus seq is often an appropriate type for a vanilla .NET API.</span></span>

<span data-ttu-id="ddddd-402">Anstelle von F#-Listen:</span><span class="sxs-lookup"><span data-stu-id="ddddd-402">Instead of F# lists:</span></span>

```fsharp
member this.PrintNames(names: string list) =
    ...
```

<span data-ttu-id="ddddd-403">Verwendung F# Sequenzen:</span><span class="sxs-lookup"><span data-stu-id="ddddd-403">Use F# sequences:</span></span>

```fsharp
member this.PrintNames(names: seq<string>) =
    ...
```

#### <a name="use-the-unit-type-as-the-only-input-type-of-a-method-to-define-a-zero-argument-method-or-as-the-only-return-type-to-define-a-void-returning-method"></a><span data-ttu-id="ddddd-404">Verwenden Sie den Typ als einzige Eingabetyp einer Methode so definieren Sie die Methode eine NULL-Argument oder als den einzigen Rückgabetyp auf eine "void" zurückgebende Methode zu definieren</span><span class="sxs-lookup"><span data-stu-id="ddddd-404">Use the unit type as the only input type of a method to define a zero-argument method, or as the only return type to define a void-returning method</span></span>

<span data-ttu-id="ddddd-405">Zu vermeiden Sie anderen Verwendungsmöglichkeiten der den Typ.</span><span class="sxs-lookup"><span data-stu-id="ddddd-405">Avoid other uses of the unit type.</span></span> <span data-ttu-id="ddddd-406">Dies sind gute:</span><span class="sxs-lookup"><span data-stu-id="ddddd-406">These are good:</span></span>

```fsharp
✔ member this.NoArguments() = 3

✔ member this.ReturnVoid(x: int) = ()
```

<span data-ttu-id="ddddd-407">Das ist nicht gut:</span><span class="sxs-lookup"><span data-stu-id="ddddd-407">This is bad:</span></span>

```fsharp
member this.WrongUnit( x: unit, z: int) = ((), ())
```

#### <a name="check-for-null-values-on-vanilla-net-api-boundaries"></a><span data-ttu-id="ddddd-408">Überprüfen Sie null-Werte auf einfaches .NET API-Grenzen</span><span class="sxs-lookup"><span data-stu-id="ddddd-408">Check for null values on vanilla .NET API boundaries</span></span>

<span data-ttu-id="ddddd-409">F#Implementierungscode tendenziell weniger null-Werte, aufgrund von unveränderlichen Entwurfsmustern und Einschränkungen bei der Verwendung von null-Literale für F# Typen.</span><span class="sxs-lookup"><span data-stu-id="ddddd-409">F# implementation code tends to have fewer null values, due to immutable design patterns and restrictions on use of null literals for F# types.</span></span> <span data-ttu-id="ddddd-410">Anderen verwenden häufig viel häufiger null als Wert.</span><span class="sxs-lookup"><span data-stu-id="ddddd-410">Other .NET languages often use null as a value much more frequently.</span></span> <span data-ttu-id="ddddd-411">Aus diesem Grund F# Code, der ein herkömmlichen .NET API verfügbar gemacht wird Überprüfen der Parameter für Null-Zeichen an der API-Grenze, und verhindern, dass diese Werte fließen tiefer in die F# Implementierungscode.</span><span class="sxs-lookup"><span data-stu-id="ddddd-411">Because of this, F# code that is exposing a vanilla .NET API should check parameters for null at the API boundary, and prevent these values from flowing deeper into the F# implementation code.</span></span> <span data-ttu-id="ddddd-412">Die `isNull` Funktion oder einen Musterabgleich für die `null` Muster kann verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ddddd-412">The `isNull` function or pattern matching on the `null` pattern can be used.</span></span>

```fsharp
let checkNonNull argName (arg: obj) =
    match arg with
    | null -> nullArg argName
    | _ -> ()

let checkNonNull` argName (arg: obj) =
    if isNull arg then nullArg argName
    else ()
```

#### <a name="avoid-using-tuples-as-return-values"></a><span data-ttu-id="ddddd-413">Vermeiden Sie die Verwendung von Tupeln als Rückgabewerte</span><span class="sxs-lookup"><span data-stu-id="ddddd-413">Avoid using tuples as return values</span></span>

<span data-ttu-id="ddddd-414">Bevorzugen Sie stattdessen die Rückgabe eines benannten Typs, der die aggregierten Daten enthält oder mit dem out-Parameter mehrere Werte zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="ddddd-414">Instead, prefer returning a named type holding the aggregate data, or using out parameters to return multiple values.</span></span> <span data-ttu-id="ddddd-415">Obwohl Tupel und Strukturieren von Tupeln an, die in .NET vorhanden sind bieten (einschließlich der C#-sprachunterstützung für Tupel, die Struktur), sie meist nicht die ideale und erwartete-API für .NET-Entwickler.</span><span class="sxs-lookup"><span data-stu-id="ddddd-415">Although tuples and struct tuples exist in .NET (including C# language support for struct tuples), they will most often not provide the ideal and expected API for .NET developers.</span></span>

#### <a name="avoid-the-use-of-currying-of-parameters"></a><span data-ttu-id="ddddd-416">Vermeiden Sie die Verwendung von currying von Parametern</span><span class="sxs-lookup"><span data-stu-id="ddddd-416">Avoid the use of currying of parameters</span></span>

<span data-ttu-id="ddddd-417">Verwenden Sie stattdessen .NET Aufrufkonventionen `Method(arg1,arg2,…,argN)`.</span><span class="sxs-lookup"><span data-stu-id="ddddd-417">Instead, use .NET calling conventions `Method(arg1,arg2,…,argN)`.</span></span>

```fsharp
member this.TupledArguments(str, num) = String.replicate num str
```

<span data-ttu-id="ddddd-418">Tipp: Wenn Sie Bibliotheken für die Verwendung von beliebigen entwerfen, dann gibt es keinen Ersatz für die tatsächlich einige experimentelle C# und Visual Basic-Programmierung, um sicherzustellen, dass Ihre Bibliotheken "Verhalten rechts" aus, aus dieser Sprachen.</span><span class="sxs-lookup"><span data-stu-id="ddddd-418">Tip: If you’re designing libraries for use from any .NET language, then there’s no substitute for actually doing some experimental C# and Visual Basic programming to ensure that your libraries "feel right" from these languages.</span></span> <span data-ttu-id="ddddd-419">Sie können auch Tools wie z. B. .NET Reflector und den Visual Studio-Objektkatalog verwenden, um sicherzustellen, dass die Bibliotheken und ihrer Dokumentation, wie Entwickler erwartet angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ddddd-419">You can also use tools such as .NET Reflector and the Visual Studio Object Browser to ensure that libraries and their documentation appear as expected to developers.</span></span>

## <a name="appendix"></a><span data-ttu-id="ddddd-420">Anhang</span><span class="sxs-lookup"><span data-stu-id="ddddd-420">Appendix</span></span>

### <a name="end-to-end-example-of-designing-f-code-for-use-by-other-net-languages"></a><span data-ttu-id="ddddd-421">End-to-End-Beispiel für das Entwerfen von F#-Code für die Verwendung von anderen .NET-Programmiersprachen</span><span class="sxs-lookup"><span data-stu-id="ddddd-421">End-to-end example of designing F# code for use by other .NET languages</span></span>

<span data-ttu-id="ddddd-422">Beachten Sie die folgende Klasse:</span><span class="sxs-lookup"><span data-stu-id="ddddd-422">Consider the following class:</span></span>

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

<span data-ttu-id="ddddd-423">Der abgeleitete F# Typ diese Klasse ist wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ddddd-423">The inferred F# type of this class is as follows:</span></span>

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

<span data-ttu-id="ddddd-424">Sehen wir uns an, wie dies F# Typ angezeigt wird, um ein Programmierer, die mithilfe einer anderen .NET-Sprache.</span><span class="sxs-lookup"><span data-stu-id="ddddd-424">Let’s take a look at how this F# type appears to a programmer using another .NET language.</span></span> <span data-ttu-id="ddddd-425">Beispielsweise ist die ungefähre c# "Signatur" wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ddddd-425">For example, the approximate C# “signature” is as follows:</span></span>

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

<span data-ttu-id="ddddd-426">Es gibt einige wichtige Punkte zu beachten Sie, dass Informationen F# stellt hier erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ddddd-426">There are some important points to notice about how F# represents constructs here.</span></span> <span data-ttu-id="ddddd-427">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ddddd-427">For example:</span></span>

* <span data-ttu-id="ddddd-428">Metadaten wie z. B. den Namen des Funktionsarguments wurde beibehalten.</span><span class="sxs-lookup"><span data-stu-id="ddddd-428">Metadata such as argument names has been preserved.</span></span>

* <span data-ttu-id="ddddd-429">F#Methoden, die zwei werden Argumente C# Methoden, die zwei Argumente akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="ddddd-429">F# methods that take two arguments become C# methods that take two arguments.</span></span>

* <span data-ttu-id="ddddd-430">Funktionen und Listen werden Verweise auf die entsprechenden Typen in der F# Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="ddddd-430">Functions and lists become references to corresponding types in the F# library.</span></span>

<span data-ttu-id="ddddd-431">Der folgende Code zeigt, wie Sie passen Sie diesen Code, um Folgendes zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="ddddd-431">The following code shows how to adjust this code to take these things into account.</span></span>

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

<span data-ttu-id="ddddd-432">Der abgeleitete F# Typ des Codes lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ddddd-432">The inferred F# type of the code is as follows:</span></span>

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

<span data-ttu-id="ddddd-433">Die C#-Signatur sieht jetzt wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="ddddd-433">The C# signature is now as follows:</span></span>

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

<span data-ttu-id="ddddd-434">Die Korrekturen vorgenommen, um dieser Typ für die Verwendung vorzubereiten, als Teil einer einfachen .NET Bibliothek sind wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ddddd-434">The fixes made to prepare this type for use as part of a vanilla .NET library are as follows:</span></span>

* <span data-ttu-id="ddddd-435">Mehrere Namen angepasst: `Point1`, `n`, `l`, und `f` wurde `RadialPoint`, `count`, `factor`, und `transform`bzw.</span><span class="sxs-lookup"><span data-stu-id="ddddd-435">Adjusted several names: `Point1`, `n`, `l`, and `f` became `RadialPoint`, `count`, `factor`, and `transform`, respectively.</span></span>

* <span data-ttu-id="ddddd-436">Verwendet einen Rückgabetyp von `seq<RadialPoint>` anstelle von `RadialPoint list` durch Ändern der Konstruktion für eine Liste mit `[ ... ]` in eine Sequenz Konstruktion `IEnumerable<RadialPoint>`.</span><span class="sxs-lookup"><span data-stu-id="ddddd-436">Used a return type of `seq<RadialPoint>` instead of `RadialPoint list` by changing a list construction using `[ ... ]` to a sequence construction using `IEnumerable<RadialPoint>`.</span></span>

* <span data-ttu-id="ddddd-437">Verwendet den .NET Delegattyp `System.Func` anstelle eines F#-Funktionstyps.</span><span class="sxs-lookup"><span data-stu-id="ddddd-437">Used the .NET delegate type `System.Func` instead of an F# function type.</span></span>

<span data-ttu-id="ddddd-438">Dies macht es viel nützlicher in C#-Code nutzen.</span><span class="sxs-lookup"><span data-stu-id="ddddd-438">This makes it far nicer to consume in C# code.</span></span>
