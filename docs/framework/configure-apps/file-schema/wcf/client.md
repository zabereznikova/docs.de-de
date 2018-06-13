---
title: '&lt;Client&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
ms.openlocfilehash: b8a006d3dee4149569b3f5b573d9d765504b0d65
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752636"
---
# <a name="ltclientgt"></a><span data-ttu-id="48c6c-102">&lt;Client&gt;</span><span class="sxs-lookup"><span data-stu-id="48c6c-102">&lt;client&gt;</span></span>
<span data-ttu-id="48c6c-103">Das `client`-Element definiert eine Liste der Endpunkte, mit denen ein Client eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="48c6c-103">The `client` element defines a list of endpoints that a client can connect to.</span></span>  
  
 <span data-ttu-id="48c6c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="48c6c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="48c6c-105">\<Client ></span><span class="sxs-lookup"><span data-stu-id="48c6c-105">\<client></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48c6c-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="48c6c-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="48c6c-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="48c6c-107">Attributes and Elements</span></span>  
 <span data-ttu-id="48c6c-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="48c6c-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="48c6c-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="48c6c-109">Attributes</span></span>  
 <span data-ttu-id="48c6c-110">Keiner</span><span class="sxs-lookup"><span data-stu-id="48c6c-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="48c6c-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="48c6c-111">Child Elements</span></span>  
  
|<span data-ttu-id="48c6c-112">Element</span><span class="sxs-lookup"><span data-stu-id="48c6c-112">Element</span></span>|<span data-ttu-id="48c6c-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="48c6c-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="48c6c-114">\<Endpunkt ></span><span class="sxs-lookup"><span data-stu-id="48c6c-114">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|<span data-ttu-id="48c6c-115">Enthält eine Auflistung der Endpunktelemente, die die Endpunkte angeben, mit denen dieser Client eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="48c6c-115">Contains a collection of endpoint elements, that specify the endpoints that this client can connect to.</span></span>|  
|[<span data-ttu-id="48c6c-116">\<Metadaten ></span><span class="sxs-lookup"><span data-stu-id="48c6c-116">\<metadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md)|<span data-ttu-id="48c6c-117">Enthält Einstellungen zum Verarbeiten von Metadaten.</span><span class="sxs-lookup"><span data-stu-id="48c6c-117">Contains settings for processing metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="48c6c-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="48c6c-118">Parent Elements</span></span>  
  
|<span data-ttu-id="48c6c-119">Element</span><span class="sxs-lookup"><span data-stu-id="48c6c-119">Element</span></span>|<span data-ttu-id="48c6c-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="48c6c-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="48c6c-121">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="48c6c-121">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="48c6c-122">Das Stammelement aller Windows Communication Foundation (WCF)-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="48c6c-122">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48c6c-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="48c6c-123">Remarks</span></span>  
 <span data-ttu-id="48c6c-124">Der `client`-Abschnitt definiert eine Liste der Endpunkte, mit denen ein Client eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="48c6c-124">The `client` section defines a list of endpoints that a client can connect to.</span></span> <span data-ttu-id="48c6c-125">Jeder im Clientabschnitt aufgeführte Endpunkt definiert seine eigene Bindung, sein eigenes Verhalten und seinen eigenen Vertrag.</span><span class="sxs-lookup"><span data-stu-id="48c6c-125">Each endpoint listed in the client section defines its own binding, behavior, and contract.</span></span> <span data-ttu-id="48c6c-126">Er wird eindeutig anhand der Kombination des `name`-Attributs mit dem `contract`-Attribut identifiziert.</span><span class="sxs-lookup"><span data-stu-id="48c6c-126">It is uniquely identified by the combination of the `name` and `contract` attributes.</span></span> <span data-ttu-id="48c6c-127">Der Clientcode gibt den `name` an, um eine Verbindung zu einem Endpunkt für den durch den Client implementierten Dienst herzustellen.</span><span class="sxs-lookup"><span data-stu-id="48c6c-127">The client code specifies the `name` to connect to an endpoint for the service that the client implements.</span></span> <span data-ttu-id="48c6c-128">Wenn das `name`-Attribut ausgelassen wird, fungiert der Endpunkt als Standardendpunkt für den Vertrag, den er implementiert.</span><span class="sxs-lookup"><span data-stu-id="48c6c-128">If the `name` attribute is omitted, the endpoint acts as the default endpoint for the contract it implements.</span></span>  
  
 <span data-ttu-id="48c6c-129">Darüber hinaus gibt dieser Abschnitt auch die Einstellungen zum Verarbeiten von Metadaten an.</span><span class="sxs-lookup"><span data-stu-id="48c6c-129">In addition, this section also specifies settings for processing metadata.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48c6c-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="48c6c-130">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="48c6c-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48c6c-131">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientSection>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 [<span data-ttu-id="48c6c-132">WCF-Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="48c6c-132">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="48c6c-133">Clients</span><span class="sxs-lookup"><span data-stu-id="48c6c-133">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
