---
title: 'Vorgehensweise: Lesen von Einstellungen zur Laufzeit mit C#'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], reading
- application settings [Windows Forms], run time
- application settings [Windows Forms], C#
ms.assetid: dbe8bf09-5e1c-49da-9192-154033d7240b
ms.openlocfilehash: 8cdc1a79f1ab327ae037cd6a04aa769196405127
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61966912"
---
# <a name="how-to-read-settings-at-run-time-with-c"></a><span data-ttu-id="e6986-102">Vorgehensweise: Lesen von Einstellungen zur Laufzeit mit C#\#</span><span class="sxs-lookup"><span data-stu-id="e6986-102">How To: Read Settings at Run Time With C\#</span></span>

<span data-ttu-id="e6986-103">Über das Properties-Objekt können Sie zur Laufzeit anwendungsspezifische und benutzerspezifische Einstellungen auslesen.</span><span class="sxs-lookup"><span data-stu-id="e6986-103">You can read both Application-scoped and User-scoped settings at run time via the Properties object.</span></span> <span data-ttu-id="e6986-104">Das Properties-Objekt macht über den Properties.Settings.Default-Member alle Standardeinstellungen für des Projekt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e6986-104">The Properties object exposes all of the default settings for the project via the Properties.Settings.Default member.</span></span>  
  
## <a name="to-read-settings-at-run-time-with-c"></a><span data-ttu-id="e6986-105">Zum Lesen von Einstellungen zur Laufzeit mit C#\#</span><span class="sxs-lookup"><span data-stu-id="e6986-105">To Read Settings at Run Time with C\#</span></span>
  
<span data-ttu-id="e6986-106">Greifen Sie über den Properties.Settings.Default-Member auf die geeignete Einstellung zu.</span><span class="sxs-lookup"><span data-stu-id="e6986-106">Access the appropriate setting via the Properties.Settings.Default member.</span></span> <span data-ttu-id="e6986-107">Im folgenden Beispiel wird gezeigt, wie Sie einer BackColor-Eigenschaft eine Einstellung mit Namen `myColor` zuweisen.</span><span class="sxs-lookup"><span data-stu-id="e6986-107">The following example shows how to assign a setting named `myColor` to a BackColor property.</span></span> <span data-ttu-id="e6986-108">Dies setzt voraus, dass Sie zuvor eine Einstellungsdatei erstellt haben, die eine Einstellung mit Namen `myColor` vom Typ `System.Drawing.Color` enthält.</span><span class="sxs-lookup"><span data-stu-id="e6986-108">It requires you to have previously created a Settings file containing a setting named `myColor` of type `System.Drawing.Color`.</span></span> <span data-ttu-id="e6986-109">Weitere Informationen zum Erstellen einer Datei, finden Sie unter [so wird's gemacht: Erstellen einer neuen Einstellung zur Entwurfszeit](how-to-create-a-new-setting-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="e6986-109">For information about creating a Settings file, see [How To: Create a New Setting at Design Time](how-to-create-a-new-setting-at-design-time.md).</span></span>  
  
```csharp
this.BackColor = Properties.Settings.Default.myColor;  
```  
  
## <a name="see-also"></a><span data-ttu-id="e6986-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6986-110">See also</span></span>

- [<span data-ttu-id="e6986-111">Verwenden von Anwendungseinstellungen und Benutzereinstellungen</span><span class="sxs-lookup"><span data-stu-id="e6986-111">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="e6986-112">How To: Schreiben von Benutzereinstellungen zur Laufzeit mitC#</span><span class="sxs-lookup"><span data-stu-id="e6986-112">How To: Write User Settings at Run Time with C#</span></span>](how-to-write-user-settings-at-run-time-with-csharp.md)
- [<span data-ttu-id="e6986-113">Übersicht über Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="e6986-113">Application Settings Overview</span></span>](application-settings-overview.md)
