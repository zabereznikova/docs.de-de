---
title: "&lt;publisherPolicy&gt;-Element | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/publisherPolicy"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/publisherPolicy"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#publisherPolicy"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<publisherPolicy>-Element"
  - "Containertags, <publisherPolicy>-Element"
  - "publisherPolicy-Element"
ms.assetid: 4613407e-d0a8-4ef2-9f81-a6acb9fdc7d4
caps.latest.revision: 18
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 17
---
# &lt;publisherPolicy&gt;-Element
Gibt an, ob die Runtime die Herausgeberrichtlinie anwendet.  
  
## Syntax  
  
```  
  
<publisherPolicy apply="yes|no"/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`apply`|Gibt an, ob die Herausgeberrichtlinie angewendet werden soll oder nicht.|  
  
## Attribut anwenden  
  
|Wert|**Beschreibung**|  
|----------|----------------------|  
|`yes`|Die Herausgeberrichtlinie wird angewendet.  Dies ist die Standardeinstellung.|  
|`no`|Die Herausgeberrichtlinie wird nicht angewendet.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## Hinweise  
 Wenn ein Komponentenanbieter eine neue Version einer Assembly herausgibt, kann er mithilfe einer Herausgeberrichtlinie festlegen, dass Anwendungen, die bisher die alte Version verwendet haben, jetzt die neue Version verwenden.  Um anzugeben ob Herausgeberrichtlinien eine bestimmte Assembly, platzieren Sie das **\<publisherPolicy\>**\-Element in das **\<dependentAssembly\>**\-Element gilt.  
  
 Die Standardeinstellung für das **apply**\-Attribut lautet **yes**.  Wird das **apply**\-Attribut auf **no** festgelegt, werden alle vorherigen **yes**\-Einstellungen für die Assembly überschrieben.  
  
 Berechtigung ist erforderlich, damit eine Anwendung explizit die Herausgeberrichtlinie mithilfe des [\<publisherPolicy apply\= " no"\/\>](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md)\-Elements in der Anwendungskonfigurationsdatei ignoriert.  Die Berechtigung wird erteilt, indem das [BindingRedirects](frlrfSystemSecurityPermissionsSecurityPermissionFlagClassTopic)\-Flag für die [SecurityPermission\-Klasse](frlrfSystemSecurityPermissionsSecurityPermissionClassTopic) festgelegt wird.  Weitere Informationen finden Sie unter [Sicherheitsberechtigung für die Umleitung der Assemblybindung](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).  
  
## Beispiel  
 Im folgenden Beispiel wird die Herausgeberrichtlinie für die Assembly `myAssembly` deaktiviert.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                                    publicKeyToken="32ab4ba45e0a69a1"  
                                    culture="neutral" />  
            <publisherPolicy apply="no"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [So sucht Common Language Runtime nach Assemblys](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)   
 [Umleiten von Assemblyversionen](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)