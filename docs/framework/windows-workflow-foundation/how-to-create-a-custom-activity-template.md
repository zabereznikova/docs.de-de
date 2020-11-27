---
title: 'Vorgehensweise: Erstellen einer benutzerdefinierten Aktivitätsvorlage'
ms.date: 03/30/2017
ms.assetid: 6760a5cc-6eb8-465f-b4fa-f89b39539429
ms.openlocfilehash: 90a54806833ff66797fb7beaa6ac8a912665bddc
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280116"
---
# <a name="how-to-create-a-custom-activity-template"></a><span data-ttu-id="b092e-102">Vorgehensweise: Erstellen einer benutzerdefinierten Aktivitätsvorlage</span><span class="sxs-lookup"><span data-stu-id="b092e-102">How to: Create a Custom Activity Template</span></span>

<span data-ttu-id="b092e-103">Benutzerdefinierte Aktivitätsvorlagen werden verwendet, um die Konfiguration von Aktivitäten, einschließlich benutzerdefinierter zusammengesetzter Aktivitäten, anzupassen. Dadurch müssen Benutzer die Aktivitäten nicht einzeln erstellen und alle zugehörigen Eigenschaften und anderen Einstellungen manuell konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b092e-103">Custom activity templates are used to customize the configuration of activities, including custom composite activities, so that users do not have to create each activity individually and configure their properties and other settings manually.</span></span> <span data-ttu-id="b092e-104">Diese benutzerdefinierten Vorlagen können in der **Toolbox** auf dem Windows-Workflow-Designer oder einem neu gehosteten Designer verfügbar gemacht werden, über den Benutzer Sie auf die vorkonfigurierte Entwurfs Oberfläche ziehen können.</span><span class="sxs-lookup"><span data-stu-id="b092e-104">These custom templates can be made available in the **Toolbox** on the Windows Workflow Designer or from a rehosted designer, from which users can drag them onto the preconfigured design surface.</span></span> <span data-ttu-id="b092e-105">Workflow-Designer enthält gute Beispiele für solche Vorlagen: den [sendandreceivereply](/visualstudio/workflow-designer/sendandreceivereply-template-designer) -Vorlagen Designer und den [receiveandsendreply](/visualstudio/workflow-designer/receiveandsendreply-template-designer) -Vorlagen Designer in der Kategorie der [Messaging-Aktivitäts Designer](/visualstudio/workflow-designer/messaging-activity-designers) .</span><span class="sxs-lookup"><span data-stu-id="b092e-105">Workflow Designer ships with good examples of such templates: the [SendAndReceiveReply Template Designer](/visualstudio/workflow-designer/sendandreceivereply-template-designer) and the [ReceiveAndSendReply Template Designer](/visualstudio/workflow-designer/receiveandsendreply-template-designer) in the [Messaging Activity Designers](/visualstudio/workflow-designer/messaging-activity-designers) category.</span></span>

 <span data-ttu-id="b092e-106">Das erste Verfahren in diesem Thema beschreibt, wie eine benutzerdefinierte Aktivitäts Vorlage für eine **Verzögerungs** Aktivität erstellt wird, und das zweite Verfahren beschreibt kurz, wie Sie in einem Workflow-Designer verfügbar gemacht wird, um zu überprüfen, ob die benutzerdefinierte Vorlage funktioniert.</span><span class="sxs-lookup"><span data-stu-id="b092e-106">The first procedure in this topic describes how to create a custom activity template for a **Delay** activity and the second procedure describes briefly how to make it available in a Workflow Designer to verify that the custom template works.</span></span>

 <span data-ttu-id="b092e-107">Benutzerdefinierte Aktivitätsvorlagen müssen <xref:System.Activities.Presentation.IActivityTemplateFactory> implementieren.</span><span class="sxs-lookup"><span data-stu-id="b092e-107">Custom activity templates must implement the <xref:System.Activities.Presentation.IActivityTemplateFactory>.</span></span> <span data-ttu-id="b092e-108">Die Schnittstelle verfügt über eine einzelne <xref:System.Activities.Presentation.IActivityTemplateFactory.Create%2A>-Methode, mit der Sie die in der Vorlage verwendeten Aktivitätsinstanzen erstellen und konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="b092e-108">The interface has a single <xref:System.Activities.Presentation.IActivityTemplateFactory.Create%2A> method with which you can create and configure the activity instances used in the template.</span></span>

## <a name="to-create-a-template-for-the-delay-activity"></a><span data-ttu-id="b092e-109">So erstellen Sie eine Vorlage für die Delay-Aktivität</span><span class="sxs-lookup"><span data-stu-id="b092e-109">To create a template for the Delay activity</span></span>

1. <span data-ttu-id="b092e-110">Starten Sie Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="b092e-110">Start Visual Studio 2010.</span></span>

2. <span data-ttu-id="b092e-111">Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="b092e-111">On the **File** menu, point to **New**, and then select **Project**.</span></span>

     <span data-ttu-id="b092e-112">Das Dialogfeld **Neues Projekt** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b092e-112">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="b092e-113">Wählen Sie im Bereich **Projekttypen** die Option **Workflow** aus den **Visual c#** -Projekten oder **Visual Basic** Gruppierungen abhängig von ihrer bevorzugte Sprache aus.</span><span class="sxs-lookup"><span data-stu-id="b092e-113">In the **Project Types** pane, select **Workflow** from either the **Visual C#** projects or **Visual Basic** groupings depending on your language preference.</span></span>

4. <span data-ttu-id="b092e-114">Wählen Sie im Bereich **Vorlagen** die Option **Aktivitäts Bibliothek** aus.</span><span class="sxs-lookup"><span data-stu-id="b092e-114">In the **Templates** pane, select **Activity Library**.</span></span>

5. <span data-ttu-id="b092e-115">Geben Sie im Feld **Name** Folgendes ein: `DelayActivityTemplate`.</span><span class="sxs-lookup"><span data-stu-id="b092e-115">In the **Name** box, enter `DelayActivityTemplate`.</span></span>

6. <span data-ttu-id="b092e-116">Akzeptieren Sie die Standardwerte in den Textfeldern **Speicherort** und Projektmappenname, und klicken Sie dann auf **OK**. **Solution name**</span><span class="sxs-lookup"><span data-stu-id="b092e-116">Accept the defaults in the **Location** and **Solution name** text boxes, and then click **OK**.</span></span>

7. <span data-ttu-id="b092e-117">Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf das Verzeichnis Verweise, und wählen Sie **Verweis hinzufügen** aus, um das Dialogfeld **Verweis hinzufügen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b092e-117">Right-click the References directory of the DelayActivityTemplate project in **Solution Explorer** and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>

8. <span data-ttu-id="b092e-118">Wechseln Sie zur Registerkarte **.net** , wählen Sie in der Spalte **Komponenten Name** auf der linken Seite **presentationframework** aus, und klicken Sie auf **OK** , um einen Verweis auf die PresentationFramework.dll Datei hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b092e-118">Go to the **.NET** tab and select **PresentationFramework** from the **Component Name** column on the left and click **OK** to add a reference to the PresentationFramework.dll file.</span></span>

9. <span data-ttu-id="b092e-119">Wiederholen Sie dieses Verfahren, um Verweise auf die Dateien "System.Activities.Presentation.dll" und "WindowsBase.dll" hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b092e-119">Repeat this procedure to add references to the System.Activities.Presentation.dll and the WindowsBase.dll files.</span></span>

10. <span data-ttu-id="b092e-120">Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt Delta activitytemplate, und wählen Sie **Hinzufügen** und dann **Neues Element** aus, um das Dialogfeld **Neues Element hinzufügen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b092e-120">Right-click the DelayActivityTemplate project in **Solution Explorer** and choose **Add** and then **New Item** to open the **Add New Item** dialog box.</span></span>

11. <span data-ttu-id="b092e-121">Wählen Sie die **Klassen** Vorlage aus, benennen Sie Sie mydelta-Template, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b092e-121">Select the **Class** template, name it MyDelayTemplate, and then click **OK**.</span></span>

12. <span data-ttu-id="b092e-122">Öffnen Sie die Datei "MyDelayTemplate.cs", und fügen Sie die folgenden Anweisungen hinzu.</span><span class="sxs-lookup"><span data-stu-id="b092e-122">Open the MyDelayTemplate.cs file and add the following statements.</span></span>

    ```csharp
    //Namespaces added
    using System.Activities;
    using System.Activities.Statements;
    using System.Activities.Presentation;
    using System.Windows;
    ```

13. <span data-ttu-id="b092e-123">Implementieren Sie <xref:System.Activities.Presentation.IActivityTemplateFactory> mit der `MyDelayActivity`-Klasse mit dem folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="b092e-123">Implement the <xref:System.Activities.Presentation.IActivityTemplateFactory> with the `MyDelayActivity` class with the following code.</span></span> <span data-ttu-id="b092e-124">Damit wird die Verzögerung mit einer Dauer von 10 Sekunden konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="b092e-124">This configures the delay to have a duration of 10 seconds.</span></span>

    ```csharp
    public sealed class MyDelayActivity : IActivityTemplateFactory
    {
        public Activity Create(System.Windows.DependencyObject target)
        {
            return new System.Activities.Statements.Delay
            {
                DisplayName = "DelayActivityTemplate",
                Duration = new TimeSpan(0, 0, 10)

            };
        }
    }
    ```

14. <span data-ttu-id="b092e-125">Wählen Sie im Menü **Erstellen** die Option Projekt Mappe **Erstellen** aus, um die DelayActivityTemplate.dll Datei zu generieren.</span><span class="sxs-lookup"><span data-stu-id="b092e-125">Select **Build Solution** from the **Build** menu to generate the DelayActivityTemplate.dll file.</span></span>

### <a name="to-make-the-template-available-in-a-workflow-designer"></a><span data-ttu-id="b092e-126">So machen Sie die Vorlage in einem Workflow-Designer verfügbar</span><span class="sxs-lookup"><span data-stu-id="b092e-126">To make the template available in a Workflow Designer</span></span>

1. <span data-ttu-id="b092e-127">Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf die Projekt Mappe Delta activitytemplate, und wählen Sie **Hinzufügen** und dann **Neues Projekt** aus, um das Dialogfeld **Neues Projekt hinzufügen** zu öffnen</span><span class="sxs-lookup"><span data-stu-id="b092e-127">Right-click the DelayActivityTemplate solution in **Solution Explorer** and choose **Add** and then **New Project** to open the **Add New Project** dialog box.</span></span>

2. <span data-ttu-id="b092e-128">Wählen Sie die Vorlage **Konsolenanwendung für Workflows** aus, benennen Sie Sie `CustomActivityTemplateApp` , und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b092e-128">Select the **Workflow Console Application** template, name it `CustomActivityTemplateApp`, and then click **OK**.</span></span>

3. <span data-ttu-id="b092e-129">Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf das Verzeichnis Verweise des Projekts customactivitytemplateapp, und wählen Sie **Verweis hinzufügen** aus, um das Dialogfeld **Verweis hinzufügen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b092e-129">Right-click the References directory of the CustomActivityTemplateApp project in **Solution Explorer** and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>

4. <span data-ttu-id="b092e-130">Wechseln Sie zur Registerkarte **Projekte** , und wählen Sie in der Spalte **Projekt Name** auf der linken Seite die Option **Delta activitytemplate** aus, und klicken Sie auf **OK** , um einen Verweis auf die DelayActivityTemplate.dll Datei hinzuzufügen, die Sie im ersten Verfahren erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="b092e-130">Go to the **Projects** tab and select **DelayActivityTemplate** from the **Project Name** column on the left and click **OK** to add a reference to the DelayActivityTemplate.dll file that you created in the first procedure.</span></span>

5. <span data-ttu-id="b092e-131">Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt customactivitytemplateapp, und wählen Sie **Erstellen** , um die Anwendung zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="b092e-131">Right-click the CustomActivityTemplateApp project in **Solution Explorer** and choose **Build** to compile the application.</span></span>

6. <span data-ttu-id="b092e-132">Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt customactivitytemplateapp, und wählen Sie **als Startprojekt festlegen** aus.</span><span class="sxs-lookup"><span data-stu-id="b092e-132">Right-click the CustomActivityTemplateApp project in **Solution Explorer** and choose **Set as Startup Project**.</span></span>

7. <span data-ttu-id="b092e-133">Wählen Sie im Menü **Debuggen** die Option **Starten ohne Debugging** aus, und drücken Sie eine beliebige Taste, um fortzufahren, wenn Sie cmd.exe im Fenster</span><span class="sxs-lookup"><span data-stu-id="b092e-133">Select **Start Without Debugging** from the **Debug** menu and press any key to continue when prompted from the cmd.exe window.</span></span>

8. <span data-ttu-id="b092e-134">Öffnen Sie die Datei Workflow1. XAML, und öffnen Sie die **Toolbox**.</span><span class="sxs-lookup"><span data-stu-id="b092e-134">Open the Workflow1.xaml file and open the **Toolbox**.</span></span>

9. <span data-ttu-id="b092e-135">Suchen Sie in der Kategorie " **Delta activitytemplate** " die Vorlage **mydelta-Activity** .</span><span class="sxs-lookup"><span data-stu-id="b092e-135">Locate the **MyDelayActivity** template in the **DelayActivityTemplate** category.</span></span> <span data-ttu-id="b092e-136">Ziehen Sie sie auf die Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="b092e-136">Drag it onto the design surface.</span></span> <span data-ttu-id="b092e-137">Vergewissern Sie sich im Fenster **Eigenschaften** , dass die `Duration` Eigenschaft auf 10 Sekunden festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="b092e-137">Confirm in the **Properties** window that the `Duration` property has been set to 10 seconds.</span></span>

## <a name="example"></a><span data-ttu-id="b092e-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b092e-138">Example</span></span>

 <span data-ttu-id="b092e-139">Die Datei "MyDelayActivity.cs" sollte den folgenden Code enthalten.</span><span class="sxs-lookup"><span data-stu-id="b092e-139">The MyDelayActivity.cs file should contain the following code.</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;

//Namespaces added
using System.Activities;
using System.Activities.Statements;
using System.Activities.Presentation;
using System.Windows;

namespace DelayActivityTemplate
{
    public sealed class MyDelayActivity : IActivityTemplateFactory
    {
        public Activity Create(System.Windows.DependencyObject target)
        {
            return new System.Activities.Statements.Delay
            {
                DisplayName = "DelayActivityTemplate",
                Duration = new TimeSpan(0, 0, 10)

            };
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="b092e-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b092e-140">See also</span></span>

- <xref:System.Activities.Presentation.IActivityTemplateFactory>
- [<span data-ttu-id="b092e-141">Anpassen des Workflowentwurfsvorgangs</span><span class="sxs-lookup"><span data-stu-id="b092e-141">Customizing the Workflow Design Experience</span></span>](customizing-the-workflow-design-experience.md)
