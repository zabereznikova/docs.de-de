---
title: "Gewusst wie: Schreiben von Benutzereinstellungen zur Laufzeit mit C# | Microsoft Docs"
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
  - "Anwendungseinstellungen [Windows Forms], Laufzeit"
  - "Anwendungseinstellungen [Windows Forms], Schreiben von Benutzereinstellungen"
ms.assetid: 9d061c7d-b33b-470f-a36d-edccb1d6f9a3
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Schreiben von Benutzereinstellungen zur Laufzeit mit C# #
Einstellungen im Gültigkeitsbereich der Anwendung sind schreibgeschützt und können nur zur Entwurfszeit oder durch Ändern der CONFIG\-Datei zwischen Anwendungssitzungen geändert werden.  Einstellungen im Gültigkeitsbereich des Benutzers können jedoch zur Laufzeit geschrieben werden, so als würden Sie einen beliebigen Eigenschaftswert ändern.  Der neue Wert wird für die Dauer der Anwendungssitzung beibehalten.  Sie können die Änderungen an den Einstellungen zwischen Anwendungssitzungen beibehalten, indem Sie die Save\-Methode aufrufen.  
  
### Gewusst wie: Schreiben und Beibehalten von Benutzereinstellungen zur Laufzeit mit C\#  
  
1.  Greifen Sie auf die Einstellung zu, und weisen Sie ihr einen neuen Wert zu, wie im folgenden Beispiel gezeigt:  
  
    ```  
    // C#  
    Properties.Settings.Default.myColor = Color.AliceBlue;  
    ```  
  
2.  Wenn Sie die Änderungen an den Einstellungen zwischen Anwendungssitzungen beibehalten möchten, rufen Sie die Save\-Methode auf, wie im folgenden Beispiel gezeigt:  
  
    ```  
    // C#  
    Properties.Settings.Default.Save();  
    ```  
  
     Benutzereinstellungen werden in einer Datei in einem Unterordner des lokalen ausgeblendeten Ordners für Anwendungsdaten des Benutzers gespeichert.  
  
## Siehe auch  
 [Verwenden von Anwendungseinstellungen und Benutzereinstellungen](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)   
 [Gewusst wie: Lesen von Einstellungen zur Laufzeit mit C\#](../../../../docs/framework/winforms/advanced/how-to-read-settings-at-run-time-with-csharp.md)   
 [Übersicht über Anwendungseinstellungen](../../../../docs/framework/winforms/advanced/application-settings-overview.md)