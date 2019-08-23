---
title: <endToEndTracing>
ms.date: 03/30/2017
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
ms.openlocfilehash: 6b23728451a051f21ad3863b9a29e6290c3c837a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919012"
---
# <a name="endtoendtracing"></a><span data-ttu-id="dc9b0-101">\<endToEndTracing></span><span class="sxs-lookup"><span data-stu-id="dc9b0-101">\<endToEndTracing></span></span>
<span data-ttu-id="dc9b0-102">Ein Konfigurationselement, das Ihnen ermöglicht, unterschiedliche Aspekte der End-to-End-Ablaufverfolgung während der Ausführung einer Dienstanwendung zu aktivieren bzw. zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="dc9b0-102">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
 <span data-ttu-id="dc9b0-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="dc9b0-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="dc9b0-104">\<Diagnose ></span><span class="sxs-lookup"><span data-stu-id="dc9b0-104">\<diagnostic></span></span>  
<span data-ttu-id="dc9b0-105">\<endToEndTracing></span><span class="sxs-lookup"><span data-stu-id="dc9b0-105">\<endToEndTracing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc9b0-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="dc9b0-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc9b0-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="dc9b0-107">Attributes and Elements</span></span>  
 <span data-ttu-id="dc9b0-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dc9b0-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc9b0-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="dc9b0-109">Attributes</span></span>  
  
|<span data-ttu-id="dc9b0-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="dc9b0-110">Attribute</span></span>|<span data-ttu-id="dc9b0-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dc9b0-111">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="dc9b0-112">Ein boolescher Wert, der angibt, ob die Aktivitätsablaufverfolgung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="dc9b0-112">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="dc9b0-113">Ein boolescher Wert, der angibt, ob die Nachrichtenfluss-Ablaufverfolgung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="dc9b0-113">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="dc9b0-114">Ein boolescher Wert, der angibt, ob das propagate-Attribut auf true festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="dc9b0-114">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dc9b0-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dc9b0-115">Child Elements</span></span>  
 <span data-ttu-id="dc9b0-116">Keine</span><span class="sxs-lookup"><span data-stu-id="dc9b0-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dc9b0-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dc9b0-117">Parent Elements</span></span>  
  
|<span data-ttu-id="dc9b0-118">Element</span><span class="sxs-lookup"><span data-stu-id="dc9b0-118">Element</span></span>|<span data-ttu-id="dc9b0-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dc9b0-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dc9b0-120">\<Diagnose ></span><span class="sxs-lookup"><span data-stu-id="dc9b0-120">\<diagnostics></span></span>](diagnostics.md)|<span data-ttu-id="dc9b0-121">Definiert WCF-Einstellungen für die Laufzeitüberprüfung und Steuerungen für den Administrator.</span><span class="sxs-lookup"><span data-stu-id="dc9b0-121">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dc9b0-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dc9b0-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>
- <xref:System.ServiceModel.Configuration.EndToEndTracingElement>
- [<span data-ttu-id="dc9b0-123">End-to-End-Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="dc9b0-123">End-to-End Tracing</span></span>](../../../wcf/diagnostics/tracing/end-to-end-tracing.md)
