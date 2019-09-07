---
title: <client>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
ms.openlocfilehash: 6cc8b80edb3206bb2ef3a8a1ffa34ab40af77612
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398154"
---
# <a name="client"></a><span data-ttu-id="cceed-101">\<client></span><span class="sxs-lookup"><span data-stu-id="cceed-101">\<client></span></span>
<span data-ttu-id="cceed-102">Das `client`-Element definiert eine Liste der Endpunkte, mit denen ein Client eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="cceed-102">The `client` element defines a list of endpoints that a client can connect to.</span></span>  
  
<span data-ttu-id="cceed-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="cceed-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="cceed-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="cceed-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="cceed-105">&nbsp;&nbsp;&nbsp;&nbsp; **\<Client >**</span><span class="sxs-lookup"><span data-stu-id="cceed-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<client>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cceed-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="cceed-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cceed-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cceed-107">Attributes and Elements</span></span>  
 <span data-ttu-id="cceed-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cceed-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cceed-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="cceed-109">Attributes</span></span>  
 <span data-ttu-id="cceed-110">None</span><span class="sxs-lookup"><span data-stu-id="cceed-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cceed-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cceed-111">Child Elements</span></span>  
  
|<span data-ttu-id="cceed-112">Element</span><span class="sxs-lookup"><span data-stu-id="cceed-112">Element</span></span>|<span data-ttu-id="cceed-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cceed-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cceed-114">\<Endpunkt ></span><span class="sxs-lookup"><span data-stu-id="cceed-114">\<endpoint></span></span>](endpoint-of-client.md)|<span data-ttu-id="cceed-115">Enthält eine Auflistung der Endpunktelemente, die die Endpunkte angeben, mit denen dieser Client eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="cceed-115">Contains a collection of endpoint elements, that specify the endpoints that this client can connect to.</span></span>|  
|[<span data-ttu-id="cceed-116">\<Metadaten></span><span class="sxs-lookup"><span data-stu-id="cceed-116">\<metadata></span></span>](metadata.md)|<span data-ttu-id="cceed-117">Enthält Einstellungen zum Verarbeiten von Metadaten.</span><span class="sxs-lookup"><span data-stu-id="cceed-117">Contains settings for processing metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cceed-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cceed-118">Parent Elements</span></span>  
  
|<span data-ttu-id="cceed-119">Element</span><span class="sxs-lookup"><span data-stu-id="cceed-119">Element</span></span>|<span data-ttu-id="cceed-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cceed-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cceed-121">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="cceed-121">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="cceed-122">Das Stammelement aller Windows Communication Foundation (WCF)-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="cceed-122">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cceed-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cceed-123">Remarks</span></span>  
 <span data-ttu-id="cceed-124">Der `client`-Abschnitt definiert eine Liste der Endpunkte, mit denen ein Client eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="cceed-124">The `client` section defines a list of endpoints that a client can connect to.</span></span> <span data-ttu-id="cceed-125">Jeder im Clientabschnitt aufgeführte Endpunkt definiert seine eigene Bindung, sein eigenes Verhalten und seinen eigenen Vertrag.</span><span class="sxs-lookup"><span data-stu-id="cceed-125">Each endpoint listed in the client section defines its own binding, behavior, and contract.</span></span> <span data-ttu-id="cceed-126">Er wird eindeutig anhand der Kombination des `name`-Attributs mit dem `contract`-Attribut identifiziert.</span><span class="sxs-lookup"><span data-stu-id="cceed-126">It is uniquely identified by the combination of the `name` and `contract` attributes.</span></span> <span data-ttu-id="cceed-127">Der Clientcode gibt den `name` an, um eine Verbindung zu einem Endpunkt für den durch den Client implementierten Dienst herzustellen.</span><span class="sxs-lookup"><span data-stu-id="cceed-127">The client code specifies the `name` to connect to an endpoint for the service that the client implements.</span></span> <span data-ttu-id="cceed-128">Wenn das `name`-Attribut ausgelassen wird, fungiert der Endpunkt als Standardendpunkt für den Vertrag, den er implementiert.</span><span class="sxs-lookup"><span data-stu-id="cceed-128">If the `name` attribute is omitted, the endpoint acts as the default endpoint for the contract it implements.</span></span>  
  
 <span data-ttu-id="cceed-129">Darüber hinaus gibt dieser Abschnitt auch die Einstellungen zum Verarbeiten von Metadaten an.</span><span class="sxs-lookup"><span data-stu-id="cceed-129">In addition, this section also specifies settings for processing metadata.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cceed-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cceed-130">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cceed-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cceed-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- [<span data-ttu-id="cceed-132">WCF-Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="cceed-132">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="cceed-133">Clients</span><span class="sxs-lookup"><span data-stu-id="cceed-133">Clients</span></span>](../../../wcf/feature-details/clients.md)
