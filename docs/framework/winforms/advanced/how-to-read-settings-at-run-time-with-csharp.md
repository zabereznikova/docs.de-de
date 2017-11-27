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
ms.openlocfilehash: 9c23fd88d33ff4ca480c435f2058f4c568320578
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-read-settings-at-run-time-with-c"></a><span data-ttu-id="ab9a9-102">Gewusst wie: Lesen von Einstellungen zur Laufzeit mit C#</span><span class="sxs-lookup"><span data-stu-id="ab9a9-102">How To: Read Settings at Run Time With C#</span></span> #
<span data-ttu-id="ab9a9-103">Über das Properties-Objekt können Sie zur Laufzeit anwendungsspezifische und benutzerspezifische Einstellungen auslesen.</span><span class="sxs-lookup"><span data-stu-id="ab9a9-103">You can read both Application-scoped and User-scoped settings at run time via the Properties object.</span></span> <span data-ttu-id="ab9a9-104">Das Properties-Objekt macht über den Properties.Settings.Default-Member alle Standardeinstellungen für des Projekt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ab9a9-104">The Properties object exposes all of the default settings for the project via the Properties.Settings.Default member.</span></span>  
  
### <a name="to-read-settings-at-run-time-with-c"></a><span data-ttu-id="ab9a9-105">So lesen Sie Einstellungen zur Laufzeit mit C#</span><span class="sxs-lookup"><span data-stu-id="ab9a9-105">To Read Settings at Run Time with C#</span></span>  
  
-   <span data-ttu-id="ab9a9-106">Greifen Sie über den Properties.Settings.Default-Member auf die geeignete Einstellung zu.</span><span class="sxs-lookup"><span data-stu-id="ab9a9-106">Access the appropriate setting via the Properties.Settings.Default member.</span></span> <span data-ttu-id="ab9a9-107">Im folgenden Beispiel wird gezeigt, wie Sie einer BackColor-Eigenschaft eine Einstellung mit Namen `myColor` zuweisen.</span><span class="sxs-lookup"><span data-stu-id="ab9a9-107">The following example shows how to assign a setting named `myColor` to a BackColor property.</span></span> <span data-ttu-id="ab9a9-108">Dies setzt voraus, dass Sie zuvor eine Einstellungsdatei erstellt haben, die eine Einstellung mit Namen `myColor` vom Typ `System.Drawing.Color` enthält.</span><span class="sxs-lookup"><span data-stu-id="ab9a9-108">It requires you to have previously created a Settings file containing a setting named `myColor` of type `System.Drawing.Color`.</span></span> <span data-ttu-id="ab9a9-109">Informationen zum Erstellen einer Initialisierungsdatei, finden Sie unter [Vorgehensweise: Erstellen einer neuen Einstellung zur Entwurfszeit](../../../../docs/framework/winforms/advanced/how-to-create-a-new-setting-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="ab9a9-109">For information about creating a Settings file, see [How To: Create a New Setting at Design Time](../../../../docs/framework/winforms/advanced/how-to-create-a-new-setting-at-design-time.md).</span></span>  
  
    ```  
    // C#  
    this.BackColor = Properties.Settings.Default.myColor;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ab9a9-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ab9a9-110">See Also</span></span>  
 [<span data-ttu-id="ab9a9-111">Verwenden von Anwendungseinstellungen und Benutzereinstellungen</span><span class="sxs-lookup"><span data-stu-id="ab9a9-111">Using Application Settings and User Settings</span></span>](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [<span data-ttu-id="ab9a9-112">Gewusst wie: Schreiben von Benutzereinstellungen zur Laufzeit mit C#</span><span class="sxs-lookup"><span data-stu-id="ab9a9-112">How To: Write User Settings at Run Time with C#</span></span>](../../../../docs/framework/winforms/advanced/how-to-write-user-settings-at-run-time-with-csharp.md)  
 [<span data-ttu-id="ab9a9-113">Übersicht über Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="ab9a9-113">Application Settings Overview</span></span>](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
