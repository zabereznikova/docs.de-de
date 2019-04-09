---
title: <endToEndTracing>
ms.date: 03/30/2017
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
ms.openlocfilehash: 266b33e9b0386d0346a86ba8bd82cc65def4f0c2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180153"
---
# <a name="endtoendtracing"></a><span data-ttu-id="b6a29-101">\<endToEndTracing></span><span class="sxs-lookup"><span data-stu-id="b6a29-101">\<endToEndTracing></span></span>
<span data-ttu-id="b6a29-102">Ein Konfigurationselement, das Ihnen ermöglicht, unterschiedliche Aspekte der End-to-End-Ablaufverfolgung während der Ausführung einer Dienstanwendung zu aktivieren bzw. zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="b6a29-102">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
 <span data-ttu-id="b6a29-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b6a29-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="b6a29-104">\<diagnostic></span><span class="sxs-lookup"><span data-stu-id="b6a29-104">\<diagnostic></span></span>  
<span data-ttu-id="b6a29-105">\<endToEndTracing></span><span class="sxs-lookup"><span data-stu-id="b6a29-105">\<endToEndTracing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6a29-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="b6a29-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b6a29-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b6a29-107">Attributes and Elements</span></span>  
 <span data-ttu-id="b6a29-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b6a29-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b6a29-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="b6a29-109">Attributes</span></span>  
  
|<span data-ttu-id="b6a29-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="b6a29-110">Attribute</span></span>|<span data-ttu-id="b6a29-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b6a29-111">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="b6a29-112">Ein boolescher Wert, der angibt, ob die Aktivitätsablaufverfolgung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="b6a29-112">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="b6a29-113">Ein boolescher Wert, der angibt, ob die Nachrichtenfluss-Ablaufverfolgung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="b6a29-113">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="b6a29-114">Ein boolescher Wert, der angibt, ob das propagate-Attribut auf true festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="b6a29-114">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b6a29-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b6a29-115">Child Elements</span></span>  
 <span data-ttu-id="b6a29-116">Keine</span><span class="sxs-lookup"><span data-stu-id="b6a29-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b6a29-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b6a29-117">Parent Elements</span></span>  
  
|<span data-ttu-id="b6a29-118">Element</span><span class="sxs-lookup"><span data-stu-id="b6a29-118">Element</span></span>|<span data-ttu-id="b6a29-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b6a29-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6a29-120">\<diagnostics></span><span class="sxs-lookup"><span data-stu-id="b6a29-120">\<diagnostics></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)|<span data-ttu-id="b6a29-121">Definiert WCF-Einstellungen für die Laufzeitüberprüfung und Steuerungen für den Administrator.</span><span class="sxs-lookup"><span data-stu-id="b6a29-121">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b6a29-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b6a29-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>
- <xref:System.ServiceModel.Configuration.EndToEndTracingElement>
- [<span data-ttu-id="b6a29-123">End-to-End-Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="b6a29-123">End-to-End Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing.md)
