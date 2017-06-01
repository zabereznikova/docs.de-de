---
title: "&lt;linkedConfiguration&gt;-Element | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding/linkedConfiguration"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#linkedConfiguration"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<linkedConfiguration>-Element"
  - "Konfigurationsdateien [.NET Framework], Verknüpfte Konfigurationsdateien"
  - "Einfügen von Konfigurationsdateien"
  - "Verknüpfte Konfigurationsdateien"
  - "linkedConfiguration-Element"
ms.assetid: 8eb34f3b-427e-4288-a7ff-c73f489deb45
caps.latest.revision: 6
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# &lt;linkedConfiguration&gt;-Element
Gibt eine einzuschließende Konfigurationsdatei an.  
  
## Syntax  
  
```  
<linkedConfiguration  
   href="URL of linked configuration file"/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`href`|Die URL der Konfigurationsdatei, die eingeschlossen werden soll.  Das einzige unterstützte Format für das `href`\-Attribut ist "file:\/\/".  Lokale Dateien und UNC\-Dateien werden unterstützt.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<assemblyBinding\>\-Element](../../../../docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md)|Gibt die Assemblybindungsrichtlinie auf Konfigurationsebene an.|  
  
## Hinweise  
 Das `<linkedConfiguration>`\-Element vereinfacht die Wartung für Komponentenassemblys.  Wenn eine oder mehrere Anwendungen eine Assembly verwenden, deren Konfigurationsdatei sich an einem bekannten Speicherort befindet, können die Konfigurationsdateien der Anwendungen, die die Assembly verwenden, das `<linkedConfiguration>`\-Element verwenden, um die Assemblykonfigurationsdatei einzuschließen, anstatt Konfigurationsinformationen direkt einzuschließen.  Wenn die Komponentenassembly gewartet wird, erhalten alle Anwendungen, die die Assembly verwenden, mit einer Aktualisierung der gemeinsamen Konfigurationsdatei aktualisierte Konfigurationsinformationen.  
  
> [!NOTE]
>  Das `<linkedConfiguration>`\-Element wird nicht für Anwendungen mit parallelen Manifestdateien in Windows unterstützt.  
  
 Die Verwendung verknüpfter Konfigurationsdateien unterliegt den folgenden Regeln.  
  
-   Die Einstellungen in eingeschlossenen Konfigurationsdateien wirken sich nur auf die Bindungsrichtlinie des Ladeprogramms aus und werden nur von ihm verwendet.  Die eingeschlossenen Konfigurationsdateien können außer den Bindungsrichtlinien andere Einstellungen haben, aber diese Einstellungen haben keine Auswirkungen.  
  
-   Das einzige unterstützte Format für das `href`\-Attribut ist "file:\/\/".  Lokale Dateien und UNC\-Dateien werden unterstützt.  
  
-   Es gibt keine Einschränkung für die Anzahl verknüpfter Konfigurationen pro Konfigurationsdatei.  
  
-   Alle verknüpften Konfigurationsdateien werden in einer Datei zusammengeführt; dies ähnelt dem Verhalten der `#include`\-Direktive in C\/C\+\+.  
  
-   Das `<linkedConfiguration>`\-Element wird nur in Anwendungskonfigurationsdateien zugelassen; in Machine.config wird es ignoriert.  
  
-   Zirkelverweise werden erkannt und beendet.  Das heißt, wenn die `<linkedConfiguration>`\-Elemente einer Reihe von Konfigurationsdateien eine Schleife bilden, wird die Schleife erkannt und gestoppt.  
  
## Beispiel  
 Das folgende Codebeispiel zeigt, wie eine Konfigurationsdatei von der lokalen Festplatte eingeschlossen wird.  
  
```  
<configuration>  
   <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
      <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>  
   </assemblyBinding>  
</configuration>  
```  
  
## Siehe auch  
 [\<assemblyBinding\>\-Element](../../../../docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md)   
 [Konfigurationsdateischema](../../../../docs/framework/configure-apps/file-schema/index.md)