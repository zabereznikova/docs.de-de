---
title: "Gewusst wie: Hinzufügen mehrerer Gruppen von Einstellungen zur Anwendung in C#"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application settings [Windows Forms], multiple sets
- application settings [Windows Forms], C#
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ec541a8f83990eec79226be7fb4880ef8dda639d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-multiple-sets-of-settings-to-your-application-in-c"></a><span data-ttu-id="fdce2-102">Gewusst wie: Hinzufügen mehrerer Gruppen von Einstellungen zur Anwendung in C#</span><span class="sxs-lookup"><span data-stu-id="fdce2-102">How To: Add Multiple Sets of Settings To Your Application in C#</span></span> #
<span data-ttu-id="fdce2-103">In einigen Fällen möchten möglicherweise haben mehrere Sätze von Einstellungen in einer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="fdce2-103">In some cases, you might want to have multiple sets of settings in an application.</span></span> <span data-ttu-id="fdce2-104">Z. B. Wenn Sie eine Anwendung entwickeln, in denen eine bestimmte Gruppe von Einstellungen muss häufig geändert werden, möglicherweise ratsam, die alle auf einer einzelnen Datei aufteilen, damit die Datei Großhändler, ersetzt werden kann. verlassen andere Einstellungen nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="fdce2-104">For example, if you are developing an application where a particular group of settings is expected to change frequently, it might be wise to separate them all into a single file so that the file can be replaced wholesale, leaving other settings unaffected.</span></span> <span data-ttu-id="fdce2-105">Visual Studio können Sie mehrere Sätze von Einstellungen zum Projekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fdce2-105">Visual Studio allows you to add multiple sets of settings to your project.</span></span> <span data-ttu-id="fdce2-106">Zusätzliche Gruppen von Einstellungen können über das Properties.Settings-Objekt zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="fdce2-106">Additional sets of settings can be accessed via the Properties.Settings object.</span></span>  
  
### <a name="to-add-an-additional-set-of-setting-to-your-application"></a><span data-ttu-id="fdce2-107">So fügen Sie einen zusätzlichen Satz von Einstellung für Ihre Anwendung hinzu</span><span class="sxs-lookup"><span data-stu-id="fdce2-107">To Add an Additional Set of Setting to your Application</span></span>  
  
1.  <span data-ttu-id="fdce2-108">Wählen Sie im Menü **Projekt** die Option **Neues Element hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="fdce2-108">From the **Project** menu, choose **Add New Item**.</span></span> <span data-ttu-id="fdce2-109">Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fdce2-109">The **Add New Item** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="fdce2-110">In der **neues Element hinzufügen** wählen Sie im Dialogfeld **Einstellungsdatei**, geben Sie einen Namen für die Datei, und klicken Sie auf **hinzufügen** der Projektmappe eine neue Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="fdce2-110">In the **Add New Item** dialog box, select **Settings File**, type in a name for the file, and click **Add** to add a new settings file to your solution.</span></span>  
  
3.  <span data-ttu-id="fdce2-111">In **Projektmappen-Explorer**, ziehen Sie die neue Einstellungsdatei in der **Eigenschaften** Ordner.</span><span class="sxs-lookup"><span data-stu-id="fdce2-111">In **Solution Explorer**, drag the new Settings file into the **Properties** folder.</span></span> <span data-ttu-id="fdce2-112">Dadurch werden die neuen Einstellungen in Code verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="fdce2-112">This allows your new settings to be available in code.</span></span>  
  
4.  <span data-ttu-id="fdce2-113">Fügen Sie hinzu und Einstellungen in dieser Datei wie jede andere Settings-Datei.</span><span class="sxs-lookup"><span data-stu-id="fdce2-113">Add and use settings in this file as you would any other settings file.</span></span> <span data-ttu-id="fdce2-114">Sie können diese Gruppe von Einstellungen über das Properties.Settings Objekt zugreifen.</span><span class="sxs-lookup"><span data-stu-id="fdce2-114">You can access this group of settings via the Properties.Settings object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdce2-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fdce2-115">See Also</span></span>  
 [<span data-ttu-id="fdce2-116">Verwenden von Anwendungseinstellungen und Benutzereinstellungen</span><span class="sxs-lookup"><span data-stu-id="fdce2-116">Using Application Settings and User Settings</span></span>](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [<span data-ttu-id="fdce2-117">Übersicht über Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="fdce2-117">Application Settings Overview</span></span>](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
