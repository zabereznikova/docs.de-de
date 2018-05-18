---
title: 'Gewusst wie: Lesen von Anwendungseinstellungen in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- reading application settings
- My.Settings object [Visual Basic], reading application settings
- application settings [Visual Basic], reading
ms.assetid: eb3428ef-115e-49a8-a878-e0613183fee0
ms.openlocfilehash: 3de6e59c2a69c430a0376ef36f8ce52e57f5f6f0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-read-application-settings-in-visual-basic"></a>Gewusst wie: Lesen von Anwendungseinstellungen in Visual Basic
Sie können eine Benutzereinstellung lesen, indem Sie auf die Einstellung der Eigenschaft im `My.Settings`-Objekt zugreifen.  
  
 Das `My.Settings`-Objekt macht jede Einstellung als Eigenschaft verfügbar. Der Eigenschaftsname ist identisch mit dem Einstellungsnamen, und der Eigenschaftentyp entspricht dem Typ der Einstellung. Der **Bereich** der Einstellung gibt an, ob die Eigenschaft schreibgeschützt ist; die Eigenschaft für den Bereich **Anwendung** ist schreibgeschützt, während die Eigenschaft für die Bereichseinstellung **Benutzer** über einen Lese-/Schreibzugriff verfügt. Weitere Informationen finden Sie unter [My.Settings-Objekt](../../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird der Wert der `Nickname`-Einstellung angezeigt.  
  
 [!code-vb[VbVbalrMyResources#14](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-read-application-settings_1.vb)]  
  
 Damit dieses Beispiel funktioniert, muss Ihre Anwendung eine `Nickname`-Einstellung vom Typ `String` aufweisen. Weitere Informationen finden Sie unter [Verwalten von Anwendungseinstellungen (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="see-also"></a>Siehe auch  
 [My.Settings-Objekt](../../../../visual-basic/language-reference/objects/my-settings-object.md)  
 [Vorgehensweise: Ändern von Benutzereinstellungen in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)  
 [Vorgehensweise: Beibehalten von Benutzereinstellungen in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)  
 [Vorgehensweise: Erstellen von Eigenschaftenrastern für Benutzereinstellungen in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)  
 [Verwalten von Anwendungseinstellungen (.NET)](/visualstudio/ide/managing-application-settings-dotnet)
