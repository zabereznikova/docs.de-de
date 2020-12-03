---
title: 'Breaking Change: Lokalisierung: ResourceManagerWithCultureStringLocalizer-Klasse und WithCulture-Schnittstellenmember entfernt'
description: 'Hier erfahren Sie mehr über den Breaking Change in ASP.NET Core 5.0 mit dem Titel „Lokalisierung: ResourceManagerWithCultureStringLocalizer-Klasse und WithCulture-Schnittstellenmember entfernt'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: cba8458f20bad77ad6c125448f192939387ba405
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759520"
---
# <a name="localization-resourcemanagerwithculturestringlocalizer-class-and-withculture-interface-member-removed"></a><span data-ttu-id="f00b1-103">Lokalisierung: ResourceManagerWithCultureStringLocalizer-Klasse und WithCulture-Schnittstellenmember entfernt</span><span class="sxs-lookup"><span data-stu-id="f00b1-103">Localization: ResourceManagerWithCultureStringLocalizer class and WithCulture interface member removed</span></span>

<span data-ttu-id="f00b1-104">Die [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1)-Klasse und die [WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1)-Methode wurden in .NET 5.0 Preview 1 entfernt.</span><span class="sxs-lookup"><span data-stu-id="f00b1-104">The [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) class and [WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) method were removed in .NET 5.0 Preview 1.</span></span>

<span data-ttu-id="f00b1-105">Weitere Informationen finden Sie unter [aspnet/Announcements#346](https://github.com/aspnet/Announcements/issues/346) und [dotnet/aspnetcore#3324](https://github.com/dotnet/aspnetcore/issues/3324).</span><span class="sxs-lookup"><span data-stu-id="f00b1-105">For context, see [aspnet/Announcements#346](https://github.com/aspnet/Announcements/issues/346) and [dotnet/aspnetcore#3324](https://github.com/dotnet/aspnetcore/issues/3324).</span></span> <span data-ttu-id="f00b1-106">Diese Änderung wird unter [dotnet/aspnetcore#7756](https://github.com/dotnet/aspnetcore/issues/7756) behandelt.</span><span class="sxs-lookup"><span data-stu-id="f00b1-106">For discussion on this change, see [dotnet/aspnetcore#7756](https://github.com/dotnet/aspnetcore/issues/7756).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="f00b1-107">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="f00b1-107">Version introduced</span></span>

<span data-ttu-id="f00b1-108">5.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="f00b1-108">5.0 Preview 1</span></span>

## <a name="old-behavior"></a><span data-ttu-id="f00b1-109">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="f00b1-109">Old behavior</span></span>

<span data-ttu-id="f00b1-110">Die `ResourceManagerWithCultureStringLocalizer`-Klasse und die `ResourceManagerStringLocalizer.WithCulture`-Methode gelten in [.NET Core 3.0 Preview 3 und höher](../../../../core/compatibility/2.2-3.0.md#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete) als veraltet.</span><span class="sxs-lookup"><span data-stu-id="f00b1-110">The `ResourceManagerWithCultureStringLocalizer` class and the `ResourceManagerStringLocalizer.WithCulture` method are [obsolete in .NET Core 3.0 Preview 3 and later](../../../../core/compatibility/2.2-3.0.md#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete).</span></span>

## <a name="new-behavior"></a><span data-ttu-id="f00b1-111">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="f00b1-111">New behavior</span></span>

<span data-ttu-id="f00b1-112">Die `ResourceManagerWithCultureStringLocalizer`-Klasse und die `ResourceManagerStringLocalizer.WithCulture`-Methode wurden in .NET 5.0 Preview 1 entfernt.</span><span class="sxs-lookup"><span data-stu-id="f00b1-112">The `ResourceManagerWithCultureStringLocalizer` class and the `ResourceManagerStringLocalizer.WithCulture` method have been removed in .NET 5.0 Preview 1.</span></span> <span data-ttu-id="f00b1-113">Eine Übersicht über die vorgenommenen Änderungen finden Sie im Pull Request unter [dotnet/extensions#2562](https://github.com/dotnet/extensions/pull/2562/files).</span><span class="sxs-lookup"><span data-stu-id="f00b1-113">For an inventory of the changes made, see the pull request at [dotnet/extensions#2562](https://github.com/dotnet/extensions/pull/2562/files).</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="f00b1-114">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="f00b1-114">Reason for change</span></span>

<span data-ttu-id="f00b1-115">Die [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1)-Klasse und die [ResourceManagerStringLocalizer.WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1)-Methode sorgten bei Benutzern mit lokalisierten Versionen häufig für Verwirrung.</span><span class="sxs-lookup"><span data-stu-id="f00b1-115">The [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) class and [ResourceManagerStringLocalizer.WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) method were often sources of confusion for users of localization.</span></span> <span data-ttu-id="f00b1-116">Das galt insbesondere für die Erstellung einer benutzerdefinierten <xref:Microsoft.Extensions.Localization.IStringLocalizer>-Implementierung.</span><span class="sxs-lookup"><span data-stu-id="f00b1-116">The confusion was especially high when creating a custom <xref:Microsoft.Extensions.Localization.IStringLocalizer> implementation.</span></span> <span data-ttu-id="f00b1-117">Diese Klasse und Methode erwecken bei Benutzern den Eindruck, dass eine `IStringLocalizer`-Instanz pro Sprache und pro Ressource gilt.</span><span class="sxs-lookup"><span data-stu-id="f00b1-117">This class and method give consumers the impression that an `IStringLocalizer` instance is expected to be "per-language, per-resource".</span></span> <span data-ttu-id="f00b1-118">Tatsächlich sollte die Instanz nur pro Ressource gelten.</span><span class="sxs-lookup"><span data-stu-id="f00b1-118">In reality, the instance should only be "per-resource".</span></span> <span data-ttu-id="f00b1-119">Zur Laufzeit bestimmt die <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType>-Eigenschaft die zu verwendende Sprache.</span><span class="sxs-lookup"><span data-stu-id="f00b1-119">At run time, the <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> property determines the language to be used.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="f00b1-120">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="f00b1-120">Recommended action</span></span>

<span data-ttu-id="f00b1-121">Verwenden Sie die `ResourceManagerWithCultureStringLocalizer`-Klasse und die `ResourceManagerStringLocalizer.WithCulture`-Methode nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="f00b1-121">Stop using the `ResourceManagerWithCultureStringLocalizer` class and the `ResourceManagerStringLocalizer.WithCulture` method.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="f00b1-122">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="f00b1-122">Affected APIs</span></span>

- [<span data-ttu-id="f00b1-123">ResourceManagerWithCultureStringLocalizer</span><span class="sxs-lookup"><span data-stu-id="f00b1-123">ResourceManagerWithCultureStringLocalizer</span></span>](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1)
- [<span data-ttu-id="f00b1-124">ResourceManagerStringLocalizer.WithCulture</span><span class="sxs-lookup"><span data-stu-id="f00b1-124">ResourceManagerStringLocalizer.WithCulture</span></span>](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1)

<!--

### Category

ASP.NET Core

### Affected APIs

- `T:Microsoft.Extensions.Localization.ResourceManagerWithCultureStringLocalizer`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.WithCulture`

-->
