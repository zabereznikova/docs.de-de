---
title: <workflowControlEndpoint>
ms.date: 03/30/2017
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
ms.openlocfilehash: 670c1573fe4378a18c19d0a58fe58241745725bd
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854783"
---
# \<workflowControlEndpoint>
<span data-ttu-id="0d4dc-101">Dieses Konfigurationselement definiert einen Standardendpunkt zur Steuerung der Ausführung von Workflowinstanzen (create, run, suspend, terminate usw.).</span><span class="sxs-lookup"><span data-stu-id="0d4dc-101">This configuration element defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowControlEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="0d4dc-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="0d4dc-102">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0d4dc-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0d4dc-103">Attributes and Elements</span></span>  
 <span data-ttu-id="0d4dc-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0d4dc-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0d4dc-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="0d4dc-105">Attributes</span></span>  
  
|<span data-ttu-id="0d4dc-106">attribute</span><span class="sxs-lookup"><span data-stu-id="0d4dc-106">Attribute</span></span>|<span data-ttu-id="0d4dc-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0d4dc-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0d4dc-108">name</span><span class="sxs-lookup"><span data-stu-id="0d4dc-108">name</span></span>|<span data-ttu-id="0d4dc-109">Eine Zeichenfolge, die den Namen der Konfiguration des Standardendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="0d4dc-109">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="0d4dc-110">Der Name wird im `endpointConfiguration`-Attribut des Dienstendpunkts zum Verknüpfen eines Standardendpunkts mit der Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="0d4dc-110">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0d4dc-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0d4dc-111">Child Elements</span></span>  
 <span data-ttu-id="0d4dc-112">Keine</span><span class="sxs-lookup"><span data-stu-id="0d4dc-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0d4dc-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0d4dc-113">Parent Elements</span></span>  
  
|<span data-ttu-id="0d4dc-114">Element</span><span class="sxs-lookup"><span data-stu-id="0d4dc-114">Element</span></span>|<span data-ttu-id="0d4dc-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0d4dc-115">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="0d4dc-116">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="0d4dc-116">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0d4dc-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0d4dc-117">See also</span></span>

- <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>
