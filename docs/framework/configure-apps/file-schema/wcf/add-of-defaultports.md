---
title: <add> von <defaultPorts>
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: 799715ef008274ead6b745e8ab97e769cb59e6b5
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55261595"
---
# <a name="add-of-defaultports"></a><span data-ttu-id="80ed0-102">\<Hinzufügen > der \<DefaultPorts ></span><span class="sxs-lookup"><span data-stu-id="80ed0-102">\<add> of \<defaultPorts></span></span>
<span data-ttu-id="80ed0-103">Ein Standardkommunikationsendpunkt, den die Clientanwendung überwacht.</span><span class="sxs-lookup"><span data-stu-id="80ed0-103">A default communications endpoint that the client application listens to.</span></span>  
  
 <span data-ttu-id="80ed0-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="80ed0-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="80ed0-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="80ed0-105">\<behaviors></span></span>  
<span data-ttu-id="80ed0-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="80ed0-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="80ed0-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="80ed0-107">\<behavior></span></span>  
<span data-ttu-id="80ed0-108">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="80ed0-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="80ed0-109">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="80ed0-109">\<defaultPorts></span></span>  
<span data-ttu-id="80ed0-110">\<add></span><span class="sxs-lookup"><span data-stu-id="80ed0-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80ed0-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="80ed0-111">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="80ed0-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="80ed0-112">Attributes and Elements</span></span>  
 <span data-ttu-id="80ed0-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="80ed0-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="80ed0-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="80ed0-114">Attributes</span></span>  
  
|<span data-ttu-id="80ed0-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="80ed0-115">Attribute</span></span>|<span data-ttu-id="80ed0-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="80ed0-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="80ed0-117">Port</span><span class="sxs-lookup"><span data-stu-id="80ed0-117">port</span></span>|<span data-ttu-id="80ed0-118">Eine ganze Zahl, die die Nummer des Standardkommunikationsports angibt.</span><span class="sxs-lookup"><span data-stu-id="80ed0-118">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="80ed0-119">scheme</span><span class="sxs-lookup"><span data-stu-id="80ed0-119">scheme</span></span>|<span data-ttu-id="80ed0-120">Eine Zeichenfolge, die die Gruppe von Protokolleinstellungen angibt, die einem Kommunikationsport zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="80ed0-120">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="80ed0-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="80ed0-121">Child Elements</span></span>  
 <span data-ttu-id="80ed0-122">Keine</span><span class="sxs-lookup"><span data-stu-id="80ed0-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="80ed0-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="80ed0-123">Parent Elements</span></span>  
  
|<span data-ttu-id="80ed0-124">Element</span><span class="sxs-lookup"><span data-stu-id="80ed0-124">Element</span></span>|<span data-ttu-id="80ed0-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="80ed0-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="80ed0-126">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="80ed0-126">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="80ed0-127">Eine Auflistung von Standardports mit den Standardkommunikationsendpunkten, die von der Clientanwendung überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="80ed0-127">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="80ed0-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="80ed0-128">See also</span></span>
- <xref:System.ServiceModel.Configuration.DefaultPortElement>
