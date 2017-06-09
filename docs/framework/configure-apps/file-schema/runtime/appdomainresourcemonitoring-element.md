---
title: "&lt;appDomainResourceMonitoring&gt;-Element | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<appDomainResourceMonitoring>-Element"
  - "appDomainResourceMonitoring-Element"
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# &lt;appDomainResourceMonitoring&gt;-Element
Weist die Laufzeit an, in allen Anwendungsdomänen des Prozesses Statistikdaten für seine Lebensdauer zu sammeln.  
  
## Syntax  
  
```  
<appDomainResourceMonitoring    
   enabled="true|false"/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob Statistikdaten für die Ressourcenüberwachung der Anwendungsdomäne von der Laufzeit gesammelt werden.|  
  
## Enabled\-Attribut  
  
|Wert|**Beschreibung**|  
|----------|----------------------|  
|`true`|Statistikdaten für die Ressourcenüberwachung der Anwendungsdomäne werden gesammelt.|  
|`false`|Statistikdaten für die Ressourcenüberwachung der Anwendungsdomäne werden nicht gesammelt.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## Hinweise  
 Die Ressourcenüberwachung der Anwendungsdomäne ist über die verwaltete Klasse der Anwendungsdomäne, über die [ICLRAppDomainResourceMonitor](../../../../../ocs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)\-Hostschnittstelle und über die Ereignisablaufverfolgung für Windows \(ETW\) verfügbar.  Wenn die Überwachung aktiviert ist, werden Statistikdaten für alle Anwendungsdomänen im Prozess für seine Lebensdauer gesammelt.  
  
 Um das Überwachen von verwaltetem Code zu aktivieren, verwenden Sie die <xref:System.AppDomain.MonitoringIsEnabled%2A>\-Eigenschaft.  
  
 Dieses Konfigurationselement ist erst ab [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] verfügbar.  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die Ressourcenüberwachung von Anwendungsdomänen aktiviert wird.  
  
```  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## Siehe auch  
 <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=fullName>   
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)