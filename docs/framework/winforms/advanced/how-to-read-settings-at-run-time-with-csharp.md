---
title: 'Vorgehensweise: Lesen von Einstellungen zur Laufzeit mit C#'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], reading
- application settings [Windows Forms], run time
- application settings [Windows Forms], C#
ms.assetid: dbe8bf09-5e1c-49da-9192-154033d7240b
ms.openlocfilehash: 6a40718d57fad4041eeea2fded03b7256abbe8d1
ms.sourcegitcommit: eb9ff6f364cde6f11322e03800d8f5ce302f3c73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2019
ms.locfileid: "68710226"
---
# <a name="how-to-read-settings-at-run-time-with-c"></a>Vorgehensweise: Lesen von Einstellungen zur Laufzeit mit C\#

Über das Properties-Objekt können Sie zur Laufzeit anwendungsspezifische und benutzerspezifische Einstellungen auslesen. Das Properties-Objekt macht alle Standardeinstellungen für das Projekt über den Properties. Settings. Default-Member im Standard Namespace des Projekts verfügbar, in dem Sie definiert sind.  
  
## <a name="to-read-settings-at-run-time-with-c"></a>So lesen Sie Einstellungen zur Laufzeit mit C\#
  
Greifen Sie über den Properties.Settings.Default-Member auf die geeignete Einstellung zu. Im folgenden Beispiel wird gezeigt, wie Sie einer BackColor-Eigenschaft eine Einstellung mit Namen `myColor` zuweisen. Dies setzt voraus, dass Sie zuvor eine Einstellungsdatei erstellt haben, die eine Einstellung mit Namen `myColor` vom Typ `System.Drawing.Color` enthält. Weitere Informationen zum Erstellen einer Einstellungsdatei finden [Sie unter Gewusst wie: Erstellen Sie eine neue Einstellung zur Entwurfs](how-to-create-a-new-setting-at-design-time.md)Zeit.  
  
```csharp
this.BackColor = Properties.Settings.Default.myColor;  
```  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden von Anwendungseinstellungen und Benutzereinstellungen](using-application-settings-and-user-settings.md)
- [How To: Schreiben von Benutzereinstellungen zur Laufzeit mitC#](how-to-write-user-settings-at-run-time-with-csharp.md)
- [Übersicht über Anwendungseinstellungen](application-settings-overview.md)
