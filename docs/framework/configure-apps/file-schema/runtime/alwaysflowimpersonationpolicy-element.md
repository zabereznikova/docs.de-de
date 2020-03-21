---
title: <alwaysFlowImpersonationPolicy>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/alwaysFlowImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#alwaysFlowImpersonationPolicy
helpviewer_keywords:
- alwaysFlowImpersonationPolicy element
- <alwaysFlowImpersonationPolicy> element
ms.assetid: ee622801-9e46-470b-85ab-88c4b1dd2ee1
ms.openlocfilehash: 7c8ac37932a528ff0f000cbaab49124dec51b88c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154482"
---
# <a name="alwaysflowimpersonationpolicy-element"></a>\<alwaysFlowImpersonationPolicy> Element
Gibt an, dass die Windows-Identität immer über asynchrone Punkte verläuft, unabhängig davon, wie der Identitätswechsel durchgeführt wurde.  
  
[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<Laufzeit>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<alwaysFlowImpersonationPolicy>**\  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<alwaysFlowImpersonationPolicy
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob die Windows-Identität über asynchrone Punkte fließt.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|value|Beschreibung|  
|-----------|-----------------|  
|`false`|Die Windows-Identität fließt nicht über asynchrone Punkte, es sei denn, der Identitätswechsel wird über verwaltete Methoden wie <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>ausgeführt. Dies ist die Standardoption.|  
|`true`|Die Windows-Identität fließt immer über asynchrone Punkte, unabhängig davon, wie Identitätswechsel ausgeführt wurde.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Bemerkungen  
 In den .NET Framework-Versionen 1.0 und 1.1 fließt die Windows-Identität nicht über asynchrone Punkte. In .NET Framework Version 2.0 <xref:System.Threading.ExecutionContext> gibt es ein Objekt, das Informationen über den aktuell ausgeführten Thread enthält und es über asynchrone Punkte innerhalb einer Anwendungsdomäne überträgt. Der <xref:System.Security.Principal.WindowsIdentity> fließt auch als Teil der Informationen, die über die asynchronen Punkte fließen, <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> vorausgesetzt, der Identitätswechsel wurde mit verwalteten Methoden erreicht, z. B. und nicht mit anderen Mitteln, wie z. B. Plattformaufruf auf systemeigenen Methoden. Dieses Element wird verwendet, um anzugeben, dass die Windows-Identität über asynchrone Punkte fließt, unabhängig davon, wie der Identitätswechsel erreicht wurde.  
  
 Sie können dieses Standardverhalten auf zwei weitere Arten ändern:  
  
1. In verwaltetem Code pro Thread.  
  
     Sie können den Fluss pro Thread unterdrücken, <xref:System.Threading.ExecutionContext> indem <xref:System.Security.SecurityContext> Sie die <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType> <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>und <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> die Einstellungen mithilfe der , oder Methode ändern.  
  
2. Beim Aufruf der nicht verwalteten Hostingschnittstelle, um die Common Language Runtime (CLR) zu laden.  
  
     Wenn zum Laden der CLR eine nicht verwaltete Hostingschnittstelle (anstelle einer einfachen verwalteten ausführbaren Datei) verwendet wird, können Sie im Aufruf der [Funktion CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) ein spezielles Flag angeben. Um den Kompatibilitätsmodus für den gesamten `flags` Prozess zu aktivieren, legen `STARTUP_ALWAYSFLOW_IMPERSONATION`Sie den Parameter für [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) auf fest.  
  
## <a name="configuration-file"></a>Konfigurationsdatei  
 In einer .NET Framework-Anwendung kann dieses Element nur in der Anwendungskonfigurationsdatei verwendet werden.  
  
 Bei einer ASP.NET Anwendung kann der Identitätswechselfluss in der Datei aspnet.config konfiguriert werden, die \<im Verzeichnis "Windows-Ordner">-Verzeichnis "Microsoft.NET-Framework" und "vx.x.xxxx" gefunden wird.  
  
 ASP.NET deaktiviert standardmäßig den Identitätswechselfluss in der Datei aspnet.config mithilfe der folgenden Konfigurationseinstellungen:  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 Wenn Sie in ASP.NET stattdessen den Fluss des Identitätswechsels zulassen möchten, müssen Sie explizit die folgenden Konfigurationseinstellungen verwenden:  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie angeben, dass die Windows-Identität über asynchrone Punkte fließt, auch wenn der Identitätswechsel mit anderen Mitteln als verwalteten Methoden erreicht wird.  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Schema für Laufzeiteinstellungen](index.md)
- [Schema der Konfigurationsdatei](../index.md)
- [\<legacyImpersonationPolicy> Element](legacyimpersonationpolicy-element.md)
