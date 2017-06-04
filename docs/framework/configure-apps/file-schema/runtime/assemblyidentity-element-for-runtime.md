---
title: "&lt;assemblyIdentity&gt;-Element f&#252;r &lt;runtime&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/assemblyIdentity"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#assemblyIdentity"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<assemblyIdentity>-Element"
  - "assemblyIdentity-Element"
  - "Containertags, <assemblyIdentity>-Element"
ms.assetid: cea4d187-6398-4da4-af09-c1abc6a349c1
caps.latest.revision: 17
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 17
---
# &lt;assemblyIdentity&gt;-Element f&#252;r &lt;runtime&gt;
Enthält Identifizierungsinformationen für die Assembly.  
  
## Syntax  
  
```  
  
   <assemblyIdentity    
name="assembly name"  
publicKeyToken="public key token"  
culture="assembly culture"/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`name`|Erforderliches Attribut.<br /><br /> Der Name der Assembly|  
|`culture`|Optionales Attribut.<br /><br /> Eine Zeichenfolge, die die Sprache sowie das Land bzw. die Region der Assembly angibt.|  
|`publicKeyToken`|Optionales Attribut.<br /><br /> Ein Hexadezimalwert, der den starken Namen der Assembly angibt.|  
|`processorArchitecture`|Optionales Attribut.<br /><br /> Einer der Werte "x86", "amd64", "msil" und "ia64". Er gibt die Prozessorarchitektur für eine Assembly an, die prozessorspezifischen Code enthält.  Bei diesen Zeichen wird die Groß\-\/Kleinschreibung nicht berücksichtigt.  Wenn dem Attribut ein anderer Wert zugewiesen wird, dann wird das ganze `<assemblyIdentity>`\-Element ignoriert.  Siehe <xref:System.Reflection.ProcessorArchitecture>.|  
  
## ProcessorArchitecture\-Attribut  
  
|Wert|**Beschreibung**|  
|----------|----------------------|  
|`amd64`|Nur ein 64\-Bit\-AMD\-Prozessor.|  
|`ia64`|Nur ein 64\-Bit\-Intel\-Prozessor.|  
|`msil`|Neutral in Bezug auf Prozessor und Bits pro Wort|  
|`x86`|Ein 32\-Bit\-Intel\-Prozessor, entweder systemeigen oder in der WOW\-Umgebung \(Windows on Windows\) auf einer 64\-Bit\-Plattform.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`assemblyBinding`|Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`dependentAssembly`|Kapselt die Bindungsrichtlinie und den Assemblyspeicherort für jede Assembly.  Verwenden Sie für jede Assembly ein `<dependentAssembly>`\-Element.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## Hinweise  
 Jedes **\<dependentAssembly\>**\-Element muss ein Element **\<assemblyIdentity\>** untergeordneten Elements verfügen.  
  
 Wenn das `processorArchitecture`\-Attribut vorhanden ist, gilt das `<assemblyIdentity>`\-Element nur für die Assembly mit der entsprechenden Prozessorarchitektur.  Ist das `processorArchitecture`\-Attribut nicht vorhanden, kann das `<assemblyIdentity>`\-Element für eine Assembly mit einer beliebigen Prozessorarchitektur gelten.  
  
 Das folgende Beispiel zeigt eine Konfigurationsdatei für zwei Assemblys mit dem gleichen Namen, die auf zwei verschiedene Dualprozessorarchitekturen abzielen und deren Versionen nicht synchron gehalten wurden.  Wenn die Anwendung auf der x86\-Plattform ausgeführt wird, gilt das erste `<assemblyIdentity>`\-Element, und das andere wird ignoriert.  Wird die Anwendung auf einer Plattform ausgeführt, die keine x86\- oder ia64\-Plattform ist, werden beide ignoriert.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"  
                  processorArchitecture="x86" />  
            <bindingRedirect oldVersion= "1.0.0.0"   
                  newVersion="1.1.0.0" />  
         </dependentAssembly>  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"   
                  processorArchitecture="ia64" />  
            <bindingRedirect oldVersion="1.0.0.0"   
                  newVersion="2.0.0.0" />  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 Wenn eine Konfigurationsdatei ein `<assemblyIdentity>`\-Element ohne `processorArchitecture`\-Attribut enthält und kein Element enthält, das der Plattform entspricht, wird das Element ohne das `processorArchitecture`\-Attribut verwendet.  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht, wie Sie Informationen über eine Assembly bereitstellen.  
  
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
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Umleiten von Assemblyversionen](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)