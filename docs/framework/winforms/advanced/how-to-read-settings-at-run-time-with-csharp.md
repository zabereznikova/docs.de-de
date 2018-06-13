---
title: 'Gewusst wie: Lesen von Einstellungen zur Laufzeit mit C#'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], reading
- application settings [Windows Forms], run time
- application settings [Windows Forms], C#
ms.assetid: dbe8bf09-5e1c-49da-9192-154033d7240b
ms.openlocfilehash: 8259e2f429718793c01868855651d1000620fae5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521013"
---
# <a name="how-to-read-settings-at-run-time-with-c"></a>Gewusst wie: Lesen von Einstellungen zur Laufzeit mit C# #
Über das Properties-Objekt können Sie zur Laufzeit anwendungsspezifische und benutzerspezifische Einstellungen auslesen. Das Properties-Objekt macht über den Properties.Settings.Default-Member alle Standardeinstellungen für des Projekt verfügbar.  
  
### <a name="to-read-settings-at-run-time-with-c"></a>So lesen Sie Einstellungen zur Laufzeit mit C#  
  
-   Greifen Sie über den Properties.Settings.Default-Member auf die geeignete Einstellung zu. Im folgenden Beispiel wird gezeigt, wie Sie einer BackColor-Eigenschaft eine Einstellung mit Namen `myColor` zuweisen. Dies setzt voraus, dass Sie zuvor eine Einstellungsdatei erstellt haben, die eine Einstellung mit Namen `myColor` vom Typ `System.Drawing.Color` enthält. Informationen zum Erstellen einer Initialisierungsdatei, finden Sie unter [Vorgehensweise: Erstellen einer neuen Einstellung zur Entwurfszeit](../../../../docs/framework/winforms/advanced/how-to-create-a-new-setting-at-design-time.md).  
  
    ```  
    // C#  
    this.BackColor = Properties.Settings.Default.myColor;  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Anwendungseinstellungen und Benutzereinstellungen](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [Gewusst wie: Schreiben von Benutzereinstellungen zur Laufzeit mit C#](../../../../docs/framework/winforms/advanced/how-to-write-user-settings-at-run-time-with-csharp.md)  
 [Übersicht über Anwendungseinstellungen](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
