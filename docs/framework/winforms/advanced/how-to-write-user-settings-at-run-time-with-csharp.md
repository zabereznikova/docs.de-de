---
title: 'Gewusst wie: Schreiben von Benutzereinstellungen zur Laufzeit mit C#'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application settings [Windows Forms], run time
- application settings [Windows Forms], writing user settings
- application settings [Windows Forms], C#
ms.assetid: 9d061c7d-b33b-470f-a36d-edccb1d6f9a3
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5966aef77c994d2657bd282ad15e8f59a64eeb47
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-user-settings-at-run-time-with-c"></a>Gewusst wie: Schreiben von Benutzereinstellungen zur Laufzeit mit C# #
Einstellungen im Gültigkeitsbereich der Anwendung sind schreibgeschützt und können nur zur Entwurfszeit oder durch Ändern der CONFIG-Datei zwischen Anwendungssitzungen geändert werden. Einstellungen im Gültigkeitsbereich des Benutzers können jedoch zur Laufzeit geschrieben werden, so als würden Sie einen beliebigen Eigenschaftswert ändern. Der neue Wert wird für die Dauer der Anwendungssitzung beibehalten. Sie können die Änderungen an den Einstellungen zwischen Anwendungssitzungen beibehalten, indem Sie die Save-Methode aufrufen.  
  
### <a name="how-to-write-and-persist-user-settings-at-run-time-with-c"></a>Gewusst wie: Schreiben und Beibehalten von Benutzereinstellungen zur Laufzeit mit C#  
  
1.  Greifen Sie auf die Einstellung zu, und weisen Sie ihr einen neuen Wert zu, wie im folgenden Beispiel gezeigt:  
  
    ```  
    // C#  
    Properties.Settings.Default.myColor = Color.AliceBlue;  
    ```  
  
2.  Wenn Sie die Änderungen an den Einstellungen zwischen Anwendungssitzungen beibehalten möchten, rufen Sie die Save-Methode auf, wie im folgenden Beispiel gezeigt:  
  
    ```  
    // C#  
    Properties.Settings.Default.Save();  
    ```  
  
     Benutzereinstellungen werden in einer Datei in einem Unterordner des lokalen ausgeblendeten Ordners für Anwendungsdaten des Benutzers gespeichert.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Anwendungseinstellungen und Benutzereinstellungen](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [Gewusst wie: Lesen von Einstellungen zur Laufzeit mit C#](../../../../docs/framework/winforms/advanced/how-to-read-settings-at-run-time-with-csharp.md)  
 [Übersicht über Anwendungseinstellungen](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
