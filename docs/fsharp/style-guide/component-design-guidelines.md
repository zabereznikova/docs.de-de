---
title: Entwurfsrichtlinien für eine F#-Komponente
description: 'Erfahren Sie mehr über die Richtlinien zum Schreiben von F #-Komponenten, die von anderen Aufrufern für'
ms.date: 05/14/2018
ms.openlocfilehash: 590bda0660d54ea73c590d31e694f3d499e0fd9f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209135"
---
# <a name="f-component-design-guidelines"></a><span data-ttu-id="0cc9b-103">Entwurfsrichtlinien für eine F#-Komponente</span><span class="sxs-lookup"><span data-stu-id="0cc9b-103">F# component design guidelines</span></span>

<span data-ttu-id="0cc9b-104">Dieses Dokument ist eine Reihe von Richtlinien zum Entwerfen von Komponenten für die f #-Programmierung, die auf den f #-Komponenten Entwurfs Richtlinien, v14, Microsoft Research und einer Version basiert, die ursprünglich von der f #-Software Foundation eingerichtet und verwaltet wurde.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-104">This document is a set of component design guidelines for F# programming, based on the F# Component Design Guidelines, v14, Microsoft Research, and a version that was originally curated and maintained by the F# Software Foundation.</span></span>

<span data-ttu-id="0cc9b-105">Dieses Dokument setzt voraus, dass Sie mit der F #-Programmierung vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-105">This document assumes you are familiar with F# programming.</span></span> <span data-ttu-id="0cc9b-106">Vielen Dank an die F #-Community für Ihre Beiträge und nützliches Feedback zu verschiedenen Versionen dieses Handbuchs.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-106">Many thanks to the F# community for their contributions and helpful feedback on various versions of this guide.</span></span>

## <a name="overview"></a><span data-ttu-id="0cc9b-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="0cc9b-107">Overview</span></span>

<span data-ttu-id="0cc9b-108">In diesem Dokument werden einige der Probleme im Zusammenhang mit dem Entwurf und der Codierung von F #-Komponenten behandelt.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-108">This document looks at some of the issues related to F# component design and coding.</span></span> <span data-ttu-id="0cc9b-109">Eine Komponente kann Folgendes bedeuten:</span><span class="sxs-lookup"><span data-stu-id="0cc9b-109">A component can mean any of the following:</span></span>

* <span data-ttu-id="0cc9b-110">Eine Ebene im F #-Projekt, die über externe Consumer innerhalb dieses Projekts verfügt.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-110">A layer in your F# project that has external consumers within that project.</span></span>
* <span data-ttu-id="0cc9b-111">Eine Bibliothek, die von F #-Code über assemblygrenzen hinweg genutzt werden soll.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-111">A library intended for consumption by F# code across assembly boundaries.</span></span>
* <span data-ttu-id="0cc9b-112">Eine Bibliothek, die von einer beliebigen .NET-Sprache über assemblygrenzen hinweg benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-112">A library intended for consumption by any .NET language across assembly boundaries.</span></span>
* <span data-ttu-id="0cc9b-113">Eine Bibliothek, die über ein Paketrepository (z. b. [nuget](https://nuget.org)) zur Verteilung vorgesehen ist</span><span class="sxs-lookup"><span data-stu-id="0cc9b-113">A library intended for distribution via a package repository, such as [NuGet](https://nuget.org).</span></span>

<span data-ttu-id="0cc9b-114">Die in diesem Artikel beschriebenen Verfahren folgen den [fünf Prinzipien von gutem F #-Code](index.md#five-principles-of-good-f-code)und verwenden daher die funktionale und die Objekt Programmierung entsprechend.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-114">Techniques described in this article follow the [Five principles of good F# code](index.md#five-principles-of-good-f-code), and thus utilize both functional and object programming as appropriate.</span></span>

<span data-ttu-id="0cc9b-115">Unabhängig von der Methodik sind der Komponenten-und Bibliotheks-Designer bei dem Versuch, eine API zu erstellen, die am einfachsten von Entwicklern verwendet werden kann, mit einigen praktischen und prosaischen Problemen konfrontiert.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-115">Regardless of the methodology, the component and library designer faces a number of practical and prosaic issues when trying to craft an API that is most easily usable by developers.</span></span> <span data-ttu-id="0cc9b-116">Die [Entwurfs Richtlinien für die Entwurfs Richtlinien von .NET-Bibliotheken](../../standard/design-guidelines/index.md) führen Sie zur Erstellung eines konsistenten Satzes von APIs, die für Sie von Nutzen sind.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-116">Conscientious application of the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md) will steer you towards creating a consistent set of APIs that are pleasant to consume.</span></span>

## <a name="general-guidelines"></a><span data-ttu-id="0cc9b-117">Allgemeine Richtlinien</span><span class="sxs-lookup"><span data-stu-id="0cc9b-117">General guidelines</span></span>

<span data-ttu-id="0cc9b-118">Es gibt ein paar universelle Richtlinien, die für F #-Bibliotheken gelten, unabhängig von der Zielgruppe für die Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-118">There are a few universal guidelines that apply to F# libraries, regardless of the intended audience for the library.</span></span>

### <a name="learn-the-net-library-design-guidelines"></a><span data-ttu-id="0cc9b-119">Erlernen der Entwurfs Richtlinien für .NET-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="0cc9b-119">Learn the .NET Library Design Guidelines</span></span>

<span data-ttu-id="0cc9b-120">Unabhängig davon, welche Art von F #-Codierung Sie durchgeführt haben, ist es von Vorteil, dass Sie über Kenntnisse der [Entwurfs Richtlinien für .NET-Bibliotheken](../../standard/design-guidelines/index.md)verfügen.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-120">Regardless of the kind of F# coding you are doing, it is valuable to have a working knowledge of the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md).</span></span> <span data-ttu-id="0cc9b-121">Die meisten anderen F #-und .NET-Programmierer sind mit diesen Richtlinien vertraut und erwarten, dass .NET-Code Ihnen entspricht.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-121">Most other F# and .NET programmers will be familiar with these guidelines, and expect .NET code to conform to them.</span></span>

<span data-ttu-id="0cc9b-122">Die Entwurfs Richtlinien für .NET-Bibliotheken bieten allgemeine Anleitungen für die Benennung, das Entwerfen von Klassen und Schnittstellen, das Entwerfen von Elementen (Eigenschaften, Methoden, Ereignisse usw.) und vieles mehr. Sie sind ein nützlicher erster Bezugspunkt für eine Vielzahl von Entwurfs Anleitungen.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-122">The .NET Library Design Guidelines provide general guidance regarding naming, designing classes and interfaces, member design (properties, methods, events, etc.) and more, and are a useful first point of reference for a variety of design guidance.</span></span>

### <a name="add-xml-documentation-comments-to-your-code"></a><span data-ttu-id="0cc9b-123">Hinzufügen von XML-Dokumentations Kommentaren zum Code</span><span class="sxs-lookup"><span data-stu-id="0cc9b-123">Add XML documentation comments to your code</span></span>

<span data-ttu-id="0cc9b-124">Die XML-Dokumentation zu öffentlichen APIs stellt sicher, dass Benutzer bei der Verwendung dieser Typen und Member großartige IntelliSense-und QuickInfo-Informationen erhalten und die Erstellung von Dokumentationsdateien für die Bibliothek aktivieren können.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-124">XML documentation on public APIs ensures that users can get great Intellisense and Quickinfo when using these types and members, and enable building documentation files for the library.</span></span> <span data-ttu-id="0cc9b-125">Informationen zu verschiedenen XML-Tags, die für zusätzliches Markup in xmlDoc--Kommentaren verwendet werden können, finden Sie in der [XML-Dokumentation](../language-reference/xml-documentation.md) .</span><span class="sxs-lookup"><span data-stu-id="0cc9b-125">See the [XML Documentation](../language-reference/xml-documentation.md) about various xml tags that can be used for additional markup within xmldoc comments.</span></span>

```fsharp
/// A class for representing (x,y) coordinates
type Point =

    /// Computes the distance between this point and another
    member DistanceTo: otherPoint:Point -> float
```

<span data-ttu-id="0cc9b-126">Sie können entweder die Kurzform-XML-Kommentare ( `/// comment` ) oder XML-Standard Kommentare ( `///<summary>comment</summary>` ) verwenden.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-126">You can use either the short form XML comments (`/// comment`), or standard XML comments (`///<summary>comment</summary>`).</span></span>

### <a name="consider-using-explicit-signature-files-fsi-for-stable-library-and-component-apis"></a><span data-ttu-id="0cc9b-127">Verwenden Sie explizite Signatur Dateien (FSI) für stabile Bibliothek-und Komponenten-APIs.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-127">Consider using explicit signature files (.fsi) for stable library and component APIs</span></span>

<span data-ttu-id="0cc9b-128">Die Verwendung von expliziten Signaturen in einer F #-Bibliothek bietet eine kurze Zusammenfassung der öffentlichen API, mit der Sie sicherstellen können, dass Sie die vollständige öffentliche Oberfläche der Bibliothek kennen, und eine saubere Trennung zwischen der öffentlichen Dokumentation und den internen Implementierungsdetails bietet.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-128">Using explicit signatures files in an F# library provides a succinct summary of public API, which helps to ensure that you know the full public surface of your library, and provides a clean separation between public documentation and internal implementation details.</span></span> <span data-ttu-id="0cc9b-129">Signatur Dateien fügen eine Reibung zum Ändern der öffentlichen API hinzu, indem Änderungen an der Implementierungs-und der Signatur Datei vorgenommen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-129">Signature files add friction to changing the public API, by requiring changes to be made in both the implementation and signature files.</span></span> <span data-ttu-id="0cc9b-130">Folglich sollten Signatur Dateien in der Regel nur dann eingefügt werden, wenn eine API gefestigt wird und sich nicht mehr in erheblichem Umfang ändert.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-130">As a result, signature files should typically only be introduced when an API has become solidified and is no longer expected to change significantly.</span></span>

### <a name="always-follow-best-practices-for-using-strings-in-net"></a><span data-ttu-id="0cc9b-131">Befolgen Sie stets die bewährten Methoden für die Verwendung von Zeichen folgen in .net</span><span class="sxs-lookup"><span data-stu-id="0cc9b-131">Always follow best practices for using strings in .NET</span></span>

<span data-ttu-id="0cc9b-132">Befolgen Sie die [bewährten Methoden zum Verwenden von Zeichen folgen in .net](../../standard/base-types/best-practices-strings.md) -Anleitungen.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-132">Follow [Best Practices for Using Strings in .NET](../../standard/base-types/best-practices-strings.md) guidance.</span></span> <span data-ttu-id="0cc9b-133">Insbesondere ist die *Kultur Absicht* beim Konvertieren und Vergleichen von Zeichen folgen immer explizit.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-133">In particular, always explicitly state *cultural intent* in the conversion and comparison of strings (where applicable).</span></span>

## <a name="guidelines-for-f-facing-libraries"></a><span data-ttu-id="0cc9b-134">Richtlinien für Bibliotheken mit F #</span><span class="sxs-lookup"><span data-stu-id="0cc9b-134">Guidelines for F#-facing libraries</span></span>

<span data-ttu-id="0cc9b-135">In diesem Abschnitt finden Sie Empfehlungen für die Entwicklung von öffentlichen F-Bibliotheken. Das heißt, Bibliotheken, die öffentliche APIs verfügbar machen, die von F #-Entwicklern verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-135">This section presents recommendations for developing public F#-facing libraries; that is, libraries exposing public APIs that are intended to be consumed by F# developers.</span></span> <span data-ttu-id="0cc9b-136">Es gibt eine Reihe von Bibliotheks Entwurfs Empfehlungen, die speziell für F # gelten.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-136">There are a variety of library-design recommendations applicable specifically to F#.</span></span> <span data-ttu-id="0cc9b-137">Wenn keine spezifischen Empfehlungen befolgt werden, sind die Entwurfs Richtlinien für .NET-Bibliotheken die Ausweich Anleitung.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-137">In the absence of the specific recommendations that follow, the .NET Library Design Guidelines are the fallback guidance.</span></span>

### <a name="naming-conventions"></a><span data-ttu-id="0cc9b-138">Benennungskonventionen</span><span class="sxs-lookup"><span data-stu-id="0cc9b-138">Naming conventions</span></span>

#### <a name="use-net-naming-and-capitalization-conventions"></a><span data-ttu-id="0cc9b-139">.Net-Benennungs-und-groß Schreibung</span><span class="sxs-lookup"><span data-stu-id="0cc9b-139">Use .NET naming and capitalization conventions</span></span>

<span data-ttu-id="0cc9b-140">In der folgenden Tabelle sind die .net-Benennungs-und-groß Schreibung</span><span class="sxs-lookup"><span data-stu-id="0cc9b-140">The following table follows .NET naming and capitalization conventions.</span></span> <span data-ttu-id="0cc9b-141">Es gibt kleine Ergänzungen, die auch F #-Konstrukte enthalten.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-141">There are small additions to also include F# constructs.</span></span>

| <span data-ttu-id="0cc9b-142">Konstrukt</span><span class="sxs-lookup"><span data-stu-id="0cc9b-142">Construct</span></span> | <span data-ttu-id="0cc9b-143">Fall</span><span class="sxs-lookup"><span data-stu-id="0cc9b-143">Case</span></span> | <span data-ttu-id="0cc9b-144">Teil</span><span class="sxs-lookup"><span data-stu-id="0cc9b-144">Part</span></span> | <span data-ttu-id="0cc9b-145">Beispiele</span><span class="sxs-lookup"><span data-stu-id="0cc9b-145">Examples</span></span> | <span data-ttu-id="0cc9b-146">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0cc9b-146">Notes</span></span> |
|-----------|------|------|----------|-------|
| <span data-ttu-id="0cc9b-147">Konkrete Typen</span><span class="sxs-lookup"><span data-stu-id="0cc9b-147">Concrete types</span></span> | <span data-ttu-id="0cc9b-148">PascalCase</span><span class="sxs-lookup"><span data-stu-id="0cc9b-148">PascalCase</span></span> | <span data-ttu-id="0cc9b-149">Substantiv/Adjektiv</span><span class="sxs-lookup"><span data-stu-id="0cc9b-149">Noun/ adjective</span></span> | <span data-ttu-id="0cc9b-150">List, Double, Complex</span><span class="sxs-lookup"><span data-stu-id="0cc9b-150">List, Double, Complex</span></span> | <span data-ttu-id="0cc9b-151">Konkrete Typen sind Strukturen, Klassen, Enumerationen, Delegaten, Datensätze und Unions.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-151">Concrete types are structs, classes, enumerations, delegates, records, and unions.</span></span> <span data-ttu-id="0cc9b-152">Obwohl Typnamen in ocaml traditionell klein geschrieben werden, hat F # das .net-Benennungs Schema für-Typen übernommen.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-152">Though type names are traditionally lowercase in OCaml, F# has adopted the .NET naming scheme for types.</span></span>
| <span data-ttu-id="0cc9b-153">DLLs</span><span class="sxs-lookup"><span data-stu-id="0cc9b-153">DLLs</span></span>           | <span data-ttu-id="0cc9b-154">PascalCase</span><span class="sxs-lookup"><span data-stu-id="0cc9b-154">PascalCase</span></span> |                 | <span data-ttu-id="0cc9b-155">Fabrikam. Core. dll</span><span class="sxs-lookup"><span data-stu-id="0cc9b-155">Fabrikam.Core.dll</span></span> |  |
| <span data-ttu-id="0cc9b-156">Union-Tags</span><span class="sxs-lookup"><span data-stu-id="0cc9b-156">Union tags</span></span>     | <span data-ttu-id="0cc9b-157">PascalCase</span><span class="sxs-lookup"><span data-stu-id="0cc9b-157">PascalCase</span></span> | <span data-ttu-id="0cc9b-158">Nomen</span><span class="sxs-lookup"><span data-stu-id="0cc9b-158">Noun</span></span> | <span data-ttu-id="0cc9b-159">Einige, hinzufügen, Erfolg</span><span class="sxs-lookup"><span data-stu-id="0cc9b-159">Some, Add, Success</span></span> | <span data-ttu-id="0cc9b-160">Verwenden Sie kein Präfix in öffentlichen APIs.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-160">Do not use a prefix in public APIs.</span></span> <span data-ttu-id="0cc9b-161">Optional ein Präfix verwenden, z. b.`type Teams = TAlpha | TBeta | TDelta.`</span><span class="sxs-lookup"><span data-stu-id="0cc9b-161">Optionally use a prefix when internal, such as `type Teams = TAlpha | TBeta | TDelta.`</span></span> |
| <span data-ttu-id="0cc9b-162">Ereignis</span><span class="sxs-lookup"><span data-stu-id="0cc9b-162">Event</span></span>          | <span data-ttu-id="0cc9b-163">PascalCase</span><span class="sxs-lookup"><span data-stu-id="0cc9b-163">PascalCase</span></span> | <span data-ttu-id="0cc9b-164">Verb</span><span class="sxs-lookup"><span data-stu-id="0cc9b-164">Verb</span></span> | <span data-ttu-id="0cc9b-165">ValueChanged/valuechanging</span><span class="sxs-lookup"><span data-stu-id="0cc9b-165">ValueChanged / ValueChanging</span></span> |  |
| <span data-ttu-id="0cc9b-166">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="0cc9b-166">Exceptions</span></span>     | <span data-ttu-id="0cc9b-167">PascalCase</span><span class="sxs-lookup"><span data-stu-id="0cc9b-167">PascalCase</span></span> |      | <span data-ttu-id="0cc9b-168">WebException</span><span class="sxs-lookup"><span data-stu-id="0cc9b-168">WebException</span></span> | <span data-ttu-id="0cc9b-169">Der Name muss auf "Exception" enden.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-169">Name should end with "Exception".</span></span> |
| <span data-ttu-id="0cc9b-170">Feld</span><span class="sxs-lookup"><span data-stu-id="0cc9b-170">Field</span></span>          | <span data-ttu-id="0cc9b-171">PascalCase</span><span class="sxs-lookup"><span data-stu-id="0cc9b-171">PascalCase</span></span> | <span data-ttu-id="0cc9b-172">Nomen</span><span class="sxs-lookup"><span data-stu-id="0cc9b-172">Noun</span></span> | <span data-ttu-id="0cc9b-173">Currentname</span><span class="sxs-lookup"><span data-stu-id="0cc9b-173">CurrentName</span></span>  | |
| <span data-ttu-id="0cc9b-174">Schnittstellentypen</span><span class="sxs-lookup"><span data-stu-id="0cc9b-174">Interface types</span></span> |  <span data-ttu-id="0cc9b-175">PascalCase</span><span class="sxs-lookup"><span data-stu-id="0cc9b-175">PascalCase</span></span> | <span data-ttu-id="0cc9b-176">Substantiv/Adjektiv</span><span class="sxs-lookup"><span data-stu-id="0cc9b-176">Noun/ adjective</span></span> | <span data-ttu-id="0cc9b-177">IDisposable</span><span class="sxs-lookup"><span data-stu-id="0cc9b-177">IDisposable</span></span> | <span data-ttu-id="0cc9b-178">Der Name sollte mit "I" beginnen.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-178">Name should start with "I".</span></span> |
| <span data-ttu-id="0cc9b-179">Methode</span><span class="sxs-lookup"><span data-stu-id="0cc9b-179">Method</span></span> |  <span data-ttu-id="0cc9b-180">PascalCase</span><span class="sxs-lookup"><span data-stu-id="0cc9b-180">PascalCase</span></span> |  <span data-ttu-id="0cc9b-181">Verb</span><span class="sxs-lookup"><span data-stu-id="0cc9b-181">Verb</span></span> | <span data-ttu-id="0cc9b-182">ToString</span><span class="sxs-lookup"><span data-stu-id="0cc9b-182">ToString</span></span> | |
| <span data-ttu-id="0cc9b-183">Namespace</span><span class="sxs-lookup"><span data-stu-id="0cc9b-183">Namespace</span></span> | <span data-ttu-id="0cc9b-184">PascalCase</span><span class="sxs-lookup"><span data-stu-id="0cc9b-184">PascalCase</span></span> | | <span data-ttu-id="0cc9b-185">Microsoft. FSharp. Core</span><span class="sxs-lookup"><span data-stu-id="0cc9b-185">Microsoft.FSharp.Core</span></span> | <span data-ttu-id="0cc9b-186">Verwenden Sie in der Regel, wenn die `<Organization>.<Technology>[.<Subnamespace>]` Organisation unabhängig von der Organisation ist.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-186">Generally use `<Organization>.<Technology>[.<Subnamespace>]`, though drop the organization if the technology is independent of organization.</span></span> |
| <span data-ttu-id="0cc9b-187">Parameter</span><span class="sxs-lookup"><span data-stu-id="0cc9b-187">Parameters</span></span> | <span data-ttu-id="0cc9b-188">CamelCase</span><span class="sxs-lookup"><span data-stu-id="0cc9b-188">camelCase</span></span> | <span data-ttu-id="0cc9b-189">Nomen</span><span class="sxs-lookup"><span data-stu-id="0cc9b-189">Noun</span></span> |  <span data-ttu-id="0cc9b-190">Typname, Transformation, Bereich</span><span class="sxs-lookup"><span data-stu-id="0cc9b-190">typeName, transform, range</span></span> | |
| <span data-ttu-id="0cc9b-191">Let-Werte (intern)</span><span class="sxs-lookup"><span data-stu-id="0cc9b-191">let values (internal)</span></span> | <span data-ttu-id="0cc9b-192">CamelCase oder PascalCase</span><span class="sxs-lookup"><span data-stu-id="0cc9b-192">camelCase or PascalCase</span></span> | <span data-ttu-id="0cc9b-193">Substantiv/Verb</span><span class="sxs-lookup"><span data-stu-id="0cc9b-193">Noun/ verb</span></span> |  <span data-ttu-id="0cc9b-194">GetValue, myTable</span><span class="sxs-lookup"><span data-stu-id="0cc9b-194">getValue, myTable</span></span> |
| <span data-ttu-id="0cc9b-195">Werte zulassen (extern)</span><span class="sxs-lookup"><span data-stu-id="0cc9b-195">let values (external)</span></span> | <span data-ttu-id="0cc9b-196">CamelCase oder PascalCase</span><span class="sxs-lookup"><span data-stu-id="0cc9b-196">camelCase or PascalCase</span></span> | <span data-ttu-id="0cc9b-197">Substantiv/Verb</span><span class="sxs-lookup"><span data-stu-id="0cc9b-197">Noun/verb</span></span>  | <span data-ttu-id="0cc9b-198">List. map, dates. heute</span><span class="sxs-lookup"><span data-stu-id="0cc9b-198">List.map, Dates.Today</span></span> | <span data-ttu-id="0cc9b-199">Let-gebundene Werte sind häufig öffentlich, wenn Sie herkömmliche funktionale Entwurfsmuster befolgen.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-199">let-bound values are often public when following traditional functional design patterns.</span></span> <span data-ttu-id="0cc9b-200">Verwenden Sie in der Regel jedoch PascalCase, wenn der Bezeichner von anderen .NET-Sprachen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-200">However, generally use PascalCase when the identifier can be used from other .NET languages.</span></span> |
| <span data-ttu-id="0cc9b-201">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="0cc9b-201">Property</span></span>  | <span data-ttu-id="0cc9b-202">PascalCase</span><span class="sxs-lookup"><span data-stu-id="0cc9b-202">PascalCase</span></span>  | <span data-ttu-id="0cc9b-203">Substantiv/Adjektiv</span><span class="sxs-lookup"><span data-stu-id="0cc9b-203">Noun/ adjective</span></span>  | <span data-ttu-id="0cc9b-204">Isendoffile, BackColor</span><span class="sxs-lookup"><span data-stu-id="0cc9b-204">IsEndOfFile, BackColor</span></span>  | <span data-ttu-id="0cc9b-205">Boolesche Eigenschaften werden in der Regel verwendet, und es kann und sein, wie in isendoffile, nicht isnotendoffile.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-205">Boolean properties generally use Is and Can and should be affirmative, as in IsEndOfFile, not IsNotEndOfFile.</span></span>

#### <a name="avoid-abbreviations"></a><span data-ttu-id="0cc9b-206">Abkürzungen vermeiden</span><span class="sxs-lookup"><span data-stu-id="0cc9b-206">Avoid abbreviations</span></span>

<span data-ttu-id="0cc9b-207">Die .NET-Richtlinien verhindern die Verwendung von Abkürzungen (z. b `OnButtonClick` . "Use anstelle `OnBtnClick` ").</span><span class="sxs-lookup"><span data-stu-id="0cc9b-207">The .NET guidelines discourage the use of abbreviations (for example, "use `OnButtonClick` rather than `OnBtnClick`").</span></span> <span data-ttu-id="0cc9b-208">Allgemeine Abkürzungen, wie z `Async` . b. für "asynchron", werden toleriert.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-208">Common abbreviations, such as `Async` for "Asynchronous", are tolerated.</span></span> <span data-ttu-id="0cc9b-209">Diese Richtlinie wird manchmal bei der funktionalen Programmierung ignoriert. Beispielsweise wird von `List.iter` eine Abkürzung für "Iterate" verwendet.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-209">This guideline is sometimes ignored for functional programming; for example, `List.iter` uses an abbreviation for "iterate".</span></span> <span data-ttu-id="0cc9b-210">Aus diesem Grund wird die Verwendung von Abkürzungen tendenziell in größerem Umfang in der f #-zu-F #-Programmierung toleriert, sollte jedoch im Entwurf der öffentlichen Komponente immer noch vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-210">For this reason, using abbreviations tends to be tolerated to a greater degree in F#-to-F# programming, but should still generally be avoided in public component design.</span></span>

#### <a name="avoid-casing-name-collisions"></a><span data-ttu-id="0cc9b-211">Vermeiden von Namenskonflikten in Großbuchstaben</span><span class="sxs-lookup"><span data-stu-id="0cc9b-211">Avoid casing name collisions</span></span>

<span data-ttu-id="0cc9b-212">Die .NET-Richtlinien sagen, dass die Groß-/Kleinschreibung allein nicht verwendet werden kann, um Namenskonflikte eindeutig zu machen, da bei einigen Client Sprachen (z. b. Visual Basic) die Groß-/Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="0cc9b-212">The .NET guidelines say that casing alone cannot be used to disambiguate name collisions, since some client languages (for example, Visual Basic) are case-insensitive.</span></span>

#### <a name="use-acronyms-where-appropriate"></a><span data-ttu-id="0cc9b-213">Verwenden Sie ggf. acronyme.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-213">Use acronyms where appropriate</span></span>

<span data-ttu-id="0cc9b-214">Akronyme, z. b. XML, sind keine Abkürzungen und werden häufig in .NET-Bibliotheken in nicht Großbuchstaben (XML) verwendet.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-214">Acronyms such as XML are not abbreviations and are widely used in .NET libraries in uncapitalized form (Xml).</span></span> <span data-ttu-id="0cc9b-215">Es sollten nur bekannte, allgemein erkannte Akronyme verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-215">Only well-known, widely recognized acronyms should be used.</span></span>

#### <a name="use-pascalcase-for-generic-parameter-names"></a><span data-ttu-id="0cc9b-216">Verwenden von PascalCase für generische Parameternamen</span><span class="sxs-lookup"><span data-stu-id="0cc9b-216">Use PascalCase for generic parameter names</span></span>

<span data-ttu-id="0cc9b-217">Verwenden Sie PascalCase für generische Parameternamen in öffentlichen APIs, z. b. für Bibliotheken mit F #.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-217">Do use PascalCase for generic parameter names in public APIs, including for F#-facing libraries.</span></span> <span data-ttu-id="0cc9b-218">Verwenden Sie insbesondere Namen wie `T` , `U` , `T1` `T2` für beliebige generische Parameter, und wenn bestimmte Namen sinnvoll sind, verwenden Sie für mit F # ausgerichtete Bibliotheken Namen wie,, `Key` `Value` `Arg` (aber nicht beispielsweise `TKey` ).</span><span class="sxs-lookup"><span data-stu-id="0cc9b-218">In particular, use names like `T`, `U`, `T1`, `T2` for arbitrary generic parameters, and when specific names make sense, then for F#-facing libraries use names like `Key`, `Value`, `Arg` (but not for example, `TKey`).</span></span>

#### <a name="use-either-pascalcase-or-camelcase-for-public-functions-and-values-in-f-modules"></a><span data-ttu-id="0cc9b-219">Verwenden Sie entweder PascalCase oder CamelCase für öffentliche Funktionen und Werte in F #-Modulen.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-219">Use either PascalCase or camelCase for public functions and values in F# modules</span></span>

<span data-ttu-id="0cc9b-220">CamelCase wird für öffentliche Funktionen verwendet, die für die Verwendung als nicht qualifiziert konzipiert sind (z. b. `invalidArg` ), und für die "Standard Auflistungs Funktionen" (z. b. List. map).</span><span class="sxs-lookup"><span data-stu-id="0cc9b-220">camelCase is used for public functions that are designed to be used unqualified (for example, `invalidArg`), and for the "standard collection functions" (for example, List.map).</span></span> <span data-ttu-id="0cc9b-221">In beiden Fällen agieren die Funktionsnamen ähnlich wie Schlüsselwörter in der Sprache.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-221">In both these cases, the function names act much like keywords in the language.</span></span>

### <a name="object-type-and-module-design"></a><span data-ttu-id="0cc9b-222">Objekt-, Typ-und Modul Entwurf</span><span class="sxs-lookup"><span data-stu-id="0cc9b-222">Object, Type, and Module design</span></span>

#### <a name="use-namespaces-or-modules-to-contain-your-types-and-modules"></a><span data-ttu-id="0cc9b-223">Verwenden von Namespaces oder Modulen zum enthalten von Typen und Modulen</span><span class="sxs-lookup"><span data-stu-id="0cc9b-223">Use namespaces or modules to contain your types and modules</span></span>

<span data-ttu-id="0cc9b-224">Jede F #-Datei in einer Komponente sollte entweder mit einer Namespace Deklaration oder einer Modul Deklaration beginnen.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-224">Each F# file in a component should begin with either a namespace declaration or a module declaration.</span></span>

```fsharp
namespace Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
     ...

module CommonOperations =
    ...
```

<span data-ttu-id="0cc9b-225">oder</span><span class="sxs-lookup"><span data-stu-id="0cc9b-225">or</span></span>

```fsharp
module Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
    ...

module CommonOperations =
    ...
```

<span data-ttu-id="0cc9b-226">Die Unterschiede zwischen der Verwendung von Modulen und Namespaces zum Organisieren von Code auf oberster Ebene lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="0cc9b-226">The differences between using modules and namespaces to organize code at the top level are as follows:</span></span>

* <span data-ttu-id="0cc9b-227">Namespaces können mehrere Dateien umfassen.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-227">Namespaces can span multiple files</span></span>
* <span data-ttu-id="0cc9b-228">Namespaces dürfen keine F #-Funktionen enthalten, es sei denn, Sie befinden sich in einem inneren Modul</span><span class="sxs-lookup"><span data-stu-id="0cc9b-228">Namespaces cannot contain F# functions unless they are within an inner module</span></span>
* <span data-ttu-id="0cc9b-229">Der Code für ein bestimmtes Modul muss in einer einzelnen Datei enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-229">The code for any given module must be contained within a single file</span></span>
* <span data-ttu-id="0cc9b-230">Module der obersten Ebene können F #-Funktionen enthalten, ohne dass ein internes Modul erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-230">Top-level modules can contain F# functions without the need for an inner module</span></span>

<span data-ttu-id="0cc9b-231">Die Wahl zwischen einem Namespace oder Modul der obersten Ebene wirkt sich auf die kompilierte Form des Codes aus und wirkt sich daher auf die Ansicht von anderen .NET-Sprachen aus, wenn Ihre API schließlich außerhalb von F #-Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-231">The choice between a top-level namespace or module affects the compiled form of the code, and thus will affect the view from other .NET languages should your API eventually be consumed outside of F# code.</span></span>

#### <a name="use-methods-and-properties-for-operations-intrinsic-to-object-types"></a><span data-ttu-id="0cc9b-232">Verwenden von Methoden und Eigenschaften für systeminterne Vorgänge in Objekttypen</span><span class="sxs-lookup"><span data-stu-id="0cc9b-232">Use methods and properties for operations intrinsic to object types</span></span>

<span data-ttu-id="0cc9b-233">Beim Arbeiten mit-Objekten ist es am besten, sicherzustellen, dass die verwendbare Funktionalität als Methoden und Eigenschaften für diesen Typ implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-233">When working with objects, it is best to ensure that consumable functionality is implemented as methods and properties on that type.</span></span>

```fsharp
type HardwareDevice() =

    member this.ID = ...

    member this.SupportedProtocols = ...

type HashTable<'Key,'Value>(comparer: IEqualityComparer<'Key>) =

    member this.Add(key, value) = ...

    member this.ContainsKey(key) = ...

    member this.ContainsValue(value) = ...
```

<span data-ttu-id="0cc9b-234">Der Großteil der Funktionalität für ein bestimmtes Element muss nicht notwendigerweise in diesem Member implementiert werden, aber der nutzbare Teil dieser Funktionalität sollte sein.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-234">The bulk of functionality for a given member need not necessarily be implemented in that member, but the consumable piece of that functionality should be.</span></span>

#### <a name="use-classes-to-encapsulate-mutable-state"></a><span data-ttu-id="0cc9b-235">Verwenden von Klassen zum Kapseln des änderbaren Zustands</span><span class="sxs-lookup"><span data-stu-id="0cc9b-235">Use classes to encapsulate mutable state</span></span>

<span data-ttu-id="0cc9b-236">In F # muss dies nur erfolgen, wenn dieser Zustand nicht bereits von einem anderen Sprachkonstrukt gekapselt ist, wie z. b. ein Abschluss, ein Sequenz Ausdruck oder eine asynchrone Berechnung.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-236">In F#, this only needs to be done where that state is not already encapsulated by another language construct, such as a closure, sequence expression, or asynchronous computation.</span></span>

```fsharp
type Counter() =
    // let-bound values are private in classes.
    let mutable count = 0

    member this.Next() =
        count <- count + 1
        count
```

#### <a name="use-interfaces-to-group-related-operations"></a><span data-ttu-id="0cc9b-237">Verwenden von Schnittstellen zum Gruppieren verwandter Vorgänge</span><span class="sxs-lookup"><span data-stu-id="0cc9b-237">Use interfaces to group related operations</span></span>

<span data-ttu-id="0cc9b-238">Verwenden Sie Schnittstellentypen, um einen Satz von Vorgängen darzustellen.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-238">Use interface types to represent a set of operations.</span></span> <span data-ttu-id="0cc9b-239">Dies wird für andere Optionen bevorzugt, wie z. b. Tupel von Funktionen oder Daten Satz Funktionen.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-239">This is preferred to other options, such as tuples of functions or records of functions.</span></span>

```fsharp
type Serializer =
    abstract Serialize<'T>: preserveRefEq: bool -> value: 'T -> string
    abstract Deserialize<'T>: preserveRefEq: bool -> pickle: string -> 'T
```

<span data-ttu-id="0cc9b-240">Vor:</span><span class="sxs-lookup"><span data-stu-id="0cc9b-240">In preference to:</span></span>

```fsharp
type Serializer<'T> = {
    Serialize: bool -> 'T -> string
    Deserialize: bool -> string -> 'T
}
```

<span data-ttu-id="0cc9b-241">Schnittstellen sind erstklassige Konzepte in .net, die Sie verwenden können, um zu erreichen, welche Funktoren Sie normalerweise erhalten.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-241">Interfaces are first-class concepts in .NET, which you can use to achieve what Functors would normally give you.</span></span> <span data-ttu-id="0cc9b-242">Darüber hinaus können Sie verwendet werden, um existentielle Typen in Ihrem Programm zu codieren, die Datensätze von Funktionen nicht haben.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-242">Additionally, they can be used to encode existential types into your program, which records of functions cannot.</span></span>

#### <a name="use-a-module-to-group-functions-that-act-on-collections"></a><span data-ttu-id="0cc9b-243">Verwenden eines Moduls zum Gruppieren von Funktionen, die auf Auflistungen reagieren</span><span class="sxs-lookup"><span data-stu-id="0cc9b-243">Use a module to group functions that act on collections</span></span>

<span data-ttu-id="0cc9b-244">Wenn Sie einen Sammlungstyp definieren, sollten Sie die Bereitstellung eines Standardsatzes von Vorgängen wie `CollectionType.map` und `CollectionType.iter` ) für neue Sammlungs Typen in Erwägung gezogen.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-244">When you define a collection type, consider providing a standard set of operations like `CollectionType.map` and `CollectionType.iter`) for new collection types.</span></span>

```fsharp
module CollectionType =
    let map f c =
        ...
    let iter f c =
        ...
```

<span data-ttu-id="0cc9b-245">Wenn Sie ein solches Modul einschließen, befolgen Sie die Standard Benennungs Konventionen für Funktionen, die in FSharp. Core gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-245">If you include such a module, follow the standard naming conventions for functions found in FSharp.Core.</span></span>

#### <a name="use-a-module-to-group-functions-for-common-canonical-functions-especially-in-math-and-dsl-libraries"></a><span data-ttu-id="0cc9b-246">Verwenden eines Moduls zum Gruppieren von Funktionen für allgemeine, kanonische Funktionen, insbesondere in mathematischen und DSL-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="0cc9b-246">Use a module to group functions for common, canonical functions, especially in math and DSL libraries</span></span>

<span data-ttu-id="0cc9b-247">Beispielsweise `Microsoft.FSharp.Core.Operators` ist eine automatisch geöffnete Auflistung von Funktionen der obersten Ebene (wie `abs` und), die `sin` von FSharp. Core. dll bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-247">For example, `Microsoft.FSharp.Core.Operators` is an automatically opened collection of top-level functions (like `abs` and `sin`) provided by FSharp.Core.dll.</span></span>

<span data-ttu-id="0cc9b-248">Ebenso kann eine Statistik Bibliothek ein Modul mit Funktionen und enthalten `erf` `erfc` , bei denen dieses Modul explizit oder automatisch geöffnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-248">Likewise, a statistics library might include a module with functions `erf` and `erfc`, where this module is designed to be explicitly or automatically opened.</span></span>

#### <a name="consider-using-requirequalifiedaccess-and-carefully-apply-autoopen-attributes"></a><span data-ttu-id="0cc9b-249">Ziehen Sie die Verwendung von "Requirements qualifiedaccess" in Erwägung, und wenden Sie die</span><span class="sxs-lookup"><span data-stu-id="0cc9b-249">Consider using RequireQualifiedAccess and carefully apply AutoOpen attributes</span></span>

<span data-ttu-id="0cc9b-250">Das Hinzufügen des- `[<RequireQualifiedAccess>]` Attributs zu einem Modul gibt an, dass das Modul möglicherweise nicht geöffnet wird und dass Verweise auf die Elemente des Moduls einen expliziten qualifizierten Zugriff erfordern.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-250">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="0cc9b-251">Beispielsweise verfügt das `Microsoft.FSharp.Collections.List` Modul über dieses Attribut.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-251">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="0cc9b-252">Dies ist nützlich, wenn Funktionen und Werte im Modulnamen haben, die mit den Namen in anderen Modulen wahrscheinlich in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-252">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="0cc9b-253">Wenn qualifizierter Zugriff erforderlich ist, kann die langfristige Wartbarkeit und die Entwicklung einer Bibliothek erheblich gesteigert werden.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-253">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

<span data-ttu-id="0cc9b-254">Das Hinzufügen des- `[<AutoOpen>]` Attributs zu einem Modul bedeutet, dass das Modul geöffnet wird, wenn der enthaltende Namespace geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-254">Adding the `[<AutoOpen>]` attribute to a module means the module will be opened when the containing namespace is opened.</span></span> <span data-ttu-id="0cc9b-255">Das- `[<AutoOpen>]` Attribut kann auch auf eine Assembly angewendet werden, um ein Modul anzugeben, das automatisch geöffnet wird, wenn auf die Assembly verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-255">The `[<AutoOpen>]` attribute may also be applied to an assembly to indicate a module that is automatically opened when the assembly is referenced.</span></span>

<span data-ttu-id="0cc9b-256">Beispielsweise kann eine Statistik Bibliothek **mathsheaven. Statistics** eine `module MathsHeaven.Statistics.Operators` enthaltende Funktion `erf` und enthalten `erfc` .</span><span class="sxs-lookup"><span data-stu-id="0cc9b-256">For example, a statistics library **MathsHeaven.Statistics** might contain a `module MathsHeaven.Statistics.Operators` containing functions `erf` and `erfc`.</span></span> <span data-ttu-id="0cc9b-257">Es ist sinnvoll, dieses Modul als zu markieren `[<AutoOpen>]` .</span><span class="sxs-lookup"><span data-stu-id="0cc9b-257">It is reasonable to mark this module as `[<AutoOpen>]`.</span></span> <span data-ttu-id="0cc9b-258">Dies bedeutet, dass `open MathsHeaven.Statistics` auch dieses Modul geöffnet und die Namen `erf` und in den Gültigkeitsbereich gebracht werden `erfc` .</span><span class="sxs-lookup"><span data-stu-id="0cc9b-258">This means `open MathsHeaven.Statistics` will also open this module and bring the names `erf` and `erfc` into scope.</span></span> <span data-ttu-id="0cc9b-259">Eine weitere gute Verwendung von `[<AutoOpen>]` ist für Module, die Erweiterungs Methoden enthalten.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-259">Another good use of `[<AutoOpen>]` is for modules containing extension methods.</span></span>

<span data-ttu-id="0cc9b-260">Die übermäßige Verwendung von `[<AutoOpen>]` führt zu verschmutzten Namespaces, und das Attribut sollte mit Bedacht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-260">Overuse of `[<AutoOpen>]` leads to polluted namespaces, and the attribute should be used with care.</span></span> <span data-ttu-id="0cc9b-261">Für bestimmte Bibliotheken in bestimmten Domänen kann die durch die Verwendung von eine `[<AutoOpen>]` bessere Benutzerfreundlichkeit führen.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-261">For specific libraries in specific domains, judicious use of `[<AutoOpen>]` can lead to better usability.</span></span>

#### <a name="consider-defining-operator-members-on-classes-where-using-well-known-operators-is-appropriate"></a><span data-ttu-id="0cc9b-262">Es empfiehlt sich, Operator Member für Klassen zu definieren, in denen bekannte Operatoren geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-262">Consider defining operator members on classes where using well-known operators is appropriate</span></span>

<span data-ttu-id="0cc9b-263">Manchmal werden Klassen verwendet, um mathematische Konstrukte zu modellieren, z. b. Vektoren.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-263">Sometimes classes are used to model mathematical constructs such as Vectors.</span></span> <span data-ttu-id="0cc9b-264">Wenn die zu modellierende Domäne über bekannte Operatoren verfügt, ist es hilfreich, Sie als intrinsische Elemente für die Klasse zu definieren.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-264">When the domain being modeled has well-known operators, defining them as members intrinsic to the class is helpful.</span></span>

```fsharp
type Vector(x: float) =

    member v.X = x

    static member (*) (vector: Vector, scalar: float) = Vector(vector.X * scalar)

    static member (+) (vector1: Vector, vector2: Vector) = Vector(vector1.X + vector2.X)

let v = Vector(5.0)

let u = v * 10.0
```

<span data-ttu-id="0cc9b-265">Diese Anleitung entspricht allgemeinen .net-Anleitungen für diese Typen.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-265">This guidance corresponds to general .NET guidance for these types.</span></span> <span data-ttu-id="0cc9b-266">Dies kann jedoch in F #-Codierungen von Bedeutung sein, da diese Typen in Verbindung mit f #-Funktionen und-Methoden mit Element Einschränkungen, z. b. List. sumBy, verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-266">However, it can be additionally important in F# coding as this allows these types to be used in conjunction with F# functions and methods with member constraints, such as List.sumBy.</span></span>

#### <a name="consider-using-compiledname-to-provide-a-net-friendly-name-for-other-net-language-consumers"></a><span data-ttu-id="0cc9b-267">Verwenden Sie CompiledName, um einen bereitzustellen. Netzwerk freundlicher Name für andere .NET-Sprachen</span><span class="sxs-lookup"><span data-stu-id="0cc9b-267">Consider using CompiledName to provide a .NET-friendly name for other .NET language consumers</span></span>

<span data-ttu-id="0cc9b-268">In manchen Fällen möchten Sie möglicherweise etwas in einem Stil für F #-Consumer benennen (z. b. ein statisches Element in Kleinbuchstaben, sodass es so aussieht, als ob es sich um eine Modul gebundene Funktion handelt), aber einen anderen Stil für den Namen haben, wenn es in eine Assembly kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-268">Sometimes you may wish to name something in one style for F# consumers (such as a static member in lower case so that it appears as if it were a module-bound function), but have a different style for the name when it is compiled into an assembly.</span></span> <span data-ttu-id="0cc9b-269">Sie können das- `[<CompiledName>]` Attribut verwenden, um einen anderen Stil für nicht F #-Code bereitzustellen, der die Assembly verwendet.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-269">You can use the `[<CompiledName>]` attribute to provide a different style for non F# code consuming the assembly.</span></span>

```fsharp
type Vector(x:float, y:float) =

    member v.X = x
    member v.Y = y

    [<CompiledName("Create")>]
    static member create x y = Vector (x, y)

let v = Vector.create 5.0 3.0
```

<span data-ttu-id="0cc9b-270">Mithilfe von `[<CompiledName>]` können Sie .net-Benennungs Konventionen für nicht-F #-Consumer der Assembly verwenden.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-270">By using `[<CompiledName>]`, you can use .NET naming conventions for non F# consumers of the assembly.</span></span>

#### <a name="use-method-overloading-for-member-functions-if-doing-so-provides-a-simpler-api"></a><span data-ttu-id="0cc9b-271">Verwenden Sie das Überladen von Methoden für Member-Funktionen, wenn dies eine einfachere API bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-271">Use method overloading for member functions, if doing so provides a simpler API</span></span>

<span data-ttu-id="0cc9b-272">Das Überladen von Methoden ist ein leistungsfähiges Tool zum Vereinfachen einer API, die möglicherweise eine ähnliche Funktionalität ausführen muss, aber mit unterschiedlichen Optionen oder Argumenten.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-272">Method overloading is a powerful tool for simplifying an API that may need to perform similar functionality, but with different options or arguments.</span></span>

```fsharp
type Logger() =

    member this.Log(message) =
        ...
    member this.Log(message, retryPolicy) =
        ...
```

<span data-ttu-id="0cc9b-273">In F # ist es häufiger, eine Überladung für die Anzahl von Argumenten anstelle von Argument Typen zu überlasten.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-273">In F#, it is more common to overload on number of arguments rather than types of arguments.</span></span>

#### <a name="hide-the-representations-of-record-and-union-types-if-the-design-of-these-types-is-likely-to-evolve"></a><span data-ttu-id="0cc9b-274">Blenden Sie die Darstellungen von Daten Satz-und Union-Typen aus, wenn sich der Entwurf dieser Typen wahrscheinlich weiterentwickelt.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-274">Hide the representations of record and union types if the design of these types is likely to evolve</span></span>

<span data-ttu-id="0cc9b-275">Vermeiden Sie es, konkrete Darstellungen von Objekten offenzulegen.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-275">Avoid revealing concrete representations of objects.</span></span> <span data-ttu-id="0cc9b-276">Beispielsweise wird die konkrete Darstellung von <xref:System.DateTime> Werten nicht von der externen öffentlichen API des Entwurfs der .NET-Bibliothek offengelegt.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-276">For example, the concrete representation of <xref:System.DateTime> values is not revealed by the external, public API of the .NET library design.</span></span> <span data-ttu-id="0cc9b-277">Zur Laufzeit kennt die Common Language Runtime die implementiertes Implementierung, die während der Ausführung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-277">At run time, the Common Language Runtime knows the committed implementation that will be used throughout execution.</span></span> <span data-ttu-id="0cc9b-278">Allerdings übernimmt der kompilierte Code nicht selbst Abhängigkeiten von der konkreten Darstellung.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-278">However, compiled code doesn't itself pick up dependencies on the concrete representation.</span></span>

#### <a name="avoid-the-use-of-implementation-inheritance-for-extensibility"></a><span data-ttu-id="0cc9b-279">Vermeiden Sie die Verwendung der Implementierungs Vererbung für die Erweiterbarkeit.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-279">Avoid the use of implementation inheritance for extensibility</span></span>

<span data-ttu-id="0cc9b-280">In F # wird die Implementierungsvererbung selten verwendet.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-280">In F#, implementation inheritance is rarely used.</span></span> <span data-ttu-id="0cc9b-281">Außerdem sind Vererbungs Hierarchien häufig komplex und schwer zu ändern, wenn neue Anforderungen eingehen.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-281">Furthermore, inheritance hierarchies are often complex and difficult to change when new requirements arrive.</span></span> <span data-ttu-id="0cc9b-282">Die Vererbungs Implementierung ist in f # weiterhin für Kompatibilität und in seltenen Fällen vorhanden, in denen es sich um die beste Lösung für ein Problem handelt, aber alternative Techniken bei der Entwicklung von Polymorphie, wie z. b. der Schnittstellen Implementierung, in ihren f #-Programmen.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-282">Inheritance implementation still exists in F# for compatibility and rare cases where it is the best solution to a problem, but alternative techniques should be sought in your F# programs when designing for polymorphism, such as interface implementation.</span></span>

### <a name="function-and-member-signatures"></a><span data-ttu-id="0cc9b-283">Funktions-und Element Signaturen</span><span class="sxs-lookup"><span data-stu-id="0cc9b-283">Function and member signatures</span></span>

#### <a name="use-tuples-for-return-values-when-returning-a-small-number-of-multiple-unrelated-values"></a><span data-ttu-id="0cc9b-284">Verwenden Sie Tupel für Rückgabewerte, wenn Sie eine kleine Anzahl von mehreren nicht verknüpften Werten zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-284">Use tuples for return values when returning a small number of multiple unrelated values</span></span>

<span data-ttu-id="0cc9b-285">Im folgenden finden Sie ein gutes Beispiel für die Verwendung eines Tupels in einem Rückgabetyp:</span><span class="sxs-lookup"><span data-stu-id="0cc9b-285">Here is a good example of using a tuple in a return type:</span></span>

```fsharp
val divrem: BigInteger -> BigInteger -> BigInteger * BigInteger
```

<span data-ttu-id="0cc9b-286">Verwenden Sie für Rückgabe Typen, die viele Komponenten enthalten oder für die die Komponenten mit einer einzelnen identifizierbaren Entität verknüpft sind, einen benannten Typ anstelle eines Tupels.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-286">For return types containing many components, or where the components are related to a single identifiable entity, consider using a named type instead of a tuple.</span></span>

#### <a name="use-asynct-for-async-programming-at-f-api-boundaries"></a><span data-ttu-id="0cc9b-287">Verwendung für die asynchrone `Async<T>` Programmierung in F #-API-Grenzen</span><span class="sxs-lookup"><span data-stu-id="0cc9b-287">Use `Async<T>` for async programming at F# API boundaries</span></span>

<span data-ttu-id="0cc9b-288">Wenn ein entsprechender synchroner Vorgang mit dem Namen vorhanden ist `Operation` , der einen zurückgibt `T` , sollte der asynchrone Vorgang bei Rückgabe von oder zurückgegeben werden `AsyncOperation` `Async<T>` `OperationAsync` `Task<T>` .</span><span class="sxs-lookup"><span data-stu-id="0cc9b-288">If there is a corresponding synchronous operation named `Operation` that returns a `T`, then the async operation should be named `AsyncOperation` if it returns `Async<T>` or `OperationAsync` if it returns `Task<T>`.</span></span> <span data-ttu-id="0cc9b-289">Für häufig verwendete .NET-Typen, die Begin/End-Methoden verfügbar machen, empfiehlt es sich, mithilfe `Async.FromBeginEnd` von Erweiterungs Methoden als Fassade zu schreiben, um diese .NET-APIs mit dem asynchronen F #-Programmiermodell bereitzustellen</span><span class="sxs-lookup"><span data-stu-id="0cc9b-289">For commonly used .NET types that expose Begin/End methods, consider using `Async.FromBeginEnd` to write extension methods as a façade to provide the F# async programming model to those .NET APIs.</span></span>

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

### <a name="exceptions"></a><span data-ttu-id="0cc9b-290">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="0cc9b-290">Exceptions</span></span>

<span data-ttu-id="0cc9b-291">Weitere Informationen zur geeigneten Verwendung von Ausnahmen, Ergebnissen und Optionen finden Sie unter [Fehler Verwaltung](conventions.md#error-management) .</span><span class="sxs-lookup"><span data-stu-id="0cc9b-291">See [Error Management](conventions.md#error-management) to learn about appropriate use of exceptions, results, and options.</span></span>

### <a name="extension-members"></a><span data-ttu-id="0cc9b-292">Erweiterungsmember</span><span class="sxs-lookup"><span data-stu-id="0cc9b-292">Extension Members</span></span>

#### <a name="carefully-apply-f-extension-members-in-f-to-f-components"></a><span data-ttu-id="0cc9b-293">Sorgfältiges Anwenden von f #-Erweiterungs Membern in f #-zu-f #-Komponenten</span><span class="sxs-lookup"><span data-stu-id="0cc9b-293">Carefully apply F# extension members in F#-to-F# components</span></span>

<span data-ttu-id="0cc9b-294">F #-Erweiterungs Elemente sollten in der Regel nur für Vorgänge verwendet werden, die bei der Schließung von systeminternen Vorgängen verwendet werden, die einem Typ in den meisten Verwendungs Modi zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-294">F# extension members should generally only be used for operations that are in the closure of intrinsic operations associated with a type in the majority of its modes of use.</span></span> <span data-ttu-id="0cc9b-295">Eine häufige Verwendung besteht darin, APIs bereitzustellen, die mehr idiomatisch in F # für verschiedene .NET-Typen sind:</span><span class="sxs-lookup"><span data-stu-id="0cc9b-295">One common use is to provide APIs that are more idiomatic to F# for various .NET types:</span></span>

```fsharp
type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        Async.FromBeginEnd(this.BeginReceive, this.EndReceive)

type System.Collections.Generic.IDictionary<'Key,'Value> with
    member this.TryGet key =
        let ok, v = this.TryGetValue key
        if ok then Some v else None
```

### <a name="union-types"></a><span data-ttu-id="0cc9b-296">Union-Typen</span><span class="sxs-lookup"><span data-stu-id="0cc9b-296">Union Types</span></span>

#### <a name="use-discriminated-unions-instead-of-class-hierarchies-for-tree-structured-data"></a><span data-ttu-id="0cc9b-297">Verwenden von Unterscheidungs-Unions anstelle von Klassenhierarchien für Struktur strukturierte Daten</span><span class="sxs-lookup"><span data-stu-id="0cc9b-297">Use discriminated unions instead of class hierarchies for tree-structured data</span></span>

<span data-ttu-id="0cc9b-298">Struktur ähnliche Strukturen werden rekursiv definiert.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-298">Tree-like structures are recursively defined.</span></span> <span data-ttu-id="0cc9b-299">Dies ist mit Vererbung, aber elegant mit Unterscheidungs-Unions sehr umständlich.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-299">This is awkward with inheritance, but elegant with Discriminated Unions.</span></span>

```fsharp
type BST<'T> =
    | Empty
    | Node of 'T * BST<'T> * BST<'T>
```

<span data-ttu-id="0cc9b-300">Das darstellen von Struktur ähnlichen Daten mit Unterscheidungs-Unions ermöglicht Ihnen außerdem, von der Erschöpfung bei der Muster Übereinstimmung profitieren zu können.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-300">Representing tree-like data with Discriminated Unions also allows you to benefit from exhaustiveness in pattern matching.</span></span>

#### <a name="use-requirequalifiedaccess-on-union-types-whose-case-names-are-not-sufficiently-unique"></a><span data-ttu-id="0cc9b-301">Verwendung `[<RequireQualifiedAccess>]` für Union-Typen, deren Groß-/Kleinschreibung nicht ausreichend eindeutig ist</span><span class="sxs-lookup"><span data-stu-id="0cc9b-301">Use `[<RequireQualifiedAccess>]` on union types whose case names are not sufficiently unique</span></span>

<span data-ttu-id="0cc9b-302">Sie können sich in einer Domäne befinden, in der derselbe Name der beste Name für verschiedene Dinge ist, wie z. b. diskriminierte Union-Fälle.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-302">You may find yourself in a domain where the same name is the best name for different things, such as Discriminated Union cases.</span></span> <span data-ttu-id="0cc9b-303">Sie können verwenden `[<RequireQualifiedAccess>]` , um Case-Namen eindeutig zu machen, um zu vermeiden, dass verwirrende Fehler ausgelöst werden, da shadodown von der Reihenfolge der Anweisungen abhängig ist. `open`</span><span class="sxs-lookup"><span data-stu-id="0cc9b-303">You can use `[<RequireQualifiedAccess>]` to disambiguate case names in order to avoid triggering confusing errors due to shadowing dependent on the ordering of `open` statements</span></span>

#### <a name="hide-the-representations-of-discriminated-unions-for-binary-compatible-apis-if-the-design-of-these-types-is-likely-to-evolve"></a><span data-ttu-id="0cc9b-304">Verbergen der Darstellungen von Unterscheidungs-Unions für Binär kompatible APIs, wenn sich der Entwurf dieser Typen wahrscheinlich weiterentwickelt</span><span class="sxs-lookup"><span data-stu-id="0cc9b-304">Hide the representations of discriminated unions for binary compatible APIs if the design of these types is likely to evolve</span></span>

<span data-ttu-id="0cc9b-305">Unions-Typen basieren auf F #-Muster Vergleichs Formularen für ein präct-Programmiermodell.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-305">Unions types rely on F# pattern-matching forms for a succinct programming model.</span></span> <span data-ttu-id="0cc9b-306">Wie bereits erwähnt, sollten Sie das Offenlegen konkreter Daten Darstellungen vermeiden, wenn sich der Entwurf dieser Typen wahrscheinlich weiterentwickelt.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-306">As mentioned previously, you should avoid revealing concrete data representations if the design of these types is likely to evolve.</span></span>

<span data-ttu-id="0cc9b-307">Beispielsweise kann die Darstellung einer Unterscheidungs-Union mit einer privaten oder internen Deklaration oder mithilfe einer Signatur Datei ausgeblendet werden.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-307">For example, the representation of a discriminated union can be hidden using a private or internal declaration, or by using a signature file.</span></span>

```fsharp
type Union =
    private
    | CaseA of int
    | CaseB of string
```

<span data-ttu-id="0cc9b-308">Wenn Sie Unterscheidungs Unions willkürlich offenlegen, ist es möglicherweise schwierig, Ihre Bibliothek zu versidieren, ohne den Benutzercode zu unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-308">If you reveal discriminated unions indiscriminately, you may find it hard to version your library without breaking user code.</span></span> <span data-ttu-id="0cc9b-309">Verwenden Sie stattdessen ein oder mehrere aktive Muster, um eine Muster Übereinstimmung für Werte des Typs zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-309">Instead, consider revealing one or more active patterns to permit pattern matching over values of your type.</span></span>

<span data-ttu-id="0cc9b-310">Aktive Muster bieten eine alternative Möglichkeit, f #-Consumer mit Muster Übereinstimmungen bereitzustellen und gleichzeitig die direkte Bereitstellung von f #-Union-Typen</span><span class="sxs-lookup"><span data-stu-id="0cc9b-310">Active patterns provide an alternate way to provide F# consumers with pattern matching while avoiding exposing F# Union Types directly.</span></span>

### <a name="inline-functions-and-member-constraints"></a><span data-ttu-id="0cc9b-311">Inline Funktionen und Element Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="0cc9b-311">Inline Functions and Member Constraints</span></span>

#### <a name="define-generic-numeric-algorithms-using-inline-functions-with-implied-member-constraints-and-statically-resolved-generic-types"></a><span data-ttu-id="0cc9b-312">Definieren von generischen numerischen Algorithmen mithilfe von Inline Funktionen mit impliziten Element Einschränkungen und statisch aufgelösten generischen Typen</span><span class="sxs-lookup"><span data-stu-id="0cc9b-312">Define generic numeric algorithms using inline functions with implied member constraints and statically resolved generic types</span></span>

<span data-ttu-id="0cc9b-313">Arithmetische Member-Einschränkungen und f #-Vergleichs Einschränkungen sind ein Standard für die f #-Programmierung.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-313">Arithmetic member constraints and F# comparison constraints are a standard for F# programming.</span></span> <span data-ttu-id="0cc9b-314">Beachten Sie z. B. folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="0cc9b-314">For example, consider the following code:</span></span>

```fsharp
let inline highestCommonFactor a b =
    let rec loop a b =
        if a = LanguagePrimitives.GenericZero<_> then b
        elif a < b then loop a (b - a)
        else loop (a - b) b
    loop a b
```

<span data-ttu-id="0cc9b-315">Der Typ dieser Funktion ist wie folgt:</span><span class="sxs-lookup"><span data-stu-id="0cc9b-315">The type of this function is as follows:</span></span>

```fsharp
val inline highestCommonFactor : ^T -> ^T -> ^T
                when ^T : (static member Zero : ^T)
                and ^T : (static member ( - ) : ^T * ^T -> ^T)
                and ^T : equality
                and ^T : comparison
```

<span data-ttu-id="0cc9b-316">Dies ist eine geeignete Funktion für eine öffentliche API in einer mathematischen Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-316">This is a suitable function for a public API in a mathematical library.</span></span>

#### <a name="avoid-using-member-constraints-to-simulate-type-classes-and-duck-typing"></a><span data-ttu-id="0cc9b-317">Vermeiden Sie die Verwendung von Element Einschränkungen zum Simulieren von Typklassen und der Typisierung</span><span class="sxs-lookup"><span data-stu-id="0cc9b-317">Avoid using member constraints to simulate type classes and duck typing</span></span>

<span data-ttu-id="0cc9b-318">Es ist möglich, "ententypisierung" mithilfe von F #-Member-Einschränkungen zu simulieren.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-318">It is possible to simulate "duck typing" using F# member constraints.</span></span> <span data-ttu-id="0cc9b-319">Member, die diese verwenden, sollten jedoch nicht im Allgemeinen in f #-zu-f #-Bibliotheks Entwürfen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-319">However, members that make use of this should not in general be used in F#-to-F# library designs.</span></span> <span data-ttu-id="0cc9b-320">Dies liegt daran, dass Bibliotheks Entwürfe, die auf unbekannten oder nicht standardmäßigen impliziten Einschränkungen basieren, dazu führen, dass Benutzercode unflexibel und an ein bestimmtes Framework-Muster gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-320">This is because library designs based on unfamiliar or non-standard implicit constraints tend to cause user code to become inflexible and tied to one particular framework pattern.</span></span>

<span data-ttu-id="0cc9b-321">Außerdem gibt es eine gute Wahrscheinlichkeit, dass Element Einschränkungen auf diese Weise sehr lange kompiliert werden können.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-321">Additionally, there is a good chance that heavy use of member constraints in this manner can result in very long compile times.</span></span>

### <a name="operator-definitions"></a><span data-ttu-id="0cc9b-322">Operator Definitionen</span><span class="sxs-lookup"><span data-stu-id="0cc9b-322">Operator Definitions</span></span>

#### <a name="avoid-defining-custom-symbolic-operators"></a><span data-ttu-id="0cc9b-323">Vermeiden der Definition benutzerdefinierter symbolischer Operatoren</span><span class="sxs-lookup"><span data-stu-id="0cc9b-323">Avoid defining custom symbolic operators</span></span>

<span data-ttu-id="0cc9b-324">Benutzerdefinierte Operatoren sind in einigen Situationen unverzichtbar und sind sehr nützliche notationgeräte innerhalb eines großen Texts von Implementierungs Code.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-324">Custom operators are essential in some situations and are highly useful notational devices within a large body of implementation code.</span></span> <span data-ttu-id="0cc9b-325">Für neue Benutzer einer Bibliothek sind benannte Funktionen häufig einfacher zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-325">For new users of a library, named functions are often easier to use.</span></span> <span data-ttu-id="0cc9b-326">Außerdem können benutzerdefinierte symbolische Operatoren schwer zu dokumentieren sein, und Benutzer können aufgrund vorhandener Einschränkungen in IDE-und Suchmaschinen die Suche nach Hilfe zu Operatoren erschweren.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-326">In addition, custom symbolic operators can be hard to document, and users find it more difficult to look up help on operators, due to existing limitations in IDE and search engines.</span></span>

<span data-ttu-id="0cc9b-327">Daher ist es am besten, ihre Funktionalität als benannte Funktionen und Member zu veröffentlichen, und zusätzlich Operatoren für diese Funktionalität nur verfügbar zu machen, wenn die notalisierungsvorteile die Dokumentation und die kognitiven Kosten Ihrer IT überwiegen.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-327">As a result, it is best to publish your functionality as named functions and members, and additionally expose operators for this functionality only if the notational benefits outweigh the documentation and cognitive cost of having them.</span></span>

### <a name="units-of-measure"></a><span data-ttu-id="0cc9b-328">Maßeinheiten</span><span class="sxs-lookup"><span data-stu-id="0cc9b-328">Units of Measure</span></span>

#### <a name="carefully-use-units-of-measure-for-added-type-safety-in-f-code"></a><span data-ttu-id="0cc9b-329">Sorgfältige Verwendung von Maßeinheiten für die hinzugefügte Typsicherheit in F #-Code</span><span class="sxs-lookup"><span data-stu-id="0cc9b-329">Carefully use units of measure for added type safety in F# code</span></span>

<span data-ttu-id="0cc9b-330">Zusätzliche Typisierungs Informationen für Maßeinheiten werden gelöscht, wenn Sie von anderen .NET-Sprachen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-330">Additional typing information for units of measure is erased when viewed by other .NET languages.</span></span> <span data-ttu-id="0cc9b-331">Beachten Sie, dass .NET-Komponenten,-Tools und-Reflektion Typen-Sans-Units sehen werden.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-331">Be aware that .NET components, tools, and reflection will see types-sans-units.</span></span> <span data-ttu-id="0cc9b-332">Beispielsweise sehen c#-Consumer `float` anstelle von `float<kg>` .</span><span class="sxs-lookup"><span data-stu-id="0cc9b-332">For example, C# consumers will see `float` rather than `float<kg>`.</span></span>

### <a name="type-abbreviations"></a><span data-ttu-id="0cc9b-333">Typabkürzungen</span><span class="sxs-lookup"><span data-stu-id="0cc9b-333">Type Abbreviations</span></span>

#### <a name="carefully-use-type-abbreviations-to-simplify-f-code"></a><span data-ttu-id="0cc9b-334">Sorgfältige Verwendung von typabkürzungen zum Vereinfachen von F #-Code</span><span class="sxs-lookup"><span data-stu-id="0cc9b-334">Carefully use type abbreviations to simplify F# code</span></span>

<span data-ttu-id="0cc9b-335">Für .NET-Komponenten,-Tools und-Reflektion werden keine abgekürzten Namen für-Typen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-335">.NET components, tools, and reflection will not see abbreviated names for types.</span></span> <span data-ttu-id="0cc9b-336">Eine bedeutende Verwendung von typabkürzungen kann auch dazu führen, dass eine Domäne komplexer erscheint, als Sie tatsächlich ist, was den Consumer verwirren könnte.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-336">Significant usage of type abbreviations can also make a domain appear more complex than it actually is, which could confuse consumers.</span></span>

#### <a name="avoid-type-abbreviations-for-public-types-whose-members-and-properties-should-be-intrinsically-different-to-those-available-on-the-type-being-abbreviated"></a><span data-ttu-id="0cc9b-337">Vermeiden Sie typabkürzungen für öffentliche Typen, deren Member und Eigenschaften sich intrinsisch von denen unterscheiden, die für den Typ verfügbar sind, der abgekürzt wird.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-337">Avoid type abbreviations for public types whose members and properties should be intrinsically different to those available on the type being abbreviated</span></span>

<span data-ttu-id="0cc9b-338">In diesem Fall wird der Typ, der abgekürzt wird, zu viel über die Darstellung des tatsächlichen Typs angezeigt, der definiert wird.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-338">In this case, the type being abbreviated reveals too much about the representation of the actual type being defined.</span></span> <span data-ttu-id="0cc9b-339">Stattdessen sollten Sie die Abkürzung in einen Klassentyp oder eine Unterscheidungs-Union einschließen (oder wenn die Leistung unverzichtbar ist, sollten Sie einen Strukturtyp verwenden, um die Abkürzung zu umschließen).</span><span class="sxs-lookup"><span data-stu-id="0cc9b-339">Instead, consider wrapping the abbreviation in a class type or a single-case discriminated union (or, when performance is essential, consider using a struct type to wrap the abbreviation).</span></span>

<span data-ttu-id="0cc9b-340">Beispielsweise ist es verlockend, eine mehrfach Zuordnung als Sonderfall einer F #-Karte zu definieren, beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="0cc9b-340">For example, it is tempting to define a multi-map as a special case of an F# map, for example:</span></span>

```fsharp
type MultiMap<'Key,'Value> = Map<'Key,'Value list>
```

<span data-ttu-id="0cc9b-341">Allerdings sind die logischen Punkt Schreibvorgänge für diesen Typ nicht mit den Vorgängen auf einer Zuordnung identisch – beispielsweise ist es sinnvoll, dass der Such Operator zugeordnet ist. [key] gibt die leere Liste zurück, wenn der Schlüssel nicht im Wörterbuch enthalten ist, anstatt eine Ausnahme zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-341">However, the logical dot-notation operations on this type are not the same as the operations on a Map – for example, it is reasonable that the lookup operator map.[key] return the empty list if the key is not in the dictionary, rather than raising an exception.</span></span>

## <a name="guidelines-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="0cc9b-342">Richtlinien für Bibliotheken zur Verwendung in anderen .NET-Sprachen</span><span class="sxs-lookup"><span data-stu-id="0cc9b-342">Guidelines for libraries for Use from other .NET Languages</span></span>

<span data-ttu-id="0cc9b-343">Beim Entwerfen von Bibliotheken für die Verwendung in anderen .NET-Sprachen ist es wichtig, die [Entwurfs Richtlinien für .net](../../standard/design-guidelines/index.md)-Bibliotheken einzuhalten.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-343">When designing libraries for use from other .NET languages, it is important to adhere to the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md).</span></span> <span data-ttu-id="0cc9b-344">In diesem Dokument werden diese Bibliotheken als "Vanille .NET-Bibliotheken" bezeichnet, im Gegensatz zu f #-orientierten Bibliotheken, die f #-Konstrukte ohne Einschränkung verwenden.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-344">In this document, these libraries are labeled as vanilla .NET libraries, as opposed to F#-facing libraries that use F# constructs without restriction.</span></span> <span data-ttu-id="0cc9b-345">Das Entwerfen von Vanille-.NET-Bibliotheken bedeutet, dass vertraute und idiomatische APIs konsistent mit dem Rest der .NET Framework sind, indem die Verwendung von F #-spezifischen Konstrukten in der öffentlichen API minimiert wird.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-345">Designing vanilla .NET libraries means providing familiar and idiomatic APIs consistent with the rest of the .NET Framework by minimizing the use of F#-specific constructs in the public API.</span></span> <span data-ttu-id="0cc9b-346">Die Regeln werden in den folgenden Abschnitten erläutert.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-346">The rules are explained in the following sections.</span></span>

### <a name="namespace-and-type-design-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="0cc9b-347">Namespace und typentwurf (für Bibliotheken zur Verwendung in anderen .NET-Sprachen)</span><span class="sxs-lookup"><span data-stu-id="0cc9b-347">Namespace and Type design (for libraries for use from other .NET Languages)</span></span>

#### <a name="apply-the-net-naming-conventions-to-the-public-api-of-your-components"></a><span data-ttu-id="0cc9b-348">Anwenden der .net-Benennungs Konventionen auf die öffentliche API ihrer Komponenten</span><span class="sxs-lookup"><span data-stu-id="0cc9b-348">Apply the .NET naming conventions to the public API of your components</span></span>

<span data-ttu-id="0cc9b-349">Achten Sie besonders auf die Verwendung von abgekürzten Namen und den .NET-Richtlinien für die Groß Schreibung</span><span class="sxs-lookup"><span data-stu-id="0cc9b-349">Pay special attention to the use of abbreviated names and the .NET capitalization guidelines.</span></span>

```fsharp
type pCoord = ...
    member this.theta = ...

type PolarCoordinate = ...
    member this.Theta = ...
```

#### <a name="use-namespaces-types-and-members-as-the-primary-organizational-structure-for-your-components"></a><span data-ttu-id="0cc9b-350">Verwenden von Namespaces, Typen und Membern als primäre Organisationsstruktur für Ihre Komponenten</span><span class="sxs-lookup"><span data-stu-id="0cc9b-350">Use namespaces, types, and members as the primary organizational structure for your components</span></span>

<span data-ttu-id="0cc9b-351">Alle Dateien, die die öffentliche Funktionalität enthalten, müssen mit einer `namespace` -Deklaration beginnen, und die einzigen öffentlich ausgerichteten Entitäten in Namespaces sollten-Typen sein.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-351">All files containing public functionality should begin with a `namespace` declaration, and the only public-facing entities in namespaces should be types.</span></span> <span data-ttu-id="0cc9b-352">Verwenden Sie keine F #-Module.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-352">Do not use F# modules.</span></span>

<span data-ttu-id="0cc9b-353">Verwenden Sie nicht öffentliche Module zum Speichern von Implementierungs Code, hilfsprogrammtypen und Hilfsprogrammfunktionen.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-353">Use non-public modules to hold implementation code, utility types, and utility functions.</span></span>

<span data-ttu-id="0cc9b-354">Statische Typen sollten gegenüber Modulen bevorzugt werden, da Sie für zukünftige Entwicklungen der API die Verwendung von überladen und anderen .NET-API-Entwurfskonzepten ermöglichen, die nicht in F #-Modulen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-354">Static types should be preferred over modules, as they allow for future evolution of the API to use overloading and other .NET API design concepts that may not be used within F# modules.</span></span>

<span data-ttu-id="0cc9b-355">Beispielsweise anstelle der folgenden öffentlichen API:</span><span class="sxs-lookup"><span data-stu-id="0cc9b-355">For example, in place of the following public API:</span></span>

```fsharp
module Fabrikam

module Utilities =
    let Name = "Bob"
    let Add2 x y = x + y
    let Add3 x y z = x + y + z
```

<span data-ttu-id="0cc9b-356">Verwenden Sie stattdessen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="0cc9b-356">Consider instead:</span></span>

```fsharp
namespace Fabrikam

[<AbstractClass; Sealed>]
type Utilities =
    static member Name = "Bob"
    static member Add(x,y) = x + y
    static member Add(x,y,z) = x + y + z
```

#### <a name="use-f-record-types-in-vanilla-net-apis-if-the-design-of-the-types-wont-evolve"></a><span data-ttu-id="0cc9b-357">Verwenden von F #-Daten Satz Typen in Vanille-.NET-APIs, wenn der Entwurf der Typen nicht weiterentwickelt wird</span><span class="sxs-lookup"><span data-stu-id="0cc9b-357">Use F# record types in vanilla .NET APIs if the design of the types won't evolve</span></span>

<span data-ttu-id="0cc9b-358">F #-Daten Satz Typen werden in eine einfache .NET-Klasse kompiliert.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-358">F# record types compile to a simple .NET class.</span></span> <span data-ttu-id="0cc9b-359">Diese sind für einige einfache, stabile Typen in APIs geeignet.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-359">These are suitable for some simple, stable types in APIs.</span></span> <span data-ttu-id="0cc9b-360">Verwenden Sie die `[<NoEquality>]` `[<NoComparison>]` Attribute und, um die automatische Generierung von Schnittstellen zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-360">Consider using the `[<NoEquality>]` and `[<NoComparison>]` attributes to suppress the automatic generation of interfaces.</span></span> <span data-ttu-id="0cc9b-361">Vermeiden Sie außerdem die Verwendung änderbarer Daten Satz Felder in den .NET-APIs von Vanille, da diese ein öffentliches Feld verfügbar machen</span><span class="sxs-lookup"><span data-stu-id="0cc9b-361">Also avoid using mutable record fields in vanilla .NET APIs as these expose a public field.</span></span> <span data-ttu-id="0cc9b-362">Denken Sie immer daran, ob eine Klasse eine flexiblere Option zur zukünftigen Entwicklung der API bereitstellen würde.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-362">Always consider whether a class would provide a more flexible option for future evolution of the API.</span></span>

<span data-ttu-id="0cc9b-363">Beispielsweise macht der folgende F #-Code die öffentliche API für einen c#-Consumer verfügbar:</span><span class="sxs-lookup"><span data-stu-id="0cc9b-363">For example, the following F# code exposes the public API to a C# consumer:</span></span>

<span data-ttu-id="0cc9b-364">F#:</span><span class="sxs-lookup"><span data-stu-id="0cc9b-364">F#:</span></span>

```fsharp
[<NoEquality; NoComparison>]
type MyRecord =
    { FirstThing: int
        SecondThing: string }
```

<span data-ttu-id="0cc9b-365">C#:</span><span class="sxs-lookup"><span data-stu-id="0cc9b-365">C#:</span></span>

```csharp
public sealed class MyRecord
{
    public MyRecord(int firstThing, string secondThing);
    public int FirstThing { get; }
    public string SecondThing { get; }
}
```

#### <a name="hide-the-representation-of-f-union-types-in-vanilla-net-apis"></a><span data-ttu-id="0cc9b-366">Ausblenden der Darstellung von F #-Union-Typen in Vanille-. NET-APIs</span><span class="sxs-lookup"><span data-stu-id="0cc9b-366">Hide the representation of F# union types in vanilla .NET APIs</span></span>

<span data-ttu-id="0cc9b-367">F #-Union-Typen werden nicht häufig über Komponenten Grenzen hinweg verwendet, auch bei f #-zu-f #-Codierungen.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-367">F# union types are not commonly used across component boundaries, even for F#-to-F# coding.</span></span> <span data-ttu-id="0cc9b-368">Sie sind ein ausgezeichnetes Implementierungs Gerät, wenn es intern innerhalb von Komponenten und Bibliotheken verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-368">They are an excellent implementation device when used internally within components and libraries.</span></span>

<span data-ttu-id="0cc9b-369">Beim Entwerfen einer .NET-API für Vanille sollten Sie die Darstellung eines Union-Typs in Erwägung gezogen, indem Sie entweder eine private oder eine Signatur Datei verwenden.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-369">When designing a vanilla .NET API, consider hiding the representation of a union type by using either a private declaration or a signature file.</span></span>

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True
```

<span data-ttu-id="0cc9b-370">Sie können auch Typen erweitern, die eine Union-Darstellung intern mit Membern verwenden, um ein gewünschtes bereitzustellen. NET-API.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-370">You may also augment types that use a union representation internally with members to provide a desired .NET-facing API.</span></span>

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

#### <a name="design-gui-and-other-components-using-the-design-patterns-of-the-framework"></a><span data-ttu-id="0cc9b-371">Entwerfen von GUI und anderen Komponenten mithilfe der Entwurfsmuster des Frameworks</span><span class="sxs-lookup"><span data-stu-id="0cc9b-371">Design GUI and other components using the design patterns of the framework</span></span>

<span data-ttu-id="0cc9b-372">In .net stehen viele verschiedene Frameworks zur Verfügung, z. b. WinForms, WPF und ASP.net.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-372">There are many different frameworks available within .NET, such as WinForms, WPF, and ASP.NET.</span></span> <span data-ttu-id="0cc9b-373">Benennungs-und Entwurfs Konventionen sollten verwendet werden, wenn Sie Komponenten für die Verwendung in diesen Frameworks entwerfen.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-373">Naming and design conventions for each should be used if you are designing components for use in these frameworks.</span></span> <span data-ttu-id="0cc9b-374">Nehmen Sie z. b. für die WPF-Programmierung WPF-Entwurfsmuster für die Klassen an, die Sie entwerfen.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-374">For example, for WPF programming, adopt WPF design patterns for the classes you are designing.</span></span> <span data-ttu-id="0cc9b-375">Verwenden Sie für Modelle in der Programmierung von Benutzeroberflächen Entwurfsmuster wie z. b. Ereignisse und Benachrichtigungs basierte Auflistungen, z. b. die in <xref:System.Collections.ObjectModel> .</span><span class="sxs-lookup"><span data-stu-id="0cc9b-375">For models in user interface programming, use design patterns such as events and notification-based collections such as those found in <xref:System.Collections.ObjectModel>.</span></span>

### <a name="object-and-member-design-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="0cc9b-376">Objekt-und Element Entwurf (für Bibliotheken zur Verwendung in anderen .NET-Sprachen)</span><span class="sxs-lookup"><span data-stu-id="0cc9b-376">Object and Member design (for libraries for use from other .NET Languages)</span></span>

#### <a name="use-the-clievent-attribute-to-expose-net-events"></a><span data-ttu-id="0cc9b-377">Verwenden des clievent-Attributs zum verfügbar machen von .NET-Ereignissen</span><span class="sxs-lookup"><span data-stu-id="0cc9b-377">Use the CLIEvent attribute to expose .NET events</span></span>

<span data-ttu-id="0cc9b-378">Erstellen `DelegateEvent` Sie ein-Objekt mit einem bestimmten .net-Delegattyp, der ein-Objekt und `EventArgs` (anstelle eines `Event` verwendet, das `FSharpHandler` standardmäßig den-Typ verwendet), sodass die Ereignisse auf vertraute Weise in anderen .NET-Sprachen veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-378">Construct a `DelegateEvent` with a specific .NET delegate type that takes an object and `EventArgs` (rather than an `Event`, which just uses the `FSharpHandler` type by default) so that the events are published in the familiar way to other .NET languages.</span></span>

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

#### <a name="expose-asynchronous-operations-as-methods-that-return-net-tasks"></a><span data-ttu-id="0cc9b-379">Verfügbar machen asynchroner Vorgänge als Methoden, die .net-Tasks zurückgeben</span><span class="sxs-lookup"><span data-stu-id="0cc9b-379">Expose asynchronous operations as methods that return .NET tasks</span></span>

<span data-ttu-id="0cc9b-380">Tasks werden in .NET verwendet, um aktive asynchrone Berechnungen darzustellen.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-380">Tasks are used in .NET to represent active asynchronous computations.</span></span> <span data-ttu-id="0cc9b-381">Aufgaben sind im Allgemeinen weniger festgesetzt als F # `Async<T>` -Objekte, da Sie "bereits ausgeführte" Aufgaben darstellen und nicht in einer Weise zusammengesetzt werden können, die eine parallele Komposition durchführt oder die Propagierung von Abbruch Signalen und anderen Kontext Parametern ausblenden.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-381">Tasks are in general less compositional than F# `Async<T>` objects, since they represent "already executing" tasks and can't be composed together in ways that perform parallel composition, or which hide the propagation of cancellation signals and other contextual parameters.</span></span>

<span data-ttu-id="0cc9b-382">Dennoch sind Methoden, die Aufgaben zurückgeben, die Standarddarstellung der asynchronen Programmierung in .net.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-382">However, despite this, methods that return Tasks are the standard representation of asynchronous programming on .NET.</span></span>

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =

    let compute (x: int): Async<int> = async { ... }

    member this.ComputeAsync(x) = compute x |> Async.StartAsTask
```

<span data-ttu-id="0cc9b-383">Sie möchten häufig auch ein explizites Abbruch Token akzeptieren:</span><span class="sxs-lookup"><span data-stu-id="0cc9b-383">You will frequently also want to accept an explicit cancellation token:</span></span>

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =
    let compute(x: int): Async<int> = async { ... }
    member this.ComputeAsTask(x, cancellationToken) = Async.StartAsTask(compute x, cancellationToken)
```

#### <a name="use-net-delegate-types-instead-of-f-function-types"></a><span data-ttu-id="0cc9b-384">Verwenden von .net-Delegattypen anstelle von F #-Funktionstypen</span><span class="sxs-lookup"><span data-stu-id="0cc9b-384">Use .NET delegate types instead of F# function types</span></span>

<span data-ttu-id="0cc9b-385">Hier sind "F #-Funktionstypen", "Pfeil"-Typen wie `int -> int` .</span><span class="sxs-lookup"><span data-stu-id="0cc9b-385">Here "F# function types" mean "arrow" types like `int -> int`.</span></span>

<span data-ttu-id="0cc9b-386">Anstelle von:</span><span class="sxs-lookup"><span data-stu-id="0cc9b-386">Instead of this:</span></span>

```fsharp
member this.Transform(f: int->int) =
    ...
```

<span data-ttu-id="0cc9b-387">Gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="0cc9b-387">Do this:</span></span>

```fsharp
member this.Transform(f: Func<int,int>) =
    ...
```

<span data-ttu-id="0cc9b-388">Der F #-Funktionstyp `class FSharpFunc<T,U>` wird als zu anderen .NET-Sprachen angezeigt und ist weniger geeignet für sprach Features und Tools, die Delegattypen verstehen.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-388">The F# function type appears as `class FSharpFunc<T,U>` to other .NET languages, and is less suitable for language features and tooling that understands delegate types.</span></span> <span data-ttu-id="0cc9b-389">Beim Erstellen einer höherwertigen Methode, die auf .NET Framework 3,5 oder höher ausgerichtet ist, sind die Delegaten `System.Func` und `System.Action` die richtigen APIs für die Veröffentlichung, damit .NET-Entwickler diese APIs auf wenig reibungslose Weise nutzen können.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-389">When authoring a higher-order method targeting .NET Framework 3.5 or higher, the `System.Func` and `System.Action` delegates are the right APIs to publish to enable .NET developers to consume these APIs in a low-friction manner.</span></span> <span data-ttu-id="0cc9b-390">(Bei .NET Framework 2,0 werden die System definierten Delegattypen eingeschränkt. verwenden Sie ggf. vordefinierte Delegattypen, z `System.Converter<T,U>` . b., oder definieren Sie einen bestimmten Delegattyp.)</span><span class="sxs-lookup"><span data-stu-id="0cc9b-390">(When targeting .NET Framework 2.0, the system-defined delegate types are more limited; consider using predefined delegate types such as `System.Converter<T,U>` or defining a specific delegate type.)</span></span>

<span data-ttu-id="0cc9b-391">Auf der Flip-Seite sind .net-Delegaten bei f #-orientierten Bibliotheken nicht von Belang (Weitere Informationen finden Sie im nächsten Abschnitt zu f #-orientierten Bibliotheken).</span><span class="sxs-lookup"><span data-stu-id="0cc9b-391">On the flip side, .NET delegates are not natural for F#-facing libraries (see the next Section on F#-facing libraries).</span></span> <span data-ttu-id="0cc9b-392">Daher besteht eine gängige Implementierungsstrategie beim Entwickeln von Methoden höherer Ordnung für die Verwendung von .NET-Bibliotheken darin, die gesamte Implementierung mithilfe von f #-Funktionstypen zu verfassen und dann die öffentliche API mithilfe von Delegaten als schlanke Fassade auf der eigentlichen f #-Implementierung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-392">As a result, a common implementation strategy when developing higher-order methods for vanilla .NET libraries is to author all the implementation using F# function types, and then create the public API using delegates as a thin façade atop the actual F# implementation.</span></span>

#### <a name="use-the-trygetvalue-pattern-instead-of-returning-f-option-values-and-prefer-method-overloading-to-taking-f-option-values-as-arguments"></a><span data-ttu-id="0cc9b-393">Verwenden Sie das TryGetValue-Muster anstelle der Rückgabe von f #-Options Werten, und bevorzugen Sie Methoden Überladung, um f #-Optionswerte als Argumente zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-393">Use the TryGetValue pattern instead of returning F# option values, and prefer method overloading to taking F# option values as arguments</span></span>

<span data-ttu-id="0cc9b-394">Gängige Verwendungs Muster für den F #-Optionstyp in APIs sind in den .NET-APIs von .NET mithilfe von .NET-Standard Entwurfs Techniken besser implementiert.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-394">Common patterns of use for the F# option type in APIs are better implemented in vanilla .NET APIs using standard .NET design techniques.</span></span> <span data-ttu-id="0cc9b-395">Anstatt einen F #-Optionswert zurückzugeben, sollten Sie den booleschen Rückgabetyp plus einen out-Parameter wie im "TryGetValue"-Muster verwenden.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-395">Instead of returning an F# option value, consider using the bool return type plus an out parameter as in the "TryGetValue" pattern.</span></span> <span data-ttu-id="0cc9b-396">Anstatt die F #-Optionswerte als Parameter zu verwenden, sollten Sie die Verwendung von Methoden Überladungen oder optionalen Argumenten in Erwägung ziehen.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-396">And instead of taking F# option values as parameters, consider using method overloading or optional arguments.</span></span>

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

#### <a name="use-the-net-collection-interface-types-ienumerablet-and-idictionarykeyvalue-for-parameters-and-return-values"></a><span data-ttu-id="0cc9b-397">Verwenden Sie die .net-Auflistungs Schnittstellentypen IEnumerable \< T \> und IDictionary \< Key, Wert \> für Parameter und Rückgabewerte.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-397">Use the .NET collection interface types IEnumerable\<T\> and IDictionary\<Key,Value\> for parameters and return values</span></span>

<span data-ttu-id="0cc9b-398">Vermeiden Sie die Verwendung von konkreten Auflistungs Typen wie .NET-Arrays `T[]` , F #-Typen und und konkreten Auflistungs `list<T>` Typen von .net, `Map<Key,Value>` `Set<T>` wie z `Dictionary<Key,Value>` . b..</span><span class="sxs-lookup"><span data-stu-id="0cc9b-398">Avoid the use of concrete collection types such as .NET arrays `T[]`, F# types `list<T>`, `Map<Key,Value>` and `Set<T>`, and .NET concrete collection types such as `Dictionary<Key,Value>`.</span></span> <span data-ttu-id="0cc9b-399">Die Entwurfs Richtlinien für .NET-Bibliotheken bieten gute Ratschläge hinsichtlich der Verwendung verschiedener Sammlungs Typen wie `IEnumerable<T>` .</span><span class="sxs-lookup"><span data-stu-id="0cc9b-399">The .NET Library Design Guidelines have good advice regarding when to use various collection types like `IEnumerable<T>`.</span></span> <span data-ttu-id="0cc9b-400">Die Verwendung von Arrays ( `T[]` ) ist unter bestimmten Umständen in Leistungsgründen akzeptabel.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-400">Some use of arrays (`T[]`) is acceptable in some circumstances, on performance grounds.</span></span> <span data-ttu-id="0cc9b-401">Beachten Sie insbesondere, dass `seq<T>` es sich bei nur um den F #-Alias für handelt und dass es sich bei der `IEnumerable<T>` .NET-API oft um einen geeigneten Typ handelt.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-401">Note especially that `seq<T>` is just the F# alias for `IEnumerable<T>`, and thus seq is often an appropriate type for a vanilla .NET API.</span></span>

<span data-ttu-id="0cc9b-402">Anstelle von F #-Listen:</span><span class="sxs-lookup"><span data-stu-id="0cc9b-402">Instead of F# lists:</span></span>

```fsharp
member this.PrintNames(names: string list) =
    ...
```

<span data-ttu-id="0cc9b-403">F #-Sequenzen verwenden:</span><span class="sxs-lookup"><span data-stu-id="0cc9b-403">Use F# sequences:</span></span>

```fsharp
member this.PrintNames(names: seq<string>) =
    ...
```

#### <a name="use-the-unit-type-as-the-only-input-type-of-a-method-to-define-a-zero-argument-method-or-as-the-only-return-type-to-define-a-void-returning-method"></a><span data-ttu-id="0cc9b-404">Verwenden Sie den Unit-Typ als einzigen Eingabetyp einer Methode, um eine Methode mit 0 (null) zu definieren, oder als einzigen Rückgabetyp, um eine Methode mit void-Rückgabe zu definieren.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-404">Use the unit type as the only input type of a method to define a zero-argument method, or as the only return type to define a void-returning method</span></span>

<span data-ttu-id="0cc9b-405">Vermeiden Sie andere Verwendungsmöglichkeiten des Einheits Typs.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-405">Avoid other uses of the unit type.</span></span> <span data-ttu-id="0cc9b-406">Diese sind gut geeignet:</span><span class="sxs-lookup"><span data-stu-id="0cc9b-406">These are good:</span></span>

```fsharp
✔ member this.NoArguments() = 3

✔ member this.ReturnVoid(x: int) = ()
```

<span data-ttu-id="0cc9b-407">Dies ist schlecht:</span><span class="sxs-lookup"><span data-stu-id="0cc9b-407">This is bad:</span></span>

```fsharp
member this.WrongUnit( x: unit, z: int) = ((), ())
```

#### <a name="check-for-null-values-on-vanilla-net-api-boundaries"></a><span data-ttu-id="0cc9b-408">Überprüfen auf NULL-Werte in den Grenzen der .NET-API</span><span class="sxs-lookup"><span data-stu-id="0cc9b-408">Check for null values on vanilla .NET API boundaries</span></span>

<span data-ttu-id="0cc9b-409">F #-Implementierungs Code verfügt tendenziell über weniger NULL-Werte, da unveränderliche Entwurfsmuster und Einschränkungen bei der Verwendung von NULL-literalen für F #-Typen vorliegen.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-409">F# implementation code tends to have fewer null values, due to immutable design patterns and restrictions on use of null literals for F# types.</span></span> <span data-ttu-id="0cc9b-410">Bei anderen .NET-Sprachen wird häufig NULL als Wert verwendet.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-410">Other .NET languages often use null as a value much more frequently.</span></span> <span data-ttu-id="0cc9b-411">Aus diesem Grund sollte F #-Code, der eine Vanille-. NET-API verfügbar macht, die Parameter auf NULL an der API-Grenze überprüfen und verhindern, dass diese Werte tiefer in den F #-Implementierungs Code fließen.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-411">Because of this, F# code that is exposing a vanilla .NET API should check parameters for null at the API boundary, and prevent these values from flowing deeper into the F# implementation code.</span></span> <span data-ttu-id="0cc9b-412">Die `isNull` Funktions-oder Muster Übereinstimmung für das `null` Muster kann verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-412">The `isNull` function or pattern matching on the `null` pattern can be used.</span></span>

```fsharp
let checkNonNull argName (arg: obj) =
    match arg with
    | null -> nullArg argName
    | _ -> ()

let checkNonNull` argName (arg: obj) =
    if isNull arg then nullArg argName
    else ()
```

#### <a name="avoid-using-tuples-as-return-values"></a><span data-ttu-id="0cc9b-413">Vermeiden der Verwendung von Tupeln als Rückgabewerte</span><span class="sxs-lookup"><span data-stu-id="0cc9b-413">Avoid using tuples as return values</span></span>

<span data-ttu-id="0cc9b-414">Stattdessen sollten Sie lieber einen benannten Typ zurückgeben, der die aggregierten Daten enthält, oder out-Parameter verwenden, um mehrere Werte zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-414">Instead, prefer returning a named type holding the aggregate data, or using out parameters to return multiple values.</span></span> <span data-ttu-id="0cc9b-415">Obwohl Tupel und strukturtupel in .net vorhanden sind (einschließlich der c#-Sprachunterstützung für strukturtupel), stellen Sie am häufigsten nicht die ideale und erwartete API für .NET-Entwickler bereit.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-415">Although tuples and struct tuples exist in .NET (including C# language support for struct tuples), they will most often not provide the ideal and expected API for .NET developers.</span></span>

#### <a name="avoid-the-use-of-currying-of-parameters"></a><span data-ttu-id="0cc9b-416">Vermeiden Sie die Verwendung von Parametern.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-416">Avoid the use of currying of parameters</span></span>

<span data-ttu-id="0cc9b-417">Verwenden Sie stattdessen .net-Aufruf Konventionen `Method(arg1,arg2,…,argN)` .</span><span class="sxs-lookup"><span data-stu-id="0cc9b-417">Instead, use .NET calling conventions `Method(arg1,arg2,…,argN)`.</span></span>

```fsharp
member this.TupledArguments(str, num) = String.replicate num str
```

<span data-ttu-id="0cc9b-418">Tipp: Wenn Sie Bibliotheken für die Verwendung in einer beliebigen .NET-Sprache entwerfen, gibt es keinen Ersatz für die eigentliche Durchführung von experimentellen c#-und Visual Basic Programmierung, um sicherzustellen, dass Ihre Bibliotheken in den folgenden Sprachen richtig aussehen.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-418">Tip: If you're designing libraries for use from any .NET language, then there's no substitute for actually doing some experimental C# and Visual Basic programming to ensure that your libraries "feel right" from these languages.</span></span> <span data-ttu-id="0cc9b-419">Sie können auch Tools wie .net Reflektor und die Visual Studio-Objektkatalog verwenden, um sicherzustellen, dass Bibliotheken und deren Dokumentation Entwicklern erwartungsgemäß angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-419">You can also use tools such as .NET Reflector and the Visual Studio Object Browser to ensure that libraries and their documentation appear as expected to developers.</span></span>

## <a name="appendix"></a><span data-ttu-id="0cc9b-420">Anhang</span><span class="sxs-lookup"><span data-stu-id="0cc9b-420">Appendix</span></span>

### <a name="end-to-end-example-of-designing-f-code-for-use-by-other-net-languages"></a><span data-ttu-id="0cc9b-421">End-to-End-Beispiel für das Entwerfen von F #-Code für die Verwendung durch andere .NET-Sprachen</span><span class="sxs-lookup"><span data-stu-id="0cc9b-421">End-to-end example of designing F# code for use by other .NET languages</span></span>

<span data-ttu-id="0cc9b-422">Beachten Sie die folgende Klasse:</span><span class="sxs-lookup"><span data-stu-id="0cc9b-422">Consider the following class:</span></span>

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

<span data-ttu-id="0cc9b-423">Der abherleitet F #-Typ dieser Klasse lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="0cc9b-423">The inferred F# type of this class is as follows:</span></span>

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

<span data-ttu-id="0cc9b-424">Sehen wir uns nun an, wie dieser F #-Typ einem Programmierer mit einer anderen .NET-Sprache erscheint.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-424">Let's take a look at how this F# type appears to a programmer using another .NET language.</span></span> <span data-ttu-id="0cc9b-425">Die ungefähre c#-Signatur lautet z. b. wie folgt:</span><span class="sxs-lookup"><span data-stu-id="0cc9b-425">For example, the approximate C# "signature" is as follows:</span></span>

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

<span data-ttu-id="0cc9b-426">Es gibt einige wichtige Punkte zu beachten, wie F # hier Konstrukte repräsentiert.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-426">There are some important points to notice about how F# represents constructs here.</span></span> <span data-ttu-id="0cc9b-427">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0cc9b-427">For example:</span></span>

* <span data-ttu-id="0cc9b-428">Metadaten, wie z. b. Argument Namen, wurden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-428">Metadata such as argument names has been preserved.</span></span>

* <span data-ttu-id="0cc9b-429">F #-Methoden, die zwei Argumente annehmen, werden zu c#-Methoden, die zwei Argumente annehmen.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-429">F# methods that take two arguments become C# methods that take two arguments.</span></span>

* <span data-ttu-id="0cc9b-430">Funktionen und Listen werden zu verweisen auf die entsprechenden Typen in der F #-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-430">Functions and lists become references to corresponding types in the F# library.</span></span>

<span data-ttu-id="0cc9b-431">Der folgende Code zeigt, wie Sie diesen Code anpassen können, um diese Aspekte zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-431">The following code shows how to adjust this code to take these things into account.</span></span>

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

<span data-ttu-id="0cc9b-432">Der abherleitet F #-Typ des Codes lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="0cc9b-432">The inferred F# type of the code is as follows:</span></span>

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

<span data-ttu-id="0cc9b-433">Die c#-Signatur lautet nun wie folgt:</span><span class="sxs-lookup"><span data-stu-id="0cc9b-433">The C# signature is now as follows:</span></span>

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

<span data-ttu-id="0cc9b-434">Die zur Vorbereitung dieses Typs für die Verwendung als Teil einer Vanille .NET-Bibliothek erstellten Korrekturen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="0cc9b-434">The fixes made to prepare this type for use as part of a vanilla .NET library are as follows:</span></span>

* <span data-ttu-id="0cc9b-435">Mehrere Namen wurden angepasst: `Point1` , `n` , und `l` `f` wurden `RadialPoint` , `count` , `factor` `transform` bzw..</span><span class="sxs-lookup"><span data-stu-id="0cc9b-435">Adjusted several names: `Point1`, `n`, `l`, and `f` became `RadialPoint`, `count`, `factor`, and `transform`, respectively.</span></span>

* <span data-ttu-id="0cc9b-436">Hat einen Rückgabetyp von `seq<RadialPoint>` anstelle von verwendet `RadialPoint list` , indem eine Listen Konstruktion mithilfe von `[ ... ]` in eine Sequenz Konstruktion geändert wird `IEnumerable<RadialPoint>` .</span><span class="sxs-lookup"><span data-stu-id="0cc9b-436">Used a return type of `seq<RadialPoint>` instead of `RadialPoint list` by changing a list construction using `[ ... ]` to a sequence construction using `IEnumerable<RadialPoint>`.</span></span>

* <span data-ttu-id="0cc9b-437">Verwendet den .net-Delegattyp `System.Func` anstelle eines F #-Funktions Typs.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-437">Used the .NET delegate type `System.Func` instead of an F# function type.</span></span>

<span data-ttu-id="0cc9b-438">Dies macht es viel leichter, in c#-Code zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="0cc9b-438">This makes it far nicer to consume in C# code.</span></span>
