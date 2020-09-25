---
title: <endToEndTracing>
ms.date: 03/30/2017
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
ms.openlocfilehash: 6b50c0c3db644787fe41ee58ced7eb640e7295f1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190019"
---
# \<endToEndTracing>

<span data-ttu-id="470d5-101">Ein Konfigurationselement, das Ihnen ermöglicht, unterschiedliche Aspekte der End-to-End-Ablaufverfolgung während der Ausführung einer Dienstanwendung zu aktivieren bzw. zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="470d5-101">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endToEndTracing>**  
  
## <a name="syntax"></a><span data-ttu-id="470d5-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="470d5-102">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="470d5-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="470d5-103">Attributes and Elements</span></span>  

 <span data-ttu-id="470d5-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="470d5-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="470d5-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="470d5-105">Attributes</span></span>  
  
|<span data-ttu-id="470d5-106">attribute</span><span class="sxs-lookup"><span data-stu-id="470d5-106">Attribute</span></span>|<span data-ttu-id="470d5-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="470d5-107">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="470d5-108">Ein boolescher Wert, der angibt, ob die Aktivitätsablaufverfolgung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="470d5-108">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="470d5-109">Ein boolescher Wert, der angibt, ob die Nachrichtenfluss-Ablaufverfolgung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="470d5-109">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="470d5-110">Ein boolescher Wert, der angibt, ob das propagate-Attribut auf true festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="470d5-110">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="470d5-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="470d5-111">Child Elements</span></span>  

 <span data-ttu-id="470d5-112">Keine</span><span class="sxs-lookup"><span data-stu-id="470d5-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="470d5-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="470d5-113">Parent Elements</span></span>  
  
|<span data-ttu-id="470d5-114">Element</span><span class="sxs-lookup"><span data-stu-id="470d5-114">Element</span></span>|<span data-ttu-id="470d5-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="470d5-115">Description</span></span>|  
|-------------|-----------------|  
|[\<diagnostics>](diagnostics.md)|<span data-ttu-id="470d5-116">Definiert WCF-Einstellungen für die Laufzeitüberprüfung und Steuerungen für den Administrator.</span><span class="sxs-lookup"><span data-stu-id="470d5-116">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="470d5-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="470d5-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>
- <xref:System.ServiceModel.Configuration.EndToEndTracingElement>
- [<span data-ttu-id="470d5-118">End-to-End-Ablauf Verfolgung</span><span class="sxs-lookup"><span data-stu-id="470d5-118">End-to-End Tracing</span></span>](../../../wcf/diagnostics/tracing/end-to-end-tracing.md)
