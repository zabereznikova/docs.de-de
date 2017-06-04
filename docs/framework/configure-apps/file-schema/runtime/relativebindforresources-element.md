---
title: "&lt;relativeBindForResources&gt;-Element | Microsoft Docs"
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
  - "<relativeBindForResources>-Element"
  - "RelativeBindForResources-Element"
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# &lt;relativeBindForResources&gt;-Element
Optimiert die Überprüfung für Satellitenassemblys.  
  
## Syntax  
  
```vb  
<relativeBindForResources    
   enabled="true|false" />  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob die Common Language Runtime die Überprüfung für Satellitenassemblys optimiert.|  
  
## Enabled\-Attribut  
  
|Wert|**Beschreibung**|  
|----------|----------------------|  
|`false`|Die Laufzeit nicht optimiert die Überprüfung für Satellitenassemblys.  Dies ist der Standardwert.|  
|`true`|Die Laufzeit optimiert die Überprüfung für Satellitenassemblys.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## Hinweise  
 Normalerweise überprüft Ressourcen\-Manager für Ressourcen, wie im Thema [Verpacken und Bereitstellen von Ressourcen](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md) dokumentiert.  Dies bedeutet, dass, wenn Ressourcen\-Manager für eine bestimmte Version einer lokalisierten Ressource überprüft, es im globalen Assemblycache, im Listenfeld Suchen in einem kulturabhängigen Ordner in der Codebase der Anwendung, in Abfragefenster Installationsprogramm nach Satellitenassemblys sowie das <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName> auslöst Ereignis findet.  Das Element `<relativeBindForResources>` optimiert die Methode, in der für Satellitenassemblys Ressourcen\-Manager überprüft.  Es kann die Leistung verbessern, beim Überprüfen für Ressourcen unter folgenden Bedingungen:  
  
-   Wenn die Satellitenassembly im gleichen Speicherort wie die Codeassembly bereitgestellt wird.  Das heißt, wenn Codeassembly, die im globalen Assemblycache installiert ist, müssen die Satellitenassemblys ebenfalls dort installiert werden.  Wenn die Codeassembly in der Codebase der Anwendung installiert wird, müssen die Satellitenassemblys in einem kulturabhängigen Ordner in der Codebase auch installiert werden.  
  
-   Wenn Windows Installer verwenden oder nur selten nicht für bedarfsabhängige Installation von Satellitenassemblys verwendet wird.  
  
-   Wenn der Anwendungscode <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName> nicht das Ereignis behandelt.  
  
 Das `enabled`\-Attribut des `<relativeBindForResources>`\-Elements auf `true` festlegen, optimiert die Überprüfung des Ressourcen\-Managers für Satellitenassemblys, wie folgt:  
  
-   Sie verwendet den Speicherort der übergeordneten Code, um die Satellitenassembly zu überprüfen.  
  
-   Sie bewirkt nicht Abfragefenster Installationsprogramm für Satellitenassemblys.  
  
-   Sie löst das <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName>\-Ereignis aus.  
  
## Siehe auch  
 [Verpacken und Bereitstellen von Ressourcen](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)   
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)