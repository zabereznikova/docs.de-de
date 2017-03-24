---
title: "How to: Create Property Grids for User Settings in Visual Basic | Microsoft Docs"
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
  - "My.Settings object, creating property grids for user settings"
  - "user settings, creating property grids"
  - "property grids, creating for user settings"
  - "property grids"
ms.assetid: b0bc737e-50d1-43d1-a6df-268db6e6f91c
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# How to: Create Property Grids for User Settings in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Sie können ein Eigenschaftenraster für Benutzereinstellungen erstellen, indem Sie ein <xref:System.Windows.Forms.PropertyGrid>\-Steuerelement mit den Benutzereinstellungseigenschaften des `My.Settings`\-Objekts auffüllen.  
  
> [!NOTE]
>  Damit dieses Beispiel ausgeführt werden kann, muss die Anwendung über konfigurierte Benutzereinstellungen verfügen.  Weitere Informationen finden Sie unter [Verwalten von Anwendungseinstellungen \(.NET\)](/visual-studio/ide/managing-application-settings-dotnet).  
  
 Das `My.Settings`\-Objekt macht alle Einstellungen als Eigenschaft verfügbar.  Der Eigenschaftenname entspricht dem Namen der Einstellung, und der Eigenschaftentyp entspricht dem Typ der Einstellung.  Der **Bereich** einer Einstellung bestimmt, ob die zugehörige Eigenschaft schreibgeschützt ist: Die Eigenschaft für eine Einstellung mit dem Bereich **Anwendung** ist schreibgeschützt, während die Eigenschaft für eine Einstellung mit dem Bereich **Benutzer** Lese\-\/Schreibzugriff ermöglicht.  Weitere Informationen finden Sie unter [My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
> [!NOTE]
>  Werte von Einstellungen, die für eine gesamte Anwendung gültig sind, können zur Laufzeit nicht geändert oder gespeichert werden.  Einstellungen, die für eine gesamte Anwendung gültig sind, können beim Erstellen der Anwendung im **Projekt\-Designer**\) oder später durch Bearbeiten der Anwendungskonfigurationsdatei geändert werden.  Weitere Informationen finden Sie unter [Verwalten von Anwendungseinstellungen \(.NET\)](/visual-studio/ide/managing-application-settings-dotnet).  
  
 In diesem Beispiel wird ein <xref:System.Windows.Forms.PropertyGrid>\-Steuerelement verwendet, um auf die Benutzereinstellungseigenschaften des `My.Settings`\-Objekts zuzugreifen.  In der Standardeinstellung zeigt das <xref:System.Windows.Forms.PropertyGrid> alle Eigenschaften des `My.Settings`\-Objekts an.  In den Benutzereinstellungseigenschaften ist jedoch auch das <xref:System.Configuration.UserScopedSettingAttribute>\-Attribut verfügbar.  In diesem Beispiel wird die <xref:System.Windows.Forms.PropertyGrid.BrowsableAttributes%2A>\-Eigenschaft von <xref:System.Windows.Forms.PropertyGrid> auf <xref:System.Configuration.UserScopedSettingAttribute> festgelegt, um ausschließlich die Benutzereinstellungseigenschaften anzuzeigen.  
  
### So fügen Sie ein Eigenschaftenraster für Benutzereinstellungen hinzu  
  
1.  Fügen Sie der Entwurfsoberfläche der Anwendung \(hier:  `Form1`\) das **PropertyGrid**\-Steuerelement aus der **Toolbox** hinzu.  
  
     Der Standardname des Steuerelements für das Eigenschaftenraster ist `PropertyGrid1`.  
  
2.  Doppelklicken Sie auf die Entwurfsoberfläche für `Form1`, um den Code für den Ereignishandler zu öffnen, der dem Laden des Formulars zugeordnet ist.  
  
3.  Legen Sie das `My.Settings`\-Objekt als ausgewähltes Objekt für das Eigenschaftenraster fest.  
  
     [!code-vb[VbVbalrMyResources#11](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-create-property-grids-for-user-settings_1.vb)]  
  
4.  Konfigurieren Sie das Eigenschaftenraster so, dass nur die Benutzereinstellungen angezeigt werden.  
  
     [!code-vb[VbVbalrMyResources#12](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-create-property-grids-for-user-settings_2.vb)]  
  
    > [!NOTE]
    >  Um nur die Einstellungen anzuzeigen, verwenden Sie das \- Attribut anstelle <xref:System.Configuration.ApplicationScopedSettingAttribute><xref:System.Configuration.UserScopedSettingAttribute>.  
  
## Robuste Programmierung  
 Die Benutzereinstellungen werden beim Beenden der Anwendung gespeichert.  Wenn Sie die Einstellungen sofort speichern möchten, rufen Sie die `My.Settings.Save`\-Methode auf.  Weitere Informationen finden Sie unter [How to: Persist User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md).  
  
## Siehe auch  
 [My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md)   
 [How to: Read Application Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)   
 [How to: Change User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)   
 [How to: Persist User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)   
 [Verwalten von Anwendungseinstellungen \(.NET\)](/visual-studio/ide/managing-application-settings-dotnet)