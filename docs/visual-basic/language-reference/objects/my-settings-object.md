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
Stellt Eigenschaften und Methoden für den Zugriff auf die Einstellungen der Anwendung bereit.  
  
## <a name="remarks"></a>Hinweise  
 Das `My.Settings`-Objekt ermöglicht den Zugriff auf die Einstellungen der Anwendung und ermöglicht das dynamische Speichern und Abrufen von Eigenschafts Einstellungen und anderen Informationen für Ihre Anwendung. Weitere Informationen finden Sie unter [Verwalten von Anwendungseinstellungen (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="properties"></a>Eigenschaften  
 Die Eigenschaften des `My.Settings`-Objekts ermöglichen den Zugriff auf die Einstellungen Ihrer Anwendung. Verwenden Sie den **Einstellungs-Designer**, um Einstellungen hinzuzufügen oder zu entfernen.  
  
 Jede Einstellung hat einen **Namen**, einen **Typ**, einen **Bereich**und einen **Wert**, und diese Einstellungen bestimmen, wie die Eigenschaft für den Zugriff auf die einzelnen Einstellungen im `My.Settings` Objekt angezeigt wird:  
  
- **Name** bestimmt den Namen der Eigenschaft.  
  
- **Typ** bestimmt den Typ der Eigenschaft.  
  
- Der **Bereich** gibt an, ob die Eigenschaft schreibgeschützt ist. Wenn der Wert " **Application**" ist, ist die Eigenschaft schreibgeschützt. Wenn der Wert **User**ist, lautet die Eigenschaft mit Lese-/Schreibzugriff.  
  
- **Value** ist der Standardwert der Eigenschaft.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|---|---|  
|`Reload`|Lädt die Benutzereinstellungen aus den letzten gespeicherten Werten erneut.|  
|`Save`|Speichert die aktuellen Benutzereinstellungen.|  
  
 Das `My.Settings`-Objekt stellt auch erweiterte Eigenschaften und Methoden bereit, die von der <xref:System.Configuration.ApplicationSettingsBase>-Klasse geerbt wurden.  
  
## <a name="tasks"></a>Aufgaben  
 In der folgenden Tabelle sind Beispiele für Aufgaben im Zusammenhang mit dem `My.Settings` Objekt aufgeführt.  
  
|Zweck|Informationen finden Sie unter .|  
|---|---|  
|Anwendungs Einstellung lesen|[Vorgehensweise: Lesen von Anwendungseinstellungen in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|Ändern einer Benutzereinstellung|[Vorgehensweise: Ändern von Benutzereinstellungen in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|Beibehalten von Benutzereinstellungen|[Vorgehensweise: Beibehalten von Benutzereinstellungen in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|Erstellen eines Eigenschaften Rasters für Benutzereinstellungen|[Vorgehensweise: Erstellen von Eigenschaftenrastern für Benutzereinstellungen in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
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
