---
title: '&lt;workflowControlEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
ms.openlocfilehash: 87c745cfb8f7cd98c25cd34fc1aa94a26a5ba507
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32754784"
---
# <a name="ltworkflowcontrolendpointgt"></a><span data-ttu-id="c1930-102">&lt;workflowControlEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="c1930-102">&lt;workflowControlEndpoint&gt;</span></span>
<span data-ttu-id="c1930-103">Dieses Konfigurationselement definiert einen Standardendpunkt zur Steuerung der Ausführung von Workflowinstanzen (create, run, suspend, terminate usw.).</span><span class="sxs-lookup"><span data-stu-id="c1930-103">This configuration element defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>  
  
<span data-ttu-id="c1930-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c1930-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c1930-105">\<StandardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="c1930-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1930-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="c1930-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c1930-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c1930-107">Attributes and Elements</span></span>  
 <span data-ttu-id="c1930-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c1930-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c1930-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="c1930-109">Attributes</span></span>  
  
|<span data-ttu-id="c1930-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="c1930-110">Attribute</span></span>|<span data-ttu-id="c1930-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1930-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c1930-112">Name</span><span class="sxs-lookup"><span data-stu-id="c1930-112">name</span></span>|<span data-ttu-id="c1930-113">Eine Zeichenfolge, die den Namen der Konfiguration des Standardendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="c1930-113">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="c1930-114">Der Name wird im `endpointConfiguration`-Attribut des Dienstendpunkts zum Verknüpfen eines Standardendpunkts mit der Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="c1930-114">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c1930-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c1930-115">Child Elements</span></span>  
 <span data-ttu-id="c1930-116">Keine</span><span class="sxs-lookup"><span data-stu-id="c1930-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c1930-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c1930-117">Parent Elements</span></span>  
  
|<span data-ttu-id="c1930-118">Element</span><span class="sxs-lookup"><span data-stu-id="c1930-118">Element</span></span>|<span data-ttu-id="c1930-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1930-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c1930-120">\<StandardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="c1930-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="c1930-121">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="c1930-121">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c1930-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1930-122">See Also</span></span>  
 <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>
