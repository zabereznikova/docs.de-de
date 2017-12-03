---
title: 'Aufgabe 1: Erstellen einer neuen Windows Presentation Foundation-Anwendung'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 89c929e71a2d64673f158f81c85d04c3443800ac
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="task-1-create-a-new-windows-presentation-foundation-application"></a><span data-ttu-id="3d946-102">Aufgabe 1: Erstellen einer neuen Windows Presentation Foundation-Anwendung</span><span class="sxs-lookup"><span data-stu-id="3d946-102">Task 1: Create a New Windows Presentation Foundation Application</span></span>
<span data-ttu-id="3d946-103">In dieser Aufgabe erstellen Sie eine leere [!INCLUDE[avalon1](../../../includes/avalon1-md.md)]-Anwendung mithilfe der WPF-Anwendungsvorlage von Visual Studio und fügen Verweise auf die entsprechenden [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]-Workflowassemblys hinzu.</span><span class="sxs-lookup"><span data-stu-id="3d946-103">In this task, you will create an empty [!INCLUDE[avalon1](../../../includes/avalon1-md.md)] application by using the WPF Application Visual Studio template and add references to the appropriate [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow assemblies.</span></span>  
  
### <a name="to-create-the-wpf-application-project"></a><span data-ttu-id="3d946-104">So erstellen Sie das WPF-Anwendungsprojekt</span><span class="sxs-lookup"><span data-stu-id="3d946-104">To create the WPF Application project</span></span>  
  
1.  <span data-ttu-id="3d946-105">Open [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] und klicken Sie auf die **Datei** Sie im Menü **neu**, und klicken Sie dann auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="3d946-105">Open [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] and on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="3d946-106">In der **neues Projekt** Dialogfeld wählen **Visual C#-** oder **Visual Basic** aus der **installierte Vorlagen** Bereich auf der linken Seite des das Feld ein.</span><span class="sxs-lookup"><span data-stu-id="3d946-106">In the **New Project** dialog box, select either **Visual C#** or **Visual Basic** from the **Installed Templates** pane on the left side of the box.</span></span> <span data-ttu-id="3d946-107">Wenn die Sprache Ihrer Wahl nicht angezeigt wird, suchen Sie unter **andere Sprachen**.</span><span class="sxs-lookup"><span data-stu-id="3d946-107">If the language of your choice does not appear, look under **Other Languages**.</span></span>  
  
3.  <span data-ttu-id="3d946-108">Wählen Sie **Windows** in der **installierte Vorlagen** Bereich.</span><span class="sxs-lookup"><span data-stu-id="3d946-108">Select **Windows** in the **Installed Templates** pane.</span></span>  
  
4.  <span data-ttu-id="3d946-109">Vergewissern Sie sich, die im oberen Bereich (Standardwert) **.NET Framework 4** im Dropdown-Listenfeld ausgewählt ist, und wählen Sie dann **WPF-Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="3d946-109">In the top pane, confirm that (the default value) **.NET Framework 4** has been selected in the drop-down list box, and then select **WPF Application**.</span></span>  
  
5.  <span data-ttu-id="3d946-110">Legen Sie den Namen des Projekts, um **HostingApplication** am unteren Rand des Fensters.</span><span class="sxs-lookup"><span data-stu-id="3d946-110">Set the name of the project to **HostingApplication** at the bottom of the window.</span></span>  
  
6.  <span data-ttu-id="3d946-111">Legen Sie den Namen der Projektmappe auf **RehostingTheDesigner**.</span><span class="sxs-lookup"><span data-stu-id="3d946-111">Set the solution name to **RehostingTheDesigner**.</span></span>  
  
7.  <span data-ttu-id="3d946-112">Klicken Sie auf **OK** das Anwendungsprojekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3d946-112">Click **OK** to create the application project.</span></span> [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)]<span data-ttu-id="3d946-113"> erstellt eine einfache WPF-Benutzeroberfläche für Ihre Anwendung und fügt die entsprechende XAML sowie Code-Behind-Dateien hinzu.</span><span class="sxs-lookup"><span data-stu-id="3d946-113"> creates a basic WPF UI for your application and includes the appropriate XAML and code-behind files.</span></span>  
  
8.  <span data-ttu-id="3d946-114">Fügen Sie Verweise auf **WorkflowModel** Assemblys.</span><span class="sxs-lookup"><span data-stu-id="3d946-114">Add references to **WorkflowModel** assemblies.</span></span> <span data-ttu-id="3d946-115">Klicken Sie hierzu in **Projektmappen-Explorer**, mit der rechten Maustaste die **HostingApplication** Projekt, und wählen Sie **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="3d946-115">To do this, in **Solution Explorer**, right-click the **HostingApplication** project and select **Add Reference**.</span></span>  
  
9. <span data-ttu-id="3d946-116">In der **Verweis hinzufügen** (Dialogfeld), klicken Sie auf die **.NET** Registerkarte, halten Sie die STRG-Taste, wählen Sie die folgenden Assemblys, und klicken Sie dann auf **OK**:</span><span class="sxs-lookup"><span data-stu-id="3d946-116">In the **Add Reference** dialog box, click the **.NET** tab, hold down the CTRL key, select the following assemblies, and then click **OK**:</span></span>  
  
    -   <span data-ttu-id="3d946-117">System.Activities</span><span class="sxs-lookup"><span data-stu-id="3d946-117">System.Activities</span></span>  
  
    -   <span data-ttu-id="3d946-118">System.Activities.Presentation</span><span class="sxs-lookup"><span data-stu-id="3d946-118">System.Activities.Presentation</span></span>  
  
    -   <span data-ttu-id="3d946-119">System.Activities.Core.Presentation</span><span class="sxs-lookup"><span data-stu-id="3d946-119">System.Activities.Core.Presentation</span></span>  
  
10. <span data-ttu-id="3d946-120">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d946-120">Click **OK**.</span></span>  
  
11. <span data-ttu-id="3d946-121">Finden Sie unter [Aufgabe 2: Hosten des Workflow-Designers](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md) Informationen zum Hosten der Designer entwurfszeichnungsbereich des Workflows.</span><span class="sxs-lookup"><span data-stu-id="3d946-121">See [Task 2: Host the Workflow Designer](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md) to learn how to host the workflow designer design canvas.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d946-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3d946-122">See Also</span></span>  
 [<span data-ttu-id="3d946-123">Erneutes Hosten des Workflow-Designers</span><span class="sxs-lookup"><span data-stu-id="3d946-123">Rehosting the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)  
 [<span data-ttu-id="3d946-124">Aufgabe 2: Hosten des Workflow-Designers</span><span class="sxs-lookup"><span data-stu-id="3d946-124">Task 2: Host the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md)
