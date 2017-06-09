---
title: "Gewusst wie: Lesen von Einstellungen zur Laufzeit mit C# | Microsoft Docs"
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
  - "Anwendungseinstellungen [Windows Forms], Lesen"
  - "Anwendungseinstellungen [Windows Forms], Laufzeit"
ms.assetid: dbe8bf09-5e1c-49da-9192-154033d7240b
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Lesen von Einstellungen zur Laufzeit mit C# #
Über das Properties\-Objekt können Sie zur Laufzeit anwendungsspezifische und benutzerspezifische Einstellungen auslesen.  Das Properties\-Objekt macht über den Properties.Settings.Default\-Member alle Standardeinstellungen für des Projekt verfügbar.  
  
### So lesen Sie Einstellungen zur Laufzeit mit C\#  
  
-   Greifen Sie über den Properties.Settings.Default\-Member auf die geeignete Einstellung zu.  Im folgenden Beispiel wird gezeigt, wie Sie einer BackColor\-Eigenschaft eine Einstellung mit Namen `myColor` zuweisen.  Dies setzt voraus, dass Sie zuvor eine Einstellungsdatei erstellt haben, die eine Einstellung mit Namen `myColor` vom Typ `System.Drawing.Color` enthält.  Informationen zum Erstellen einer neuen Einstellungsdatei finden Sie unter [Gewusst wie: Erstellen einer neuen Einstellung zur Entwurfszeit](../../../../docs/framework/winforms/advanced/how-to-create-a-new-setting-at-design-time.md).  
  
    ```  
    // C#  
    this.BackColor = Properties.Settings.Default.myColor;  
    ```  
  
## Siehe auch  
 [Verwenden von Anwendungseinstellungen und Benutzereinstellungen](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)   
 [Gewusst wie: Schreiben von Benutzereinstellungen zur Laufzeit mit C\#](../../../../docs/framework/winforms/advanced/how-to-write-user-settings-at-run-time-with-csharp.md)   
 [Übersicht über Anwendungseinstellungen](../../../../docs/framework/winforms/advanced/application-settings-overview.md)