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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 164492eb1abc7329481f158963118b47d2c4aebc
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252862"
---
# <a name="alwaysflowimpersonationpolicy-element"></a>\<alwaysFlowImpersonationPolicy-> Element
Gibt an, dass die Windows-Identität immer über asynchrone Punkte verläuft, unabhängig davon, wie der Identitätswechsel durchgeführt wurde.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<Lauf Zeit >** ](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<alwaysFlowImpersonationPolicy>** \  
  
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
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob die Windows-Identität über asynchrone Punkte hinweg verläuft.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`false`|Die Windows-Identität fließt nicht über asynchrone Punkte, es sei denn, der Identitätswechsel wird über verwaltete Methoden <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>wie ausgeführt. Dies ist die Standardeinstellung.|  
|`true`|Die Windows-Identität verläuft immer über asynchrone Punkte, unabhängig davon, wie der Identitätswechsel durchgeführt wurde.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 In den .NET Framework Versionen 1,0 und 1,1 wird die Windows-Identität nicht über asynchrone Punkte hinweg übertragen. In der .NET Framework Version 2,0 ist ein <xref:System.Threading.ExecutionContext> Objekt vorhanden, das Informationen über den derzeit ausgeführten Thread enthält und über asynchrone Punkte innerhalb einer Anwendungsdomäne fließt. Der <xref:System.Security.Principal.WindowsIdentity> fließt auch als Teil der Informationen, die über die asynchronen Punkte hinweg fließen, vorausgesetzt, der Identitätswechsel wurde mithilfe verwalteter <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> Methoden wie z. b. und nicht über andere Mittel (z. b. Platt Form Aufrufe auf Native Methoden) erreicht. Mit diesem Element wird angegeben, dass die Windows-Identität unabhängig davon, wie der Identitätswechsel erfolgt ist, über asynchrone Punkte hinweg erfolgt.  
  
 Sie können dieses Standardverhalten auf zwei verschiedene Arten ändern:  
  
1. In verwaltetem Code auf Thread Basis.  
  
     Sie können den Flow auf Thread Basis unterdrücken, indem Sie <xref:System.Threading.ExecutionContext> die-Einstellung und die-Einstellung mithilfe der <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>- <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> , <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>-oder- <xref:System.Security.SecurityContext> Methode ändern.  
  
2. Im aufzurufenden Befehl an die nicht verwaltete Hostingschnittstelle zum Laden der Common Language Runtime (CLR).  
  
     Wenn eine nicht verwaltete Hostingschnittstelle (anstelle einer einfachen verwalteten ausführbaren Datei) zum Laden der CLR verwendet wird, können Sie ein spezielles Flag im Aufrufen der [CorBindToRuntimeEx-Funktions](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) Funktion angeben. Um den Kompatibilitätsmodus für den gesamten Prozess zu aktivieren, `flags` legen Sie den-Parameter für die [CorBindToRuntimeEx-Funktion](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) auf `STARTUP_ALWAYSFLOW_IMPERSONATION`fest.  
  
## <a name="configuration-file"></a>Konfigurationsdatei  
 In einer .NET Framework Anwendung kann dieses Element nur in der Anwendungs Konfigurationsdatei verwendet werden.  
  
 Bei einer ASP.NET-Anwendung kann der Identitätswechsel in der Datei "ASPNET. config" konfiguriert werden, die \<sich im Windows-Ordner > Verzeichnis "\Microsoft.NET\Framework\vx.x.xxxx" befindet.  
  
 ASP.net deaktiviert den Identitätswechsel in der Datei Aspnet. config standardmäßig mithilfe der folgenden Konfigurationseinstellungen:  
  
```xml
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
 Im folgenden Beispiel wird gezeigt, wie angegeben wird, dass die Windows-Identität über asynchrone Punkte hinweg verläuft, auch wenn der Identitätswechsel durch andere Mittel als verwaltete Methoden erreicht wird.  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
- [\<Legacy-Identitätswechsel Richtlinien-> Element](legacyimpersonationpolicy-element.md)
