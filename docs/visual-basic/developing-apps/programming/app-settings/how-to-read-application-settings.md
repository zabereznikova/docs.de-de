---
title: 'Vorgehensweise: Lesen von Anwendungseinstellungen in Visual Basic| Microsoft-Dokumentation'
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
- reading application settings
- My.Settings object, reading application settings
- application settings, reading
ms.assetid: eb3428ef-115e-49a8-a878-e0613183fee0
caps.latest.revision: 12
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 39c98f4fa461d037f5a0c551b5c1ea089f25451d
ms.contentlocale: de-de
ms.lasthandoff: 05/22/2017

---
# <a name="how-to-read-application-settings-in-visual-basic"></a>Gewusst wie: Lesen von Anwendungseinstellungen in Visual Basic
Sie können eine Benutzereinstellung lesen, indem Sie auf die Einstellung der Eigenschaft im `My.Settings`-Objekt zugreifen.  
  
 Das `My.Settings`-Objekt macht jede Einstellung als Eigenschaft verfügbar. Der Eigenschaftsname ist identisch mit dem Einstellungsnamen, und der Eigenschaftentyp entspricht dem Typ der Einstellung. Der **Bereich** der Einstellung gibt an, ob die Eigenschaft schreibgeschützt ist; die Eigenschaft für den Bereich **Anwendung** ist schreibgeschützt, während die Eigenschaft für die Bereichseinstellung **Benutzer** über einen Lese-/Schreibzugriff verfügt. Weitere Informationen finden Sie unter [My.Settings-Objekt](../../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird der Wert der `Nickname`-Einstellung angezeigt.  
  
 [!code-vb[VbVbalrMyResources#14](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-read-application-settings_1.vb)]  
  
 Damit dieses Beispiel funktioniert, muss Ihre Anwendung eine `Nickname`-Einstellung vom Typ `String` aufweisen. Weitere Informationen finden Sie unter [Verwalten von Anwendungseinstellungen (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="see-also"></a>Siehe auch  
 [My.Settings-Objekt](../../../../visual-basic/language-reference/objects/my-settings-object.md)   
 [Vorgehensweise: Ändern von Benutzereinstellungen in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)   
 [Vorgehensweise: Beibehalten von Benutzereinstellungen in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)   
 [Vorgehensweise: Erstellen von Eigenschaftenrastern für Benutzereinstellungen in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)   
 [Verwalten von Anwendungseinstellungen (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet)
