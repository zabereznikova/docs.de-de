---
title: '&lt;endToEndTracing&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a43801f4c45d7ac518c3b24cadc58ffbec40adb4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltendtoendtracinggt"></a><span data-ttu-id="943d8-102">&lt;endToEndTracing&gt;</span><span class="sxs-lookup"><span data-stu-id="943d8-102">&lt;endToEndTracing&gt;</span></span>
<span data-ttu-id="943d8-103">Ein Konfigurationselement, das Ihnen ermöglicht, unterschiedliche Aspekte der End-to-End-Ablaufverfolgung während der Ausführung einer Dienstanwendung zu aktivieren bzw. zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="943d8-103">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
 <span data-ttu-id="943d8-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="943d8-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="943d8-105">\<Diagnose ></span><span class="sxs-lookup"><span data-stu-id="943d8-105">\<diagnostic></span></span>  
<span data-ttu-id="943d8-106">\<EndToEndTracing ></span><span class="sxs-lookup"><span data-stu-id="943d8-106">\<endToEndTracing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="943d8-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="943d8-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
   <diagnostics>  
       <endToEndTracing activityTracing="Boolean"  
          messageFlowTracing="Boolean"  
          propagateActivity="Boolean" />  
   </diagnostics>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="943d8-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="943d8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="943d8-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="943d8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="943d8-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="943d8-110">Attributes</span></span>  
  
|<span data-ttu-id="943d8-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="943d8-111">Attribute</span></span>|<span data-ttu-id="943d8-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="943d8-112">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="943d8-113">Ein boolescher Wert, der angibt, ob die Aktivitätsablaufverfolgung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="943d8-113">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="943d8-114">Ein boolescher Wert, der angibt, ob die Nachrichtenfluss-Ablaufverfolgung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="943d8-114">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="943d8-115">Ein boolescher Wert, der angibt, ob das propagate-Attribut auf true festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="943d8-115">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="943d8-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="943d8-116">Child Elements</span></span>  
 <span data-ttu-id="943d8-117">Keine</span><span class="sxs-lookup"><span data-stu-id="943d8-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="943d8-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="943d8-118">Parent Elements</span></span>  
  
|<span data-ttu-id="943d8-119">Element</span><span class="sxs-lookup"><span data-stu-id="943d8-119">Element</span></span>|<span data-ttu-id="943d8-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="943d8-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="943d8-121">\<Diagnose ></span><span class="sxs-lookup"><span data-stu-id="943d8-121">\<diagnostics></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)|<span data-ttu-id="943d8-122">Definiert WCF-Einstellungen für die Laufzeitüberprüfung und Steuerungen für den Administrator.</span><span class="sxs-lookup"><span data-stu-id="943d8-122">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="943d8-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="943d8-123">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection>  
 <xref:System.ServiceModel.Diagnostics>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>  
 <xref:System.ServiceModel.Configuration.EndToEndTracingElement>  
 [<span data-ttu-id="943d8-124">End-to-End-Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="943d8-124">End-to-End Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing.md)
