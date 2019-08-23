---
title: <client>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
ms.openlocfilehash: 7dce5984882e48c3e62efc44ef00b6256d9eb64e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919527"
---
# <a name="client"></a><span data-ttu-id="1b007-101">\<client></span><span class="sxs-lookup"><span data-stu-id="1b007-101">\<client></span></span>
<span data-ttu-id="1b007-102">Das `client`-Element definiert eine Liste der Endpunkte, mit denen ein Client eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="1b007-102">The `client` element defines a list of endpoints that a client can connect to.</span></span>  
  
 <span data-ttu-id="1b007-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1b007-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="1b007-104">\<client></span><span class="sxs-lookup"><span data-stu-id="1b007-104">\<client></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b007-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1b007-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1b007-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1b007-106">Attributes and Elements</span></span>  
 <span data-ttu-id="1b007-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1b007-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1b007-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="1b007-108">Attributes</span></span>  
 <span data-ttu-id="1b007-109">None</span><span class="sxs-lookup"><span data-stu-id="1b007-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1b007-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1b007-110">Child Elements</span></span>  
  
|<span data-ttu-id="1b007-111">Element</span><span class="sxs-lookup"><span data-stu-id="1b007-111">Element</span></span>|<span data-ttu-id="1b007-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1b007-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1b007-113">\<Endpunkt ></span><span class="sxs-lookup"><span data-stu-id="1b007-113">\<endpoint></span></span>](endpoint-of-client.md)|<span data-ttu-id="1b007-114">Enthält eine Auflistung der Endpunktelemente, die die Endpunkte angeben, mit denen dieser Client eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="1b007-114">Contains a collection of endpoint elements, that specify the endpoints that this client can connect to.</span></span>|  
|[<span data-ttu-id="1b007-115">\<Metadaten></span><span class="sxs-lookup"><span data-stu-id="1b007-115">\<metadata></span></span>](metadata.md)|<span data-ttu-id="1b007-116">Enthält Einstellungen zum Verarbeiten von Metadaten.</span><span class="sxs-lookup"><span data-stu-id="1b007-116">Contains settings for processing metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1b007-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1b007-117">Parent Elements</span></span>  
  
|<span data-ttu-id="1b007-118">Element</span><span class="sxs-lookup"><span data-stu-id="1b007-118">Element</span></span>|<span data-ttu-id="1b007-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1b007-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1b007-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1b007-120">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="1b007-121">Das Stammelement aller Windows Communication Foundation (WCF)-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="1b007-121">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b007-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1b007-122">Remarks</span></span>  
 <span data-ttu-id="1b007-123">Der `client`-Abschnitt definiert eine Liste der Endpunkte, mit denen ein Client eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="1b007-123">The `client` section defines a list of endpoints that a client can connect to.</span></span> <span data-ttu-id="1b007-124">Jeder im Clientabschnitt aufgeführte Endpunkt definiert seine eigene Bindung, sein eigenes Verhalten und seinen eigenen Vertrag.</span><span class="sxs-lookup"><span data-stu-id="1b007-124">Each endpoint listed in the client section defines its own binding, behavior, and contract.</span></span> <span data-ttu-id="1b007-125">Er wird eindeutig anhand der Kombination des `name`-Attributs mit dem `contract`-Attribut identifiziert.</span><span class="sxs-lookup"><span data-stu-id="1b007-125">It is uniquely identified by the combination of the `name` and `contract` attributes.</span></span> <span data-ttu-id="1b007-126">Der Clientcode gibt den `name` an, um eine Verbindung zu einem Endpunkt für den durch den Client implementierten Dienst herzustellen.</span><span class="sxs-lookup"><span data-stu-id="1b007-126">The client code specifies the `name` to connect to an endpoint for the service that the client implements.</span></span> <span data-ttu-id="1b007-127">Wenn das `name`-Attribut ausgelassen wird, fungiert der Endpunkt als Standardendpunkt für den Vertrag, den er implementiert.</span><span class="sxs-lookup"><span data-stu-id="1b007-127">If the `name` attribute is omitted, the endpoint acts as the default endpoint for the contract it implements.</span></span>  
  
 <span data-ttu-id="1b007-128">Darüber hinaus gibt dieser Abschnitt auch die Einstellungen zum Verarbeiten von Metadaten an.</span><span class="sxs-lookup"><span data-stu-id="1b007-128">In addition, this section also specifies settings for processing metadata.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b007-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1b007-129">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1b007-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b007-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- [<span data-ttu-id="1b007-131">WCF-Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="1b007-131">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="1b007-132">Clients</span><span class="sxs-lookup"><span data-stu-id="1b007-132">Clients</span></span>](../../../wcf/feature-details/clients.md)
