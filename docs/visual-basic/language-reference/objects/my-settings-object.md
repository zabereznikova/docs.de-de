---
title: My.Settings-Objekt
ms.date: 07/20/2015
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
ms.openlocfilehash: 9560a51332ea596d4cf2228f1e07c158a0457ece
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350360"
---
# <a name="mysettings-object"></a>My.Settings-Objekt
Provides properties and methods for accessing the application's settings.  
  
## <a name="remarks"></a>Hinweise  
 The `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application. Weitere Informationen finden Sie unter [Verwalten von Anwendungseinstellungen (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="properties"></a>Eigenschaften  
 Die Eigenschaften des `My.Settings`-Objekts ermöglichen den Zugriff auf die Einstellungen Ihrer Anwendung. To add or remove settings, use the **Settings Designer**.  
  
 Each setting has a **Name**, **Type**, **Scope**, and **Value**, and these settings determine how the property to access each setting appears in the `My.Settings` object:  
  
- **Name** determines the name of the property.  
  
- **Type** determines the type of the property.  
  
- **Scope** indicates if the property is read-only. If the value is **Application**, the property is read-only; if the value is **User**, the property is read-write.  
  
- **Value** is the default value of the property.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|---|---|  
|`Reload`|Reloads the user settings from the last saved values.|  
|`Save`|Saves the current user settings.|  
  
 The `My.Settings` object also provides advanced properties and methods, inherited from the <xref:System.Configuration.ApplicationSettingsBase> class.  
  
## <a name="tasks"></a>Aufgaben  
 The following table lists examples of tasks involving the `My.Settings` object.  
  
|Beschreibung|Siehe|  
|---|---|  
|Read an application setting|[Vorgehensweise: Lesen von Anwendungseinstellungen in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|Change a user setting|[Vorgehensweise: Ändern von Benutzereinstellungen in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|Persist user settings|[Vorgehensweise: Beibehalten von Benutzereinstellungen in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|Create a property grid for user settings|[Vorgehensweise: Erstellen von Eigenschaftenrastern für Benutzereinstellungen in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird der Wert der `Nickname`-Einstellung angezeigt.  
  
 [!code-vb[VbVbalrMyResources#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#14)]  
  
 Damit dieses Beispiel funktioniert, muss Ihre Anwendung eine `Nickname`-Einstellung vom Typ `String` aufweisen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Configuration.ApplicationSettingsBase>
- [Vorgehensweise: Lesen von Anwendungseinstellungen in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)
- [Vorgehensweise: Ändern von Benutzereinstellungen in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)
- [Vorgehensweise: Beibehalten von Benutzereinstellungen in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)
- [Vorgehensweise: Erstellen von Eigenschaftenrastern für Benutzereinstellungen in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [Verwalten von Anwendungseinstellungen (.NET)](/visualstudio/ide/managing-application-settings-dotnet)
