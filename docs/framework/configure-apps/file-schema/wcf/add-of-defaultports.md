---
title: '&lt;add&gt; von &lt;defaultPorts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1efe61bf5f4276836c65e9c81d316dc0664f3de2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltdefaultportsgt"></a><span data-ttu-id="f66e4-102">&lt;add&gt; von &lt;defaultPorts&gt;</span><span class="sxs-lookup"><span data-stu-id="f66e4-102">&lt;add&gt; of &lt;defaultPorts&gt;</span></span>
<span data-ttu-id="f66e4-103">Ein Standardkommunikationsendpunkt, den die Clientanwendung überwacht.</span><span class="sxs-lookup"><span data-stu-id="f66e4-103">A default communications endpoint that the client application listens to.</span></span>  
  
 <span data-ttu-id="f66e4-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="f66e4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f66e4-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="f66e4-105">\<behaviors></span></span>  
<span data-ttu-id="f66e4-106">\<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="f66e4-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="f66e4-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="f66e4-107">\<behavior></span></span>  
<span data-ttu-id="f66e4-108">\<UseRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="f66e4-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="f66e4-109">\<DefaultPorts ></span><span class="sxs-lookup"><span data-stu-id="f66e4-109">\<defaultPorts></span></span>  
<span data-ttu-id="f66e4-110">\<add></span><span class="sxs-lookup"><span data-stu-id="f66e4-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f66e4-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="f66e4-111">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>   <defaultPorts>      <add port="Integer" scheme="String" />   </defaultPorts></useRequestHeadersForMetadataAddress>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f66e4-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f66e4-112">Attributes and Elements</span></span>  
 <span data-ttu-id="f66e4-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f66e4-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f66e4-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="f66e4-114">Attributes</span></span>  
  
|<span data-ttu-id="f66e4-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="f66e4-115">Attribute</span></span>|<span data-ttu-id="f66e4-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f66e4-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f66e4-117">Port</span><span class="sxs-lookup"><span data-stu-id="f66e4-117">port</span></span>|<span data-ttu-id="f66e4-118">Eine ganze Zahl, die die Nummer des Standardkommunikationsports angibt.</span><span class="sxs-lookup"><span data-stu-id="f66e4-118">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="f66e4-119">scheme</span><span class="sxs-lookup"><span data-stu-id="f66e4-119">scheme</span></span>|<span data-ttu-id="f66e4-120">Eine Zeichenfolge, die die Gruppe von Protokolleinstellungen angibt, die einem Kommunikationsport zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="f66e4-120">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f66e4-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f66e4-121">Child Elements</span></span>  
 <span data-ttu-id="f66e4-122">Keine</span><span class="sxs-lookup"><span data-stu-id="f66e4-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f66e4-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f66e4-123">Parent Elements</span></span>  
  
|<span data-ttu-id="f66e4-124">Element</span><span class="sxs-lookup"><span data-stu-id="f66e4-124">Element</span></span>|<span data-ttu-id="f66e4-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f66e4-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f66e4-126">\<DefaultPorts ></span><span class="sxs-lookup"><span data-stu-id="f66e4-126">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="f66e4-127">Eine Auflistung von Standardports mit den Standardkommunikationsendpunkten, die von der Clientanwendung überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="f66e4-127">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f66e4-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f66e4-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DefaultPortElement>
