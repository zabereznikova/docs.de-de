---
title: "Gewusst wie: &#196;ndern des Werts einer Einstellung zwischen Anwendungssitzungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Anwendungseinstellungen [Windows Forms], Zwischen Anwendungssitzungen"
  - "Anwendungseinstellungen [Windows Forms], Ändern"
ms.assetid: 1a85911f-97b2-476c-930b-83379edd890c
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: &#196;ndern des Werts einer Einstellung zwischen Anwendungssitzungen
Es kann vorkommen, dass Sie den Wert einer Einstellung zwischen Anwendungssitzungen ändern möchten, nachdem die Anwendung kompiliert und bereitgestellt wurde.  Vielleicht möchten Sie eine Verbindungszeichenfolge ändern, um auf den richtigen Datenbankspeicherort zu verweisen.  Da nach dem Kompilieren und Bereitstellen der Anwendung keine Entwurfszeittools verfügbar sind, müssen Sie den Einstellungswert manuell in der Datei ändern.  
  
### So ändern Sie den Wert einer Einstellung zwischen Anwendungssitzungen  
  
1.  Öffnen Sie in Microsoft Editor bzw. einem anderen Text\- bzw. XML\-Editor die mit der Anwendung verknüpfte CONFIG\-Datei.  
  
2.  Suchen Sie den Eintrag der Einstellung, die Sie ändern möchten.  Er sollte ähnlich wie im folgenden Beispiel aussehen.  
  
    ```  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3.  Geben Sie einen neuen Wert für die Einstellung ein, und speichern Sie die Datei.  
  
## Siehe auch  
 [Verwenden von Anwendungseinstellungen und Benutzereinstellungen](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)   
 [Übersicht über Anwendungseinstellungen](../../../../docs/framework/winforms/advanced/application-settings-overview.md)