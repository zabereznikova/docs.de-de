---
title: 'Aufgabe 1: Erstellen einer neuen Windows Presentation Foundation-Anwendung'
ms.date: 03/30/2017
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
ms.openlocfilehash: 3205840da575041b449eb841fc8084e89937fca7
ms.sourcegitcommit: 10db6551ea3c971470cf5d2cc21ba1cbcefe5c55
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2019
ms.locfileid: "72031895"
---
# <a name="task-1-create-a-new-windows-presentation-foundation-application"></a><span data-ttu-id="d1e57-102">Aufgabe 1: Erstellen einer neuen Windows Presentation Foundation-Anwendung</span><span class="sxs-lookup"><span data-stu-id="d1e57-102">Task 1: Create a New Windows Presentation Foundation Application</span></span>

<span data-ttu-id="d1e57-103">In dieser Aufgabe erstellen Sie eine leere Windows Presentation Foundation (WPF)-Anwendung, indem Sie die Visual Studio-Vorlage der WPF-Anwendung verwenden und Verweise auf die entsprechenden [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]-Workflowassemblys hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d1e57-103">In this task, you will create an empty Windows Presentation Foundation (WPF) application by using the WPF Application Visual Studio template and add references to the appropriate [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow assemblies.</span></span>  
  
## <a name="to-create-the-wpf-application-project"></a><span data-ttu-id="d1e57-104">So erstellen Sie das WPF-Anwendungsprojekt</span><span class="sxs-lookup"><span data-stu-id="d1e57-104">To create the WPF Application project</span></span>

1. <span data-ttu-id="d1e57-105">Öffnen Sie Visual Studio, zeigen Sie im Menü **Datei** auf **neu**, und klicken Sie dann auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="d1e57-105">Open Visual Studio and on the **File** menu, point to **New**, and then click **Project**.</span></span>

2. <span data-ttu-id="d1e57-106">Wählen Sie im Dialogfeld **Neues Projekt** im Bereich **installierte Vorlagen** auf der linken Seite des Fensters entweder  **C# Visual** oder **Visual Basic** aus.</span><span class="sxs-lookup"><span data-stu-id="d1e57-106">In the **New Project** dialog box, select either **Visual C#** or **Visual Basic** from the **Installed Templates** pane on the left side of the box.</span></span> <span data-ttu-id="d1e57-107">Wenn die gewünschte Sprache nicht angezeigt wird, suchen Sie unter **andere Sprachen**.</span><span class="sxs-lookup"><span data-stu-id="d1e57-107">If the language of your choice does not appear, look under **Other Languages**.</span></span>

3. <span data-ttu-id="d1e57-108">Wählen Sie im Bereich **installierte Vorlagen** die Option **Windows** aus.</span><span class="sxs-lookup"><span data-stu-id="d1e57-108">Select **Windows** in the **Installed Templates** pane.</span></span>

4. <span data-ttu-id="d1e57-109">Vergewissern Sie sich im oberen Bereich, dass (der Standardwert) **.NET Framework 4** im Dropdown-Listenfeld ausgewählt wurde, und wählen Sie dann **WPF-Anwendung**aus.</span><span class="sxs-lookup"><span data-stu-id="d1e57-109">In the top pane, confirm that (the default value) **.NET Framework 4** has been selected in the drop-down list box, and then select **WPF Application**.</span></span>

5. <span data-ttu-id="d1e57-110">Legen Sie den Namen des Projekts im unteren Bereich des Fensters auf **HostingApplication** fest.</span><span class="sxs-lookup"><span data-stu-id="d1e57-110">Set the name of the project to **HostingApplication** at the bottom of the window.</span></span>

6. <span data-ttu-id="d1e57-111">Legen Sie den Projektmappennamen auf **rehostingder Designer**fest.</span><span class="sxs-lookup"><span data-stu-id="d1e57-111">Set the solution name to **RehostingTheDesigner**.</span></span>

7. <span data-ttu-id="d1e57-112">Klicken Sie auf **OK** , um das Anwendungsprojekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d1e57-112">Click **OK** to create the application project.</span></span> <span data-ttu-id="d1e57-113">Visual Studio erstellt eine einfache WPF-Benutzeroberfläche für Ihre Anwendung und enthält die entsprechenden XAML-und Code Behind-Dateien.</span><span class="sxs-lookup"><span data-stu-id="d1e57-113">Visual Studio creates a basic WPF UI for your application and includes the appropriate XAML and code-behind files.</span></span>

8. <span data-ttu-id="d1e57-114">Fügen Sie Verweise auf **Workflow Model** -Assemblys hinzu.</span><span class="sxs-lookup"><span data-stu-id="d1e57-114">Add references to **WorkflowModel** assemblies.</span></span> <span data-ttu-id="d1e57-115">Klicken Sie hierzu in **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt **HostingApplication** , und wählen Sie **Verweis hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="d1e57-115">To do this, in **Solution Explorer**, right-click the **HostingApplication** project and select **Add Reference**.</span></span>

9. <span data-ttu-id="d1e57-116">Klicken Sie im Dialogfeld **Verweis hinzufügen** auf die Registerkarte **.net** , halten Sie die STRG-Taste gedrückt, wählen Sie die folgenden Assemblys aus, und klicken Sie dann auf **OK**:</span><span class="sxs-lookup"><span data-stu-id="d1e57-116">In the **Add Reference** dialog box, click the **.NET** tab, hold down the CTRL key, select the following assemblies, and then click **OK**:</span></span>

    - <span data-ttu-id="d1e57-117">System.Activities</span><span class="sxs-lookup"><span data-stu-id="d1e57-117">System.Activities</span></span>
    - <span data-ttu-id="d1e57-118">System.Activities.Presentation</span><span class="sxs-lookup"><span data-stu-id="d1e57-118">System.Activities.Presentation</span></span>
    - <span data-ttu-id="d1e57-119">System.Activities.Core.Presentation</span><span class="sxs-lookup"><span data-stu-id="d1e57-119">System.Activities.Core.Presentation</span></span>

10. <span data-ttu-id="d1e57-120">Weitere Informationen zum Hosten des Entwurfs Canvas des Workflow-Designers finden Sie unter [Aufgabe 2: Hosten der Workflow-Designer](task-2-host-the-workflow-designer.md) .</span><span class="sxs-lookup"><span data-stu-id="d1e57-120">See [Task 2: Host the Workflow Designer](task-2-host-the-workflow-designer.md) to learn how to host the workflow designer design canvas.</span></span>

## <a name="see-also"></a><span data-ttu-id="d1e57-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d1e57-121">See also</span></span>

- [<span data-ttu-id="d1e57-122">Erneutes Hosten des Workflow-Designers</span><span class="sxs-lookup"><span data-stu-id="d1e57-122">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)
- [<span data-ttu-id="d1e57-123">Aufgabe 2: Hosten des Workflow-Designers</span><span class="sxs-lookup"><span data-stu-id="d1e57-123">Task 2: Host the Workflow Designer</span></span>](task-2-host-the-workflow-designer.md)
