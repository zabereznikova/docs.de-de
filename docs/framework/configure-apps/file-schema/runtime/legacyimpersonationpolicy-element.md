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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154103"
---
# <a name="legacyimpersonationpolicy-element"></a>\<legacyImpersonationPolicy> Element
Gibt an, dass die Windows-Identität nicht über asynchrone Punkte verläuft, unabhängig von den Floweinstellungen für den Ausführungskontext im aktuellen Thread.  
  
[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<Laufzeit>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyImpersonationPolicy>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<legacyImpersonationPolicy
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, <xref:System.Security.Principal.WindowsIdentity> dass der nicht über asynchrone <xref:System.Threading.ExecutionContext> Punkte fließt, unabhängig von den Flusseinstellungen im aktuellen Thread.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|value|Beschreibung|  
|-----------|-----------------|  
|`false`|<xref:System.Security.Principal.WindowsIdentity>fließt über asynchrone Punkte, abhängig von den <xref:System.Threading.ExecutionContext> Flusseinstellungen für den aktuellen Thread. Dies ist die Standardoption.|  
|`true`|<xref:System.Security.Principal.WindowsIdentity>fließt nicht über asynchrone Punkte, <xref:System.Threading.ExecutionContext> unabhängig von den Flusseinstellungen im aktuellen Thread.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Bemerkungen  
 In den .NET Framework-Versionen 1.0 <xref:System.Security.Principal.WindowsIdentity> und 1.1 fließt der nicht über benutzerdefinierte asynchrone Punkte. Ab .NET Framework Version 2.0 gibt <xref:System.Threading.ExecutionContext> es ein Objekt, das Informationen über den aktuell ausgeführten Thread enthält und über asynchrone Punkte innerhalb einer Anwendungsdomäne fließt. Der <xref:System.Security.Principal.WindowsIdentity> ist in diesem Ausführungskontext enthalten und fließt daher auch über die asynchronen Punkte, was bedeutet, dass, wenn ein Identitätswechselkontext vorhanden ist, er auch fließt.  
  
 Ab .NET Framework 2.0 können Sie `<legacyImpersonationPolicy>` das Element <xref:System.Security.Principal.WindowsIdentity> verwenden, um anzugeben, dass es nicht über asynchrone Punkte fließt.  
  
> [!NOTE]
> Die Common Language Runtime (CLR) ist sich der Identitätswechselvorgänge bewusst, die nur mit verwaltetem Code ausgeführt werden, und nicht von Identitätswechsel, die außerhalb des verwalteten Codes ausgeführt werden, z. B. durch Plattformaufruf an nicht verwalteten Code oder durch direkte Aufrufe von Win32-Funktionen. Nur <xref:System.Security.Principal.WindowsIdentity> verwaltete Objekte können über asynchrone Punkte fließen, es sei denn, das `alwaysFlowImpersonationPolicy` Element wurde auf true (`<alwaysFlowImpersonationPolicy enabled="true"/>`) festgelegt. Wenn `alwaysFlowImpersonationPolicy` Sie das Element auf true festlegen, wird angegeben, dass die Windows-Identität immer über asynchrone Punkte fließt, unabhängig davon, wie Identitätswechsel ausgeführt wurde. Weitere Informationen zum Fließen von nicht verwaltetem Identitätswechsel über asynchrone Punkte finden Sie unter [ \<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).  
  
 Sie können dieses Standardverhalten auf zwei weitere Arten ändern:  
  
1. In verwaltetem Code pro Thread.  
  
     Sie können den Fluss pro Thread unterdrücken, <xref:System.Threading.ExecutionContext> indem <xref:System.Security.SecurityContext> Sie die <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType> <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> und <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> die Einstellungen mithilfe der , oder Methode ändern.  
  
2. Beim Aufruf der nicht verwalteten Hostingschnittstelle, um die Common Language Runtime (CLR) zu laden.  
  
     Wenn zum Laden der CLR eine nicht verwaltete Hostingschnittstelle (anstelle einer einfachen verwalteten ausführbaren Datei) verwendet wird, können Sie im Aufruf der [Funktion CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) ein spezielles Flag angeben. Um den Kompatibilitätsmodus für den gesamten `flags` Prozess zu aktivieren, legen Sie den Parameter für [die CorBindToRuntimeEx-Funktion](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) auf STARTUP_LEGACY_IMPERSONATION.  
  
 Weitere Informationen finden Sie in der [ \<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).  
  
## <a name="configuration-file"></a>Konfigurationsdatei  
 In einer .NET Framework-Anwendung kann dieses Element nur in der Anwendungskonfigurationsdatei verwendet werden.  
  
 Bei einer ASP.NET Anwendung kann der Identitätswechselfluss in der Datei aspnet.config konfiguriert werden, die \<im Verzeichnis "Windows-Ordner">-Verzeichnis "Microsoft.NET-Framework" und "vx.x.xxxx" gefunden wird.  
  
 ASP.NET deaktiviert standardmäßig den Identitätswechselfluss in der Datei aspnet.config mithilfe der folgenden Konfigurationseinstellungen:  
  
``` xml
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
 Das folgende Beispiel zeigt, wie Sie das Legacyverhalten angeben, das die Windows-Identität nicht über asynchrone Punkte hinweg durchläuft.  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Schema für Laufzeiteinstellungen](index.md)
- [Schema der Konfigurationsdatei](../index.md)
- [\<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md)
