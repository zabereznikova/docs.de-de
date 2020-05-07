---
ms.openlocfilehash: 6deeb7debce9b731f3871b7de0ad8df8a8cdafea
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728303"
---
### <a name="localization-resourcemanagerwithculturestringlocalizer-class-and-withculture-interface-member-removed"></a><span data-ttu-id="dbd2b-101">Lokalisierung: ResourceManagerWithCultureStringLocalizer-Klasse und WithCulture-Schnittstellenmember entfernt</span><span class="sxs-lookup"><span data-stu-id="dbd2b-101">Localization: ResourceManagerWithCultureStringLocalizer class and WithCulture interface member removed</span></span>

<span data-ttu-id="dbd2b-102">Die [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1)-Klasse und die [WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1)-Methode wurden in .NET 5.0 Preview 1 entfernt.</span><span class="sxs-lookup"><span data-stu-id="dbd2b-102">The [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) class and [WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) method were removed in .NET 5.0 Preview 1.</span></span>

<span data-ttu-id="dbd2b-103">Weitere Informationen finden Sie unter [aspnet/Announcements#346](https://github.com/aspnet/Announcements/issues/346) und [dotnet/aspnetcore#3324](https://github.com/dotnet/aspnetcore/issues/3324).</span><span class="sxs-lookup"><span data-stu-id="dbd2b-103">For context, see [aspnet/Announcements#346](https://github.com/aspnet/Announcements/issues/346) and [dotnet/aspnetcore#3324](https://github.com/dotnet/aspnetcore/issues/3324).</span></span> <span data-ttu-id="dbd2b-104">Diese Änderung wird unter [dotnet/aspnetcore#7756](https://github.com/dotnet/aspnetcore/issues/7756) behandelt.</span><span class="sxs-lookup"><span data-stu-id="dbd2b-104">For discussion on this change, see [dotnet/aspnetcore#7756](https://github.com/dotnet/aspnetcore/issues/7756).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="dbd2b-105">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="dbd2b-105">Version introduced</span></span>

<span data-ttu-id="dbd2b-106">5.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="dbd2b-106">5.0 Preview 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="dbd2b-107">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="dbd2b-107">Old behavior</span></span>

<span data-ttu-id="dbd2b-108">Die `ResourceManagerWithCultureStringLocalizer`-Klasse und die `ResourceManagerStringLocalizer.WithCulture`-Methode gelten in [.NET Core 3.0 Preview 3 und höher](/dotnet/core/compatibility/2.2-3.0#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete) als veraltet.</span><span class="sxs-lookup"><span data-stu-id="dbd2b-108">The `ResourceManagerWithCultureStringLocalizer` class and the `ResourceManagerStringLocalizer.WithCulture` method are [obsolete in .NET Core 3.0 Preview 3 and later](/dotnet/core/compatibility/2.2-3.0#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete).</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="dbd2b-109">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="dbd2b-109">New behavior</span></span>

<span data-ttu-id="dbd2b-110">Die `ResourceManagerWithCultureStringLocalizer`-Klasse und die `ResourceManagerStringLocalizer.WithCulture`-Methode wurden in .NET 5.0 Preview 1 entfernt.</span><span class="sxs-lookup"><span data-stu-id="dbd2b-110">The `ResourceManagerWithCultureStringLocalizer` class and the `ResourceManagerStringLocalizer.WithCulture` method have been removed in .NET 5.0 Preview 1.</span></span> <span data-ttu-id="dbd2b-111">Eine Übersicht über die vorgenommenen Änderungen finden Sie im Pull Request unter [dotnet/extensions#2562](https://github.com/dotnet/extensions/pull/2562/files).</span><span class="sxs-lookup"><span data-stu-id="dbd2b-111">For an inventory of the changes made, see the pull request at [dotnet/extensions#2562](https://github.com/dotnet/extensions/pull/2562/files).</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="dbd2b-112">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="dbd2b-112">Reason for change</span></span>

<span data-ttu-id="dbd2b-113">Die [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1)-Klasse und die [ResourceManagerStringLocalizer.WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1)-Methode sorgten bei Benutzern mit lokalisierten Versionen häufig für Verwirrung.</span><span class="sxs-lookup"><span data-stu-id="dbd2b-113">The [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) class and [ResourceManagerStringLocalizer.WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) method were often sources of confusion for users of localization.</span></span> <span data-ttu-id="dbd2b-114">Das galt insbesondere für die Erstellung einer benutzerdefinierten <xref:Microsoft.Extensions.Localization.IStringLocalizer>-Implementierung.</span><span class="sxs-lookup"><span data-stu-id="dbd2b-114">The confusion was especially high when creating a custom <xref:Microsoft.Extensions.Localization.IStringLocalizer> implementation.</span></span> <span data-ttu-id="dbd2b-115">Diese Klasse und Methode erwecken bei Benutzern den Eindruck, dass eine `IStringLocalizer`-Instanz pro Sprache und pro Ressource gilt.</span><span class="sxs-lookup"><span data-stu-id="dbd2b-115">This class and method give consumers the impression that an `IStringLocalizer` instance is expected to be "per-language, per-resource".</span></span> <span data-ttu-id="dbd2b-116">Tatsächlich sollte die Instanz nur pro Ressource gelten.</span><span class="sxs-lookup"><span data-stu-id="dbd2b-116">In reality, the instance should only be "per-resource".</span></span> <span data-ttu-id="dbd2b-117">Zur Laufzeit bestimmt die <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType>-Eigenschaft die zu verwendende Sprache.</span><span class="sxs-lookup"><span data-stu-id="dbd2b-117">At run time, the <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> property determines the language to be used.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="dbd2b-118">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="dbd2b-118">Recommended action</span></span>

<span data-ttu-id="dbd2b-119">Verwenden Sie die `ResourceManagerWithCultureStringLocalizer`-Klasse und die `ResourceManagerStringLocalizer.WithCulture`-Methode nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="dbd2b-119">Stop using the `ResourceManagerWithCultureStringLocalizer` class and the `ResourceManagerStringLocalizer.WithCulture` method.</span></span>

#### <a name="category"></a><span data-ttu-id="dbd2b-120">Kategorie</span><span class="sxs-lookup"><span data-stu-id="dbd2b-120">Category</span></span>

<span data-ttu-id="dbd2b-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="dbd2b-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="dbd2b-122">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="dbd2b-122">Affected APIs</span></span>

- [<span data-ttu-id="dbd2b-123">ResourceManagerWithCultureStringLocalizer</span><span class="sxs-lookup"><span data-stu-id="dbd2b-123">ResourceManagerWithCultureStringLocalizer</span></span>](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1)
- [<span data-ttu-id="dbd2b-124">ResourceManagerStringLocalizer.WithCulture</span><span class="sxs-lookup"><span data-stu-id="dbd2b-124">ResourceManagerStringLocalizer.WithCulture</span></span>](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1)

<!--

#### Affected APIs

- `T:Microsoft.Extensions.Localization.ResourceManagerWithCultureStringLocalizer`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.WithCulture`

-->
