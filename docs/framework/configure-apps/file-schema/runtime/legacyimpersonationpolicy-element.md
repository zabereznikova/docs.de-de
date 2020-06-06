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
ms.openlocfilehash: 5e43ead278ecd4049014f4000a2f056b2190f7e5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154103"
---
# <a name="legacyimpersonationpolicy-element"></a>\<legacyImpersonationPolicy>-Element
Gibt an, dass die Windows-Identität nicht über asynchrone Punkte verläuft, unabhängig von den Floweinstellungen für den Ausführungskontext im aktuellen Thread.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyImpersonationPolicy>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<legacyImpersonationPolicy
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, dass der <xref:System.Security.Principal.WindowsIdentity> nicht über asynchrone Punkte fließt, unabhängig von den <xref:System.Threading.ExecutionContext> Fluss Einstellungen im aktuellen Thread.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|`false`|<xref:System.Security.Principal.WindowsIdentity>verläuft in Abhängigkeit von den <xref:System.Threading.ExecutionContext> Fluss Einstellungen für den aktuellen Thread über asynchrone Punkte hinweg. Dies ist die Standardeinstellung.|  
|`true`|<xref:System.Security.Principal.WindowsIdentity>fließt nicht über asynchrone Punkte hinweg, unabhängig von den <xref:System.Threading.ExecutionContext> Fluss Einstellungen im aktuellen Thread.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Bemerkungen  
 In den .NET Framework Versionen 1,0 und 1,1 fließt der <xref:System.Security.Principal.WindowsIdentity> nicht über benutzerdefinierte asynchrone Punkte. Beginnend mit der .NET Framework Version 2,0 gibt es ein <xref:System.Threading.ExecutionContext> Objekt, das Informationen über den aktuell ausgeführten Thread enthält und über asynchrone Punkte innerhalb einer Anwendungsdomäne fließt. Der <xref:System.Security.Principal.WindowsIdentity> ist in diesem Ausführungs Kontext enthalten und verläuft daher auch über die asynchronen Punkte. Dies bedeutet, dass, wenn ein Identitätswechsel Kontext vorhanden ist, auch der Fluss erfolgt.  
  
 Beginnend mit dem .NET Framework 2,0 können Sie das-Element verwenden, `<legacyImpersonationPolicy>` um anzugeben, dass <xref:System.Security.Principal.WindowsIdentity> nicht über asynchrone Punkte fließt.  
  
> [!NOTE]
> Der Common Language Runtime (CLR) kennt Identitätswechsel Vorgänge, die nur mit verwaltetem Code ausgeführt werden, nicht den Identitätswechsel außerhalb von verwaltetem Code, wie z. b. durch Platt Form Aufrufe zu nicht verwaltetem Code oder durch direkte Aufrufe von Win32-Funktionen. Nur verwaltete <xref:System.Security.Principal.WindowsIdentity> Objekte können über asynchrone Punkte hinweg fließen, es sei denn, das `alwaysFlowImpersonationPolicy` Element wurde auf true () festgelegt `<alwaysFlowImpersonationPolicy enabled="true"/>` . Das Festlegen des- `alwaysFlowImpersonationPolicy` Elements auf true gibt an, dass die Windows-Identität immer über asynchrone Punkte hinweg verläuft, unabhängig davon, wie der Identitätswechsel durchgeführt wurde. Weitere Informationen zum Übertragen von nicht verwaltetem Identitätswechsel über asynchrone Punkte hinweg finden Sie unter [ \<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).  
  
 Sie können dieses Standardverhalten auf zwei verschiedene Arten ändern:  
  
1. In verwaltetem Code auf Thread Basis.  
  
     Sie können den Flow auf Thread Basis unterdrücken, indem Sie die <xref:System.Threading.ExecutionContext> -Einstellung und die- <xref:System.Security.SecurityContext> Einstellung mithilfe der- <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType> ,-oder-Methode ändern <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> .  
  
2. Im aufzurufenden Befehl an die nicht verwaltete Hostingschnittstelle zum Laden der Common Language Runtime (CLR).  
  
     Wenn eine nicht verwaltete Hostingschnittstelle (anstelle einer einfachen verwalteten ausführbaren Datei) zum Laden der CLR verwendet wird, können Sie ein spezielles Flag im Aufrufen der [CorBindToRuntimeEx-Funktions](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) Funktion angeben. Um den Kompatibilitätsmodus für den gesamten Prozess zu aktivieren, legen Sie den- `flags` Parameter für die [CorBindToRuntimeEx-Funktion](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) auf STARTUP_LEGACY_IMPERSONATION fest.  
  
 Weitere Informationen finden Sie unter dem- [ \<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).  
  
## <a name="configuration-file"></a>Konfigurationsdatei  
 In einer .NET Framework Anwendung kann dieses Element nur in der Anwendungs Konfigurationsdatei verwendet werden.  
  
 Bei einer ASP.NET-Anwendung kann der Identitätswechsel in der ASPNET. config-Datei konfiguriert werden, die im \<Windows Folder> Verzeichnis \Microsoft.NET\Framework\vx.x.xxxx enthalten ist.  
  
 ASP.net deaktiviert den Identitätswechsel in der Datei Aspnet. config standardmäßig mithilfe der folgenden Konfigurationseinstellungen:  
  
``` xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 Wenn Sie in ASP.NET den Fluss des Identitäts Wechsels zulassen möchten, müssen Sie explizit die folgenden Konfigurationseinstellungen verwenden:  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie das Legacy Verhalten angegeben wird, das die Windows-Identität nicht über asynchrone Punkte hinweg fließt.  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
- [\<alwaysFlowImpersonationPolicy>Gewisses](alwaysflowimpersonationpolicy-element.md)
