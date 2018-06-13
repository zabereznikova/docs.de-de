---
title: 'Gewusst wie: Hinzufügen mehrerer Gruppen von Einstellungen zur Anwendung in C#'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], multiple sets
- application settings [Windows Forms], C#
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
ms.openlocfilehash: 029dffc878c62613e291620a2bd86971f369d15a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33520808"
---
# <a name="how-to-add-multiple-sets-of-settings-to-your-application-in-c"></a>Gewusst wie: Hinzufügen mehrerer Gruppen von Einstellungen zur Anwendung in C# #
In einigen Fällen möchten möglicherweise haben mehrere Sätze von Einstellungen in einer Anwendung. Z. B. Wenn Sie eine Anwendung entwickeln, in denen eine bestimmte Gruppe von Einstellungen muss häufig geändert werden, möglicherweise ratsam, die alle auf einer einzelnen Datei aufteilen, damit die Datei Großhändler, ersetzt werden kann. verlassen andere Einstellungen nicht betroffen. Visual Studio können Sie mehrere Sätze von Einstellungen zum Projekt hinzufügen. Zusätzliche Gruppen von Einstellungen können über das Properties.Settings-Objekt zugegriffen werden.  
  
### <a name="to-add-an-additional-set-of-setting-to-your-application"></a>So fügen Sie einen zusätzlichen Satz von Einstellung für Ihre Anwendung hinzu  
  
1.  Wählen Sie im Menü **Projekt** die Option **Neues Element hinzufügen** aus. Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.  
  
2.  In der **neues Element hinzufügen** wählen Sie im Dialogfeld **Einstellungsdatei**, geben Sie einen Namen für die Datei, und klicken Sie auf **hinzufügen** der Projektmappe eine neue Datei hinzu.  
  
3.  In **Projektmappen-Explorer**, ziehen Sie die neue Einstellungsdatei in der **Eigenschaften** Ordner. Dadurch werden die neuen Einstellungen in Code verfügbar sein.  
  
4.  Fügen Sie hinzu und Einstellungen in dieser Datei wie jede andere Settings-Datei. Sie können diese Gruppe von Einstellungen über das Properties.Settings Objekt zugreifen.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Anwendungseinstellungen und Benutzereinstellungen](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [Übersicht über Anwendungseinstellungen](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
