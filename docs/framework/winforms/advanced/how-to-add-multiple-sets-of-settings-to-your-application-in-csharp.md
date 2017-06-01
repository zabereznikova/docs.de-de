---
title: "Gewusst wie: Hinzuf&#252;gen mehrerer Gruppen von Einstellungen zur Anwendung in C# | Microsoft Docs"
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
  - "Anwendungseinstellungen [Windows Forms], C#"
  - "Anwendungseinstellungen [Windows Forms], Mehrere Gruppen"
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Hinzuf&#252;gen mehrerer Gruppen von Einstellungen zur Anwendung in C# #
In einigen Fällen möchten Sie vielleicht mehrere Gruppen von Einstellungen in einer Anwendung vorsehen.  Wenn Sie beispielsweise eine Anwendung entwickeln, in der sich eine bestimmte Gruppe von Einstellungen häufig ändert, kann es von Vorteil sein, sie alle in einer einzelnen Datei zu speichern, die dann als Ganzes ausgetauscht wird, ohne dass die anderen Einstellungen betroffen sind.  Visual Studio ermöglicht es Ihnen, dem Projekt mehrere Gruppen von Einstellungen hinzuzufügen.  Auf zusätzliche Gruppen von Einstellungen kann über das Properties.Settings\-Objekt zugegriffen werden.  
  
### So fügen Sie der Anwendung eine zusätzliche Gruppe von Einstellungen hinzu  
  
1.  Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.  Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.  
  
2.  Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Einstellungsdatei** aus, geben Sie einen Dateinamen ein, und klicken Sie auf **Hinzufügen**, um der Projektmappe eine neue Einstellungsdatei hinzuzufügen.  
  
3.  Ziehen Sie im **Projektmappen\-Explorer** die neue Einstellungsdatei in den Ordner **Eigenschaften**.  Auf diese Weise machen Sie die neuen Einstellungen für den Code verfügbar.  
  
4.  In dieser Datei können Sie Einstellungen auf dieselbe Weise hinzufügen und verwenden wie in einer anderen Einstellungsdatei.  Sie können über das Properties.Settings\-Objekt auf diese Gruppe von Einstellungen zugreifen.  
  
## Siehe auch  
 [Verwenden von Anwendungseinstellungen und Benutzereinstellungen](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)   
 [Übersicht über Anwendungseinstellungen](../../../../docs/framework/winforms/advanced/application-settings-overview.md)