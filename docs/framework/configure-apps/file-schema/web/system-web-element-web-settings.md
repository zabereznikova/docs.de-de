---
title: "&lt;system.web&gt;-Element (Webeinstellungen) | Microsoft Docs"
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
  - "<system.Web>-Element"
  - "ASP.NET-Konfigurationssystem"
  - "Konfigurationsdateien [ASP.NET]"
  - "system.Web-Element"
  - "Web.config (Konfigurationsdatei) [ASP.NET]"
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# &lt;system.web&gt;-Element (Webeinstellungen)
Enthält Informationen darüber, wie prozessweites Verhalten von der ASP.NET\-Hostebene verwaltet wird.  
  
## Syntax  
  
```  
<system.web>  
</system.web>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine.  
  
### Untergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<applicationPool\>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|Gibt Konfigurationseinstellungen für IIS\-Anwendungspools in einer aspnet.config\-Datei an.|  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<konfiguration\>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Gibt das Stammelement in jeder von den Common Language Runtime\- und [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]\-Anwendungen verwendeten Konfigurationsdatei an.|  
  
## Hinweise  
 Das `system.web`\-Element und das untergeordnete `applicationPool`\-Element sind seit [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] in [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] enthalten.  Wenn Sie [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] oder eine höhere Version im integrierten Modus ausführen, können Sie mit dieser Elementkombination angeben, wie ASP.NET Threads verwaltet und wie Anforderungen in die Warteschlange gestellt werden, wenn ASP.NET in einem IIS\-Anwendungspool gehostet wird.  Wenn Sie [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] oder eine höhere Version im klassischen Modus oder im ISAPI\-Modus ausführen, werden diese Einstellungen ignoriert.  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie prozessweites Verhalten von ASP.NET in der aspnet.config\-Datei konfiguriert wird, wenn ASP.NET in einem IIS\-Anwendungspool gehostet wird.  Im Beispiel wird davon ausgegangen, dass IIS im integrierten Modus ausgeführt und [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] oder eine höhere Version von der Anwendung verwendet wird.  Dieses Verhalten tritt in [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] ab [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] auf.  Die Werte, die im Beispiel verwendet werden, sind Standardwerte.  
  
```  
<configuration>  
  <system.web>  
    <applicationPool   
        maxConcurrentRequestsPerCPU="5000"   
        maxConcurrentThreadsPerCPU="0"   
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## Elementinformationen  
  
|||  
|-|-|  
|Namespace||  
|Schemaname||  
|Validierungsdatei||  
|Kann leer sein||  
  
## Siehe auch  
 [\<applicationPool\>\-Element \(Webeinstellungen\)](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)