---
title: <legacyImpersonationPolicy>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#legacyImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/legacyImpersonationPolicy
helpviewer_keywords:
- <legacyImpersonationPolicy> element
- legacyImpersonationPolicy element
ms.assetid: 6e00af10-42f3-4235-8415-1bb2db78394e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c39ee551dde19d87a75403f3db7433d1ef829f3b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59333989"
---
# <a name="legacyimpersonationpolicy-element"></a>\<LegacyImpersonationPolicy >-Element
Gibt an, dass die Windows-Identität nicht über asynchrone Punkte verläuft, unabhängig von den Floweinstellungen für den Ausführungskontext im aktuellen Thread.  
  
 \<configuration>  
\<runtime>  
\<legacyImpersonationPolicy>  
  
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
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, dass die <xref:System.Security.Principal.WindowsIdentity> fließen nicht über asynchrone Punkte verläuft, unabhängig von der <xref:System.Threading.ExecutionContext> übertragen von Einstellungen für den aktuellen Thread.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`false`|<xref:System.Security.Principal.WindowsIdentity> Flows über asynchrone Punkte, die abhängig von der <xref:System.Threading.ExecutionContext> übertragen von Einstellungen für den aktuellen Thread. Dies ist die Standardeinstellung.|  
|`true`|<xref:System.Security.Principal.WindowsIdentity> fließen nicht über asynchrone Punkte verläuft, unabhängig von der <xref:System.Threading.ExecutionContext> übertragen von Einstellungen für den aktuellen Thread.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 In den .NET Framework-Versionen 1.0 und 1.1 die <xref:System.Security.Principal.WindowsIdentity> nicht über benutzerdefinierte asynchrone Punkte übergeben. Ab .NET Framework, Version 2.0, es ist ein <xref:System.Threading.ExecutionContext> -Objekt, das Informationen zu den aktuell ausgeführten Thread und enthält, die über asynchrone Punkte innerhalb einer Anwendungsdomäne übergeben. Die <xref:System.Security.Principal.WindowsIdentity> in diesem Ausführungskontext enthalten ist, und daher auch über die asynchrone Punkte verläuft, was bedeutet, dass wenn der Kontext eines Identitätswechsels vorhanden ist, es auch fließt.  
  
 Ab .NET Framework 2.0, können Sie die `<legacyImpersonationPolicy>` Element an, dass <xref:System.Security.Principal.WindowsIdentity> nicht über asynchrone Punkte übergeben.  
  
> [!NOTE]
>  Die common Language Runtime (CLR) beachtet des Identitätswechsels, die für das Aufrufen von Vorgängen, die ausgeführt wird, verwenden nur verwalteter Code, nicht des Identitätswechsels, die außerhalb von verwaltetem Code, z. B. über Plattform ausgeführt, von nicht verwaltetem Code oder durch direkte Aufrufe für Win32-Funktionen zur Verfügung. Nur verwaltete <xref:System.Security.Principal.WindowsIdentity> -Objekte können über asynchrone Punkte übergeben, es sei denn, die `alwaysFlowImpersonationPolicy` Elements wurde festgelegt auf "true" (`<alwaysFlowImpersonationPolicy enabled="true"/>`). Festlegen der `alwaysFlowImpersonationPolicy` Element auf "true" gibt an, dass die Windows-Identität immer über asynchrone Punkte verläuft, unabhängig davon, wie der Identitätswechsel durchgeführt wurde. Weitere Informationen zur Übergabe von nicht verwaltetem Identitätswechsel über asynchrone Punkte, finden Sie unter [ \<AlwaysFlowImpersonationPolicy >-Element](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).  
  
 Sie können dieses Standardverhalten auf zwei weitere Arten ändern:  
  
1. In verwaltetem Code auf einer pro-Thread-Basis.  
  
     Sie können den Fluss auf einer pro-Thread-Basis unterdrücken, indem Sie ändern die <xref:System.Threading.ExecutionContext> und <xref:System.Security.SecurityContext> Einstellungen mithilfe der <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> oder <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> Methode.  
  
2. Im Aufruf der nicht verwaltete Hostschnittstelle die common Language Runtime (CLR) geladen.  
  
     Wenn eine nicht verwaltete Hostschnittstelle (anstatt eine einfache verwaltete ausführbare Datei) zum Laden der CLR verwendet wird, können Sie ein spezielles Flag angeben, in dem Aufruf der [CorBindToRuntimeEx-Funktion](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) Funktion. Legen Sie zum Aktivieren des Kompatibilitätsmodus für den gesamten Prozess der `flags` -Parameter für [CorBindToRuntimeEx-Funktion](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) auf STARTUP_LEGACY_IMPERSONATION fest.  
  
 Weitere Informationen finden Sie unter den [ \<AlwaysFlowImpersonationPolicy >-Element](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).  
  
## <a name="configuration-file"></a>Konfigurationsdatei  
 In einer .NET Framework-Anwendung kann dieses Element nur in der Anwendungskonfigurationsdatei verwendet werden.  
  
 Für eine ASP.NET-Anwendung kann der Identitätswechsel-Flow in der Datei "aspnet.config" finden Sie unter konfiguriert werden die \<Windows-Ordner > \Microsoft.NET\Framework\vx.x.xxxx-Verzeichnis.  
  
 ASP.NET standardmäßig deaktiviert über die folgenden Konfigurationseinstellungen den Identitätswechsel-Flow in der Datei aspnet.config hinzu:  
  
``` xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 In ASP.NET, wenn Sie zulassen, den Fluss des Identitätswechsels stattdessen möchten müssen Sie explizit die folgenden Konfigurationseinstellungen verwenden:  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie das Legacyverhalten angeben, das nicht die Windows-Identität über asynchrone Punkte übergeben wird.  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [\<AlwaysFlowImpersonationPolicy >-Element](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)
