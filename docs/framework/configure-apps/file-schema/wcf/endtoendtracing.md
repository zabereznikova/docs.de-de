---
title: <endToEndTracing>
ms.date: 03/30/2017
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
ms.openlocfilehash: 1a274f15800c6a132994a2437943c83982de9de0
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855295"
---
# <a name="endtoendtracing"></a><span data-ttu-id="ab1f3-101">\<endToEndTracing></span><span class="sxs-lookup"><span data-stu-id="ab1f3-101">\<endToEndTracing></span></span>
<span data-ttu-id="ab1f3-102">Ein Konfigurationselement, das Ihnen ermöglicht, unterschiedliche Aspekte der End-to-End-Ablaufverfolgung während der Ausführung einer Dienstanwendung zu aktivieren bzw. zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="ab1f3-102">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
<span data-ttu-id="ab1f3-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ab1f3-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ab1f3-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ab1f3-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ab1f3-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Diagnose >** ](diagnostics.md)</span><span class="sxs-lookup"><span data-stu-id="ab1f3-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)</span></span>\
<span data-ttu-id="ab1f3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> "endback endtracing"**</span><span class="sxs-lookup"><span data-stu-id="ab1f3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endToEndTracing>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab1f3-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="ab1f3-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ab1f3-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ab1f3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ab1f3-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ab1f3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ab1f3-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="ab1f3-110">Attributes</span></span>  
  
|<span data-ttu-id="ab1f3-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="ab1f3-111">Attribute</span></span>|<span data-ttu-id="ab1f3-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ab1f3-112">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="ab1f3-113">Ein boolescher Wert, der angibt, ob die Aktivitätsablaufverfolgung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ab1f3-113">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="ab1f3-114">Ein boolescher Wert, der angibt, ob die Nachrichtenfluss-Ablaufverfolgung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ab1f3-114">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="ab1f3-115">Ein boolescher Wert, der angibt, ob das propagate-Attribut auf true festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ab1f3-115">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ab1f3-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ab1f3-116">Child Elements</span></span>  
 <span data-ttu-id="ab1f3-117">Keine</span><span class="sxs-lookup"><span data-stu-id="ab1f3-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ab1f3-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ab1f3-118">Parent Elements</span></span>  
  
|<span data-ttu-id="ab1f3-119">Element</span><span class="sxs-lookup"><span data-stu-id="ab1f3-119">Element</span></span>|<span data-ttu-id="ab1f3-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ab1f3-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ab1f3-121">\<Diagnose ></span><span class="sxs-lookup"><span data-stu-id="ab1f3-121">\<diagnostics></span></span>](diagnostics.md)|<span data-ttu-id="ab1f3-122">Definiert WCF-Einstellungen für die Laufzeitüberprüfung und Steuerungen für den Administrator.</span><span class="sxs-lookup"><span data-stu-id="ab1f3-122">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ab1f3-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ab1f3-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>
- <xref:System.ServiceModel.Configuration.EndToEndTracingElement>
- [<span data-ttu-id="ab1f3-124">End-to-End-Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="ab1f3-124">End-to-End Tracing</span></span>](../../../wcf/diagnostics/tracing/end-to-end-tracing.md)
