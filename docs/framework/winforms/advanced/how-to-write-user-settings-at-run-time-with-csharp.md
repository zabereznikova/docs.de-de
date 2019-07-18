---
title: 'Vorgehensweise: Schreiben von Benutzereinstellungen zur Laufzeit mit C#'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], run time
- application settings [Windows Forms], writing user settings
- application settings [Windows Forms], C#
ms.assetid: 9d061c7d-b33b-470f-a36d-edccb1d6f9a3
ms.openlocfilehash: 264fa9706f9255d7324cad6d02c36cc424e28995
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778832"
---
# <a name="how-to-write-user-settings-at-run-time-with-c"></a>Vorgehensweise: Schreiben von Benutzereinstellungen zur Laufzeit mit C#\#

Einstellungen im Gültigkeitsbereich der Anwendung sind schreibgeschützt und können nur zur Entwurfszeit oder durch Ändern der CONFIG-Datei zwischen Anwendungssitzungen geändert werden. Einstellungen im Gültigkeitsbereich des Benutzers können jedoch zur Laufzeit geschrieben werden, so als würden Sie einen beliebigen Eigenschaftswert ändern. Der neue Wert wird für die Dauer der Anwendungssitzung beibehalten. Sie können die Änderungen an den Einstellungen zwischen Anwendungssitzungen beibehalten, indem Sie die Save-Methode aufrufen.  
  
## <a name="how-to-write-and-persist-user-settings-at-run-time-with-c"></a>Vorgehensweise: Schreiben und Beibehalten von Benutzereinstellungen zur Laufzeit mit C#\#
  
1. Greifen Sie auf die Einstellung zu, und weisen Sie ihr einen neuen Wert zu, wie im folgenden Beispiel gezeigt:  
  
   ```csharp
   Properties.Settings.Default.myColor = Color.AliceBlue;  
   ```  
  
2. Wenn Sie die Änderungen an den Einstellungen zwischen Anwendungssitzungen beibehalten möchten, rufen Sie die Save-Methode auf, wie im folgenden Beispiel gezeigt:  
  
    ```csharp
    Properties.Settings.Default.Save();  
    ```  
  
Benutzereinstellungen werden in einer Datei in einem Unterordner des lokalen ausgeblendeten Ordners für Anwendungsdaten des Benutzers gespeichert.  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden von Anwendungseinstellungen und Benutzereinstellungen](using-application-settings-and-user-settings.md)
- [How To: Lesen von Einstellungen zur Laufzeit mitC#](how-to-read-settings-at-run-time-with-csharp.md)
- [Übersicht über Anwendungseinstellungen](application-settings-overview.md)
