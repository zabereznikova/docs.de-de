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
ms.openlocfilehash: bb187302000291fd6b540b562ed7aebf1db7add2
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltendtoendtracinggt"></a><span data-ttu-id="bcc43-102">&lt;endToEndTracing&gt;</span><span class="sxs-lookup"><span data-stu-id="bcc43-102">&lt;endToEndTracing&gt;</span></span>
<span data-ttu-id="bcc43-103">Ein Konfigurationselement, das Ihnen ermöglicht, unterschiedliche Aspekte der End-to-End-Ablaufverfolgung während der Ausführung einer Dienstanwendung zu aktivieren bzw. zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="bcc43-103">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
 <span data-ttu-id="bcc43-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="bcc43-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="bcc43-105">\<Diagnose ></span><span class="sxs-lookup"><span data-stu-id="bcc43-105">\<diagnostic></span></span>  
<span data-ttu-id="bcc43-106">\<EndToEndTracing ></span><span class="sxs-lookup"><span data-stu-id="bcc43-106">\<endToEndTracing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcc43-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="bcc43-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
   <diagnostics>  
       <endToEndTracing activityTracing="Boolean"  
          messageFlowTracing="Boolean"  
          propagateActivity="Boolean" />  
   </diagnostics>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bcc43-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bcc43-108">Attributes and Elements</span></span>  
 <span data-ttu-id="bcc43-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bcc43-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bcc43-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="bcc43-110">Attributes</span></span>  
  
|<span data-ttu-id="bcc43-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="bcc43-111">Attribute</span></span>|<span data-ttu-id="bcc43-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bcc43-112">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="bcc43-113">Ein boolescher Wert, der angibt, ob die Aktivitätsablaufverfolgung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="bcc43-113">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="bcc43-114">Ein boolescher Wert, der angibt, ob die Nachrichtenfluss-Ablaufverfolgung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="bcc43-114">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="bcc43-115">Ein boolescher Wert, der angibt, ob das propagate-Attribut auf true festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="bcc43-115">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bcc43-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bcc43-116">Child Elements</span></span>  
 <span data-ttu-id="bcc43-117">Keine</span><span class="sxs-lookup"><span data-stu-id="bcc43-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bcc43-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bcc43-118">Parent Elements</span></span>  
  
|<span data-ttu-id="bcc43-119">Element</span><span class="sxs-lookup"><span data-stu-id="bcc43-119">Element</span></span>|<span data-ttu-id="bcc43-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bcc43-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bcc43-121">\<Diagnose ></span><span class="sxs-lookup"><span data-stu-id="bcc43-121">\<diagnostics></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)|<span data-ttu-id="bcc43-122">Definiert WCF-Einstellungen für die Laufzeitüberprüfung und Steuerungen für den Administrator.</span><span class="sxs-lookup"><span data-stu-id="bcc43-122">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bcc43-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bcc43-123">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection>  
 <xref:System.ServiceModel.Diagnostics>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>  
 <xref:System.ServiceModel.Configuration.EndToEndTracingElement>  
 [<span data-ttu-id="bcc43-124">End-to-End-Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="bcc43-124">End-to-End Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing.md)
