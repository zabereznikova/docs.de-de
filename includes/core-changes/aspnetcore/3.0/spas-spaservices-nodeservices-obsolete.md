---
ms.openlocfilehash: ac5a3c4f3aefbb59418ad92b2d795f36916f877f
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032677"
---
### <a name="spas-spaservices-and-nodeservices-marked-obsolete"></a><span data-ttu-id="7bf93-101">SPAs: SpaServices und NodeServices wurden als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="7bf93-101">SPAs: SpaServices and NodeServices marked obsolete</span></span>

<span data-ttu-id="7bf93-102">Der Inhalt der folgenden NuGet-Pakete ist seit ASP.NET Core 2.1 nicht mehr erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7bf93-102">The contents of the following NuGet packages have all been unnecessary since ASP.NET Core 2.1.</span></span> <span data-ttu-id="7bf93-103">Aus diesem Grund werden die folgenden Pakete als veraltet markiert:</span><span class="sxs-lookup"><span data-stu-id="7bf93-103">Consequently, the following packages are being marked as obsolete:</span></span>

- [<span data-ttu-id="7bf93-104">Microsoft.AspNetCore.SpaServices</span><span class="sxs-lookup"><span data-stu-id="7bf93-104">Microsoft.AspNetCore.SpaServices</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.SpaServices/)
- [<span data-ttu-id="7bf93-105">Microsoft.AspNetCore.NodeServices</span><span class="sxs-lookup"><span data-stu-id="7bf93-105">Microsoft.AspNetCore.NodeServices</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.NodeServices/)

<span data-ttu-id="7bf93-106">Aus demselben Grund werden die folgenden npm-Module als veraltet markiert:</span><span class="sxs-lookup"><span data-stu-id="7bf93-106">For the same reason, the following npm modules are being marked as deprecated:</span></span>

- [<span data-ttu-id="7bf93-107">aspnet-angular</span><span class="sxs-lookup"><span data-stu-id="7bf93-107">aspnet-angular</span></span>](https://www.npmjs.com/package/aspnet-angular)
- [<span data-ttu-id="7bf93-108">aspnet-prerendering</span><span class="sxs-lookup"><span data-stu-id="7bf93-108">aspnet-prerendering</span></span>](https://www.npmjs.com/package/aspnet-prerendering)
- [<span data-ttu-id="7bf93-109">aspnet-webpack</span><span class="sxs-lookup"><span data-stu-id="7bf93-109">aspnet-webpack</span></span>](https://www.npmjs.com/package/aspnet-webpack)
- [<span data-ttu-id="7bf93-110">aspnet-webpack-react</span><span class="sxs-lookup"><span data-stu-id="7bf93-110">aspnet-webpack-react</span></span>](https://www.npmjs.com/package/aspnet-webpack-react)
- [<span data-ttu-id="7bf93-111">domain-task</span><span class="sxs-lookup"><span data-stu-id="7bf93-111">domain-task</span></span>](https://www.npmjs.com/package/domain-task)

<span data-ttu-id="7bf93-112">Die obigen Pakete und npm-Module werden später aus .NET 5 entfernt.</span><span class="sxs-lookup"><span data-stu-id="7bf93-112">The preceding packages and npm modules will later be removed in .NET 5.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="7bf93-113">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="7bf93-113">Version introduced</span></span>

<span data-ttu-id="7bf93-114">3.0</span><span class="sxs-lookup"><span data-stu-id="7bf93-114">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="7bf93-115">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="7bf93-115">Old behavior</span></span>

<span data-ttu-id="7bf93-116">Die veralteten Pakete und npm-Module waren für die Integration von ASP.NET Core mit verschiedenen SPA-Frameworks (Single-Page-Webanwendung) vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="7bf93-116">The deprecated packages and npm modules were intended to integrate ASP.NET Core with various Single-Page App (SPA) frameworks.</span></span> <span data-ttu-id="7bf93-117">Zu diesen Frameworks gehören Angular, React und React mit Redux.</span><span class="sxs-lookup"><span data-stu-id="7bf93-117">Such frameworks include Angular, React, and React with Redux.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="7bf93-118">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="7bf93-118">New behavior</span></span>

<span data-ttu-id="7bf93-119">Im NuGet-Paket [Microsoft.AspNetCore.SpaServices.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.SpaServices.Extensions/) steht ein neuer Integrationsmechanismus zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="7bf93-119">A new integration mechanism exists in the [Microsoft.AspNetCore.SpaServices.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.SpaServices.Extensions/) NuGet package.</span></span> <span data-ttu-id="7bf93-120">Das Paket bleibt die Basis der Angular- und React-Projektvorlagen seit ASP.NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="7bf93-120">The package remains the basis of the Angular and React project templates since ASP.NET Core 2.1.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="7bf93-121">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="7bf93-121">Reason for change</span></span>

<span data-ttu-id="7bf93-122">ASP.NET Core unterstützt die Integration mit verschiedenen SPA-Frameworks (Single-Page-Webanwendung), einschließlich Angular, React und React mit Redux.</span><span class="sxs-lookup"><span data-stu-id="7bf93-122">ASP.NET Core supports integration with various Single-Page App (SPA) frameworks, including Angular, React, and React with Redux.</span></span> <span data-ttu-id="7bf93-123">Anfänglich wurde die Integration mit diesen Frameworks über ASP.NET Core-spezifische Komponenten erzielt, die Szenarien wie die serverseitige Vorabgenerierung und Integration mit WebPack behandelt haben.</span><span class="sxs-lookup"><span data-stu-id="7bf93-123">Initially, integration with these frameworks was accomplished with ASP.NET Core-specific components that handled scenarios like server-side prerendering and integration with Webpack.</span></span> <span data-ttu-id="7bf93-124">Im Laufe der Zeit haben sich die Industriestandards geändert.</span><span class="sxs-lookup"><span data-stu-id="7bf93-124">As time went on, industry standards changed.</span></span> <span data-ttu-id="7bf93-125">Alle SPA-Frameworks haben ihre eigenen Standard-Befehlszeilenschnittstellen veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="7bf93-125">Each of the SPA frameworks released their own standard command-line interfaces.</span></span> <span data-ttu-id="7bf93-126">Dazu gehören beispielsweise die Angular CLI und die create-react-app.</span><span class="sxs-lookup"><span data-stu-id="7bf93-126">For example, Angular CLI and create-react-app.</span></span>

<span data-ttu-id="7bf93-127">Als ASP.NET Core 2.1 im Mai 2018 veröffentlicht wurde, reagierte das Team auf die Änderungen bei den Standards.</span><span class="sxs-lookup"><span data-stu-id="7bf93-127">When ASP.NET Core 2.1 was released in May 2018, the team responded to the change in standards.</span></span> <span data-ttu-id="7bf93-128">Es wurde eine neuere und einfachere Möglichkeit zur Integration mit den eigenen Toolketten des SPA-Frameworks bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="7bf93-128">A newer and simpler way to integrate with the SPA frameworks' own toolchains was provided.</span></span> <span data-ttu-id="7bf93-129">Der neue Integrationsmechanismus ist im Paket `Microsoft.AspNetCore.SpaServices.Extensions` enthalten und bleibt die Basis der Angular- und React-Projektvorlagen seit ASP.NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="7bf93-129">The new integration mechanism exists in the package `Microsoft.AspNetCore.SpaServices.Extensions` and remains the basis of the Angular and React project templates since ASP.NET Core 2.1.</span></span>

<span data-ttu-id="7bf93-130">Um deutlich zu machen, dass die älteren ASP.NET Core-spezifischen Komponenten irrelevant sind und nicht empfohlen werden, wurde Folgendes umgesetzt:</span><span class="sxs-lookup"><span data-stu-id="7bf93-130">To clarify that the older ASP.NET Core-specific components are irrelevant and not recommended:</span></span>

- <span data-ttu-id="7bf93-131">Der Integrationsmechanismus vor Version 2.1 wurde als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="7bf93-131">The pre-2.1 integration mechanism is marked as obsolete.</span></span>
- <span data-ttu-id="7bf93-132">Die unterstützenden npm-Pakete wurden als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="7bf93-132">The supporting npm packages are marked as deprecated.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="7bf93-133">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="7bf93-133">Recommended action</span></span>

<span data-ttu-id="7bf93-134">Wenn Sie diese Pakete verwenden, aktualisieren Sie Ihre Apps, um diese Funktionalität zu nutzen:</span><span class="sxs-lookup"><span data-stu-id="7bf93-134">If you're using these packages, update your apps to use the functionality:</span></span>

- <span data-ttu-id="7bf93-135">Im Paket `Microsoft.AspNetCore.SpaServices.Extensions`.</span><span class="sxs-lookup"><span data-stu-id="7bf93-135">In the `Microsoft.AspNetCore.SpaServices.Extensions` package.</span></span>
- <span data-ttu-id="7bf93-136">Bereitgestellt von den von Ihnen verwendeten SPA-Frameworks</span><span class="sxs-lookup"><span data-stu-id="7bf93-136">Provided by the SPA frameworks you're using</span></span>

<span data-ttu-id="7bf93-137">Informationen zum Aktivieren von Features wie dem serverseitigen Vorabrendering und dem „heißen“ Neuladen von Modulen finden Sie in der Dokumentation zum zugehörigen SPA-Framework.</span><span class="sxs-lookup"><span data-stu-id="7bf93-137">To enable features like server-side prerendering and hot module reload, see the documentation for the corresponding SPA framework.</span></span> <span data-ttu-id="7bf93-138">Die Funktionen in `Microsoft.AspNetCore.SpaServices.Extensions` sind *nicht* veraltet und werden weiterhin unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7bf93-138">The functionality in `Microsoft.AspNetCore.SpaServices.Extensions` is *not* obsolete and will continue to be supported.</span></span>

#### <a name="category"></a><span data-ttu-id="7bf93-139">Kategorie</span><span class="sxs-lookup"><span data-stu-id="7bf93-139">Category</span></span>

<span data-ttu-id="7bf93-140">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7bf93-140">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7bf93-141">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="7bf93-141">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Builder.SpaRouteExtensions?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Builder.WebpackDevMiddleware?displayProperty=nameWithType>

- <xref:Microsoft.AspNetCore.NodeServices.EmbeddedResourceReader?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.INodeServices?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.NodeServicesFactory?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.NodeServicesOptions?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.StringAsTempFile?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.INodeInstance?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.NodeInvocationException?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.NodeInvocationInfo?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.NodeServicesOptionsExtensions?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.OutOfProcessNodeInstance?displayProperty=nameWithType>

- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.ISpaPrerenderer?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.ISpaPrerendererBuilder?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.JavaScriptModuleExport?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.Prerenderer?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.PrerenderTagHelper?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.RenderToStringResult?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Webpack.WebpackDevMiddlewareOptions?displayProperty=nameWithType>

- <xref:Microsoft.Extensions.DependencyInjection.NodeServicesServiceCollectionExtensions?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.DependencyInjection.PrerenderingServiceCollectionExtensions?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:Microsoft.AspNetCore.Builder.SpaRouteExtensions`
- `T:Microsoft.AspNetCore.Builder.WebpackDevMiddleware`

- `T:Microsoft.AspNetCore.NodeServices.EmbeddedResourceReader`
- `T:Microsoft.AspNetCore.NodeServices.INodeServices`
- `T:Microsoft.AspNetCore.NodeServices.NodeServicesFactory`
- `T:Microsoft.AspNetCore.NodeServices.NodeServicesOptions`
- `T:Microsoft.AspNetCore.NodeServices.StringAsTempFile`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.INodeInstance`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.NodeInvocationException`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.NodeInvocationInfo`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.NodeServicesOptionsExtensions`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.OutOfProcessNodeInstance`

- `T:Microsoft.AspNetCore.SpaServices.Prerendering.ISpaPrerenderer`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.ISpaPrerendererBuilder`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.JavaScriptModuleExport`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.Prerenderer`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.PrerenderTagHelper`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.RenderToStringResult`
- `T:Microsoft.AspNetCore.SpaServices.Webpack.WebpackDevMiddlewareOptions`

- `T:Microsoft.Extensions.DependencyInjection.NodeServicesServiceCollectionExtensions`
- `T:Microsoft.Extensions.DependencyInjection.PrerenderingServiceCollectionExtensions`

-->
