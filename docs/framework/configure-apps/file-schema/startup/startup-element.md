---
title: '&lt;Start&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup
- http://schemas.microsoft.com/.NetConfiguration/v2.0#startup
helpviewer_keywords:
- container tags, <startup> element
- <startup> element
- startup element
ms.assetid: 536acfd8-f827-452f-838a-e14fa3b87621
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 60699f0335bb35589341558800cfd64503d0aa0a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltstartupgt-element"></a>&lt;Start&gt; Element
Gibt die common Language Runtime-Startinformationen.  
  
 \<configuration>  
\<Start >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<startup useLegacyV2RuntimeActivationPolicy="true|false" >   
</startup>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`useLegacyV2RuntimeActivationPolicy`|Optionales Attribut.<br /><br /> Gibt an, ob die [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] Runtime Aktivierungsrichtlinie oder zur Verwendung der [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] Aktivierungsrichtlinie.|  
  
## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a>useLegacyV2RuntimeActivationPolicy-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`true`|Aktivieren Sie [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] Aktivierung Laufzeitrichtlinie für die ausgewählte Runtime legacylaufzeit Aktivierung Techniken gebunden ist (z. B. der [CorBindToRuntimeEx-Funktion](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)) für die Laufzeit, die aus der Konfigurationsdatei anstelle von ausgewählt Capping diese auf CLR, Version 2.0. Wenn CLR-Version 4 oder höher aus der Konfigurationsdatei ausgewählt wird, werden im gemischten Modus Assemblys, die mit früheren Versionen von .NET Framework erstellt daher mit der ausgewählten Version der CLR geladen. Wenn dieser Wert verhindert, dass CLR, Version 1.1 oder CLR, Version 2.0 Laden in den gleichen Prozess, die in-Process-Seite-an-Seite-Funktion effektiv deaktiviert.|  
|`false`|Verwenden Sie die Standardrichtlinie für die Aktivierung für die [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] und später ist das ermöglichen legacylaufzeit Aktivierung Techniken, mit denen CLR, Version 1.1 oder 2.0 in den Prozess zu laden. Das Festlegen dieses Werts wird verhindert, dass im gemischten Modus Assemblys vor dem Laden in .NET Framework 4 oder höher, es sei denn, sie mit .NET Framework 4 oder höher erstellt wurden. Dies ist der Standardwert.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<requiredRuntime>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)|Gibt an, dass die Anwendung nur Version 1.0 der Common Language Runtime unterstützt. Mit der Common Language Runtime-Version 1.1 oder höher entwickelte Anwendungen sollten verwenden die  **\<SupportedRuntime >** Element.|  
|[\<supportedRuntime>](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)|Gibt an, welche Versionen der Common Language Runtime von der Anwendung unterstützt werden.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
  
## <a name="remarks"></a>Hinweise  
 Die  **\<SupportedRuntime >** -Element sollte von allen Anwendungen, die mit Version 1.1 oder höher der Runtime erstellt verwendet werden. Anwendungen, die nur Version 1.0 der Laufzeit unterstützen müssen verwenden die  **\<RequiredRuntime >** Element.  
  
 Der Startcode für eine in Microsoft Internet Explorer gehostete Anwendung ignoriert die  **\<Start >** Element und seine untergeordneten Elemente.  
  
## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a>Das Attribut useLegacyV2RuntimeActivationPolicy  
 Dieses Attribut ist hilfreich, wenn Ihre Anwendung legacy-Aktivierungspfade,, wie z. B. verwendet die [CorBindToRuntimeEx-Funktion](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), und Sie möchten diese Pfade Version 4 der CLR anstelle von einer früheren Version aktivieren, oder wenn die Anwendung erstellt mit dem [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] , enthält jedoch eine Abhängigkeit auf eine im gemischten Modus-Assembly, die mit einer früheren Version von .NET Framework erstellt. Legen Sie in jenen Szenarien kann das Attribut auf `true`.  
  
> [!NOTE]
>  Wenn das Attribut auf `true` verhindert CLR, Version 1.1 oder CLR, Version 2.0 lädt in den gleichen Prozess, die in-Process-Seite-an-Seite-Funktion effektiv deaktiviert (finden Sie unter [Side-by-Side-Ausführung für COM-Interop](http://msdn.microsoft.com/library/4302318c-3586-49bf-8620-b9a39cdf4a32)).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird gezeigt, wie die Common Language Runtime-Version in einer Konfigurationsdatei angegeben.  
  
```xml  
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
  
## <a name="see-also"></a>Siehe auch  
 [Startup Settings Schema (Schema für Starteinstellungen)](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<PaveOver> Specifying Which Runtime Version to Use (Festlegen der zu verwendenden Runtimeversion)](http://msdn.microsoft.com/library/c376208d-980d-42b4-865b-fbe0d9cc97c2)  
 [Seite-an-Seite-Ausführung für COM-Interop](http://msdn.microsoft.com/library/4302318c-3586-49bf-8620-b9a39cdf4a32)  
 [Prozessinterne parallele Ausführung](../../../../../docs/framework/deployment/in-process-side-by-side-execution.md)
