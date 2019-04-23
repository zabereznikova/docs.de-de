---
title: <client>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
ms.openlocfilehash: 2e0352efdd5b709984338fe4484b120bddb7d545
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59164358"
---
# <a name="client"></a><span data-ttu-id="fd0f7-101">\<client></span><span class="sxs-lookup"><span data-stu-id="fd0f7-101">\<client></span></span>
<span data-ttu-id="fd0f7-102">Das `client`-Element definiert eine Liste der Endpunkte, mit denen ein Client eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="fd0f7-102">The `client` element defines a list of endpoints that a client can connect to.</span></span>  
  
 <span data-ttu-id="fd0f7-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fd0f7-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="fd0f7-104">\<client></span><span class="sxs-lookup"><span data-stu-id="fd0f7-104">\<client></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd0f7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="fd0f7-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <client>
    <endpoint>
    </endpoint>
    <metadata>
    </metadata>
  </client>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fd0f7-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fd0f7-106">Attributes and Elements</span></span>  
 <span data-ttu-id="fd0f7-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fd0f7-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fd0f7-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="fd0f7-108">Attributes</span></span>  
 <span data-ttu-id="fd0f7-109">Keiner</span><span class="sxs-lookup"><span data-stu-id="fd0f7-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fd0f7-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fd0f7-110">Child Elements</span></span>  
  
|<span data-ttu-id="fd0f7-111">Element</span><span class="sxs-lookup"><span data-stu-id="fd0f7-111">Element</span></span>|<span data-ttu-id="fd0f7-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fd0f7-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fd0f7-113">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="fd0f7-113">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|<span data-ttu-id="fd0f7-114">Enthält eine Auflistung der Endpunktelemente, die die Endpunkte angeben, mit denen dieser Client eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="fd0f7-114">Contains a collection of endpoint elements, that specify the endpoints that this client can connect to.</span></span>|  
|[<span data-ttu-id="fd0f7-115">\<metadata></span><span class="sxs-lookup"><span data-stu-id="fd0f7-115">\<metadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md)|<span data-ttu-id="fd0f7-116">Enthält Einstellungen zum Verarbeiten von Metadaten.</span><span class="sxs-lookup"><span data-stu-id="fd0f7-116">Contains settings for processing metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fd0f7-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fd0f7-117">Parent Elements</span></span>  
  
|<span data-ttu-id="fd0f7-118">Element</span><span class="sxs-lookup"><span data-stu-id="fd0f7-118">Element</span></span>|<span data-ttu-id="fd0f7-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fd0f7-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fd0f7-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="fd0f7-120">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="fd0f7-121">Das Stammelement aller Windows Communication Foundation (WCF)-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="fd0f7-121">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd0f7-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fd0f7-122">Remarks</span></span>  
 <span data-ttu-id="fd0f7-123">Der `client`-Abschnitt definiert eine Liste der Endpunkte, mit denen ein Client eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="fd0f7-123">The `client` section defines a list of endpoints that a client can connect to.</span></span> <span data-ttu-id="fd0f7-124">Jeder im Clientabschnitt aufgeführte Endpunkt definiert seine eigene Bindung, sein eigenes Verhalten und seinen eigenen Vertrag.</span><span class="sxs-lookup"><span data-stu-id="fd0f7-124">Each endpoint listed in the client section defines its own binding, behavior, and contract.</span></span> <span data-ttu-id="fd0f7-125">Er wird eindeutig anhand der Kombination des `name`-Attributs mit dem `contract`-Attribut identifiziert.</span><span class="sxs-lookup"><span data-stu-id="fd0f7-125">It is uniquely identified by the combination of the `name` and `contract` attributes.</span></span> <span data-ttu-id="fd0f7-126">Der Clientcode gibt den `name` an, um eine Verbindung zu einem Endpunkt für den durch den Client implementierten Dienst herzustellen.</span><span class="sxs-lookup"><span data-stu-id="fd0f7-126">The client code specifies the `name` to connect to an endpoint for the service that the client implements.</span></span> <span data-ttu-id="fd0f7-127">Wenn das `name`-Attribut ausgelassen wird, fungiert der Endpunkt als Standardendpunkt für den Vertrag, den er implementiert.</span><span class="sxs-lookup"><span data-stu-id="fd0f7-127">If the `name` attribute is omitted, the endpoint acts as the default endpoint for the contract it implements.</span></span>  
  
 <span data-ttu-id="fd0f7-128">Darüber hinaus gibt dieser Abschnitt auch die Einstellungen zum Verarbeiten von Metadaten an.</span><span class="sxs-lookup"><span data-stu-id="fd0f7-128">In addition, this section also specifies settings for processing metadata.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd0f7-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fd0f7-129">Example</span></span>  
  
```xml  
<client>
  <endpoint address="/HelloWorld/"
            bindingConfiguration="usingDefaults"
            name="MyBinding"
            binding="customBinding"
            contract="HelloWorld">
    <addressProperties actingAs="http://www.microsoft.com/TestActor"
                       identityData="BasicReadWrite"
                       identityType="Spn"
                       isAddressPrivate="false">
  </endpoint>
</client>
```  
  
## <a name="see-also"></a><span data-ttu-id="fd0f7-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd0f7-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- [<span data-ttu-id="fd0f7-131">WCF-Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="fd0f7-131">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="fd0f7-132">Clients</span><span class="sxs-lookup"><span data-stu-id="fd0f7-132">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
