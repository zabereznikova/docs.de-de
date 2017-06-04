---
title: "&lt;legacyImpersonationPolicy&gt;-Element | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#legacyImpersonationPolicy"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/legacyImpersonationPolicy"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<legacyImpersonationPolicy>-Element"
  - "legacyImpersonationPolicy-Element"
ms.assetid: 6e00af10-42f3-4235-8415-1bb2db78394e
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# &lt;legacyImpersonationPolicy&gt;-Element
Gibt an, dass die Windows\-Identität, unabhängig von den Flusseinstellungen für den Ausführungskontext des aktuellen Threads, nicht über asynchrone Punkte übergeben wird.  
  
## Syntax  
  
```  
<legacyImpersonationPolicy    
   enabled="true|false"/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, dass die <xref:System.Security.Principal.WindowsIdentity>, unabhängig von den <xref:System.Threading.ExecutionContext>\-Flusseinstellungen für den Ausführungskontext des aktuellen Threads, nicht über asynchrone Punkte übergeben wird.|  
  
## Enabled\-Attribut  
  
|Wert|**Beschreibung**|  
|----------|----------------------|  
|`false`|Die <xref:System.Security.Principal.WindowsIdentity> wird, je nach den <xref:System.Threading.ExecutionContext>\-Flusseinstellungen für den aktuellen Thread, über asynchrone Punkte übergeben.  Dies ist der Standardwert.|  
|`true`|Die <xref:System.Security.Principal.WindowsIdentity> wird, unabhängig von den <xref:System.Threading.ExecutionContext>\-Flusseinstellungen für den Ausführungskontext des aktuellen Threads, nicht über asynchrone Punkte übergeben.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## Hinweise  
 In den .NET Framework\-Versionen 1.0 und 1.1 wird die <xref:System.Security.Principal.WindowsIdentity> nicht über benutzerdefinierte asynchrone Punkte übergeben.  .NET Framework, Version 2.0, enthält ein <xref:System.Threading.ExecutionContext>\-Objekt mit Informationen über den gegenwärtig ausgeführten Thread, das über asynchrone Punkte innerhalb einer Anwendungsdomäne übergeben wird.  Dabei wird auch die <xref:System.Security.Principal.WindowsIdentity> übergeben, d. h., ein Identitätswechselkontext wird, sofern vorhanden, ebenfalls übergeben.  Mit diesem Element wird angegeben, dass die <xref:System.Security.Principal.WindowsIdentity> nicht über asynchrone Punkte übergeben wird.  
  
> [!NOTE]
>  Die Common Language Runtime \(CLR\) kann Identitätswechsel erkennen, die nur mit verwaltetem Code vorgenommen werden. Anders verhält es sich bei Identitätswechsel außerhalb von verwaltetem Code, z. B. über Plattformaufrufe zu nicht verwaltetem Code oder über direkte Aufrufe zu Win32\-Funktionen.  Nur verwaltete <xref:System.Security.Principal.WindowsIdentity>\-Objekte können über asynchrone Punkte übergeben werden, sofern das `alwaysFlowImpersonationPolicy`\-Element nicht auf true \(`<alwaysFlowImpersonationPolicy enabled="true"/>`\) festgelegt wurde.  Wenn das `alwaysFlowImpersonationPolicy`\-Element auf true festgelegt wird, gibt dies an, dass die Windows\-Identität immer über asynchrone Punkte übergeben wird, unabhängig von der Art des Identitätswechsels.  Weitere Informationen zur Übergabe von nicht verwaltetem Identitätswechsel über asynchrone Punkte finden Sie unter [\<alwaysFlowImpersonationPolicy\>\-Element](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).  
  
 Dieses Element kann nur in der Anwendungskonfigurationsdatei verwendet werden.  
  
 Es gibt zwei Möglichkeiten zum Ändern dieses Standardverhaltens:  
  
1.  In verwaltetem Code für die einzelnen Threads.  
  
     Sie können die Übergabe für die einzelnen Threads unterdrücken, indem Sie die <xref:System.Threading.ExecutionContext>\-Einstellungen und die <xref:System.Security.SecurityContext>\-Einstellungen mithilfe der Methoden <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=fullName>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=fullName> oder <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=fullName> ändern.  
  
2.  Im Aufruf der nicht verwalteten Hostschnittstelle zum Laden der Common Language Runtime \(CLR\).  
  
     Wenn die CLR über eine nicht verwaltete Hostschnittstelle \(anstelle einer einfachen verwalteten ausführbaren Datei\) geladen wird, können Sie beim Aufruf der [CorBindToRuntimeEx\-Funktion](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)\-Funktion ein spezielles Flag angeben.  Um den Kompatibilitätsmodus für den gesamten Prozess zu aktivieren, legen Sie den `flags`\-Parameter für [CorBindToRuntimeEx\-Funktion](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) auf STARTUP\_LEGACY\_IMPERSONATION fest.  
  
## Beispiel  
 Im folgenden Beispiel wird das Angeben des Legacyverhaltens veranschaulicht, sodass die Windows\-Identität nicht über asynchrone Punkte übergeben wird.  
  
```  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)