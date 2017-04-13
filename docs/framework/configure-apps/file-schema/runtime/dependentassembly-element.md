---
title: "&lt;dependentAssembly&gt;-Element | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#dependentAssembly"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<dependentAssembly>-Element"
  - "Containertags, <dependentAssembly>-Element"
  - "dependentAssembly-Element"
ms.assetid: 14e95627-dd79-4b82-ac85-e682aa3a31d8
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# &lt;dependentAssembly&gt;-Element
Kapselt die Bindungsrichtlinie und den Assemblyspeicherort für jede Assembly.  Verwenden Sie für jede Assembly ein `dependentAssembly`\-Element.  
  
## Syntax  
  
```  
<dependentAssembly>   
</dependentAssembly>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine.  
  
### Untergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`assemblyIdentity`|Enthält Identifizierungsinformationen für die Assembly.  Dieses Element muss in jedes `dependentAssembly`\-Element eingefügt werden.|  
|`codeBase`|Gibt an, wo die Runtime eine freigegebene Assembly finden kann, wenn sie nicht auf dem Computer installiert ist.|  
|`bindingRedirect`|Leitet eine Assemblyversion in eine andere um.|  
|`publisherPolicy`|Gibt an, ob die Runtime die Herausgeberrichtlinie für diese Assembly anwendet.|  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`assemblyBinding`|Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht, wie Sie Assemblyinformationen für zwei Assemblys kapseln.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for myAssembly.-->  
         </dependentAssembly>  
         <dependentAssembly>  
            <assemblyIdentity name="mySecondAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for mySecondAssembly.-->  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Umleiten von Assemblyversionen](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)