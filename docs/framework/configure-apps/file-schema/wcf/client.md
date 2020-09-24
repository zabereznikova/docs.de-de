---
title: <client>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
ms.openlocfilehash: b3234bfa60cd1e3c88778951fc27301c615c84ba
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148957"
---
# \<client>

<span data-ttu-id="4ed3e-101">Das `client`-Element definiert eine Liste der Endpunkte, mit denen ein Client eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="4ed3e-101">The `client` element defines a list of endpoints that a client can connect to.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<client>**

## <a name="syntax"></a><span data-ttu-id="4ed3e-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="4ed3e-102">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="4ed3e-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4ed3e-103">Attributes and Elements</span></span>

 <span data-ttu-id="4ed3e-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4ed3e-104">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="4ed3e-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="4ed3e-105">Attributes</span></span>

 <span data-ttu-id="4ed3e-106">Keine</span><span class="sxs-lookup"><span data-stu-id="4ed3e-106">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="4ed3e-107">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4ed3e-107">Child Elements</span></span>

|<span data-ttu-id="4ed3e-108">Element</span><span class="sxs-lookup"><span data-stu-id="4ed3e-108">Element</span></span>|<span data-ttu-id="4ed3e-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4ed3e-109">Description</span></span>|
|-------------|-----------------|
|[\<endpoint>](endpoint-of-client.md)|<span data-ttu-id="4ed3e-110">Enthält eine Auflistung von Endpunkt Elementen, mit denen die Endpunkte angegeben werden, mit denen dieser Client eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="4ed3e-110">Contains a collection of endpoint elements that specify the endpoints that this client can connect to.</span></span>|
|[\<metadata>](metadata.md)|<span data-ttu-id="4ed3e-111">Enthält Einstellungen zum Verarbeiten von Metadaten.</span><span class="sxs-lookup"><span data-stu-id="4ed3e-111">Contains settings for processing metadata.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4ed3e-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4ed3e-112">Parent Elements</span></span>

|<span data-ttu-id="4ed3e-113">Element</span><span class="sxs-lookup"><span data-stu-id="4ed3e-113">Element</span></span>|<span data-ttu-id="4ed3e-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4ed3e-114">Description</span></span>|
|-------------|-----------------|
|[\<system.serviceModel>](system-servicemodel.md)|<span data-ttu-id="4ed3e-115">Das Stammelement aller Windows Communication Foundation (WCF)-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="4ed3e-115">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4ed3e-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="4ed3e-116">Remarks</span></span>

 <span data-ttu-id="4ed3e-117">Der `client`-Abschnitt definiert eine Liste der Endpunkte, mit denen ein Client eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="4ed3e-117">The `client` section defines a list of endpoints that a client can connect to.</span></span> <span data-ttu-id="4ed3e-118">Jeder im Clientabschnitt aufgeführte Endpunkt definiert seine eigene Bindung, sein eigenes Verhalten und seinen eigenen Vertrag.</span><span class="sxs-lookup"><span data-stu-id="4ed3e-118">Each endpoint listed in the client section defines its own binding, behavior, and contract.</span></span> <span data-ttu-id="4ed3e-119">Er wird eindeutig anhand der Kombination des `name`-Attributs mit dem `contract`-Attribut identifiziert.</span><span class="sxs-lookup"><span data-stu-id="4ed3e-119">It is uniquely identified by the combination of the `name` and `contract` attributes.</span></span> <span data-ttu-id="4ed3e-120">Der Clientcode gibt den `name` an, um eine Verbindung zu einem Endpunkt für den durch den Client implementierten Dienst herzustellen.</span><span class="sxs-lookup"><span data-stu-id="4ed3e-120">The client code specifies the `name` to connect to an endpoint for the service that the client implements.</span></span> <span data-ttu-id="4ed3e-121">Wenn das `name`-Attribut ausgelassen wird, fungiert der Endpunkt als Standardendpunkt für den Vertrag, den er implementiert.</span><span class="sxs-lookup"><span data-stu-id="4ed3e-121">If the `name` attribute is omitted, the endpoint acts as the default endpoint for the contract it implements.</span></span>

 <span data-ttu-id="4ed3e-122">Darüber hinaus gibt dieser Abschnitt auch die Einstellungen zum Verarbeiten von Metadaten an.</span><span class="sxs-lookup"><span data-stu-id="4ed3e-122">In addition, this section also specifies settings for processing metadata.</span></span>

## <a name="example"></a><span data-ttu-id="4ed3e-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4ed3e-123">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="4ed3e-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4ed3e-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- [<span data-ttu-id="4ed3e-125">WCF-Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="4ed3e-125">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="4ed3e-126">Clients</span><span class="sxs-lookup"><span data-stu-id="4ed3e-126">Clients</span></span>](../../../wcf/feature-details/clients.md)
