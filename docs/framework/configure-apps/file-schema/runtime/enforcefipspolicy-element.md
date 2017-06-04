---
title: "&lt;enforceFIPSPolicy&gt;-Element | Microsoft Docs"
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
  - "<enforceFIPSPolicy>-Element"
  - "enforceFIPSPolicy-Element"
  - "Federal Information Processing Standards (FIPS)"
  - "FIPS"
ms.assetid: c35509c4-35cf-43c0-bb47-75e4208aa24e
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# &lt;enforceFIPSPolicy&gt;-Element
Gibt an, ob eine Computerkonfigurationsforderung erzwungen wird, dass kryptografische Algorithmen Federal Information Processing Standards \(FIPS\) entsprechen müssen.  
  
## Syntax  
  
```  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|enabled|Erforderliches Attribut.<br /><br /> Gibt an, ob die Erzwingung einer Computerkonfigurationsanforderung aktiviert wird, dass kryptografische Algorithmen mit FIPS kompatibel sein müssen.|  
  
## Enabled\-Attribut  
  
|Wert|**Beschreibung**|  
|----------|----------------------|  
|`true`|Wenn der Computer so konfiguriert ist, dass die Kryptografiealgorithmen FIPS\-kompatibel sein müssen, wird die Anforderung erzwungen.  Wenn eine Klasse einen Algorithmus implementiert, der nicht mit FIPS kompatibel ist, lösen die Konstruktoren oder `Create`\-Methoden für diese Klasse Ausnahmen aus, wenn sie auf diesem Computer ausgeführt werden.  Dies ist der Standardwert.|  
|`false`|Kryptografische Algorithmen, die von der Anwendung verwendet werden, müssen unabhängig von der Computerkonfiguration nicht mit FIPS kompatibel sein.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## Hinweise  
 Ab .NET Framework 2.0 wird die Erstellung von Klassen, die kryptografische Algorithmen implementieren, durch die Konfiguration des Computers gesteuert.  Wenn der Computer so konfiguriert ist, dass Algorithmen mit FIPS kompatibel sein müssen, und eine Klasse einen Algorithmus implementiert, der nicht mit FIPS kompatibel ist, wird bei jedem Versuch, eine Instanz dieser Klasse zu erstellen, eine Ausnahme ausgelöst.  Konstruktoren lösen eine <xref:System.InvalidOperationException>\-Ausnahme aus, und `Create`\-Methoden lösen eine <xref:System.Reflection.TargetInvocationException>\-Ausnahme mit einer inneren <xref:System.InvalidOperationException>\-Ausnahme aus.  
  
 Wenn die Anwendung auf Computern ausgeführt wird, deren Konfigurationen die Kompatibilität mit FIPS erfordern, und die Anwendung einen Algorithmus verwendet, der nicht mit FIPS kompatibel ist, kann dieses Element in der Konfigurationsdatei verwendet werden, um die Common Language Runtime \(CLR\) am Erzwingen der FIPS\-Kompatibilität zu hindern.  Dieses Element wurde in [!INCLUDE[net_v20SP1_long](../../../../../includes/net-v20sp1-long-md.md)] eingeführt.  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie verhindert wird, dass die CLR FIPS\-Einhaltung erzwingt.  
  
```  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Cryptography Model](../../../../../docs/standard/security/cryptography-model.md)