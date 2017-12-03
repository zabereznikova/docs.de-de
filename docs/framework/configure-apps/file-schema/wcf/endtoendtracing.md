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
# <a name="ltendtoendtracinggt"></a>&lt;endToEndTracing&gt;
Ein Konfigurationselement, das Ihnen ermöglicht, unterschiedliche Aspekte der End-to-End-Ablaufverfolgung während der Ausführung einer Dienstanwendung zu aktivieren bzw. zu deaktivieren.  
  
 \<System. ServiceModel >  
\<Diagnose >  
\<EndToEndTracing >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.serviceModel>  
   <diagnostics>  
       <endToEndTracing activityTracing="Boolean"  
          messageFlowTracing="Boolean"  
          propagateActivity="Boolean" />  
   </diagnostics>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`activityTracing`|Ein boolescher Wert, der angibt, ob die Aktivitätsablaufverfolgung aktiviert ist.|  
|`messageFlowTracing`|Ein boolescher Wert, der angibt, ob die Nachrichtenfluss-Ablaufverfolgung aktiviert ist.|  
|`propagateActivity`|Ein boolescher Wert, der angibt, ob das propagate-Attribut auf true festgelegt ist.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Diagnose >](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)|Definiert WCF-Einstellungen für die Laufzeitüberprüfung und Steuerungen für den Administrator.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.DiagnosticSection>  
 <xref:System.ServiceModel.Diagnostics>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>  
 <xref:System.ServiceModel.Configuration.EndToEndTracingElement>  
 [End-to-End-Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing.md)
