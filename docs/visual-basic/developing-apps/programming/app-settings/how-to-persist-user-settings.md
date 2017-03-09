---
title: "How to: Persist User Settings in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Settings object, persisting user settings"
  - "persistence, persisting user settings [Visual Basic]"
  - "user settings, persisting"
ms.assetid: 0e5e6415-b6e2-4602-9be0-a65fa167d007
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# How to: Persist User Settings in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Mit der `My.Settings.Save`\-Methode können Sie Änderungen an den Benutzereinstellungen beibehalten.  
  
 In der Regel werden Anwendungen so entworfen, dass Änderungen an den Benutzereinstellungen erst beim Schließen der Anwendung gespeichert werden.  Dies liegt daran, dass das Speichern der Einstellungen in Abhängigkeit von mehreren Faktoren mehrere Sekunden dauern kann.  
  
 Weitere Informationen finden Sie unter [My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
> [!NOTE]
>  Obwohl Sie die Werte benutzerbezogener Einstellungen zur Laufzeit ändern und speichern können, sind anwendungsbezogene Einstellungen schreibgeschützt und können nicht programmgesteuert geändert werden.  Sie können anwendungsbezogene Einstellungen beim Erstellen der Anwendung über den **Projekt\-Designer** oder durch Bearbeiten der Konfigurationsdatei der Anwendung ändern.  Weitere Informationen finden Sie unter [Verwalten von Anwendungseinstellungen \(.NET\)](/visual-studio/ide/managing-application-settings-dotnet).  
  
## Beispiel  
 In diesem Beispiel wird die `LastChanged`\-Benutzereinstellung geändert und diese Änderung durch Aufrufen der `My.Settings.Save`\-Methode gespeichert.  
  
 [!code-vb[VbVbalrMyResources#5](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/visualbasic/VbVbalrMyResources2/Form1.vb#5)]  
  
 Für dieses Beispiel muss die Anwendung über eine `LastChanged`\-Benutzereinstellung vom Typ `Date` verfügen.  Weitere Informationen finden Sie unter [Verwalten von Anwendungseinstellungen \(.NET\)](/visual-studio/ide/managing-application-settings-dotnet).  
  
## Siehe auch  
 [My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md)   
 [How to: Read Application Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)   
 [How to: Change User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)   
 [How to: Create Property Grids for User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)   
 [Verwalten von Anwendungseinstellungen \(.NET\)](/visual-studio/ide/managing-application-settings-dotnet)