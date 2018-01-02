---
title: '&lt;Client&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a7d52d74c36ea1b1d722d781f554f8cc6691d53e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltclientgt"></a><span data-ttu-id="f17b3-102">&lt;Client&gt;</span><span class="sxs-lookup"><span data-stu-id="f17b3-102">&lt;client&gt;</span></span>
<span data-ttu-id="f17b3-103">Das `client`-Element definiert eine Liste der Endpunkte, mit denen ein Client eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="f17b3-103">The `client` element defines a list of endpoints that a client can connect to.</span></span>  
  
 <span data-ttu-id="f17b3-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="f17b3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f17b3-105">\<Client ></span><span class="sxs-lookup"><span data-stu-id="f17b3-105">\<client></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f17b3-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="f17b3-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f17b3-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f17b3-107">Attributes and Elements</span></span>  
 <span data-ttu-id="f17b3-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f17b3-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f17b3-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="f17b3-109">Attributes</span></span>  
 <span data-ttu-id="f17b3-110">Keiner</span><span class="sxs-lookup"><span data-stu-id="f17b3-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f17b3-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f17b3-111">Child Elements</span></span>  
  
|<span data-ttu-id="f17b3-112">Element</span><span class="sxs-lookup"><span data-stu-id="f17b3-112">Element</span></span>|<span data-ttu-id="f17b3-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f17b3-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f17b3-114">\<Endpunkt ></span><span class="sxs-lookup"><span data-stu-id="f17b3-114">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|<span data-ttu-id="f17b3-115">Enthält eine Auflistung der Endpunktelemente, die die Endpunkte angeben, mit denen dieser Client eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="f17b3-115">Contains a collection of endpoint elements, that specify the endpoints that this client can connect to.</span></span>|  
|[<span data-ttu-id="f17b3-116">\<Metadaten ></span><span class="sxs-lookup"><span data-stu-id="f17b3-116">\<metadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md)|<span data-ttu-id="f17b3-117">Enthält Einstellungen zum Verarbeiten von Metadaten.</span><span class="sxs-lookup"><span data-stu-id="f17b3-117">Contains settings for processing metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f17b3-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f17b3-118">Parent Elements</span></span>  
  
|<span data-ttu-id="f17b3-119">Element</span><span class="sxs-lookup"><span data-stu-id="f17b3-119">Element</span></span>|<span data-ttu-id="f17b3-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f17b3-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f17b3-121">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f17b3-121">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="f17b3-122">Das Stammelement aller Windows Communication Foundation (WCF)-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="f17b3-122">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f17b3-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f17b3-123">Remarks</span></span>  
 <span data-ttu-id="f17b3-124">Der `client`-Abschnitt definiert eine Liste der Endpunkte, mit denen ein Client eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="f17b3-124">The `client` section defines a list of endpoints that a client can connect to.</span></span> <span data-ttu-id="f17b3-125">Jeder im Clientabschnitt aufgeführte Endpunkt definiert seine eigene Bindung, sein eigenes Verhalten und seinen eigenen Vertrag.</span><span class="sxs-lookup"><span data-stu-id="f17b3-125">Each endpoint listed in the client section defines its own binding, behavior, and contract.</span></span> <span data-ttu-id="f17b3-126">Er wird eindeutig anhand der Kombination des `name`-Attributs mit dem `contract`-Attribut identifiziert.</span><span class="sxs-lookup"><span data-stu-id="f17b3-126">It is uniquely identified by the combination of the `name` and `contract` attributes.</span></span> <span data-ttu-id="f17b3-127">Der Clientcode gibt den `name` an, um eine Verbindung zu einem Endpunkt für den durch den Client implementierten Dienst herzustellen.</span><span class="sxs-lookup"><span data-stu-id="f17b3-127">The client code specifies the `name` to connect to an endpoint for the service that the client implements.</span></span> <span data-ttu-id="f17b3-128">Wenn das `name`-Attribut ausgelassen wird, fungiert der Endpunkt als Standardendpunkt für den Vertrag, den er implementiert.</span><span class="sxs-lookup"><span data-stu-id="f17b3-128">If the `name` attribute is omitted, the endpoint acts as the default endpoint for the contract it implements.</span></span>  
  
 <span data-ttu-id="f17b3-129">Darüber hinaus gibt dieser Abschnitt auch die Einstellungen zum Verarbeiten von Metadaten an.</span><span class="sxs-lookup"><span data-stu-id="f17b3-129">In addition, this section also specifies settings for processing metadata.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f17b3-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f17b3-130">Example</span></span>  
  
```xml  
<client>  
    <endpoint address="/HelloWorld/"  
              bindingConfiguration="usingDefaults"  
              name="MyBinding"  
              binding="customBinding"  
              contract="HelloWorld">  
    <addressProperties actingAs="http://www.microsoft.com/TestActor"  
             identityData="BasicReadWrite" identityType="Spn" isAddressPrivate="false">  
    </endpoint>  
</client>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f17b3-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f17b3-131">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientSection>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 [<span data-ttu-id="f17b3-132">WCF-Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="f17b3-132">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="f17b3-133">Clients</span><span class="sxs-lookup"><span data-stu-id="f17b3-133">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
