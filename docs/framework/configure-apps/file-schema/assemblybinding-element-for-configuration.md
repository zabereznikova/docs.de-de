---
title: "&lt;assemblyBinding&gt;-Element f&#252;r &lt;configuration&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<assemblyBinding>-Element"
  - "assemblyBinding-Element"
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
caps.latest.revision: 6
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# &lt;assemblyBinding&gt;-Element f&#252;r &lt;configuration&gt;
Gibt die Assemblybindungsrichtlinie auf Konfigurationsebene an.  
  
## Syntax  
  
```  
<assemblyBinding    
   xmlns="urn:schemas-microsoft-com:asm.v1">  
</assemblyBinding>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`xmlns`|Erforderliches Attribut.<br /><br /> Gibt den XML‑Namespace an, der für die Assemblybindung benötigt wird.  Verwenden Sie als Wert die Zeichenfolge **urn:schemas\-microsoft\-com:asm.v1**.|  
  
### Untergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<linkedConfiguration\>\-Element](../../../../docs/framework/configure-apps/file-schema/linkedconfiguration-element.md)|Gibt eine einzuschließende Konfigurationsdatei an.|  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<configuration\>\-Element](../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
  
## Hinweise  
 Das [\<linkedConfiguration\>\-Element](../../../../docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) vereinfacht die Verwaltung von  dadurch, dass Anwendungskonfigurationsdateien Assemblykonfigurationsdateien in bekannte Speicherorte aufnehmen können, anstatt Assemblykonfigurationseinstellungen zu duplizieren.  
  
> [!NOTE]
>  Das `<linkedConfiguration>`\-Element wird nicht für Anwendungen mit parallelen Manifestdateien in Windows unterstützt.  
  
## Beispiel  
 Das folgende Codebeispiel zeigt, wie eine Konfigurationsdatei auf der lokalen Festplatte eingeschlossen wird.  
  
```  
<configuration>  
   <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
      <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>  
   </assemblyBinding>  
</configuration>  
```  
  
## Siehe auch  
 [Konfigurationsdateischema](../../../../docs/framework/configure-apps/file-schema/index.md)