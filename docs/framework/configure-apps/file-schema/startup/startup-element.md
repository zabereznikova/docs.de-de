---
title: '&lt;Beim Start&gt; Element'
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
ms.openlocfilehash: 4d39dc28082fbed932a60228ac216f2f700c2e9f
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2018
ms.locfileid: "44366058"
---
# <a name="ltstartupgt-element"></a>&lt;Beim Start&gt; Element
Gibt beim Start zur common Language Runtime an.  
  
 \<configuration>  
\<Startup >  
  
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
|`useLegacyV2RuntimeActivationPolicy`|Optionales Attribut.<br /><br /> Gibt an, ob die [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] Richtlinie für die laufzeitaktivierung oder verwendet den [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] Activation-Richtlinie.|  
  
## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a>useLegacyV2RuntimeActivationPolicy-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`true`|Aktivieren Sie [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] Runtime Activation-Richtlinie für die ausgewählte Runtime, die ältere Laufzeit Aktivierung Techniken gebunden ist (z. B. die [CorBindToRuntimeEx-Funktion](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)) zur Laufzeit ausgewählt wird, aus der Konfigurationsdatei anstelle von sodass sie an der CLR, Version 2.0. Wenn CLR-Version 4 oder höher aus der Konfigurationsdatei ausgewählt wird, sind gemischte Assemblys, die mit früheren Versionen von .NET Framework erstellt daher mit der ausgewählten Version der CLR geladen. Festlegen dieses Werts verhindert, dass CLR, Version 1.1 oder CLR-Version 2.0 in den gleichen Prozess, effektiv deaktivieren, die in-Process-Seite-an-Seite lädt.|  
|`false`|Verwenden Sie die Standardrichtlinie für die Aktivierung für die [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] und höheren Versionen, die auf ältere Laufzeit Activation-Verfahren, um die CLR, Version 1.1 oder 2.0 in den Prozess zu laden kann. Wenn dieser Wert verhindert, dass im gemischten Modus Assemblys in .NET Framework 4 oder höher werden geladen, es sei denn, sie mit .NET Framework 4 oder höher erstellt wurden. Dies ist der Standardwert.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<requiredRuntime>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)|Gibt an, dass die Anwendung nur Version 1.0 der Common Language Runtime unterstützt. Anwendungen, die mit der Common Language RuntimeVersion 1.1 oder höher verwenden, sollte die  **\<SupportedRuntime >** Element.|  
|[\<supportedRuntime>](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)|Gibt an, welche Versionen der Common Language Runtime von der Anwendung unterstützt werden.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
  
## <a name="remarks"></a>Hinweise  
 Die  **\<SupportedRuntime >** Element sollte verwendet werden, von allen Anwendungen, die mit Version 1.1 oder höher der Runtime erstellt. Anwendungen, die nur in Version 1.0 von der Laufzeit nicht verwenden, müssen die  **\<RequiredRuntime >** Element.  
  
 Der Startcode für eine in Microsoft Internet Explorer gehostete Anwendung ignoriert die  **\<Start >** -Element und seine untergeordneten Elemente.  
  
## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a>Das Attribut useLegacyV2RuntimeActivationPolicy  
 Dieses Attribut ist nützlich, wenn Ihre Anwendung legacy-Aktivierungspfade,, wie z. B. verwendet die [CorBindToRuntimeEx-Funktion](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), und diese Pfade Version 4 der CLR anstelle von einer früheren Version aktivieren möchten oder wenn Ihre Anwendung Dank der [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] weist jedoch eine Abhängigkeit für eine gemischte-Assembly, die mit einer früheren Version von .NET Framework erstellt. In diesen Szenarien legen Sie das Attribut auf `true`.  
  
> [!NOTE]
>  Festlegen des Attributs auf `true` verhindert CLR, Version 1.1 oder CLR, Version 2.0 lädt in den gleichen Prozess, der effektiv den deaktivieren, in-Process Side-by-Side (finden Sie unter [Seite-an-Seite-Ausführung für COM-Interop](https://msdn.microsoft.com/library/4302318c-3586-49bf-8620-b9a39cdf4a32)).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie die Runtime-Version in einer Konfigurationsdatei angegeben wird.  
  
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
 [\<PaveOver> Specifying Which Runtime Version to Use (Festlegen der zu verwendenden Runtimeversion)](https://msdn.microsoft.com/library/c376208d-980d-42b4-865b-fbe0d9cc97c2)  
 [Seite-an-Seite-Ausführung für COM-Interop](https://msdn.microsoft.com/library/4302318c-3586-49bf-8620-b9a39cdf4a32)  
 [Prozessinterne parallele Ausführung](../../../../../docs/framework/deployment/in-process-side-by-side-execution.md)
