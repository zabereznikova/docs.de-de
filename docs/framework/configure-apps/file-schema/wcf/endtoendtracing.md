---
title: "&lt;endToEndTracing&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# &lt;endToEndTracing&gt;
Ein Konfigurationselement, das Ihnen ermöglicht, unterschiedliche Aspekte der End\-to\-End\-Ablaufverfolgung während der Ausführung einer Dienstanwendung zu aktivieren bzw. zu deaktivieren.  
  
## Syntax  
  
```  
  
<system.serviceModel>  
   <diagnostics>  
       <endToEndTracing activityTracing="Boolean"  
          messageFlowTracing="Boolean"  
          propagateActivity="Boolean" />  
   </diagnostics>  
</system.serviceModel>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|`activityTracing`|Ein boolescher Wert, der angibt, ob die Aktivitätsablaufverfolgung aktiviert ist.|  
|`messageFlowTracing`|Ein boolescher Wert, der angibt, ob die Nachrichtenfluss\-Ablaufverfolgung aktiviert ist.|  
|`propagateActivity`|Ein boolescher Wert, der angibt, ob das propagate\-Attribut auf true festgelegt ist.|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Diagnose\>](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)|Definiert WCF\-Einstellungen für die Laufzeitüberprüfung und Steuerungen für den Administrator.|  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.DiagnosticSection>   
 <xref:System.ServiceModel.Diagnostics>   
 <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>   
 <xref:System.ServiceModel.Configuration.EndToEndTracingElement>   
 [End\-to\-End\-Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing.md)