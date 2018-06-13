---
title: '&lt;AlwaysFlowImpersonationPolicy&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/alwaysFlowImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#alwaysFlowImpersonationPolicy
helpviewer_keywords:
- alwaysFlowImpersonationPolicy element
- <alwaysFlowImpersonationPolicy> element
ms.assetid: ee622801-9e46-470b-85ab-88c4b1dd2ee1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5cc704bbf8631936dbbeb3539ea5ed0d8499f378
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752272"
---
# <a name="ltalwaysflowimpersonationpolicygt-element"></a>&lt;AlwaysFlowImpersonationPolicy&gt; Element
Gibt an, dass die Windows-Identität immer über asynchrone Punkte verläuft, unabhängig davon, wie der Identitätswechsel durchgeführt wurde.  
  
 \<configuration>  
\<Common Language Runtime >  
\<alwaysFlowImpersonationPolicy>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<alwaysFlowImpersonationPolicy    
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob die Windows-Identität über asynchrone Punkte übergeben.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`false`|Die Windows-Identität nicht über asynchrone Punkte übergeben wird, es sei denn, der Identitätswechsel über erfolgt verwaltete Methoden, wie z. B. <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>. Dies ist die Standardeinstellung.|  
|`true`|Die Windows-Identität fließen immer über asynchrone Punkte, unabhängig davon, wie Identitätswechsel durchgeführt wurde.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 In der .NET Framework-Versionen 1.0 und 1.1 die Windows-Identität nicht über asynchrone Punkte übergeben. In .NET Framework, Version 2.0, besteht eine <xref:System.Threading.ExecutionContext> Objekt, das enthält Informationen zu den gerade ausgeführten Thread und übergibt ihn über asynchrone Punkte innerhalb einer Anwendungsdomäne. Die <xref:System.Security.Principal.WindowsIdentity> auch Datenflüsse im Rahmen der Informationen, die über die asynchrone Punkte fließen bereitgestellten des Identitätswechsels mit verwalteten Methoden wie z. B. <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> und nicht mithilfe anderer Methoden wie z. B. Plattform Aufrufen von systemeigenen Methoden. Dieses Element wird verwendet, um anzugeben, dass die Windows-Identität über asynchrone Punkte, unabhängig davon, wie des Identitätswechsels fließen.  
  
 Sie können dieses Standardverhalten auf zwei andere Arten ändern:  
  
1.  In verwaltetem Code auf eine Threadbasis.  
  
     Sie können den Fluss auf eine Threadbasis unterdrücken, indem Sie ändern die <xref:System.Threading.ExecutionContext> und <xref:System.Security.SecurityContext> Einstellungen mithilfe der <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, oder <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> Methode.  
  
2.  Im Aufruf der nicht verwaltete Hostschnittstelle die common Language Runtime (CLR) geladen.  
  
     Wenn eine nicht verwaltete Hostschnittstelle (statt einer einfachen verwalteten ausführbaren Datei) zum Laden der CLR verwendet wird, können Sie ein spezielles Flag angeben, in dem Aufruf der [CorBindToRuntimeEx-Funktion](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) Funktion. Um den Kompatibilitätsmodus für den gesamten Prozess zu aktivieren, legen Sie die `flags` -Parameter für [CorBindToRuntimeEx-Funktion](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) auf `STARTUP_ALWAYSFLOW_IMPERSONATION`.  
  
## <a name="configuration-file"></a>Konfigurationsdatei  
 In einer .NET Framework-Anwendung kann dieses Element nur in der Anwendungskonfigurationsdatei verwendet werden.  
  
 Für eine ASP.NET-Anwendung der Identitätswechsel-Fluss kann in der Datei Aspnet.config-Datei im konfiguriert die \<Ordner "Windows" > \Microsoft.NET\Framework\vx.x.xxxx-Verzeichnis.  
  
 ASP.NET standardmäßig deaktiviert den Ablauf Identitätswechsel in aspnet.config-Datei mit den folgenden Konfigurationseinstellungen:  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 In ASP.NET verwenden Wenn Sie zulassen, den Fluss des Identitätswechsels stattdessen möchten müssen Sie explizit die folgenden Konfigurationseinstellungen verwenden:  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie an, dass die Windows-Identität über asynchrone Punkte fließen, selbst wenn der Identitätswechsel Weise als verwaltete Methoden erreicht wird.  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<LegacyImpersonationPolicy >-Element](../../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)
