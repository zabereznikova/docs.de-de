---
title: My.Settings-Objekt
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
helpviewer_keywords: My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2f744460f8ea6c6c7f5c8c5e1658bd357e910def
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="mysettings-object"></a>My.Settings-Objekt
Stellt Eigenschaften und Methoden für den Zugriff auf die Einstellungen der Anwendung.  
  
## <a name="remarks"></a>Hinweise  
 Die `My.Settings` Objekt ermöglicht den Zugriff auf die Einstellungen der Anwendung, und lassen sich dynamisch speichern und Abrufen von Einstellungen und andere Informationen für Ihre Anwendung. Weitere Informationen finden Sie unter [Verwalten von Anwendungseinstellungen (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="properties"></a>Eigenschaften  
 Die Eigenschaften des `My.Settings`-Objekts ermöglichen den Zugriff auf die Einstellungen Ihrer Anwendung. Verwenden Sie zum Hinzufügen oder entfernen Sie die Einstellungen, die **Einstellungs-Designer**.  
  
 Jede Einstellung hat eine **Namen**, **Typ**, **Bereich**, und **Wert**, und diese Einstellungen bestimmen wie die einzelnen Einstellungen aufzurufende Eigenschaft wird angezeigt, der `My.Settings` Objekt:  
  
-   **Namen** bestimmt den Namen der Eigenschaft.  
  
-   **Typ** bestimmt den Typ der Eigenschaft.  
  
-   **Bereich** gibt an, ob die Eigenschaft schreibgeschützt ist. Wenn der Wert **Anwendung**, die Eigenschaft ist schreibgeschützt; Wenn der Wert **Benutzer**, die Eigenschaft ist Lese-/ Schreibzugriff.  
  
-   **Wert** ist der Standardwert der Eigenschaft.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|---|---|  
|`Reload`|Lädt die benutzereinstellungen aus dem zuletzt gespeicherten Werte.|  
|`Save`|Speichert den aktuellen Einstellungen des Benutzers an.|  
  
 Die `My.Settings` Objekt stellt auch erweiterte Eigenschaften und Methoden, geerbt von der <xref:System.Configuration.ApplicationSettingsBase> Klasse.  
  
## <a name="tasks"></a>Aufgaben  
 Die folgende Tabelle enthält Beispiele für Aufgaben im Zusammenhang mit der `My.Settings` Objekt.  
  
|Beschreibung|Siehe|  
|---|---|  
|Eine anwendungseinstellung lesen|[Vorgehensweise: Lesen von Anwendungseinstellungen in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|Ändern einer benutzereinstellung|[Vorgehensweise: Ändern von Benutzereinstellungen in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|Beibehalten von benutzereinstellungen|[Vorgehensweise: Beibehalten von Benutzereinstellungen in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|Erstellen Sie eine Eigenschaftenraster für benutzereinstellungen|[Vorgehensweise: Erstellen von Eigenschaftenrastern für Benutzereinstellungen in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird der Wert der `Nickname`-Einstellung angezeigt.  
  
 [!code-vb[VbVbalrMyResources#14](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-settings-object_1.vb)]  
  
 Damit dieses Beispiel funktioniert, muss Ihre Anwendung eine `Nickname`-Einstellung vom Typ `String` aufweisen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Configuration.ApplicationSettingsBase>  
 [Vorgehensweise: Lesen von Anwendungseinstellungen in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)  
 [Vorgehensweise: Ändern von Benutzereinstellungen in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)  
 [Vorgehensweise: Beibehalten von Benutzereinstellungen in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)  
 [Vorgehensweise: Erstellen von Eigenschaftenrastern für Benutzereinstellungen in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)  
 [Verwalten von Anwendungseinstellungen (.NET)](/visualstudio/ide/managing-application-settings-dotnet)
