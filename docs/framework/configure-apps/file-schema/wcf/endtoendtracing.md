---
title: '&lt;endToEndTracing&gt;'
ms.date: 03/30/2017
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
ms.openlocfilehash: c2f5e33eff4fdc6dfa85bcc10b59a7c1436cabb6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54519376"
---
# <a name="ltendtoendtracinggt"></a><span data-ttu-id="64cfa-102">&lt;endToEndTracing&gt;</span><span class="sxs-lookup"><span data-stu-id="64cfa-102">&lt;endToEndTracing&gt;</span></span>
<span data-ttu-id="64cfa-103">Ein Konfigurationselement, das Ihnen ermöglicht, unterschiedliche Aspekte der End-to-End-Ablaufverfolgung während der Ausführung einer Dienstanwendung zu aktivieren bzw. zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="64cfa-103">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
 <span data-ttu-id="64cfa-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="64cfa-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="64cfa-105">\<diagnostic></span><span class="sxs-lookup"><span data-stu-id="64cfa-105">\<diagnostic></span></span>  
<span data-ttu-id="64cfa-106">\<endToEndTracing></span><span class="sxs-lookup"><span data-stu-id="64cfa-106">\<endToEndTracing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64cfa-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="64cfa-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="64cfa-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="64cfa-108">Attributes and Elements</span></span>  
 <span data-ttu-id="64cfa-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="64cfa-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="64cfa-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="64cfa-110">Attributes</span></span>  
  
|<span data-ttu-id="64cfa-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="64cfa-111">Attribute</span></span>|<span data-ttu-id="64cfa-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="64cfa-112">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="64cfa-113">Ein boolescher Wert, der angibt, ob die Aktivitätsablaufverfolgung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="64cfa-113">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="64cfa-114">Ein boolescher Wert, der angibt, ob die Nachrichtenfluss-Ablaufverfolgung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="64cfa-114">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="64cfa-115">Ein boolescher Wert, der angibt, ob das propagate-Attribut auf true festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="64cfa-115">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="64cfa-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="64cfa-116">Child Elements</span></span>  
 <span data-ttu-id="64cfa-117">Keine</span><span class="sxs-lookup"><span data-stu-id="64cfa-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="64cfa-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="64cfa-118">Parent Elements</span></span>  
  
|<span data-ttu-id="64cfa-119">Element</span><span class="sxs-lookup"><span data-stu-id="64cfa-119">Element</span></span>|<span data-ttu-id="64cfa-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="64cfa-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="64cfa-121">\<diagnostics></span><span class="sxs-lookup"><span data-stu-id="64cfa-121">\<diagnostics></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)|<span data-ttu-id="64cfa-122">Definiert WCF-Einstellungen für die Laufzeitüberprüfung und Steuerungen für den Administrator.</span><span class="sxs-lookup"><span data-stu-id="64cfa-122">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="64cfa-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64cfa-123">See also</span></span>
- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>
- <xref:System.ServiceModel.Configuration.EndToEndTracingElement>
- [<span data-ttu-id="64cfa-124">End-to-End-Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="64cfa-124">End-to-End Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing.md)
