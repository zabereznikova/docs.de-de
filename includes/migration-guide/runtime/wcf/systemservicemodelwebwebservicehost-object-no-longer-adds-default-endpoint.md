---
ms.openlocfilehash: 57f68c10d5d1edc9b8deaca2f4fe7edda2dd69b0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620393"
---
### <a name="systemservicemodelwebwebservicehost-object-no-longer-adds-a-default-endpoint"></a><span data-ttu-id="e69f8-101">Das System.ServiceModel.Web.WebServiceHost-Objekt fügt keinen Standardendpunkt mehr hinzu</span><span class="sxs-lookup"><span data-stu-id="e69f8-101">System.ServiceModel.Web.WebServiceHost object no longer adds a default endpoint</span></span>

#### <a name="details"></a><span data-ttu-id="e69f8-102">Details</span><span class="sxs-lookup"><span data-stu-id="e69f8-102">Details</span></span>

<span data-ttu-id="e69f8-103">Das <xref:System.ServiceModel.Web.WebServiceHost>-Objekt fügt keinen standardmäßigen Endpunkt mehr hinzu, wenn ein expliziter Endpunkt vom Anwendungscode hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="e69f8-103">The <xref:System.ServiceModel.Web.WebServiceHost> object no longer adds a default endpoint if an explicit endpoint has been added by application code.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e69f8-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="e69f8-104">Suggestion</span></span>

<span data-ttu-id="e69f8-105">Wenn Benutzer erwarten, dass sie eine Verbindung mit einem Standardendpunkt herstellen können und andere explizite Endpunkte zu <xref:System.ServiceModel.Web.WebServiceHost?displayProperty=fullName> hinzugefügt wurden, sollten (über <xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints?displayProperty=fullName>) auch die Standardendpunkte explizit hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="e69f8-105">If users will expect to be able to connect to a default endpoint and other explicit endpoints have been added to the <xref:System.ServiceModel.Web.WebServiceHost?displayProperty=fullName>, default endpoints should also be added explicitly (using <xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints?displayProperty=fullName>).</span></span>

| <span data-ttu-id="e69f8-106">name</span><span class="sxs-lookup"><span data-stu-id="e69f8-106">Name</span></span>    | <span data-ttu-id="e69f8-107">Wert</span><span class="sxs-lookup"><span data-stu-id="e69f8-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e69f8-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="e69f8-108">Scope</span></span>   |<span data-ttu-id="e69f8-109">Gering</span><span class="sxs-lookup"><span data-stu-id="e69f8-109">Minor</span></span>|
|<span data-ttu-id="e69f8-110">Version</span><span class="sxs-lookup"><span data-stu-id="e69f8-110">Version</span></span>|<span data-ttu-id="e69f8-111">4.5</span><span class="sxs-lookup"><span data-stu-id="e69f8-111">4.5</span></span>|
|<span data-ttu-id="e69f8-112">Typ</span><span class="sxs-lookup"><span data-stu-id="e69f8-112">Type</span></span>|<span data-ttu-id="e69f8-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="e69f8-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e69f8-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="e69f8-114">Affected APIs</span></span>

-<xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.String)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.Uri)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.String,System.Uri)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.Uri,System.Uri)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.Uri,System.Uri)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.ServiceModel.Description.ServiceEndpoint)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.String)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.Uri)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.String,System.Uri)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.Uri,System.Uri)?displayProperty=nameWithType></li></ul>|
