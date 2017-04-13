---
title: "&lt;generatePublisherEvidence&gt;-Element | Microsoft Docs"
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
  - "<generatePublisherEvidence>-Element"
  - "generatePublisherEvidence-Element"
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
caps.latest.revision: 21
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 21
---
# &lt;generatePublisherEvidence&gt;-Element
Gibt an, ob die Laufzeit <xref:System.Security.Policy.Publisher>\-Beweise für die Codezugriffssicherheit \(CAS\) erstellt.  
  
## Syntax  
  
```  
<generatePublisherEvidence    
   enabled="true|false"/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob die Laufzeit <xref:System.Security.Policy.Publisher>\-Beweise erstellt.|  
  
## Enabled\-Attribut  
  
|Wert|**Beschreibung**|  
|----------|----------------------|  
|`false`|Erstellt keinen <xref:System.Security.Policy.Publisher>\-Beweis.|  
|`true`|Erstellt <xref:System.Security.Policy.Publisher>\-Beweis.  Dies ist der Standardwert.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## Hinweise  
  
> [!NOTE]
>  In [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] und höher hat dieses Element keine Auswirkung auf die Ladezeiten von Assemblys.  Weitere Informationen finden Sie im "Sicherheitsrichtlinienvereinfachung"\-Abschnitt in [Sicherheitsänderungen](../../../../../docs/framework/security/security-changes.md).  
  
 Die Common Language Runtime \(CLR\) versucht, die Authenticode\-Signatur zur Ladezeit zu überprüfen, damit der <xref:System.Security.Policy.Publisher>\-Beweis für die Assembly erstellt wird.  Standardmäßig benötigen die meisten Anwendungen jedoch keinen <xref:System.Security.Policy.Publisher>\-Beweis.  Die Standard\-CAS\-Richtlinie ist nicht auf <xref:System.Security.Policy.PublisherMembershipCondition> angewiesen.  Vermeiden Sie die unnötigen Startkosten, die mit der Prüfung der Herausgebersignatur zusammenhängen, es sei denn, die Anwendung wird auf einem Computer mit benutzerdefinierter CAS\-Richtlinie ausgeführt oder muss den Anforderungen von <xref:System.Security.Permissions.PublisherIdentityPermission> in einer nur teilweise vertrauenswürdigen Umgebung genügen. \(Forderungen nach Identitätsberechtigungen haben in einer vollständig vertrauenswürdigen Umgebung immer Erfolg.\)  
  
> [!NOTE]
>  Dienste sollten das `<generatePublisherEvidence>`\-Element verwenden, um die Startleistung zu verbessern.  Durch die Verwendung dieses Elements können auch Verzögerungen vermieden werden, die sonst ein Timeout und den Abbruch des Dienststarts verursachen können.  
  
## Konfigurationsdatei  
 Dieses Element kann nur in der Anwendungskonfigurationsdatei verwendet werden.  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie Sie mit dem `<generatePublisherEvidence>`\-Element die Suche nach der CAS\-Herausgeberrichtlinie für eine Anwendung deaktivieren.  
  
```  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)