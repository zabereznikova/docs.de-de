---
title: <endToEndTracing>
ms.date: 03/30/2017
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
ms.openlocfilehash: 1867e307ba004af821045e7d1b5775c470d8a3e8
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266753"
---
# <a name="endtoendtracing"></a><span data-ttu-id="871ea-101">\<endToEndTracing></span><span class="sxs-lookup"><span data-stu-id="871ea-101">\<endToEndTracing></span></span>
<span data-ttu-id="871ea-102">Ein Konfigurationselement, das Ihnen ermöglicht, unterschiedliche Aspekte der End-to-End-Ablaufverfolgung während der Ausführung einer Dienstanwendung zu aktivieren bzw. zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="871ea-102">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
 <span data-ttu-id="871ea-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="871ea-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="871ea-104">\<diagnostic></span><span class="sxs-lookup"><span data-stu-id="871ea-104">\<diagnostic></span></span>  
<span data-ttu-id="871ea-105">\<endToEndTracing></span><span class="sxs-lookup"><span data-stu-id="871ea-105">\<endToEndTracing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="871ea-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="871ea-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="871ea-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="871ea-107">Attributes and Elements</span></span>  
 <span data-ttu-id="871ea-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="871ea-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="871ea-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="871ea-109">Attributes</span></span>  
  
|<span data-ttu-id="871ea-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="871ea-110">Attribute</span></span>|<span data-ttu-id="871ea-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="871ea-111">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="871ea-112">Ein boolescher Wert, der angibt, ob die Aktivitätsablaufverfolgung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="871ea-112">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="871ea-113">Ein boolescher Wert, der angibt, ob die Nachrichtenfluss-Ablaufverfolgung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="871ea-113">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="871ea-114">Ein boolescher Wert, der angibt, ob das propagate-Attribut auf true festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="871ea-114">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="871ea-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="871ea-115">Child Elements</span></span>  
 <span data-ttu-id="871ea-116">Keine</span><span class="sxs-lookup"><span data-stu-id="871ea-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="871ea-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="871ea-117">Parent Elements</span></span>  
  
|<span data-ttu-id="871ea-118">Element</span><span class="sxs-lookup"><span data-stu-id="871ea-118">Element</span></span>|<span data-ttu-id="871ea-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="871ea-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="871ea-120">\<diagnostics></span><span class="sxs-lookup"><span data-stu-id="871ea-120">\<diagnostics></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)|<span data-ttu-id="871ea-121">Definiert WCF-Einstellungen für die Laufzeitüberprüfung und Steuerungen für den Administrator.</span><span class="sxs-lookup"><span data-stu-id="871ea-121">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="871ea-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="871ea-122">See also</span></span>
- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>
- <xref:System.ServiceModel.Configuration.EndToEndTracingElement>
- [<span data-ttu-id="871ea-123">End-to-End-Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="871ea-123">End-to-End Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing.md)
