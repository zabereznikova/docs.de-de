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
# <a name="how-to-write-user-settings-at-run-time-with-c"></a><span data-ttu-id="921a0-102">Vorgehensweise: Schreiben von Benutzereinstellungen zur Laufzeit mit C#\#</span><span class="sxs-lookup"><span data-stu-id="921a0-102">How To: Write User Settings at Run Time with C\#</span></span>

<span data-ttu-id="921a0-103">Einstellungen im Gültigkeitsbereich der Anwendung sind schreibgeschützt und können nur zur Entwurfszeit oder durch Ändern der CONFIG-Datei zwischen Anwendungssitzungen geändert werden.</span><span class="sxs-lookup"><span data-stu-id="921a0-103">Settings that are application-scoped are read-only, and can only be changed at design time or by altering the .config file in between application sessions.</span></span> <span data-ttu-id="921a0-104">Einstellungen im Gültigkeitsbereich des Benutzers können jedoch zur Laufzeit geschrieben werden, so als würden Sie einen beliebigen Eigenschaftswert ändern.</span><span class="sxs-lookup"><span data-stu-id="921a0-104">Settings that are user-scoped, however, can be written at run time just as you would change any property value.</span></span> <span data-ttu-id="921a0-105">Der neue Wert wird für die Dauer der Anwendungssitzung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="921a0-105">The new value persists for the duration of the application session.</span></span> <span data-ttu-id="921a0-106">Sie können die Änderungen an den Einstellungen zwischen Anwendungssitzungen beibehalten, indem Sie die Save-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="921a0-106">You can persist the changes to the settings between application sessions by calling the Save method.</span></span>  
  
## <a name="how-to-write-and-persist-user-settings-at-run-time-with-c"></a><span data-ttu-id="921a0-107">Vorgehensweise: Schreiben und Beibehalten von Benutzereinstellungen zur Laufzeit mit C#\#</span><span class="sxs-lookup"><span data-stu-id="921a0-107">How To: Write and Persist User Settings at Run Time with C\#</span></span>
  
1. <span data-ttu-id="921a0-108">Greifen Sie auf die Einstellung zu, und weisen Sie ihr einen neuen Wert zu, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="921a0-108">Access the setting and assign it a new value as shown in this example:</span></span>  
  
   ```csharp
   Properties.Settings.Default.myColor = Color.AliceBlue;  
   ```  
  
2. <span data-ttu-id="921a0-109">Wenn Sie die Änderungen an den Einstellungen zwischen Anwendungssitzungen beibehalten möchten, rufen Sie die Save-Methode auf, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="921a0-109">If you want to persist the changes to the settings between application sessions, call the Save method as shown in this example:</span></span>  
  
    ```csharp
    Properties.Settings.Default.Save();  
    ```  
  
<span data-ttu-id="921a0-110">Benutzereinstellungen werden in einer Datei in einem Unterordner des lokalen ausgeblendeten Ordners für Anwendungsdaten des Benutzers gespeichert.</span><span class="sxs-lookup"><span data-stu-id="921a0-110">User settings are saved in a file within a subfolder of the user’s local hidden application data folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="921a0-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="921a0-111">See also</span></span>

- [<span data-ttu-id="921a0-112">Verwenden von Anwendungseinstellungen und Benutzereinstellungen</span><span class="sxs-lookup"><span data-stu-id="921a0-112">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="921a0-113">How To: Lesen von Einstellungen zur Laufzeit mitC#</span><span class="sxs-lookup"><span data-stu-id="921a0-113">How To: Read Settings at Run Time With C#</span></span>](how-to-read-settings-at-run-time-with-csharp.md)
- [<span data-ttu-id="921a0-114">Übersicht über Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="921a0-114">Application Settings Overview</span></span>](application-settings-overview.md)
