---
title: 'Vorgehensweise: Beibehalten von Benutzereinstellungen in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], persisting user settings
- persistence [Visual Basic], persisting user settings [Visual Basic]
- user settings [Visual Basic], persisting
ms.assetid: 0e5e6415-b6e2-4602-9be0-a65fa167d007
ms.openlocfilehash: dab285f175838fb71e4218cbafdd4f7593c9e786
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611292"
---
# <a name="how-to-persist-user-settings-in-visual-basic"></a>Vorgehensweise: Beibehalten von Benutzereinstellungen in Visual Basic
Sie können mit der `My.Settings.Save`-Methode Änderungen der Benutzereinstellungen beibehalten.  
  
 Anwendungen werden üblicherweise so entwickelt, dass sie Änderungen der Benutzereinstellungen beibehalten, wenn die Anwendung beendet wird. Dies liegt daran, dass das Speichern der Einstellungen mehrere Sekunden in Anspruch nehmen kann; dabei hängt die Länge des Speichervorgangs von mehreren Faktoren ab.  
  
 Weitere Informationen finden Sie unter [My.Settings-Objekt](../../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
> [!NOTE]
>  Obwohl Sie die Werte der Einstellungen für den Benutzerbereich zur Laufzeit ändern und speichern können, sind die Einstellungen für den Anwendungsbereich schreibgeschützt und können nicht programmgesteuert geändert werden. Sie können die Einstellungen für den Anwendungsbereich nur ändern, wenn Sie die Anwendung (über den **Projekt-Designer**) erstellen, oder indem Sie die Anwendungskonfigurationsdatei bearbeiten. Weitere Informationen finden Sie unter [Verwalten von Anwendungseinstellungen (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird der Wert der Benutzereinstellung `LastChanged` geändert, und diese Änderung wird mit einem Aufruf an die `My.Settings.Save`-Methode gespeichert.  
  
 [!code-vb[VbVbalrMyResources#5](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-persist-user-settings_1.vb)]  
  
 Damit dieses Beispiel funktioniert, muss Ihre Anwendung eine `LastChanged`-Benutzereinstellung vom Typ `Date` aufweisen. Weitere Informationen finden Sie unter [Verwalten von Anwendungseinstellungen (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="see-also"></a>Siehe auch
- [My.Settings-Objekt](../../../../visual-basic/language-reference/objects/my-settings-object.md)
- [Vorgehensweise: Lesen von Anwendungseinstellungen in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)
- [Vorgehensweise: Ändern von Benutzereinstellungen in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)
- [Vorgehensweise: Erstellen von Eigenschaftenrastern für Benutzereinstellungen in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [Verwalten von Anwendungseinstellungen (.NET)](/visualstudio/ide/managing-application-settings-dotnet)
