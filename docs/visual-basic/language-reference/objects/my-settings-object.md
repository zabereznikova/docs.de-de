---
title: My.Settings-Objekt
ms.date: 07/20/2015
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
ms.openlocfilehash: c905ff85c8e9729dd4d6068f0d34f729962bbb57
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84372400"
---
# <a name="mysettings-object"></a>My.Settings-Objekt
Stellt Eigenschaften und Methoden für den Zugriff auf die Einstellungen der Anwendung bereit.  
  
## <a name="remarks"></a>Bemerkungen  
 Das `My.Settings` -Objekt bietet Zugriff auf die Einstellungen der Anwendung und ermöglicht das dynamische Speichern und Abrufen von Eigenschafts Einstellungen und anderen Informationen für Ihre Anwendung. Weitere Informationen finden Sie unter [Verwalten von Anwendungseinstellungen (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="properties"></a>Eigenschaften  
 Die Eigenschaften des `My.Settings`-Objekts ermöglichen den Zugriff auf die Einstellungen Ihrer Anwendung. Verwenden Sie den **Einstellungs-Designer**, um Einstellungen hinzuzufügen oder zu entfernen.  
  
 Jede Einstellung hat einen **Namen**, einen **Typ**, einen **Bereich**und einen **Wert**, und diese Einstellungen bestimmen, wie die Eigenschaft für den Zugriff auf die einzelnen Einstellungen im Objekt angezeigt wird `My.Settings` :  
  
- **Name** bestimmt den Namen der Eigenschaft.  
  
- **Typ** bestimmt den Typ der Eigenschaft.  
  
- Der **Bereich** gibt an, ob die Eigenschaft schreibgeschützt ist. Wenn der Wert " **Application**" ist, ist die Eigenschaft schreibgeschützt. Wenn der Wert **User**ist, lautet die Eigenschaft mit Lese-/Schreibzugriff.  
  
- **Value** ist der Standardwert der Eigenschaft.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|---|---|  
|`Reload`|Lädt die Benutzereinstellungen aus den letzten gespeicherten Werten erneut.|  
|`Save`|Speichert die aktuellen Benutzereinstellungen.|  
  
 Das `My.Settings` -Objekt stellt auch erweiterte Eigenschaften und Methoden bereit, die von der-Klasse geerbt wurden <xref:System.Configuration.ApplicationSettingsBase> .  
  
## <a name="tasks"></a>Aufgaben  
 In der folgenden Tabelle sind Beispiele für Aufgaben aufgeführt, die das- `My.Settings` Objekt betreffen.  
  
|Beschreibung|Siehe|  
|---|---|  
|Anwendungs Einstellung lesen|[How to: Lesen von Anwendungseinstellungen in Visual Basic](../../developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|Ändern einer Benutzereinstellung|[How to: Ändern von Benutzereinstellungen in Visual Basic](../../developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|Beibehalten von Benutzereinstellungen|[How to: Beibehalten von Benutzereinstellungen in Visual Basic](../../developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|Erstellen eines Eigenschaften Rasters für Benutzereinstellungen|[How to: Erstellen von Eigenschaftenrastern für Benutzereinstellungen in Visual Basic](../../developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird der Wert der `Nickname`-Einstellung angezeigt.  
  
 [!code-vb[VbVbalrMyResources#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#14)]  
  
 Damit dieses Beispiel funktioniert, muss Ihre Anwendung eine `Nickname`-Einstellung vom Typ `String` aufweisen.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Configuration.ApplicationSettingsBase>
- [How to: Lesen von Anwendungseinstellungen in Visual Basic](../../developing-apps/programming/app-settings/how-to-read-application-settings.md)
- [How to: Ändern von Benutzereinstellungen in Visual Basic](../../developing-apps/programming/app-settings/how-to-change-user-settings.md)
- [How to: Beibehalten von Benutzereinstellungen in Visual Basic](../../developing-apps/programming/app-settings/how-to-persist-user-settings.md)
- [How to: Erstellen von Eigenschaftenrastern für Benutzereinstellungen in Visual Basic](../../developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [Verwalten von Anwendungseinstellungen (.NET)](/visualstudio/ide/managing-application-settings-dotnet)
