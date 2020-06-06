---
title: <client>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
ms.openlocfilehash: 7aa3755be97a839cb576d53852b75cfe50e39276
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "72773946"
---
# \<client>
<span data-ttu-id="dad02-101">Das `client`-Element definiert eine Liste der Endpunkte, mit denen ein Client eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="dad02-101">The `client` element defines a list of endpoints that a client can connect to.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<client>**

## <a name="syntax"></a><span data-ttu-id="dad02-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="dad02-102">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="dad02-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="dad02-103">Attributes and Elements</span></span>
 <span data-ttu-id="dad02-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dad02-104">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="dad02-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="dad02-105">Attributes</span></span>
 <span data-ttu-id="dad02-106">Keine</span><span class="sxs-lookup"><span data-stu-id="dad02-106">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="dad02-107">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dad02-107">Child Elements</span></span>

|<span data-ttu-id="dad02-108">Element</span><span class="sxs-lookup"><span data-stu-id="dad02-108">Element</span></span>|<span data-ttu-id="dad02-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="dad02-109">Description</span></span>|
|-------------|-----------------|
|[\<endpoint>](endpoint-of-client.md)|<span data-ttu-id="dad02-110">Enthält eine Auflistung von Endpunkt Elementen, mit denen die Endpunkte angegeben werden, mit denen dieser Client eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="dad02-110">Contains a collection of endpoint elements that specify the endpoints that this client can connect to.</span></span>|
|[\<metadata>](metadata.md)|<span data-ttu-id="dad02-111">Enthält Einstellungen zum Verarbeiten von Metadaten.</span><span class="sxs-lookup"><span data-stu-id="dad02-111">Contains settings for processing metadata.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="dad02-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dad02-112">Parent Elements</span></span>

|<span data-ttu-id="dad02-113">Element</span><span class="sxs-lookup"><span data-stu-id="dad02-113">Element</span></span>|<span data-ttu-id="dad02-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="dad02-114">Description</span></span>|
|-------------|-----------------|
|[\<system.serviceModel>](system-servicemodel.md)|<span data-ttu-id="dad02-115">Das Stammelement aller Windows Communication Foundation (WCF)-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="dad02-115">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|

## <a name="remarks"></a><span data-ttu-id="dad02-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="dad02-116">Remarks</span></span>
 <span data-ttu-id="dad02-117">Der `client`-Abschnitt definiert eine Liste der Endpunkte, mit denen ein Client eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="dad02-117">The `client` section defines a list of endpoints that a client can connect to.</span></span> <span data-ttu-id="dad02-118">Jeder im Clientabschnitt aufgeführte Endpunkt definiert seine eigene Bindung, sein eigenes Verhalten und seinen eigenen Vertrag.</span><span class="sxs-lookup"><span data-stu-id="dad02-118">Each endpoint listed in the client section defines its own binding, behavior, and contract.</span></span> <span data-ttu-id="dad02-119">Er wird eindeutig anhand der Kombination des `name`-Attributs mit dem `contract`-Attribut identifiziert.</span><span class="sxs-lookup"><span data-stu-id="dad02-119">It is uniquely identified by the combination of the `name` and `contract` attributes.</span></span> <span data-ttu-id="dad02-120">Der Clientcode gibt den `name` an, um eine Verbindung zu einem Endpunkt für den durch den Client implementierten Dienst herzustellen.</span><span class="sxs-lookup"><span data-stu-id="dad02-120">The client code specifies the `name` to connect to an endpoint for the service that the client implements.</span></span> <span data-ttu-id="dad02-121">Wenn das `name`-Attribut ausgelassen wird, fungiert der Endpunkt als Standardendpunkt für den Vertrag, den er implementiert.</span><span class="sxs-lookup"><span data-stu-id="dad02-121">If the `name` attribute is omitted, the endpoint acts as the default endpoint for the contract it implements.</span></span>

 <span data-ttu-id="dad02-122">Darüber hinaus gibt dieser Abschnitt auch die Einstellungen zum Verarbeiten von Metadaten an.</span><span class="sxs-lookup"><span data-stu-id="dad02-122">In addition, this section also specifies settings for processing metadata.</span></span>

## <a name="example"></a><span data-ttu-id="dad02-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dad02-123">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="dad02-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dad02-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- [<span data-ttu-id="dad02-125">WCF-Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="dad02-125">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="dad02-126">Clients</span><span class="sxs-lookup"><span data-stu-id="dad02-126">Clients</span></span>](../../../wcf/feature-details/clients.md)
