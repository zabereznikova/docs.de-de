---
title: "&lt;assemblyBinding&gt;-Element f&#252;r &lt;runtime&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<assemblyBinding>-Element"
  - "assemblyBinding-Element"
  - "Containertags, <assemblyBinding>-Element"
ms.assetid: 964cbb35-ab49-4498-8471-209689e5dada
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# &lt;assemblyBinding&gt;-Element f&#252;r &lt;runtime&gt;
Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.  
  
## Syntax  
  
```  
  
        <assemblyBinding    
   xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
</assemblyBinding>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|**xmlns**|Erforderliches Attribut.<br /><br /> Gibt den XML\-Namespace an, der für die Assemblybindung erforderlich ist.  Verwenden Sie die Zeichenfolge "urn:schemas\-microsoft\-com:asm.v1" als Wert.|  
|**appliesTo**|Gibt die Laufzeitversion an, die für die .NET Framework\-Assemblyumleitungen gilt.  Dieses optionale Attribut verwendet eine .NET Framework\-Versionsnummer, um anzugeben, welche Version verwendet wird.  Ohne Angabe eines **appliesTo**\-Attributs gilt das **\<assemblyBinding\>**\-Element für alle Versionen von .NET Framework.  Das **appliesTo**\-Attribut wurde mit .NET Framework, Version 1.1 eingeführt; es wird von .NET Framework, Version 1.0, ignoriert.  Dies bedeutet, dass alle **\<assemblyBinding\>**\-Elemente bei Verwendung von .NET Framework, Version 1.0, angewendet werden, auch wenn das **appliesTo**\-Attribut angegeben wurde.|  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<dependentAssembly\>](../../../../../docs/framework/configure-apps/file-schema/runtime/dependentassembly-element.md)|Kapselt die Bindungsrichtlinie und den Assemblyspeicherort für eine Assembly.  Verwenden Sie für jede Assembly ein **\<dependentAssembly\>**\-Tag.|  
|[\<probing\>](../../../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md)|Gibt Unterverzeichnisse an, die die Common Language Runtime beim Laden von Assemblys durchsucht.|  
|[\<publisherPolicy\>](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md)|Gibt an, ob die Common Language Runtime die Herausgeberrichtlinie anwendet.|  
|[\<qualifyAssembly\>](../../../../../docs/framework/configure-apps/file-schema/runtime/qualifyassembly-element.md)|Gibt den vollständigen Namen der Assembly an, die dynamisch geladen werden soll, wenn Sie ein Teilname verwendet wird.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht, wie Sie eine Assemblyversion zu einer anderen umleiten und eine Codebasis bereitstellen.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <bindingRedirect oldVersion="1.0.0.0"  
                             newVersion="2.0.0.0"/>  
            <codeBase version="2.0.0.0"  
                      href="http://www.litwareinc.com/myAssembly.dll"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 Das folgende Beispiel zeigt, wie Sie das **appliesTo**\-Attribut zum Umleiten der Bindung einer .NET Framework\-Assembly verwenden.  
  
```  
<runtime>  
   <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
      <dependentAssembly>   
         <assemblyIdentity name="mscorcfg" publicKeyToken="b03f5f7f11d50a3a" culture=""/>  
         <bindingRedirect oldVersion="0.0.0.0-65535.65535.65535.65535" newVersion="1.0.3300.0"/>  
      </dependentAssembly>  
   </assemblyBinding>  
</runtime>  
```  
  
## Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Umleiten von Assemblyversionen](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)