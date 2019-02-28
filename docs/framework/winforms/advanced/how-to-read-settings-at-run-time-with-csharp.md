---
title: 'Vorgehensweise: Lesen von Einstellungen zur Laufzeit mitC#'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], reading
- application settings [Windows Forms], run time
- application settings [Windows Forms], C#
ms.assetid: dbe8bf09-5e1c-49da-9192-154033d7240b
ms.openlocfilehash: 8cdc1a79f1ab327ae037cd6a04aa769196405127
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56974847"
---
# <a name="how-to-read-settings-at-run-time-with-c"></a>Vorgehensweise: Lesen von Einstellungen zur Laufzeit mit C#\#

Über das Properties-Objekt können Sie zur Laufzeit anwendungsspezifische und benutzerspezifische Einstellungen auslesen. Das Properties-Objekt macht über den Properties.Settings.Default-Member alle Standardeinstellungen für des Projekt verfügbar.  
  
## <a name="to-read-settings-at-run-time-with-c"></a>Zum Lesen von Einstellungen zur Laufzeit mit C#\#
  
Greifen Sie über den Properties.Settings.Default-Member auf die geeignete Einstellung zu. Im folgenden Beispiel wird gezeigt, wie Sie einer BackColor-Eigenschaft eine Einstellung mit Namen `myColor` zuweisen. Dies setzt voraus, dass Sie zuvor eine Einstellungsdatei erstellt haben, die eine Einstellung mit Namen `myColor` vom Typ `System.Drawing.Color` enthält. Weitere Informationen zum Erstellen einer Datei, finden Sie unter [so wird's gemacht: Erstellen einer neuen Einstellung zur Entwurfszeit](how-to-create-a-new-setting-at-design-time.md).  
  
```csharp
this.BackColor = Properties.Settings.Default.myColor;  
```  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden von Anwendungseinstellungen und Benutzereinstellungen](using-application-settings-and-user-settings.md)
- [How To: Schreiben von Benutzereinstellungen zur Laufzeit mitC#](how-to-write-user-settings-at-run-time-with-csharp.md)
- [Übersicht über Anwendungseinstellungen](application-settings-overview.md)
