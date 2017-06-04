---
title: "&lt;alwaysFlowImpersonationPolicy&gt;-Element | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/alwaysFlowImpersonationPolicy"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#alwaysFlowImpersonationPolicy"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<alwaysFlowImpersonationPolicy>-Element"
  - "alwaysFlowImpersonationPolicy-Element"
ms.assetid: ee622801-9e46-470b-85ab-88c4b1dd2ee1
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# &lt;alwaysFlowImpersonationPolicy&gt;-Element
Gibt an, dass die Windows\-Identität immer über asynchrone Punkte übergeben wird, unabhängig von der Art des Identitätswechsels.  
  
## Syntax  
  
```  
<alwaysFlowImpersonationPolicy    
  enabled="true|false"/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob die Windows\-Identität über asynchrone Punkte übergeben wird.|  
  
## Enabled\-Attribut  
  
|Wert|**Beschreibung**|  
|----------|----------------------|  
|`false`|Die Windows\-Identität wird nicht über asynchrone Punkte übergeben, es sei denn, der der Identitätswechsel erfolgt über eine verwaltete Methode wie <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.  Dies ist der Standardwert.|  
|`true`|Die Windows\-Identität wird immer über asynchrone Punkte übergeben, unabhängig von der Art des Identitätswechsels.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## Hinweise  
 In den .NET Framework\-Versionen 1.0 und 1.1 wird die Windows\-Identität nicht über asynchrone Punkte übergeben.  .NET Framework, Version 2.0, enthält ein <xref:System.Threading.ExecutionContext>\-Objekt mit Informationen über den gegenwärtig ausgeführten Thread, das über asynchrone Punkte innerhalb einer Anwendungsdomäne übergeben wird.  Dabei wird auch die <xref:System.Security.Principal.WindowsIdentity> übergeben. Dies setzt jedoch voraus, dass der Identitätswechsel über eine verwaltete Methode wie <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> und nicht anderweitig erfolgt, z. B. über Plattformaufrufe systemeigener Methoden.  Mit diesem Element wird angegeben, dass die Windows\-Identität über asynchrone Punkte übergeben wird, unabhängig von der Art des Identitätswechsels.  
  
 Es gibt zwei Möglichkeiten zum Ändern dieses Standardverhaltens:  
  
1.  In verwaltetem Code für die einzelnen Threads.  
  
     Sie können die Übergabe für die einzelnen Threads unterdrücken, indem Sie die <xref:System.Threading.ExecutionContext>\-Einstellungen und die <xref:System.Security.SecurityContext>\-Einstellungen mithilfe der Methoden <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=fullName>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=fullName> oder <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=fullName> ändern.  
  
2.  Im Aufruf der nicht verwalteten Hostschnittstelle zum Laden der Common Language Runtime \(CLR\).  
  
     Wenn die CLR über eine nicht verwaltete Hostschnittstelle \(anstelle einer einfachen verwalteten ausführbaren Datei\) geladen wird, können Sie beim Aufruf der [CorBindToRuntimeEx\-Funktion](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)\-Funktion ein spezielles Flag angeben.  Um den Kompatibilitätsmodus für den gesamten Prozess zu aktivieren, legen Sie den `flags`\-Parameter für [CorBindToRuntimeEx\-Funktion](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) auf STARTUP\_ALWAYSFLOW\_IMPERSONATION fest.  
  
## Konfigurationsdatei  
 Dieses Element kann nur in der Anwendungskonfigurationsdatei verwendet werden.  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Sie angeben können, dass die Windows\-Identität auch dann über asynchrone Punkte übergeben werden soll, wenn der Identitätswechsel auf andere Weise als über verwaltete Methoden erfolgt.  
  
```  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [\<legacyImpersonationPolicy\>\-Element](../../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)