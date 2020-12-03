---
title: 'Breaking Change: Blazor: Unbedeutende Leerzeichen zur Kompilierzeit aus Komponenten entfernt'
description: 'Hier erfahren Sie mehr über den Breaking Change in ASP.NET Core 5.0 mit dem Titel „Blazor: Unbedeutende Leerzeichen zur Kompilierzeit aus Komponenten entfernt'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 92a961bb377bedd27b793c77d4be31ce52179ee2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759536"
---
# <a name="blazor-insignificant-whitespace-trimmed-from-components-at-compile-time"></a><span data-ttu-id="ce095-103">Blazor: Unbedeutende Leerzeichen zur Kompilierzeit aus Komponenten entfernt</span><span class="sxs-lookup"><span data-stu-id="ce095-103">Blazor: Insignificant whitespace trimmed from components at compile time</span></span>

<span data-ttu-id="ce095-104">Ab ASP.NET Core 5.0 Preview 7 werden vom Razor-Compiler in Blazor-Komponenten ( *.razor*-Dateien) zur Kompilierzeit unbedeutende Leerzeichen weggelassen.</span><span class="sxs-lookup"><span data-stu-id="ce095-104">Starting with ASP.NET Core 5.0 Preview 7, the Razor compiler omits insignificant whitespace in Blazor components (*.razor* files) at compile time.</span></span> <span data-ttu-id="ce095-105">Weitere Informationen finden Sie unter dem Issue [dotnet/aspnetcore#23568](https://github.com/dotnet/aspnetcore/issues/23568).</span><span class="sxs-lookup"><span data-stu-id="ce095-105">For discussion, see issue [dotnet/aspnetcore#23568](https://github.com/dotnet/aspnetcore/issues/23568).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="ce095-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="ce095-106">Version introduced</span></span>

<span data-ttu-id="ce095-107">5.0 Preview 7</span><span class="sxs-lookup"><span data-stu-id="ce095-107">5.0 Preview 7</span></span>

## <a name="old-behavior"></a><span data-ttu-id="ce095-108">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="ce095-108">Old behavior</span></span>

<span data-ttu-id="ce095-109">In 3.x-Versionen von Blazor Server und Blazor WebAssembly werden Leerzeichen im Quellcode einer Komponente berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="ce095-109">In 3.x versions of Blazor Server and Blazor WebAssembly, whitespace is honored in a component's source code.</span></span> <span data-ttu-id="ce095-110">Textknoten, die nur Leerzeichen enthalten, werden im Dokumentobjektmodell (DOM) des Browsers auch dann gerendert, wenn dies keine visuellen Auswirkungen hat.</span><span class="sxs-lookup"><span data-stu-id="ce095-110">Whitespace-only text nodes render in the browser's Document Object Model (DOM) even when there's no visual effect.</span></span>

<span data-ttu-id="ce095-111">Sehen Sie sich den folgenden Code für eine Blazor-Komponente an:</span><span class="sxs-lookup"><span data-stu-id="ce095-111">Consider the following Blazor component code:</span></span>

```razor
<ul>
    @foreach (var item in Items)
    {
        <li>
            @item.Text
        </li>
    }
</ul>
```

<span data-ttu-id="ce095-112">Im obigen Beispiel werden zwei Leerzeichenknoten gerendert:</span><span class="sxs-lookup"><span data-stu-id="ce095-112">The preceding example renders two whitespace nodes:</span></span>

* <span data-ttu-id="ce095-113">Außerhalb des Codeblocks `@foreach`.</span><span class="sxs-lookup"><span data-stu-id="ce095-113">Outside of the `@foreach` code block.</span></span>
* <span data-ttu-id="ce095-114">Im Bereich des Elements `<li>`.</span><span class="sxs-lookup"><span data-stu-id="ce095-114">Around the `<li>` element.</span></span>
* <span data-ttu-id="ce095-115">Im Bereich der Ausgabe `@item.Text`.</span><span class="sxs-lookup"><span data-stu-id="ce095-115">Around the `@item.Text` output.</span></span>

<span data-ttu-id="ce095-116">Eine Liste mit 100 Einträgen führt zu 402 Leerzeichenknoten.</span><span class="sxs-lookup"><span data-stu-id="ce095-116">A list containing 100 items results in 402 whitespace nodes.</span></span> <span data-ttu-id="ce095-117">Dies entspricht mehr als der Hälfte aller gerenderten Knoten, auch wenn keiner der Leerzeichenknoten eine visuelle Auswirkung auf die gerenderte Ausgabe hat.</span><span class="sxs-lookup"><span data-stu-id="ce095-117">That's over half of all nodes rendered, even though none of the whitespace nodes visually affect the rendered output.</span></span>

<span data-ttu-id="ce095-118">Beim Rendern von statischem HTML-Code für Komponenten wurden Leerzeichen innerhalb eines Tags nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="ce095-118">When rendering static HTML for components, whitespace inside a tag wasn't preserved.</span></span> <span data-ttu-id="ce095-119">Sehen Sie sich beispielsweise die Quelle der folgenden Komponente an:</span><span class="sxs-lookup"><span data-stu-id="ce095-119">For example, view the source of the following component:</span></span>

```razor
<foo        bar="baz"     />
```

<span data-ttu-id="ce095-120">Leerzeichen werden nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="ce095-120">Whitespace isn't preserved.</span></span> <span data-ttu-id="ce095-121">Die vorab gerenderte Ausgabe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ce095-121">The pre-rendered output is:</span></span>

```razor
<foo bar="baz" />
```

## <a name="new-behavior"></a><span data-ttu-id="ce095-122">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="ce095-122">New behavior</span></span>

<span data-ttu-id="ce095-123">Sofern nicht die Anweisung `@preservewhitespace` mit dem Wert `true` verwendet wird, werden Leerzeichenknoten entfernt, wenn dafür Folgendes gilt:</span><span class="sxs-lookup"><span data-stu-id="ce095-123">Unless the `@preservewhitespace` directive is used with value `true`, whitespace nodes are removed if they:</span></span>

* <span data-ttu-id="ce095-124">Stehen in einem Element am Anfang oder am Ende.</span><span class="sxs-lookup"><span data-stu-id="ce095-124">Are leading or trailing within an element.</span></span>
* <span data-ttu-id="ce095-125">Stehen in einem `RenderFragment`-Parameter am Anfang oder am Ende.</span><span class="sxs-lookup"><span data-stu-id="ce095-125">Are leading or trailing within a `RenderFragment` parameter.</span></span> <span data-ttu-id="ce095-126">Ein Beispiel hierfür ist untergeordneter Inhalt, der an eine andere Komponente übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="ce095-126">For example, child content being passed to another component.</span></span>
* <span data-ttu-id="ce095-127">Stehen am Anfang oder Ende eines C#-Codeblocks, z. B. `@if` und `@foreach`.</span><span class="sxs-lookup"><span data-stu-id="ce095-127">Precede or follow a C# code block such as `@if` and `@foreach`.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="ce095-128">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="ce095-128">Reason for change</span></span>

<span data-ttu-id="ce095-129">Ein Ziel für Blazor in ASP.NET Core 5.0 ist die Verbesserung der Leistung beim Rendern und Vergleichen.</span><span class="sxs-lookup"><span data-stu-id="ce095-129">A goal for Blazor in ASP.NET Core 5.0 is to improve the performance of rendering and diffing.</span></span> <span data-ttu-id="ce095-130">Für Strukturknoten mit unbedeutenden Leerzeichen wurden bei Benchmarktests bis zu 40 Prozent der Renderzeit verbraucht.</span><span class="sxs-lookup"><span data-stu-id="ce095-130">Insignificant whitespace tree nodes consumed up to 40 percent of the rendering time in benchmarks.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="ce095-131">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="ce095-131">Recommended action</span></span>

<span data-ttu-id="ce095-132">In den meisten Fällen ergeben sich keinerlei Auswirkungen auf das visuelle Layout der gerenderten Komponente.</span><span class="sxs-lookup"><span data-stu-id="ce095-132">In most cases, the visual layout of the rendered component is unaffected.</span></span> <span data-ttu-id="ce095-133">Das Entfernen der Leerzeichen kann sich aber auf die gerenderte Ausgabe auswirken, wenn eine CSS-Regel wie `white-space: pre` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ce095-133">However, the whitespace removal might affect the rendered output when using a CSS rule like `white-space: pre`.</span></span> <span data-ttu-id="ce095-134">Führen Sie eine der folgenden Aktionen durch, um diese Leistungsoptimierung zu deaktivieren und die Leerzeichen beizubehalten:</span><span class="sxs-lookup"><span data-stu-id="ce095-134">To disable this performance optimization and preserve the whitespace, take one of the following actions:</span></span>

* <span data-ttu-id="ce095-135">Fügen Sie oben in der *.razor*-Datei die Anweisung `@preservewhitespace true` hinzu, um sie auf eine bestimmte Komponente anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="ce095-135">Add the `@preservewhitespace true` directive at the top of the *.razor* file to apply the preference to a specific component.</span></span>
* <span data-ttu-id="ce095-136">Fügen Sie die Anweisung `@preservewhitespace true` in einer *_Imports.razor*-Datei hinzu, um sie auf ein gesamtes Unterverzeichnis oder das gesamte Projekt anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="ce095-136">Add the `@preservewhitespace true` directive inside an *_Imports.razor* file to apply the preference to an entire subdirectory or the entire project.</span></span>

<span data-ttu-id="ce095-137">In den meisten Fällen ist keine Aktion erforderlich, weil sich Anwendungen normalerweise wie gewohnt (aber schneller) verhalten.</span><span class="sxs-lookup"><span data-stu-id="ce095-137">In most cases, no action is required, as applications will typically continue to behave normally (but faster).</span></span> <span data-ttu-id="ce095-138">Falls das Entfernen der Leerzeichen für eine bestimmte Komponente zu Problemen führt, sollten Sie darin `@preservewhitespace true` nutzen, um diese Optimierung zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="ce095-138">If the whitespace stripping causes any problems for a particular component, use `@preservewhitespace true` in that component to disable this optimization.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="ce095-139">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="ce095-139">Affected APIs</span></span>

<span data-ttu-id="ce095-140">Keine</span><span class="sxs-lookup"><span data-stu-id="ce095-140">None</span></span>

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
