---
title: "&lt;codeBase&gt;-Element | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#codeBase"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/codeBase"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<codeBase>-Element"
  - "codeBase-Element"
  - "Containertags, <codeBase>-Element"
ms.assetid: d48a3983-2297-43ff-a14d-1f29d3995822
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# &lt;codeBase&gt;-Element
Gibt an, wo die Common Language Runtime eine Assembly finden kann.  
  
## Syntax  
  
```  
  
   <codeBase    
version="Assembly version"  
href="URL of assembly"/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`href`|Erforderliches Attribut.<br /><br /> Gibt die URL an, unter der die Runtime die angegebene Version der Assembly finden kann.|  
|`version`|Erforderliches Attribut.<br /><br /> Gibt die Versionsnummer der Assembly an, für die die CodeBase gilt.  Das Format einer Assemblyversionsnummer lautet *major.minor.build.revision*.|  
  
## version\-Attribut  
  
|Wert|**Beschreibung**|  
|----------|----------------------|  
|Gültige Werte für jeden Abschnitt der Versionsnummer sind 0 bis 65535.|Nicht zutreffend.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`buildproviders`|Definiert eine Auflistung von Buildanbietern, die zum Kompilieren benutzerdefinierter Ressourcendateien verwendet werden.  Sie können eine beliebige Anzahl von Buildanbietern verwenden.|  
|`compilation`|Konfiguriert alle Kompilierungseinstellungen, die ASP.NET verwendet.|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`System.web`|Gibt das Stammelement für den ASP.NET\-Konfigurationsabschnitt an.|  
  
## Hinweise  
 Während der Laufzeit, den **\<codeBase\>** zu verwenden, das in eine Computerkonfigurationsdatei oder eine Herausgeberrichtliniendatei festlegt, muss die Datei auch die Assemblyversion umleiten.  Eine Anwendungskonfigurationsdatei kann eine CodeBase\-Einstellung enthalten, ohne dass die Assemblyversion umgeleitet wird.  Nachdem die Runtime ermittelt hat, welche Assemblyversion zu verwenden ist, wendet sie die CodeBase\-Einstellung aus der Datei an, die die Version bestimmt.  Wird keine CodeBase angegeben, sucht die Runtime auf die übliche Weise nach der Assembly.  
  
 Wenn die Assembly einen starken Namen hat, kann die CodeBase ein beliebiger Speicherort im lokalen Intranet oder im Internet sein.  Ist die Assembly eine private Assembly, muss die CodeBase\-Einstellung ein Pfad relativ zum Anwendungsverzeichnis sein.  
  
 Bei Assemblys ohne einen starken Namen, ist Version und die Ladeprogrammverwendung das erste nicht der CodeBase \<im Ausfüllbereich\> dependentAssembly \<\>ignoriert.  Wenn ein Eintrag in der Anwendungskonfigurationsdatei vorliegt, der die Bindung an eine andere Assembly umleitet, hat die Umleitung Vorrang, selbst wenn die Assemblyversion nicht der Bindungsanforderung entspricht.  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht, wie Sie angeben, wo die Runtime eine Assembly finden kann.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <codeBase version="2.0.0.0"  
                      href="http://www.litwareinc.com/myAssembly.dll"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Festlegen des Speicherortes einer Assembly](../../../../../docs/framework/configure-apps/specify-assembly-location.md)   
 [So sucht Common Language Runtime nach Assemblys](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)