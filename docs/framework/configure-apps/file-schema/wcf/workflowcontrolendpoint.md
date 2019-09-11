---
title: <workflowControlEndpoint>
ms.date: 03/30/2017
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
ms.openlocfilehash: 670c1573fe4378a18c19d0a58fe58241745725bd
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854783"
---
# <a name="workflowcontrolendpoint"></a><span data-ttu-id="ebd8a-101">\<workflowControlEndpoint></span><span class="sxs-lookup"><span data-stu-id="ebd8a-101">\<workflowControlEndpoint></span></span>
<span data-ttu-id="ebd8a-102">Dieses Konfigurationselement definiert einen Standardendpunkt zur Steuerung der Ausführung von Workflowinstanzen (create, run, suspend, terminate usw.).</span><span class="sxs-lookup"><span data-stu-id="ebd8a-102">This configuration element defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>  
  
<span data-ttu-id="ebd8a-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ebd8a-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ebd8a-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ebd8a-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ebd8a-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<standardendpoints->** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="ebd8a-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="ebd8a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<WorkflowControlEndpoint->**</span><span class="sxs-lookup"><span data-stu-id="ebd8a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowControlEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebd8a-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="ebd8a-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ebd8a-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ebd8a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ebd8a-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ebd8a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ebd8a-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="ebd8a-110">Attributes</span></span>  
  
|<span data-ttu-id="ebd8a-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="ebd8a-111">Attribute</span></span>|<span data-ttu-id="ebd8a-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ebd8a-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ebd8a-113">NAME</span><span class="sxs-lookup"><span data-stu-id="ebd8a-113">name</span></span>|<span data-ttu-id="ebd8a-114">Eine Zeichenfolge, die den Namen der Konfiguration des Standardendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="ebd8a-114">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="ebd8a-115">Der Name wird im `endpointConfiguration`-Attribut des Dienstendpunkts zum Verknüpfen eines Standardendpunkts mit der Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="ebd8a-115">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ebd8a-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ebd8a-116">Child Elements</span></span>  
 <span data-ttu-id="ebd8a-117">Keine</span><span class="sxs-lookup"><span data-stu-id="ebd8a-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ebd8a-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ebd8a-118">Parent Elements</span></span>  
  
|<span data-ttu-id="ebd8a-119">Element</span><span class="sxs-lookup"><span data-stu-id="ebd8a-119">Element</span></span>|<span data-ttu-id="ebd8a-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ebd8a-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ebd8a-121">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="ebd8a-121">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="ebd8a-122">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="ebd8a-122">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ebd8a-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ebd8a-123">See also</span></span>

- <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>
