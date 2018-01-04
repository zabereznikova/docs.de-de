---
title: 'Gewusst wie: Lesen von Einstellungen zur Laufzeit mit C#'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application settings [Windows Forms], reading
- application settings [Windows Forms], run time
- application settings [Windows Forms], C#
ms.assetid: dbe8bf09-5e1c-49da-9192-154033d7240b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 85dc3a2c97b8fe5003c6026874dbdcaa9af89d77
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
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
