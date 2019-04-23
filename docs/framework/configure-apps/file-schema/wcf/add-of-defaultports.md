---
title: <add> von <defaultPorts>
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: 5200c8893a89488b72c2c71d1a3703bf2aad1235
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59136746"
---
# <a name="add-of-defaultports"></a><span data-ttu-id="c1e64-102">\<Hinzufügen > der \<DefaultPorts ></span><span class="sxs-lookup"><span data-stu-id="c1e64-102">\<add> of \<defaultPorts></span></span>
<span data-ttu-id="c1e64-103">Ein Standardkommunikationsendpunkt, den die Clientanwendung überwacht.</span><span class="sxs-lookup"><span data-stu-id="c1e64-103">A default communications endpoint that the client application listens to.</span></span>  
  
 <span data-ttu-id="c1e64-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c1e64-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c1e64-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="c1e64-105">\<behaviors></span></span>  
<span data-ttu-id="c1e64-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="c1e64-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="c1e64-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="c1e64-107">\<behavior></span></span>  
<span data-ttu-id="c1e64-108">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="c1e64-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="c1e64-109">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="c1e64-109">\<defaultPorts></span></span>  
<span data-ttu-id="c1e64-110">\<add></span><span class="sxs-lookup"><span data-stu-id="c1e64-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1e64-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="c1e64-111">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c1e64-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c1e64-112">Attributes and Elements</span></span>  
 <span data-ttu-id="c1e64-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c1e64-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c1e64-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="c1e64-114">Attributes</span></span>  
  
|<span data-ttu-id="c1e64-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="c1e64-115">Attribute</span></span>|<span data-ttu-id="c1e64-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1e64-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c1e64-117">Port</span><span class="sxs-lookup"><span data-stu-id="c1e64-117">port</span></span>|<span data-ttu-id="c1e64-118">Eine ganze Zahl, die die Nummer des Standardkommunikationsports angibt.</span><span class="sxs-lookup"><span data-stu-id="c1e64-118">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="c1e64-119">scheme</span><span class="sxs-lookup"><span data-stu-id="c1e64-119">scheme</span></span>|<span data-ttu-id="c1e64-120">Eine Zeichenfolge, die die Gruppe von Protokolleinstellungen angibt, die einem Kommunikationsport zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="c1e64-120">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c1e64-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c1e64-121">Child Elements</span></span>  
 <span data-ttu-id="c1e64-122">Keine</span><span class="sxs-lookup"><span data-stu-id="c1e64-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c1e64-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c1e64-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c1e64-124">Element</span><span class="sxs-lookup"><span data-stu-id="c1e64-124">Element</span></span>|<span data-ttu-id="c1e64-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1e64-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c1e64-126">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="c1e64-126">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="c1e64-127">Eine Auflistung von Standardports mit den Standardkommunikationsendpunkten, die von der Clientanwendung überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="c1e64-127">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c1e64-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1e64-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElement>
