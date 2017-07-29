---
title: "Gewusst wie: Erstellen von Eigenschaftenrastern für Benutzereinstellungen in Visual Basic"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- My.Settings object, creating property grids for user settings
- user settings, creating property grids
- property grids, creating for user settings
- property grids
ms.assetid: b0bc737e-50d1-43d1-a6df-268db6e6f91c
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c21b458f9c28f4d25e5b0d8099b9a5255f31ac52
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-property-grids-for-user-settings-in-visual-basic"></a>Gewusst wie: Erstellen von Eigenschaftenrastern für Benutzereinstellungen in Visual Basic
Sie können ein Eigenschaftenraster für Benutzereinstellungen erstellen, indem Sie ein <xref:System.Windows.Forms.PropertyGrid>-Steuerelement mit den Benutzereinstellungseigenschaften des `My.Settings`-Objekts auffüllen.  
  
> [!NOTE]
>  Damit dieses Beispiel funktioniert, muss Ihre Anwendung über konfigurierte Benutzereinstellungen verfügen. Weitere Informationen finden Sie unter [Verwalten von Anwendungseinstellungen (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
 Das `My.Settings`-Objekt macht jede Einstellung als Eigenschaft verfügbar. Der Eigenschaftenname ist identisch mit dem Einstellungsnamen, und der Eigenschaftentyp entspricht dem Typ der Einstellung. Der **Bereich** der Einstellung gibt an, ob die Eigenschaft schreibgeschützt ist; die Eigenschaft für den Bereich **Anwendung** ist schreibgeschützt, während die Eigenschaft für die Bereichseinstellung **Benutzer** über einen Lese-/Schreibzugriff verfügt. Weitere Informationen finden Sie unter [My.Settings-Objekt](../../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
> [!NOTE]
>  Sie können die Werte der Einstellungen für den Anwendungsbereich zur Laufzeit nicht ändern oder speichern. Einstellungen für den Anwendungsbereich können nur geändert werden, wenn Sie die Anwendung (über den **Projekt-Designer**) erstellen, oder indem Sie die Anwendungskonfigurationsdatei bearbeiten. Weitere Informationen finden Sie unter [Verwalten von Anwendungseinstellungen (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
 Dieses Beispiel verwendet ein <xref:System.Windows.Forms.PropertyGrid>-Steuerelement, um auf die Benutzereinstellungseigenschaften des `My.Settings`-Objekts zuzugreifen. In der Standardeinstellung zeigt <xref:System.Windows.Forms.PropertyGrid> alle Eigenschaften des `My.Settings`-Objekts an. Die Eigenschaften von Benutzereinstellungen müssen jedoch das <xref:System.Configuration.UserScopedSettingAttribute>-Attribut aufweisen. In diesem Beispiel wird die <xref:System.Windows.Forms.PropertyGrid.BrowsableAttributes%2A>-Eigenschaft von <xref:System.Windows.Forms.PropertyGrid> auf <xref:System.Configuration.UserScopedSettingAttribute> festgelegt, um nur die Eigenschaften von Benutzereinstellungen anzuzeigen.  
  
### <a name="to-add-a-user-setting-property-grid"></a>So fügen Sie ein Eigenschaftenraster für Benutzereinstellungen hinzu  
  
1.  Fügen Sie das **PropertyGrid**-Steuerelement aus der **Toolbox** der Entwurfsoberfläche für Ihre Anwendung hinzu, von der davon ausgegangen wird, dass sie `Form1` ist.  
  
     Der Standardname für das Steuerelement des Eigenschaftenrasters ist `PropertyGrid1`.  
  
2.  Doppelklicken Sie auf die Entwurfsoberfläche für `Form1`, um den Code für den Ereignishandler zum Laden von Formularen zu öffnen.  
  
3.  Legen Sie das `My.Settings`-Objekt als ausgewähltes Objekt für das Eigenschaftenraster fest.  
  
     [!code-vb[VbVbalrMyResources#11](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-create-property-grids-for-user-settings_1.vb)]  
  
4.  Konfigurieren Sie das Eigenschaftenraster so, dass nur die Benutzereinstellungen angezeigt werden.  
  
     [!code-vb[VbVbalrMyResources#12](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-create-property-grids-for-user-settings_2.vb)]  
  
    > [!NOTE]
    >  Um nur die Einstellungen des Anwendungsbereichs anzuzeigen, verwenden Sie das <xref:System.Configuration.ApplicationScopedSettingAttribute>-Attribut anstelle von <xref:System.Configuration.UserScopedSettingAttribute>.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die Anwendung speichert die Benutzereinstellungen beim Herunterfahren der Anwendung. Um die Einstellungen sofort zu speichern, rufen Sie die `My.Settings.Save`-Methode auf. Weitere Informationen finden Sie unter [Vorgehensweise: Beibehalten von Benutzereinstellungen in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md).  
  
## <a name="see-also"></a>Siehe auch  
 [My.Settings-Objekt](../../../../visual-basic/language-reference/objects/my-settings-object.md)   
 [Vorgehensweise: Lesen von Anwendungseinstellungen in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)   
 [Vorgehensweise: Ändern von Benutzereinstellungen in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)   
 [Vorgehensweise: Beibehalten von Benutzereinstellungen in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)   
 [Verwalten von Anwendungseinstellungen (.NET)](/visualstudio/ide/managing-application-settings-dotnet)

