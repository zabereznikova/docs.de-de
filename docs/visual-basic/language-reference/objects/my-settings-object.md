---
title: My.Settings-Objekt (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
ms.openlocfilehash: 83bba35340a917b649369fc1eb7a01a2bc6a2188
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43442771"
---
# <a name="mysettings-object"></a>My.Settings-Objekt
Stellt Eigenschaften und Methoden für den Zugriff auf die Einstellungen der Anwendung.  
  
## <a name="remarks"></a>Hinweise  
 Die `My.Settings` Objekt bietet Zugriff auf die Einstellungen der Anwendung und ermöglicht es Ihnen, dynamisch speichern und Abrufen von Eigenschaften und andere Informationen für Ihre Anwendung. Weitere Informationen finden Sie unter [Verwalten von Anwendungseinstellungen (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="properties"></a>Eigenschaften  
 Die Eigenschaften des `My.Settings`-Objekts ermöglichen den Zugriff auf die Einstellungen Ihrer Anwendung. Verwenden Sie zum Hinzufügen oder entfernen Sie die Einstellungen, die **Einstellungs-Designer**.  
  
 Jede Einstellung eine **Namen**, **Typ**, **Bereich**, und **Wert**, und diese Einstellungen bestimmen, wie die Eigenschaft auf jede Einstellung wird in der `My.Settings` Objekt:  
  
-   **Namen** bestimmt den Namen der Eigenschaft.  
  
-   **Typ** bestimmt den Typ der Eigenschaft.  
  
-   **Bereich** gibt an, ob die Eigenschaft schreibgeschützt ist. Wenn der Wert ist **Anwendung**, die Eigenschaft schreibgeschützt ist; wenn der Wert ist **Benutzer**, die Eigenschaft ist schreibgeschützt.  
  
-   **Wert** ist der Standardwert der Eigenschaft.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|---|---|  
|`Reload`|Lädt die benutzereinstellungen, über die zuletzt gespeicherten Werte.|  
|`Save`|Speichert die aktuellen benutzereinstellungen.|  
  
 Die `My.Settings` -Objekt bietet auch erweiterte Eigenschaften und Methoden, geerbt von der <xref:System.Configuration.ApplicationSettingsBase> Klasse.  
  
## <a name="tasks"></a>Aufgaben  
 Die folgende Tabelle enthält Beispiele für Aufgaben im Zusammenhang mit der `My.Settings` Objekt.  
  
|Beschreibung|Siehe|  
|---|---|  
|Lesen Sie eine anwendungseinstellung|[Vorgehensweise: Lesen von Anwendungseinstellungen in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|Eine benutzereinstellung ändern|[Vorgehensweise: Ändern von Benutzereinstellungen in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|Beibehalten von benutzereinstellungen|[Vorgehensweise: Beibehalten von Benutzereinstellungen in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|Erstellen Sie ein Eigenschaftenraster für benutzereinstellungen|[Vorgehensweise: Erstellen von Eigenschaftenrastern für Benutzereinstellungen in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
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
