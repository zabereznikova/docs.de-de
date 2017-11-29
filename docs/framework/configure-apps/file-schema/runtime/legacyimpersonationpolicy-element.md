---
title: '&lt;LegacyImpersonationPolicy&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#legacyImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/legacyImpersonationPolicy
helpviewer_keywords:
- <legacyImpersonationPolicy> element
- legacyImpersonationPolicy element
ms.assetid: 6e00af10-42f3-4235-8415-1bb2db78394e
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8f6bed837ab7b0c6a4aebe6116c5ab28bbc62175
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltlegacyimpersonationpolicygt-element"></a>&lt;LegacyImpersonationPolicy&gt; Element
Gibt an, dass die Windows-Identität nicht über asynchrone Punkte verläuft, unabhängig von den Floweinstellungen für den Ausführungskontext im aktuellen Thread.  
  
 \<configuration>  
\<Common Language Runtime >  
\<LegacyImpersonationPolicy >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<legacyImpersonationPolicy    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, dass die <xref:System.Security.Principal.WindowsIdentity> nicht über asynchrone Punkte übergeben, unabhängig von der <xref:System.Threading.ExecutionContext> übertragen von Einstellungen für den aktuellen Thread.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`false`|<xref:System.Security.Principal.WindowsIdentity>Arbeitsabläufe über asynchrone Punkte, die abhängig von der <xref:System.Threading.ExecutionContext> übertragen von Einstellungen für den aktuellen Thread. Dies ist die Standardeinstellung.|  
|`true`|<xref:System.Security.Principal.WindowsIdentity>nicht über asynchrone Punkte übergeben, unabhängig von der <xref:System.Threading.ExecutionContext> übertragen von Einstellungen für den aktuellen Thread.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 In der .NET Framework-Versionen 1.0 und 1.1 kann die <xref:System.Security.Principal.WindowsIdentity> nicht über eine beliebige benutzerdefinierte asynchrone Punkte übergeben. Beginnend mit .NET Framework, Version 2.0, besteht eine <xref:System.Threading.ExecutionContext> -Objekt, das Informationen zu den gerade ausgeführten Thread, und es enthält, die über asynchrone Punkte innerhalb einer Anwendungsdomäne übergeben. Die <xref:System.Security.Principal.WindowsIdentity> ist in dieser Ausführungskontext enthalten und daher auch über die asynchrone Punkte übergeben, was bedeutet, dass der Kontext eines Identitätswechsels vorhanden ist, es ebenfalls übertragen wird.  
  
 Beginnend mit .NET Framework 2.0, können Sie die `<legacyImpersonationPolicy>` Element angeben, dass <xref:System.Security.Principal.WindowsIdentity> nicht über asynchrone Punkte übergeben.  
  
> [!NOTE]
>  Die common Language Runtime (CLR) ist bekannt, des Identitätswechsels, die Operationen mit nur verwaltetem Code, nicht des Identitätswechsels, die außerhalb von verwaltetem Code, z. B. über Plattform ausgeführt zu nicht verwaltetem Code oder durch direkte Aufrufe für Win32-Funktionen aufrufen. Nur verwaltete <xref:System.Security.Principal.WindowsIdentity> Objekte können über asynchrone Punkte übergeben, es sei denn, die `alwaysFlowImpersonationPolicy` Element festgelegt wurde auf "true" (`<alwaysFlowImpersonationPolicy enabled="true"/>`). Festlegen der `alwaysFlowImpersonationPolicy` Element auf "true" gibt an, dass die Windows-Identität immer über asynchrone Punkte, unabhängig davon, wie Identitätswechsel durchgeführt wurde. Weitere Informationen finden Sie Informationen zur Übergabe von nicht verwaltetem Identitätswechsel über asynchrone Punkte [ \<AlwaysFlowImpersonationPolicy >-Element](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).  
  
 Sie können dieses Standardverhalten auf zwei andere Arten ändern:  
  
1.  In verwaltetem Code auf eine Threadbasis.  
  
     Sie können den Fluss auf eine Threadbasis unterdrücken, indem Sie ändern die <xref:System.Threading.ExecutionContext> und <xref:System.Security.SecurityContext> Einstellungen mithilfe der <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> oder <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> Methode.  
  
2.  Im Aufruf der nicht verwaltete Hostschnittstelle die common Language Runtime (CLR) geladen.  
  
     Wenn eine nicht verwaltete Hostschnittstelle (statt einer einfachen verwalteten ausführbaren Datei) zum Laden der CLR verwendet wird, können Sie ein spezielles Flag angeben, in dem Aufruf der [CorBindToRuntimeEx-Funktion](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) Funktion. Um den Kompatibilitätsmodus für den gesamten Prozess zu aktivieren, legen Sie die `flags` -Parameter für [CorBindToRuntimeEx-Funktion](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) auf STARTUP_LEGACY_IMPERSONATION fest.  
  
 Weitere Informationen finden Sie unter der [ \<AlwaysFlowImpersonationPolicy >-Element](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).  
  
## <a name="configuration-file"></a>Konfigurationsdatei  
 In einer .NET Framework-Anwendung kann dieses Element nur in der Anwendungskonfigurationsdatei verwendet werden.  
  
 Für eine ASP.NET-Anwendung der Identitätswechsel-Fluss kann in der Datei Aspnet.config-Datei im konfiguriert die \<Ordner "Windows" > \Microsoft.NET\Framework\vx.x.xxxx-Verzeichnis.  
  
 ASP.NET standardmäßig deaktiviert den Ablauf Identitätswechsel in aspnet.config-Datei mit den folgenden Konfigurationseinstellungen:  
  
```  
configuration>  
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
 Das folgende Beispiel zeigt, wie die Legacyverhalten an, das nicht die Windows-Identität über asynchrone Punkte übergeben.  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<AlwaysFlowImpersonationPolicy >-Element](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)
