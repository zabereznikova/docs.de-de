---
title: 'Vorgehensweise: Fügen Sie mehrerer Gruppen von Einstellungen zur Anwendung hinzuC#'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], multiple sets
- application settings [Windows Forms], C#
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
ms.openlocfilehash: 43402d8a1b0b1ca26e656be1424a5fa341ac4728
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57719649"
---
# <a name="how-to-add-multiple-sets-of-settings-to-your-application-in-c"></a>Vorgehensweise: Fügen Sie mehrerer Gruppen von Einstellungen zur Anwendung in C hinzu\#
In einigen Fällen empfiehlt es sich um mehrere Gruppen von Einstellungen in einer Anwendung zu erhalten. Z. B. Wenn Sie eine Anwendung entwickeln, muss eine bestimmte Gruppe von Einstellungen häufig ändern, kann es sein es ratsam, alle in einer einzelnen Datei trennen, damit die Datei ersetzt werden kann, global, lassen andere Einstellungen sind nicht betroffen. Visual Studio können Sie mehrere Sätze von Einstellungen zu Ihrem Projekt hinzufügen. Weitere Gruppen von Einstellungen können über das Properties.Settings-Objekt zugegriffen werden.  
  
### <a name="to-add-an-additional-set-of-setting-to-your-application"></a>Hinzufügen ein zusätzlichen Satzes von Einstellung für Ihre Anwendung  
  
1.  Wählen Sie im Menü **Projekt** die Option **Neues Element hinzufügen** aus. Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.  
  
2.  In der **neues Element hinzufügen** wählen Sie im Dialogfeld **Einstellungsdatei**, geben Sie einen Namen für die Datei, und klicken Sie auf **hinzufügen** Ihrer Projektmappe eine neue Datei hinzu.  
  
3.  In **Projektmappen-Explorer**, ziehen Sie die neue Einstellungsdatei in die **Eigenschaften** Ordner. Dadurch werden die neuen Einstellungen in Code verfügbar sein.  
  
4.  Fügen Sie hinzu und verwenden Sie Einstellungen in dieser Datei, wie jeder anderen Einstellungsdatei. Sie können diese Gruppe von Einstellungen über das Properties.Settings-Objekt zugreifen.  
  
## <a name="see-also"></a>Siehe auch
- [Verwenden von Anwendungseinstellungen und Benutzereinstellungen](using-application-settings-and-user-settings.md)
- [Übersicht über Anwendungseinstellungen](application-settings-overview.md)
