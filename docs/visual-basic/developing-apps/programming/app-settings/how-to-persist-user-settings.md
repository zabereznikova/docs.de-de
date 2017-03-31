---
title: 'Vorgehensweise: Beibehalten von Benutzereinstellungen in Visual Basic | Microsoft-Dokumentation'
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
- My.Settings object, persisting user settings
- persistence, persisting user settings [Visual Basic]
- user settings, persisting
ms.assetid: 0e5e6415-b6e2-4602-9be0-a65fa167d007
caps.latest.revision: 15
author: stevehoag
ms.author: shoag
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: edb813500202b313b7e306ab8f34bd1d1ca1391c
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-persist-user-settings-in-visual-basic"></a>Gewusst wie: Beibehalten von Benutzereinstellungen in Visual Basic
Sie können mit der `My.Settings.Save`-Methode Änderungen der Benutzereinstellungen beibehalten.  
  
 Anwendungen werden üblicherweise so entwickelt, dass sie Änderungen der Benutzereinstellungen beibehalten, wenn die Anwendung beendet wird. Dies liegt daran, dass das Speichern der Einstellungen mehrere Sekunden in Anspruch nehmen kann; dabei hängt die Länge des Speichervorgangs von mehreren Faktoren ab.  
  
 Weitere Informationen finden Sie unter [My.Settings-Objekt](../../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
> [!NOTE]
>  Obwohl Sie die Werte der Einstellungen für den Benutzerbereich zur Laufzeit ändern und speichern können, sind die Einstellungen für den Anwendungsbereich schreibgeschützt und können nicht programmgesteuert geändert werden. Sie können die Einstellungen für den Anwendungsbereich nur ändern, wenn Sie die Anwendung (über den **Projekt-Designer**) erstellen, oder indem Sie die Anwendungskonfigurationsdatei bearbeiten. Weitere Informationen finden Sie unter [Verwalten von Anwendungseinstellungen (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird der Wert der Benutzereinstellung `LastChanged` geändert, und diese Änderung wird mit einem Aufruf an die `My.Settings.Save`-Methode gespeichert.  
  
 [!code-vb[VbVbalrMyResources#5](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-persist-user-settings_1.vb)]  
  
 Damit dieses Beispiel funktioniert, muss Ihre Anwendung eine `LastChanged`-Benutzereinstellung vom Typ `Date` aufweisen. Weitere Informationen finden Sie unter [Verwalten von Anwendungseinstellungen (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="see-also"></a>Siehe auch  
 [My.Settings-Objekt](../../../../visual-basic/language-reference/objects/my-settings-object.md)   
 [Vorgehensweise: Lesen von Anwendungseinstellungen in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)   
 [Vorgehensweise: Ändern von Benutzereinstellungen in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)   
 [Vorgehensweise: Erstellen von Eigenschaftenrastern für Benutzereinstellungen in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)   
 [Verwalten von Anwendungseinstellungen (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet)
