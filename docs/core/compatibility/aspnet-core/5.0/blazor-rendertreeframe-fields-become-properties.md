---
title: 'Breaking Change: Blazor: Schreibgeschützte öffentliche RenderTreeFrame-Felder sind jetzt Eigenschaften'
description: 'Hier erfahren Sie mehr über den Breaking Change in ASP.NET Core 5.0 mit dem Titel „Blazor: Schreibgeschützte öffentliche RenderTreeFrame-Felder sind jetzt Eigenschaften'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: e9da9c538cc0a8ed4f138ef64ece0c7d144f28d3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759205"
---
# <a name="blazor-rendertreeframe-readonly-public-fields-have-become-properties"></a><span data-ttu-id="6da6c-103">Blazor: Schreibgeschützte öffentliche RenderTreeFrame-Felder sind jetzt Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="6da6c-103">Blazor: RenderTreeFrame readonly public fields have become properties</span></span>

<span data-ttu-id="6da6c-104">In ASP.NET Core 3.0 und 3.1 machte die <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame>-Struktur verschiedene `readonly public`-Felder verfügbar, u. a. <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.FrameType> und <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="6da6c-104">In ASP.NET Core 3.0 and 3.1, the <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame> struct exposed various `readonly public` fields, including <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.FrameType>, <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.Sequence>, and others.</span></span> <span data-ttu-id="6da6c-105">Ab ASP.NET Core 5.0 RC1 wurden alle `readonly public`-Felder in `readonly public`-Eigenschaften geändert.</span><span class="sxs-lookup"><span data-stu-id="6da6c-105">In ASP.NET Core 5.0 RC1 and later versions, all the `readonly public` fields changed to `readonly public` properties.</span></span>

<span data-ttu-id="6da6c-106">Diese Änderung wirkt sich aus folgenden Gründen nicht auf viele Entwickler aus:</span><span class="sxs-lookup"><span data-stu-id="6da6c-106">This change won't affect many developers because:</span></span>

* <span data-ttu-id="6da6c-107">Jede Anwendung oder Bibliothek, die einfach `.razor`-Dateien (oder sogar manuelle <xref:Microsoft.AspNetCore.Components.Rendering.RenderTreeBuilder>-Aufrufe) verwendet, um ihre Komponenten zu definieren, würde nicht direkt auf diesen Typ verweisen.</span><span class="sxs-lookup"><span data-stu-id="6da6c-107">Any app or library that simply uses `.razor` files (or even manual <xref:Microsoft.AspNetCore.Components.Rendering.RenderTreeBuilder> calls) to define its components wouldn't be referencing this type directly.</span></span>
* <span data-ttu-id="6da6c-108">Der Typ `RenderTreeFrame` selbst wird als Implementierungsdetail betrachtet, das nicht für eine Verwendung außerhalb des Frameworks vorgesehen ist.</span><span class="sxs-lookup"><span data-stu-id="6da6c-108">The `RenderTreeFrame` type itself is regarded as an implementation detail, not intended for use outside of the framework.</span></span> <span data-ttu-id="6da6c-109">Ab ASP.NET Core 3.0 steht ein Analysetool zur Verfügung, das Compilerwarnungen ausgibt, wenn der Typ direkt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6da6c-109">ASP.NET Core 3.0 and later includes an analyzer that issues compiler warnings if the type is being used directly.</span></span>
* <span data-ttu-id="6da6c-110">Selbst wenn Sie direkt auf `RenderTreeFrame` verweisen, ist diese Änderung ein binärer Breaking Change, aber kein Breaking Change im Quellcode.</span><span class="sxs-lookup"><span data-stu-id="6da6c-110">Even if you reference `RenderTreeFrame` directly, this change is binary-breaking but not source-breaking.</span></span> <span data-ttu-id="6da6c-111">Das heißt, dass der vorhandene Quellcode kompiliert wird und sich verhält ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="6da6c-111">That is, your existing source code will compile and behave properly.</span></span> <span data-ttu-id="6da6c-112">Sie werden nur dann auf ein Problem stoßen, wenn Sie mit einem .NET Core 3.x-Framework kompilieren und diese Binärdateien dann mit dem .NET 5.0 RC1-Framework und höher ausführen.</span><span class="sxs-lookup"><span data-stu-id="6da6c-112">You'll only encounter an issue if compiling against a .NET Core 3.x framework and then running those binaries against the .NET 5.0 RC1 and later framework.</span></span>

<span data-ttu-id="6da6c-113">Weitere Informationen finden Sie unter GitHub-Issue [dotnet/aspnetcore#25727](https://github.com/dotnet/aspnetcore/issues/25727).</span><span class="sxs-lookup"><span data-stu-id="6da6c-113">For discussion, see GitHub issue [dotnet/aspnetcore#25727](https://github.com/dotnet/aspnetcore/issues/25727).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="6da6c-114">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="6da6c-114">Version introduced</span></span>

<span data-ttu-id="6da6c-115">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="6da6c-115">5.0 RC1</span></span>

## <a name="old-behavior"></a><span data-ttu-id="6da6c-116">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="6da6c-116">Old behavior</span></span>

<span data-ttu-id="6da6c-117">Öffentliche Member in `RenderTreeFrame` werden als Felder definiert.</span><span class="sxs-lookup"><span data-stu-id="6da6c-117">Public members on `RenderTreeFrame` are defined as fields.</span></span> <span data-ttu-id="6da6c-118">Beispiel: `renderTreeFrame.Sequence` und `renderTreeFrame.ElementName`.</span><span class="sxs-lookup"><span data-stu-id="6da6c-118">For example, `renderTreeFrame.Sequence` and `renderTreeFrame.ElementName`.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="6da6c-119">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="6da6c-119">New behavior</span></span>

<span data-ttu-id="6da6c-120">Öffentliche Member in `RenderTreeFrame` werden als Eigenschaften mit denselben Namen wie zuvor definiert.</span><span class="sxs-lookup"><span data-stu-id="6da6c-120">Public members on `RenderTreeFrame` are defined as properties with the same names as before.</span></span> <span data-ttu-id="6da6c-121">Beispiel: `renderTreeFrame.Sequence` und `renderTreeFrame.ElementName`.</span><span class="sxs-lookup"><span data-stu-id="6da6c-121">For example, `renderTreeFrame.Sequence` and `renderTreeFrame.ElementName`.</span></span>

<span data-ttu-id="6da6c-122">Wenn älterer vorkompilierter Code seit dieser Änderung nicht neu kompiliert wurde, kann er eine Ausnahme ähnlich dieser auslösen: *MissingFieldException: Feld nicht gefunden: Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.FrameType*.</span><span class="sxs-lookup"><span data-stu-id="6da6c-122">If older precompiled code hasn't been recompiled since this change, it may throw an exception similar to *MissingFieldException: Field not found: 'Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.FrameType'*.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="6da6c-123">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="6da6c-123">Reason for change</span></span>

<span data-ttu-id="6da6c-124">Diese Änderung war notwendig, um erhebliche Leistungsverbesserungen beim Rendering von Blazor-Komponenten in ASP.NET Core 5.0 zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="6da6c-124">This change was necessary to implement high-impact performance improvements in Blazor component rendering in ASP.NET Core 5.0.</span></span> <span data-ttu-id="6da6c-125">Die gleichen Sicherheits- und Kapselungsebenen bleiben erhalten.</span><span class="sxs-lookup"><span data-stu-id="6da6c-125">The same levels of safety and encapsulation are maintained.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="6da6c-126">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="6da6c-126">Recommended action</span></span>

<span data-ttu-id="6da6c-127">Die meisten Blazor-Entwickler sind von dieser Änderung nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="6da6c-127">Most Blazor developers are unaffected by this change.</span></span> <span data-ttu-id="6da6c-128">Die Änderung betrifft eher Ersteller von Bibliotheken und Paketen, aber nur in seltenen Fällen.</span><span class="sxs-lookup"><span data-stu-id="6da6c-128">The change is more likely to affect library and package authors, but only in rare cases.</span></span> <span data-ttu-id="6da6c-129">Das gibt insbesondere, wenn Sie Folgendes entwickeln:</span><span class="sxs-lookup"><span data-stu-id="6da6c-129">Specifically, if you're developing:</span></span>

* <span data-ttu-id="6da6c-130">Eine App und mit ASP.NET Core 3.x arbeiten oder ein Upgrade auf mindestens 5.0 RC1 vornehmen. Dann brauchen Sie Ihren eigenen Code nicht zu ändern.</span><span class="sxs-lookup"><span data-stu-id="6da6c-130">An app and using ASP.NET Core 3.x or upgrading to 5.0 RC1 or later, you don't need to change your own code.</span></span> <span data-ttu-id="6da6c-131">Wenn Sie jedoch von einer Bibliothek abhängig sind, für die ein Upgrade erfolgt ist, um diese Änderung zu berücksichtigen, müssen Sie auf eine neuere Version dieser Bibliothek aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="6da6c-131">However, if you depend on a library that upgraded to account for this change, then you need to update to a newer version of that library.</span></span>
* <span data-ttu-id="6da6c-132">Eine Bibliothek und nur ASP.NET Core 5.0 RC1 oder höher unterstützen möchten. Dann ist keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6da6c-132">A library and want to support only ASP.NET Core 5.0 RC1 or later, no action is needed.</span></span> <span data-ttu-id="6da6c-133">Stellen Sie einfach sicher, dass Ihre Projektdatei den `<TargetFramework>`-Wert `net5.0` oder eine spätere Version deklariert.</span><span class="sxs-lookup"><span data-stu-id="6da6c-133">Just ensure that your project file declares a `<TargetFramework>` value of `net5.0` or a later version.</span></span>
* <span data-ttu-id="6da6c-134">Eine Bibliothek und Sie sowohl ASP.NET Core 3.x *und* 5.0 unterstützen möchten. Dann müssen Sie bestimmen, ob Ihr Code `RenderTreeFrame`-Member liest.</span><span class="sxs-lookup"><span data-stu-id="6da6c-134">A library and want to support both ASP.NET Core 3.x *and* 5.0, determine whether your code reads any `RenderTreeFrame` members.</span></span> <span data-ttu-id="6da6c-135">Beispielsweise beim Auswerten von `someRenderTreeFrame.FrameType`.</span><span class="sxs-lookup"><span data-stu-id="6da6c-135">For example, evaluating `someRenderTreeFrame.FrameType`.</span></span>
  * <span data-ttu-id="6da6c-136">Die meisten Bibliotheken lesen keine `RenderTreeFrame`-Member, einschließlich Bibliotheken mit `.razor`-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="6da6c-136">Most libraries won't read `RenderTreeFrame` members, including libraries that contain `.razor` components.</span></span> <span data-ttu-id="6da6c-137">In diesem Fall ist keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6da6c-137">In this case, no action is needed.</span></span>
  * <span data-ttu-id="6da6c-138">Wenn Ihre Bibliothek dies jedoch tut, müssen Sie mehrere Ziele abdecken, um sowohl `netstandard2.1` als auch `net5.0` zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="6da6c-138">However, if your library does that, you'll need to multi-target to support both `netstandard2.1` and `net5.0`.</span></span> <span data-ttu-id="6da6c-139">Wenden Sie die folgenden Änderungen in Ihrer Projektdatei an:</span><span class="sxs-lookup"><span data-stu-id="6da6c-139">Apply the following changes in your project file:</span></span>
    * <span data-ttu-id="6da6c-140">Ersetzen Sie das vorhandene `<TargetFramework>`-Element durch `<TargetFrameworks>netstandard2.0;net5.0</TargetFrameworks>`.</span><span class="sxs-lookup"><span data-stu-id="6da6c-140">Replace the existing `<TargetFramework>` element with `<TargetFrameworks>netstandard2.0;net5.0</TargetFrameworks>`.</span></span>
    * <span data-ttu-id="6da6c-141">Verwenden Sie einen bedingten Verweis auf das `Microsoft.AspNetCore.Components`-Paket, um beide Versionen zu berücksichtigen, die Sie unterstützen möchten.</span><span class="sxs-lookup"><span data-stu-id="6da6c-141">Use a conditional `Microsoft.AspNetCore.Components` package reference to account for both versions you wish to support.</span></span> <span data-ttu-id="6da6c-142">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6da6c-142">For example:</span></span>

        ```xml
        <PackageReference Include="Microsoft.AspNetCore.Components" Version="3.0.0" Condition="'$(TargetFramework)' == 'netstandard2.0'" />
        <PackageReference Include="Microsoft.AspNetCore.Components" Version="5.0.0-rc.1.*" Condition="'$(TargetFramework)' != 'netstandard2.0'" />
        ```

<span data-ttu-id="6da6c-143">Weitere Erläuterungen finden sich in diesem [-Diff, das zeigt, wie @jsakamoto bereits die `Toolbelt.Blazor.HeadElement` Bibliothek](https://github.com/jsakamoto/Toolbelt.Blazor.HeadElement/commit/090df430ba725f9420d412753db8104e8c32bf51) aktualisiert hat.</span><span class="sxs-lookup"><span data-stu-id="6da6c-143">For further clarification, see this [diff showing how @jsakamoto already upgraded the `Toolbelt.Blazor.HeadElement` library](https://github.com/jsakamoto/Toolbelt.Blazor.HeadElement/commit/090df430ba725f9420d412753db8104e8c32bf51).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="6da6c-144">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="6da6c-144">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`T:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame`

-->
