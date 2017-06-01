---
title: "&lt;startup&gt;-Element | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#startup"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<startup>-Element"
  - "Containertags, <startup>-Element"
  - "startup-Element"
ms.assetid: 536acfd8-f827-452f-838a-e14fa3b87621
caps.latest.revision: 19
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 19
---
# &lt;startup&gt;-Element
Gibt Common Language Runtime\-Startinformationen an.  
  
## Syntax  
  
```  
<startup useLegacyV2RuntimeActivationPolicy="true|false" >   
</startup>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`useLegacyV2RuntimeActivationPolicy`|Optionales Attribut.<br /><br /> Gibt an, ob die [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)]\-Laufzeitaktivierungsrichtlinie aktiviert oder die [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]\-Aktivierungsrichtlinie verwendet werden soll.|  
  
## useLegacyV2RuntimeActivationPolicy\-Attribut  
  
|Wert|**Beschreibung**|  
|----------|----------------------|  
|`true`|Aktivieren Sie die [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)]\-Laufzeitaktivierungsrichtlinie für die gewählte Laufzeit, die ältere Laufzeitaktivierungstechniken \(z. B. die [](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)CorBindToRuntimeEx\-Funktion\) an die Laufzeit bindet, die aus der Konfigurationsdatei ausgewählt wurde, anstatt sie auf CLR\-Version 2.0 zu begrenzen.  Daher, wenn CLR\-Version 4 oder höher von der Konfigurationsdatei gewählt ist, werden Gemischter\-Modus\-Assemblys, die mit früheren Versionen von .NET Framework erstellt wurden, mit der gewählten Version der CLR geladen.  Das Festlegen dieses Werts verhindert, dass CLR\-Version 1.1 oder CLR\-Version 2.0 in den gleichen Prozess lädt, und deaktiviert effektiv die prozessinterne Parallelfunktion.|  
|`false`|Verwenden Sie die Standardaktivierungsrichtlinie für [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] und höher, wodurch ältere Laufzeitaktivierungstechniken zum Laden der CLR\-Version 1.1 oder 2.0 in den Prozess ermöglicht werden.  Das Festlegen dieses Werts verhindert Assemblys im gemischten Modus am Laden in .NET Framework 4 oder höher, es sei denn, sie mit .NET Framework 4 oder höher erstellt wurden.  Dies ist der Standardwert.|  
  
### Untergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<requiredRuntime\>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)|Gibt an, dass die Anwendung lediglich Version 1.0 der Common Language Runtime unterstützt.  Anwendungen, die mit der Laufzeitversion 1.1 oder höher erstellt wurden, sollten die **\<supportedRuntime\>**\-Element verwenden.|  
|[\<supportedRuntime\>](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)|Gibt an, welche Versionen der Common Language Runtime von der Anwendung unterstützt werden.|  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
  
## Hinweise  
 Das **\<supportedRuntime\>**\-Element sollte von allen Anwendungen verwendet werden, die mit Version 1.1 oder einer höheren Version der Laufzeit erstellt wurden.  Anwendungen, die nur Version 1.0 der Laufzeit unterstützen, müssen das **\<requiredRuntime\>**\-Element verwenden.  
  
 Der Startcode für eine Anwendung, die in Microsoft Internet Explorer gehostetes, ignoriert das **\<startup\>**\-Element und seine untergeordneten Elemente.  
  
## Das useLegacyV2RuntimeActivationPolicy\-Attribut  
 Dieses Attribut ist hilfreich, wenn Ihre Anwendung ältere Aktivierungspfade verwendet, z. B. die [CorBindToRuntimeEx\-Funktion](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), und Sie möchten, dass diese Pfade Version 4 der CLR anstelle von einer früheren Version aktivieren, oder wenn Ihre Anwendung mit [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] erstellt wurde, aber eine Abhängigkeit von einer Gemischter\-Modus\-Assembly hat, die mit einer früheren Version von .NET Framework erstellt wurde.  Legen Sie in diesen Szenarien das Attribut auf `true` fest.  
  
> [!NOTE]
>  Das Festlegen des Attributs auf `true` verhindert, dass CLR\-Version 1.1 oder CLR\-Version 2.0 in den gleichen Prozess lädt, und deaktiviert effektiv die prozessinterne Parallelfunktion \(siehe [Side\-by\-Side Execution for COM Interop](http://msdn.microsoft.com/de-de/4302318c-3586-49bf-8620-b9a39cdf4a32)\).  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht, wie Sie die Runtimeversion in einer Konfigurationsdatei angeben.  
  
```  
<!-- When used with version 1.0 of the .NET Framework runtime -->  
<configuration>  
   <startup>  
      <requiredRuntime version="v1.0.3705" safemode="true"/>  
   </startup>  
</configuration>  
<!-- When used with version 1.1 (or later) of the runtime -->  
<configuration>  
   <startup>  
      <supportedRuntime version="v1.1.4322"/>  
      <supportedRuntime version="v1.0.3705"/>  
   </startup>  
</configuration>  
```  
  
## Siehe auch  
 [Schema für Starteinstellungen](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [\<PaveOver\> Specifying Which Runtime Version to Use](http://msdn.microsoft.com/de-de/c376208d-980d-42b4-865b-fbe0d9cc97c2)   
 [Side\-by\-Side Execution for COM Interop](http://msdn.microsoft.com/de-de/4302318c-3586-49bf-8620-b9a39cdf4a32)   
 [Prozessinterne parallele Ausführung](../../../../../docs/framework/deployment/in-process-side-by-side-execution.md)