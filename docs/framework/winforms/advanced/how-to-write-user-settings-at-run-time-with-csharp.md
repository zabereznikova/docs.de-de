---
title: 'Vorgehensweise: Schreiben von Benutzereinstellungen zur Laufzeit mit C#'
description: Erfahren Sie, wie Sie Einstellungen zur Laufzeit mit c# schreiben, indem Sie die Änderungen an den Einstellungen zwischen Anwendungs Sitzungen beibehalten, indem Sie die Save-Methode aufrufen.
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], run time
- application settings [Windows Forms], writing user settings
- application settings [Windows Forms], C#
ms.assetid: 9d061c7d-b33b-470f-a36d-edccb1d6f9a3
ms.openlocfilehash: 6154ff1b92d6c2d4c788299e59eb8f73e6b69c4b
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904324"
---
# <a name="how-to-write-user-settings-at-run-time-with-c"></a><span data-ttu-id="ef2b6-103">Gewusst wie: Schreiben von Benutzereinstellungen zur Laufzeit mit C\#</span><span class="sxs-lookup"><span data-stu-id="ef2b6-103">How To: Write User Settings at Run Time with C\#</span></span>

<span data-ttu-id="ef2b6-104">Einstellungen im Gültigkeitsbereich der Anwendung sind schreibgeschützt und können nur zur Entwurfszeit oder durch Ändern der CONFIG-Datei zwischen Anwendungssitzungen geändert werden.</span><span class="sxs-lookup"><span data-stu-id="ef2b6-104">Settings that are application-scoped are read-only, and can only be changed at design time or by altering the .config file in between application sessions.</span></span> <span data-ttu-id="ef2b6-105">Einstellungen im Gültigkeitsbereich des Benutzers können jedoch zur Laufzeit geschrieben werden, so als würden Sie einen beliebigen Eigenschaftswert ändern.</span><span class="sxs-lookup"><span data-stu-id="ef2b6-105">Settings that are user-scoped, however, can be written at run time just as you would change any property value.</span></span> <span data-ttu-id="ef2b6-106">Der neue Wert wird für die Dauer der Anwendungssitzung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="ef2b6-106">The new value persists for the duration of the application session.</span></span> <span data-ttu-id="ef2b6-107">Sie können die Änderungen an den Einstellungen zwischen Anwendungssitzungen beibehalten, indem Sie die Save-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="ef2b6-107">You can persist the changes to the settings between application sessions by calling the Save method.</span></span>  
  
## <a name="how-to-write-and-persist-user-settings-at-run-time-with-c"></a><span data-ttu-id="ef2b6-108">Gewusst wie: schreiben und beibehalten von Benutzereinstellungen zur Laufzeit mit C\#</span><span class="sxs-lookup"><span data-stu-id="ef2b6-108">How To: Write and Persist User Settings at Run Time with C\#</span></span>
  
1. <span data-ttu-id="ef2b6-109">Greifen Sie auf die Einstellung zu, und weisen Sie ihr einen neuen Wert zu, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="ef2b6-109">Access the setting and assign it a new value as shown in this example:</span></span>  
  
   ```csharp
   Properties.Settings.Default.myColor = Color.AliceBlue;  
   ```  
  
2. <span data-ttu-id="ef2b6-110">Wenn Sie die Änderungen an den Einstellungen zwischen Anwendungssitzungen beibehalten möchten, rufen Sie die Save-Methode auf, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="ef2b6-110">If you want to persist the changes to the settings between application sessions, call the Save method as shown in this example:</span></span>  
  
    ```csharp
    Properties.Settings.Default.Save();  
    ```  
  
<span data-ttu-id="ef2b6-111">Benutzereinstellungen werden in einer Datei in einem Unterordner des lokalen ausgeblendeten Ordners für Anwendungsdaten des Benutzers gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ef2b6-111">User settings are saved in a file within a subfolder of the user’s local hidden application data folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef2b6-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ef2b6-112">See also</span></span>

- [<span data-ttu-id="ef2b6-113">Verwenden von Anwendungseinstellungen und Benutzereinstellungen</span><span class="sxs-lookup"><span data-stu-id="ef2b6-113">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="ef2b6-114">Vorgehensweise: Lesen von Einstellungen zur Laufzeit mit C#</span><span class="sxs-lookup"><span data-stu-id="ef2b6-114">How To: Read Settings at Run Time With C#</span></span>](how-to-read-settings-at-run-time-with-csharp.md)
- [<span data-ttu-id="ef2b6-115">Übersicht über Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="ef2b6-115">Application Settings Overview</span></span>](application-settings-overview.md)
