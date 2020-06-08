---
title: 'Vorgehensweise: Ändern von Benutzereinstellungen'
ms.date: 07/20/2015
helpviewer_keywords:
- user settings [Visual Basic], changing in Visual Basic
- user settings
- My.Settings object [Visual Basic], changing user settings
- examples [Visual Basic], changing user settings
ms.assetid: 41250181-c594-4854-9988-8183b9eb03cf
ms.openlocfilehash: c9b89459f9b443c3a447edce90fee3437bbf1b6a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410178"
---
# <a name="how-to-change-user-settings-in-visual-basic"></a>Vorgehensweise: Ändern von Benutzereinstellungen in Visual Basic

Sie können eine Benutzereinstellung ändern, indem Sie der Einstellung der Eigenschaft auf dem `My.Settings`-Objekt einen neuen Wert zuweisen.  
  
 Das `My.Settings`-Objekt macht jede Einstellung als Eigenschaft verfügbar. Der Eigenschaftenname ist identisch mit dem Einstellungsnamen, und der Eigenschaftentyp entspricht dem Typ der Einstellung. Der **Gültigkeitsbereich** einer Einstellung bestimmt, ob die Eigenschaft schreibgeschützt ist: Die Eigenschaft für eine Bereichseinstellung für die **Anwendung** ist schreibgeschützt, während die Eigenschaft für eine Bereichseinstellung für den **Benutzer** nicht schreibgeschützt ist. Weitere Informationen finden Sie unter [My.Settings-Objekt](../../../language-reference/objects/my-settings-object.md).  
  
> [!NOTE]
> Obwohl Sie die Werte der Einstellungen für den Benutzerbereich zur Laufzeit ändern und speichern können, sind die Einstellungen für den Anwendungsbereich schreibgeschützt und können nicht programmgesteuert geändert werden. Sie können die Einstellungen für den Anwendungsbereich nur ändern, wenn Sie die Anwendung mithilfe des **Projekt-Designers** erstellen, oder indem Sie die Anwendungskonfigurationsdatei bearbeiten. Weitere Informationen finden Sie unter [Verwalten von Anwendungseinstellungen (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="example"></a>Beispiel  

 In diesem Beispiel wird der Wert der `Nickname`-Benutzereinstellung geändert.  
  
 [!code-vb[VbVbalrMyResources#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#7)]  
  
 Damit dieses Beispiel funktioniert, muss Ihre Anwendung eine `Nickname`-Benutzereinstellung vom Typ `String` aufweisen.  
  
 Die Anwendung speichert die Benutzereinstellungen beim Herunterfahren der Anwendung. Um die Einstellungen sofort zu speichern, rufen Sie die `My.Settings.Save`-Methode auf. Weitere Informationen finden Sie unter [Vorgehensweise: Beibehalten von Benutzereinstellungen](how-to-persist-user-settings.md).  
  
## <a name="see-also"></a>Siehe auch

- [My.Settings-Objekt](../../../language-reference/objects/my-settings-object.md)
- [How to: Lesen von Anwendungseinstellungen in Visual Basic](how-to-read-application-settings.md)
- [How to: Beibehalten von Benutzereinstellungen in Visual Basic](how-to-persist-user-settings.md)
- [How to: Erstellen von Eigenschaftenrastern für Benutzereinstellungen in Visual Basic](how-to-create-property-grids-for-user-settings.md)
- [Verwalten von Anwendungseinstellungen (.NET)](/visualstudio/ide/managing-application-settings-dotnet)
