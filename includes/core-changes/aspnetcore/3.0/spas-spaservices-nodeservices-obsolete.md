---
ms.openlocfilehash: ac5a3c4f3aefbb59418ad92b2d795f36916f877f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394208"
---
### <a name="spas-spaservices-and-nodeservices-marked-obsolete"></a>SPAs: SpaServices und NodeServices wurden als veraltet markiert.

Der Inhalt der folgenden NuGet-Pakete ist seit ASP.NET Core 2.1 nicht mehr erforderlich. Aus diesem Grund werden die folgenden Pakete als veraltet markiert:

- [Microsoft.AspNetCore.SpaServices](https://www.nuget.org/packages/Microsoft.AspNetCore.SpaServices/)
- [Microsoft.AspNetCore.NodeServices](https://www.nuget.org/packages/Microsoft.AspNetCore.NodeServices/)

Aus demselben Grund werden die folgenden npm-Module als veraltet markiert:

- [aspnet-angular](https://www.npmjs.com/package/aspnet-angular)
- [aspnet-prerendering](https://www.npmjs.com/package/aspnet-prerendering)
- [aspnet-webpack](https://www.npmjs.com/package/aspnet-webpack)
- [aspnet-webpack-react](https://www.npmjs.com/package/aspnet-webpack-react)
- [domain-task](https://www.npmjs.com/package/domain-task)

Die obigen Pakete und npm-Module werden später aus .NET 5 entfernt.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

Die veralteten Pakete und npm-Module waren für die Integration von ASP.NET Core mit verschiedenen SPA-Frameworks (Single-Page-Webanwendung) vorgesehen. Zu diesen Frameworks gehören Angular, React und React mit Redux.

#### <a name="new-behavior"></a>Neues Verhalten

Im NuGet-Paket [Microsoft.AspNetCore.SpaServices.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.SpaServices.Extensions/) steht ein neuer Integrationsmechanismus zur Verfügung. Das Paket bleibt die Basis der Angular- und React-Projektvorlagen seit ASP.NET Core 2.1.

#### <a name="reason-for-change"></a>Grund für die Änderung

ASP.NET Core unterstützt die Integration mit verschiedenen SPA-Frameworks (Single-Page-Webanwendung), einschließlich Angular, React und React mit Redux. Anfänglich wurde die Integration mit diesen Frameworks über ASP.NET Core-spezifische Komponenten erzielt, die Szenarien wie die serverseitige Vorabgenerierung und Integration mit WebPack behandelt haben. Im Laufe der Zeit haben sich die Industriestandards geändert. Alle SPA-Frameworks haben ihre eigenen Standard-Befehlszeilenschnittstellen veröffentlicht. Dazu gehören beispielsweise die Angular CLI und die create-react-app.

Als ASP.NET Core 2.1 im Mai 2018 veröffentlicht wurde, reagierte das Team auf die Änderungen bei den Standards. Es wurde eine neuere und einfachere Möglichkeit zur Integration mit den eigenen Toolketten des SPA-Frameworks bereitgestellt. Der neue Integrationsmechanismus ist im Paket `Microsoft.AspNetCore.SpaServices.Extensions` enthalten und bleibt die Basis der Angular- und React-Projektvorlagen seit ASP.NET Core 2.1.

Um deutlich zu machen, dass die älteren ASP.NET Core-spezifischen Komponenten irrelevant sind und nicht empfohlen werden, wurde Folgendes umgesetzt:

- Der Integrationsmechanismus vor Version 2.1 wurde als veraltet markiert.
- Die unterstützenden npm-Pakete wurden als veraltet markiert.

#### <a name="recommended-action"></a>Empfohlene Aktion

Wenn Sie diese Pakete verwenden, aktualisieren Sie Ihre Apps, um diese Funktionalität zu nutzen:

- Im Paket `Microsoft.AspNetCore.SpaServices.Extensions`.
- Bereitgestellt von den von Ihnen verwendeten SPA-Frameworks

Informationen zum Aktivieren von Features wie dem serverseitigen Vorabrendering und dem „heißen“ Neuladen von Modulen finden Sie in der Dokumentation zum zugehörigen SPA-Framework. Die Funktionen in `Microsoft.AspNetCore.SpaServices.Extensions` sind *nicht* veraltet und werden weiterhin unterstützt.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

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
