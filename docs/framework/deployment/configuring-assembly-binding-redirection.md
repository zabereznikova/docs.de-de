---
title: "Konfigurieren der Umleitung der Assemblybindung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
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
  - "Assemblys [.NET Framework], Bindungsumleitung"
  - "Parallele Ausführung, Umleitung der Assemblybindung"
ms.assetid: d266cbd8-bf91-41d1-baf0-afbc481a741f
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# Konfigurieren der Umleitung der Assemblybindung
Standardmäßig verwenden Anwendungen eine Reihe von .NET Framework\-Assemblys, die mit der Laufzeitversion bereitgestellt werden, die zum Kompilieren der Anwendung verwendet wird.  Mithilfe des **appliesTo**\-Attributs im [\<assemblyBinding\>](../../../docs/framework/configure-apps/file-schema/runtime/assemblybinding-element-for-runtime.md)\-Element in einer Anwendungskonfigurationsdatei können Sie Assemblybindungsverweise zu einer bestimmten Version der .NET Framework\-Assemblys umleiten.  Dieses optionale Attribut verwendet eine .NET Framework\-Versionsnummer, um anzugeben, welche Version verwendet wird.  Ohne Angabe eines **appliesTo**\-Attributs gilt das **\<assemblyBinding\>**\-Element für alle Versionen von .NET Framework.  
  
 Das **appliesTo**\-Attribut wurde mit .NET Framework, Version 1.1 eingeführt; es wird von .NET Framework, Version 1.0, ignoriert.  Dies bedeutet, dass alle **\<assemblyBinding\>**\-Elemente bei Verwendung von .NET Framework, Version 1.0, angewendet werden, auch wenn das **appliesTo**\-Attribut angegeben wurde.  
  
> [!NOTE]
>  Verwenden Sie das **appliesTo**\-Attribut, um die Umleitung der Assemblybindung auf eine spezielle Version der Laufzeit zu beschränken.  
  
 Um zum Beispiel die Assemblybindung einer .NET Framework 1.0\-Assembly umzuleiten, müssten Sie den folgenden XML\-Code in die Anwendungskonfigurationsdatei einfügen.  
  
```  
<runtime>  
        <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
            <dependentAssembly>   
               * assembly information goes here *  
            </dependentAssembly>  
       </assemblyBinding>  
</runtime>  
```  
  
 Die **\<assemblyBinding\>**\-Elemente werden nach Reihenfolge ausgeführt.  Sie sollten zuerst Umleitungsinformationen für die Assemlybindungen aller .NET Framework 1.0\-Assemblys eingeben, gefolgt von den Umleitungsinformationen für die Assemblybindungen beliebiger .NET Framework 1.1\-Assemblys.  Geben Sie zuletzt die Informationen zum Umleiten der Assemblybindung für alle .NET Framework\-Assemblyumleitungen ein, bei denen nicht das **appliesTo**\-Attribut verwendet wird und die daher für alle Versionen .NET Framework\-Versionen gelten.  Falls bei der Umleitung Konflikte auftreten, wird die erste passende Umleitungsanweisung in der Konfigurationsdatei verwendet.  
  
 Beispiel: Zum Umleiten eines Verweises auf eine .NET Framework 1.0\-Assembly und eines anderen Verweises auf eine .NET Framework 1.1\-Assembly müssten Sie nach dem Muster im folgenden Pseudocode vorgehen.  
  
```  
<assemblyBinding xmlns="..." appliesTo="v1.0.3705">   
<! — .NET Framework version 1.0 redirects here. -->   
</assemblyBinding>   
  
<assemblyBinding xmlns="..." appliesTo="v1.1.4322">   
    <! — .NET Framework version 1.1 redirects here. -->   
</assemblyBinding>   
  
<assemblyBinding xmlns="...">   
<!-- Redirects meant for all versions of the .NET Framework. -->   
</assemblyBinding>  
```  
  
## Fehler beim Debuggen der Konfigurationsdatei  
 Die Laufzeit analysiert Konfigurationsdateien einmal, wenn eine Anwendungsdomäne erstellt wird, und lädt dann Code in diese Anwendungsdomäne.  Die Common Language Runtime behandelt Fehler in einer Konfigurationsdatei, indem der jeweilige Eintrag ignoriert wird.  Zur Laufzeit wird die gesamte Konfigurationsdatei ignoriert, wenn sie fehlerhaft formatierte XLM enthält.  Bei ungültiger XML werden nur die ungültigen Abschnitte ignoriert.  
  
 Sie können feststellen, ob eine Konfigurationsdatei genutzt wird, indem Sie ermitteln, ob Umleitungen der Assemblybindung auftreten.  Verwenden Sie den [Assembly Binding Log Viewer \(Fuslogvw.exe\)](../../../docs/framework/tools/fuslogvw-exe-assembly-binding-log-viewer.md), um zu sehen, welche Assemblys geladen werden.  Um alle Assemblybindungen anzuzeigen, müssen Sie in der Registrierung einen Eintrag für **ForceLog** eingeben.  
  
## Siehe auch  
 [Gewusst wie: Aktivieren und Deaktivieren der Bindungsumleitung](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)