---
title: "&lt;bypassTrustedAppStrongNames&gt;-Element | Microsoft Docs"
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
  - "<bypassTrustedAppStrongNames>-Element"
  - "bypassTrustedAppStrongNames-Element"
  - "Strong-Name Bypass-Funktion"
  - "Assemblys mit starken Namen, Laden in vertrauenswürdige Anwendungsdomänen"
ms.assetid: 71b2ebf6-3843-41e2-ad52-ffa5cd083a40
caps.latest.revision: 18
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 18
---
# &lt;bypassTrustedAppStrongNames&gt;-Element
Gibt an, ob die Validierung von starken Namen in vollständig vertrauenswürdigen Assemblys umgangen werden soll, wenn die Assemblys in einen vollständig vertrauenswürdigen <xref:System.AppDomain> geladen werden.  
  
## Syntax  
  
```  
<bypassTrustedAppStrongNames    
   enabled="true|false"/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob das Bypassfeature aktiviert wird, mit dem die Überprüfung starker Namen für vollständig vertrauenswürdige Assemblys umgangen wird.  Wenn diese Funktion aktiviert wird, werden starke Namen beim Laden der Assembly nicht auf deren Korrektheit überprüft.  Die Standardeinstellung ist `true`.|  
  
## Enabled\-Attribut  
  
|Wert|**Beschreibung**|  
|----------|----------------------|  
|`true`|Signaturen mit starkem Namen auf vollständig vertrauenswürdigen Assemblys werden nicht überprüft, wenn die Assemblys in einen vollständig vertrauenswürdigen <xref:System.AppDomain> geladen werden.  Dies ist der Standardwert.|  
|`false`|Signaturen mit starkem Namen auf vollständig vertrauenswürdigen Assemblys werden überprüft, wenn die Assemblys in einen vollständig vertrauenswürdigen <xref:System.AppDomain> geladen werden.  Die Signaturen mit starkem Namen werden nur auf die Richtigkeit der Signatur geprüft, die starken Namen werden jedoch nicht auf Übereinstimmungen verglichen.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## Hinweise  
 Die Strong\-Name\-Bypass\-Funktion vermeidet den Aufwand von Überprüfungen von Signaturen mit starkem Namen für vollständig vertrauenswürdige Assemblys.  
  
 Das Bypass\-Feature gilt für jede Assembly, die mit einem starken Namen signiert ist und die folgenden Eigenschaften aufweist:  
  
-   Voll vertrauenswürdig ohne <xref:System.Security.Policy.StrongName>\-Beweis \(hat z. B. `MyComputer`\-Zone\-Beweis\).  
  
-   Geladen in eine voll vertrauenswürdige <xref:System.AppDomain>.  
  
-   Geladen von einem Speicherort unter der <xref:System.AppDomainSetup.ApplicationBase%2A>\-Eigenschaft von diesem <xref:System.AppDomain>.  
  
-   Nicht verzögert signiert.  
  
> [!NOTE]
>  Wenn die Bypass\-Funktion mithilfe eines Registrierungsschlüssels für alle Anwendungen auf dem Computer deaktiviert wurde, hat diese Einstellung der Konfigurationsdatei keine Auswirkungen.  Weitere Informationen finden Sie unter [Gewusst wie: Deaktivieren des Strong\-Name\-Bypass\-Features](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md).  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie das Verhalten angegeben wird, das die Signatur mit starkem Namen auf vollständig vertrauenswürdigen Assemblys überprüft.  
  
```  
<configuration>  
   <runtime>  
      <bypassTrustedAppStrongNames enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
## Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Gewusst wie: Deaktivieren des Strong\-Name\-Bypass\-Features](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md)