---
title: <endToEndTracing>
ms.date: 03/30/2017
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
ms.openlocfilehash: 1a274f15800c6a132994a2437943c83982de9de0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855295"
---
# \<endToEndTracing>
<span data-ttu-id="56b2e-101">Ein Konfigurationselement, das Ihnen ermöglicht, unterschiedliche Aspekte der End-to-End-Ablaufverfolgung während der Ausführung einer Dienstanwendung zu aktivieren bzw. zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="56b2e-101">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endToEndTracing>**  
  
## <a name="syntax"></a><span data-ttu-id="56b2e-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="56b2e-102">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56b2e-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="56b2e-103">Attributes and Elements</span></span>  
 <span data-ttu-id="56b2e-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="56b2e-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56b2e-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="56b2e-105">Attributes</span></span>  
  
|<span data-ttu-id="56b2e-106">attribute</span><span class="sxs-lookup"><span data-stu-id="56b2e-106">Attribute</span></span>|<span data-ttu-id="56b2e-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="56b2e-107">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="56b2e-108">Ein boolescher Wert, der angibt, ob die Aktivitätsablaufverfolgung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="56b2e-108">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="56b2e-109">Ein boolescher Wert, der angibt, ob die Nachrichtenfluss-Ablaufverfolgung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="56b2e-109">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="56b2e-110">Ein boolescher Wert, der angibt, ob das propagate-Attribut auf true festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="56b2e-110">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="56b2e-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="56b2e-111">Child Elements</span></span>  
 <span data-ttu-id="56b2e-112">Keine</span><span class="sxs-lookup"><span data-stu-id="56b2e-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="56b2e-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="56b2e-113">Parent Elements</span></span>  
  
|<span data-ttu-id="56b2e-114">Element</span><span class="sxs-lookup"><span data-stu-id="56b2e-114">Element</span></span>|<span data-ttu-id="56b2e-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="56b2e-115">Description</span></span>|  
|-------------|-----------------|  
|[\<diagnostics>](diagnostics.md)|<span data-ttu-id="56b2e-116">Definiert WCF-Einstellungen für die Laufzeitüberprüfung und Steuerungen für den Administrator.</span><span class="sxs-lookup"><span data-stu-id="56b2e-116">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="56b2e-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="56b2e-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>
- <xref:System.ServiceModel.Configuration.EndToEndTracingElement>
- [<span data-ttu-id="56b2e-118">End-to-End-Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="56b2e-118">End-to-End Tracing</span></span>](../../../wcf/diagnostics/tracing/end-to-end-tracing.md)
