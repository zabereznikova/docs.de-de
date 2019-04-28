---
title: 'Vorgehensweise: Hinzufügen mehrerer Gruppen von Einstellungen zur Anwendung in C#'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], multiple sets
- application settings [Windows Forms], C#
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
ms.openlocfilehash: 9a4913f635204aac2214d97225c7b8147c6fe9ab
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768549"
---
# <a name="how-to-add-multiple-sets-of-settings-to-your-application-in-c"></a><span data-ttu-id="5172c-102">Vorgehensweise: Fügen Sie mehrerer Gruppen von Einstellungen zur Anwendung in C hinzu\#</span><span class="sxs-lookup"><span data-stu-id="5172c-102">How To: Add Multiple Sets of Settings To Your Application in C\#</span></span>
<span data-ttu-id="5172c-103">In einigen Fällen empfiehlt es sich um mehrere Gruppen von Einstellungen in einer Anwendung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="5172c-103">In some cases, you might want to have multiple sets of settings in an application.</span></span> <span data-ttu-id="5172c-104">Z. B. Wenn Sie eine Anwendung entwickeln, muss eine bestimmte Gruppe von Einstellungen häufig ändern, kann es sein es ratsam, alle in einer einzelnen Datei trennen, damit die Datei ersetzt werden kann, global, lassen andere Einstellungen sind nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="5172c-104">For example, if you are developing an application where a particular group of settings is expected to change frequently, it might be wise to separate them all into a single file so that the file can be replaced wholesale, leaving other settings unaffected.</span></span> <span data-ttu-id="5172c-105">Visual Studio können Sie mehrere Sätze von Einstellungen zu Ihrem Projekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5172c-105">Visual Studio allows you to add multiple sets of settings to your project.</span></span> <span data-ttu-id="5172c-106">Weitere Gruppen von Einstellungen können über das Properties.Settings-Objekt zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="5172c-106">Additional sets of settings can be accessed via the Properties.Settings object.</span></span>  
  
### <a name="to-add-an-additional-set-of-setting-to-your-application"></a><span data-ttu-id="5172c-107">Hinzufügen ein zusätzlichen Satzes von Einstellung für Ihre Anwendung</span><span class="sxs-lookup"><span data-stu-id="5172c-107">To Add an Additional Set of Setting to your Application</span></span>  
  
1. <span data-ttu-id="5172c-108">Wählen Sie im Menü **Projekt** die Option **Neues Element hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="5172c-108">From the **Project** menu, choose **Add New Item**.</span></span> <span data-ttu-id="5172c-109">Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5172c-109">The **Add New Item** dialog box opens.</span></span>  
  
2. <span data-ttu-id="5172c-110">In der **neues Element hinzufügen** wählen Sie im Dialogfeld **Einstellungsdatei**, geben Sie einen Namen für die Datei, und klicken Sie auf **hinzufügen** Ihrer Projektmappe eine neue Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="5172c-110">In the **Add New Item** dialog box, select **Settings File**, type in a name for the file, and click **Add** to add a new settings file to your solution.</span></span>  
  
3. <span data-ttu-id="5172c-111">In **Projektmappen-Explorer**, ziehen Sie die neue Einstellungsdatei in die **Eigenschaften** Ordner.</span><span class="sxs-lookup"><span data-stu-id="5172c-111">In **Solution Explorer**, drag the new Settings file into the **Properties** folder.</span></span> <span data-ttu-id="5172c-112">Dadurch werden die neuen Einstellungen in Code verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="5172c-112">This allows your new settings to be available in code.</span></span>  
  
4. <span data-ttu-id="5172c-113">Fügen Sie hinzu und verwenden Sie Einstellungen in dieser Datei, wie jeder anderen Einstellungsdatei.</span><span class="sxs-lookup"><span data-stu-id="5172c-113">Add and use settings in this file as you would any other settings file.</span></span> <span data-ttu-id="5172c-114">Sie können diese Gruppe von Einstellungen über das Properties.Settings-Objekt zugreifen.</span><span class="sxs-lookup"><span data-stu-id="5172c-114">You can access this group of settings via the Properties.Settings object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5172c-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5172c-115">See also</span></span>

- [<span data-ttu-id="5172c-116">Verwenden von Anwendungseinstellungen und Benutzereinstellungen</span><span class="sxs-lookup"><span data-stu-id="5172c-116">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="5172c-117">Übersicht über Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="5172c-117">Application Settings Overview</span></span>](application-settings-overview.md)
