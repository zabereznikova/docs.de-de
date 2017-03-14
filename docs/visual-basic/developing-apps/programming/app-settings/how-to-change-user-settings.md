---
title: "How to: Change User Settings in Visual Basic | Microsoft Docs"
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
  - "user settings, changing in Visual Basic"
  - "user settings"
  - "My.Settings object, changing user settings"
  - "examples [Visual Basic], changing user settings"
ms.assetid: 41250181-c594-4854-9988-8183b9eb03cf
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# How to: Change User Settings in Visual Basic
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Sie können Benutzereinstellungen ändern, indem Sie der zugehörigen Eigenschaft für die Einstellung im `My.Settings`\-Objekt einen neuen Wert zuweisen.  
  
 Das `My.Settings`\-Objekt macht alle Einstellungen als Eigenschaft verfügbar.  Der Eigenschaftenname entspricht dem Namen der Einstellung, und der Eigenschaftentyp entspricht dem Typ der Einstellung.  Der **Bereich** einer Einstellung bestimmt, ob die zugehörige Eigenschaft schreibgeschützt ist: Die Eigenschaft für eine Einstellung mit dem Bereich **Anwendung** ist schreibgeschützt, während die Eigenschaft für eine Einstellung mit dem Bereich **Benutzer** Lese\-\/Schreibzugriff ermöglicht.  Weitere Informationen finden Sie unter [My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
> [!NOTE]
>  Obwohl Sie die Werte benutzerbezogener Einstellungen zur Laufzeit ändern und speichern können, sind anwendungsbezogene Einstellungen schreibgeschützt und können nicht programmgesteuert geändert werden.  Sie können anwendungsbezogene Einstellungen beim Erstellen der Anwendung über den **Projekt\-Designer** oder durch Bearbeiten der Konfigurationsdatei der Anwendung ändern.  Weitere Informationen finden Sie unter [Verwalten von Anwendungseinstellungen \(.NET\)](/visual-studio/ide/managing-application-settings-dotnet).  
  
## Beispiel  
 Im nachfolgenden Beispiel wird der Wert der Benutzereinstellung `Nickname` geändert.  
  
 [!code-vb[VbVbalrMyResources#7](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-change-user-settings_1.vb)]  
  
 Für dieses Beispiel muss die Anwendung über eine `Nickname`\-Benutzereinstellung vom Typ `String` verfügen.  
  
 Die Benutzereinstellungen werden beim Beenden der Anwendung gespeichert.  Wenn Sie die Einstellungen sofort speichern möchten, rufen Sie die `My.Settings.Save`\-Methode auf.  Weitere Informationen finden Sie unter [How to: Persist User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md).  
  
## Siehe auch  
 [My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md)   
 [How to: Read Application Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)   
 [How to: Persist User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)   
 [How to: Create Property Grids for User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)   
 [Verwalten von Anwendungseinstellungen \(.NET\)](/visual-studio/ide/managing-application-settings-dotnet)