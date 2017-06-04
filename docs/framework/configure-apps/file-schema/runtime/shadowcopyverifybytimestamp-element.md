---
title: "&lt;shadowCopyVerifyByTimestamp&gt;-Element | Microsoft Docs"
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
  - "<shadowCopyTimeStampVerification>-Element"
  - "shadowCopyTimeStampVerification-Element"
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# &lt;shadowCopyVerifyByTimestamp&gt;-Element
Gibt an, ob das Schattenkopieren das in [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] eingeführte Standardstartverhalten verwenden soll oder verwendet das Startverhalten der früheren Versionen von .NET Framework.  
  
## Syntax  
  
```  
<shadowCopyVerifyByTimestamp enabled="true|false" />  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|enabled|Erforderliches Attribut.<br /><br /> Gibt an, ob Anwendungsdomänen, die Schattenkopien verwenden, beim Starten Assemblyzeitstempel vergleichen, um zu bestimmen, ob eine Assembly vor dem Schattenkopieren der Assembly aktualisiert wurde.|  
  
## Enabled\-Attribut  
  
|Wert|**Beschreibung**|  
|----------|----------------------|  
|true|Bei Start werden nur Assemblys kopiert, die aktualisiert wurden, nachdem sie zuletzt in das Schattenkopieverzeichnis kopiert wurden.  Dies ist der Standard für [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].|  
|false|Setzt auf das Startverhalten \(alle Dateien beim Start kopieren\) der früheren Versionen von .NET Framework zurück.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## Hinweise  
 Mit dem [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] beginnend, sind Assemblys nur Schattenkopien, wenn ihre Zeitstempel angeben, dass sie sich geändert haben, seit sie zuletzt in das Schattenkopieverzeichnis kopiert wurden.  Dies verbessert Startzeiten für zahlreiche Anwendungen, die Schattenkopien verwenden \(siehe [Erstellen von Schattenkopien von Assemblys](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md)\).  Anwendungen, die einen hohen Prozentsatz und eine Häufigkeit von Assemblyaktualisierungen haben, profitieren könnten möglicherweise nicht von dieser Änderung im Verhalten.  In diesem Fall können Sie dieses Element verwenden, um das Verhalten der früheren Versionen des .NET Framework wiederherstellen.  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie das Startverhalten des Schattenkopierens in [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] deaktiviert und auf das Startverhalten vorheriger Versionen von .NET Framework gesetzt wird.  
  
```  
<configuration>  
   <runtime>  
      <shadowCopyVerifyByTimestamp enabled="false" />  
   </runtime>  
</configuration>  
```  
  
## Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Erstellen von Schattenkopien von Assemblys](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md)