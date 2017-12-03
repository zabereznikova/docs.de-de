---
title: '&lt;workflowControlEndpoint&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 741968e160683ab38f79effdfa0bdf56053cfb93
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltworkflowcontrolendpointgt"></a><span data-ttu-id="3013b-102">&lt;workflowControlEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="3013b-102">&lt;workflowControlEndpoint&gt;</span></span>
<span data-ttu-id="3013b-103">Dieses Konfigurationselement definiert einen Standardendpunkt zur Steuerung der Ausführung von Workflowinstanzen (create, run, suspend, terminate usw.).</span><span class="sxs-lookup"><span data-stu-id="3013b-103">This configuration element defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>  
  
<span data-ttu-id="3013b-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="3013b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3013b-105">\<StandardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="3013b-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3013b-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="3013b-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3013b-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3013b-107">Attributes and Elements</span></span>  
 <span data-ttu-id="3013b-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3013b-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3013b-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="3013b-109">Attributes</span></span>  
  
|<span data-ttu-id="3013b-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="3013b-110">Attribute</span></span>|<span data-ttu-id="3013b-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3013b-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3013b-112">Name</span><span class="sxs-lookup"><span data-stu-id="3013b-112">name</span></span>|<span data-ttu-id="3013b-113">Eine Zeichenfolge, die den Namen der Konfiguration des Standardendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="3013b-113">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="3013b-114">Der Name wird im `endpointConfiguration`-Attribut des Dienstendpunkts zum Verknüpfen eines Standardendpunkts mit der Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="3013b-114">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3013b-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3013b-115">Child Elements</span></span>  
 <span data-ttu-id="3013b-116">Keine</span><span class="sxs-lookup"><span data-stu-id="3013b-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3013b-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3013b-117">Parent Elements</span></span>  
  
|<span data-ttu-id="3013b-118">Element</span><span class="sxs-lookup"><span data-stu-id="3013b-118">Element</span></span>|<span data-ttu-id="3013b-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3013b-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3013b-120">\<StandardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="3013b-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="3013b-121">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="3013b-121">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3013b-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3013b-122">See Also</span></span>  
 <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>
