---
title: "&lt;PreferComInsteadOfManagedRemoting&gt;-Element | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<PreferComInsteadOfManagedRemoting>-Element"
  - "PreferComInsteadOfManagedRemoting-Element"
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
caps.latest.revision: 17
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 17
---
# &lt;PreferComInsteadOfManagedRemoting&gt;-Element
Gibt an, ob die Laufzeit COM\-Interop anstelle von Remoting für Aufrufe über Anwendungsdomänengrenzen hinweg verwendet.  
  
## Syntax  
  
```  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob die Laufzeit zwischen Anwendungsdomänengrenzen COM\-Interop anstelle von Remoting verwendet.|  
  
## Enabled\-Attribut  
  
|Wert|**Beschreibung**|  
|----------|----------------------|  
|`false`|Die Laufzeit verwendet Remoting zwischen Anwendungsdomänengrenzen.  Dies ist der Standardwert.|  
|`true`|Die Laufzeit verwendet COM\-Interop zwischen Anwendungsdomänengrenzen.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## Hinweise  
 Wenn Sie das `enabled`\-Attribut auf `true` festlegen, zeigt die Laufzeit folgendes Verhalten:  
  
-   Die Laufzeit ruft [IUnknown::QueryInterface](http://go.microsoft.com/fwlink/?LinkID=144867) nicht [IManagedObject](../../../../../ocs/framework/unmanaged-api/hosting/imanagedobject-interface.md) für eine Schnittstelle auf, wenn eine [IUnknown](http://go.microsoft.com/fwlink/?LinkId=148003)\-Schnittstelle über eine COM\-Schnittstelle in die Domäne eintritt.  Stattdessen wird ein [Runtime Callable Wrapper](../../../../../docs/framework/interop/runtime-callable-wrapper.md) \(RCW\) um das Objekt erstellt.  
  
-   Wenn ein `QueryInterface`\-Aufruf für die [IManagedObject](../../../../../ocs/framework/unmanaged-api/hosting/imanagedobject-interface.md)\-Schnittstelle eines [COM Callable Wrapper](../../../../../docs/framework/interop/com-callable-wrapper.md) \(CCW\) empfangen wird, der in dieser Domäne erstellt wurde, gibt die Laufzeit E\_NOINTERFACE zurück.  
  
 Diese zwei Verhaltensweisen stellen sicher, dass alle Aufrufe über COM\-Schnittstellen zwischen verwalteten Objekten über Anwendungsdomänengrenzen hinweg COM und COM\-Interop anstelle von Remoting verwenden.  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie angegeben wird, dass die Laufzeit COM\-Interop über Isolationsgrenzen hinweg verwenden soll:  
  
```  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)