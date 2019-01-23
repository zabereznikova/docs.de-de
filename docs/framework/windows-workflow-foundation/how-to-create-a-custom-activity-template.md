---
title: 'Vorgehensweise: Erstellen einer benutzerdefinierten Aktivitätsvorlage'
ms.date: 03/30/2017
ms.assetid: 6760a5cc-6eb8-465f-b4fa-f89b39539429
ms.openlocfilehash: c90721676fc5b77704ee86bcd5e98c99e3af6683
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54512709"
---
# <a name="how-to-create-a-custom-activity-template"></a><span data-ttu-id="94be8-102">Vorgehensweise: Erstellen einer benutzerdefinierten Aktivitätsvorlage</span><span class="sxs-lookup"><span data-stu-id="94be8-102">How to: Create a Custom Activity Template</span></span>

<span data-ttu-id="94be8-103">Benutzerdefinierte Aktivitätsvorlagen werden verwendet, um die Konfiguration von Aktivitäten, einschließlich benutzerdefinierter zusammengesetzter Aktivitäten, anzupassen. Dadurch müssen Benutzer die Aktivitäten nicht einzeln erstellen und alle zugehörigen Eigenschaften und anderen Einstellungen manuell konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="94be8-103">Custom activity templates are used to customize the configuration of activities, including custom composite activities, so that users do not have to create each activity individually and configure their properties and other settings manually.</span></span> <span data-ttu-id="94be8-104">Diese benutzerdefinierten Vorlagen in verfügbar gemacht werden die **Toolbox** auf die [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] oder in einem neu gehosteten Designer, von dem Benutzer auf können sie die vorkonfigurierte Entwurfsoberfläche ziehen.</span><span class="sxs-lookup"><span data-stu-id="94be8-104">These custom templates can be made available in the **Toolbox** on the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] or from a rehosted designer, from which users can drag them onto the preconfigured design surface.</span></span> [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] <span data-ttu-id="94be8-105">gehören gute Beispiele für solche Vorlagen: die [SendAndReceiveReply-Vorlagendesigner](/visualstudio/workflow-designer/sendandreceivereply-template-designer) und [ReceiveAndSendReply-Vorlagendesigner](/visualstudio/workflow-designer/receiveandsendreply-template-designer) in die [Messaging-Aktivitätsdesigner](/visualstudio/workflow-designer/messaging-activity-designers) Kategorie.</span><span class="sxs-lookup"><span data-stu-id="94be8-105">ships with good examples of such templates: the [SendAndReceiveReply Template Designer](/visualstudio/workflow-designer/sendandreceivereply-template-designer) and the [ReceiveAndSendReply Template Designer](/visualstudio/workflow-designer/receiveandsendreply-template-designer) in the [Messaging Activity Designers](/visualstudio/workflow-designer/messaging-activity-designers) category.</span></span>

 <span data-ttu-id="94be8-106">Das erste Verfahren in diesem Thema wird beschrieben, wie zum Erstellen einer benutzerdefinierten Aktivitätsvorlage für eine **Verzögerung** Aktivität und das zweite Verfahren beschreibt kurz, wie es in zur Verfügung stellen eine [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] zu überprüfen, ob die benutzerdefinierte Vorlage funktioniert.</span><span class="sxs-lookup"><span data-stu-id="94be8-106">The first procedure in this topic describes how to create a custom activity template for a **Delay** activity and the second procedure describes briefly how to make it available in a [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] to verify that the custom template works.</span></span>

 <span data-ttu-id="94be8-107">Benutzerdefinierte Aktivitätsvorlagen müssen <xref:System.Activities.Presentation.IActivityTemplateFactory> implementieren.</span><span class="sxs-lookup"><span data-stu-id="94be8-107">Custom activity templates must implement the <xref:System.Activities.Presentation.IActivityTemplateFactory>.</span></span> <span data-ttu-id="94be8-108">Die Schnittstelle verfügt über eine einzelne <xref:System.Activities.Presentation.IActivityTemplateFactory.Create%2A>-Methode, mit der Sie die in der Vorlage verwendeten Aktivitätsinstanzen erstellen und konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="94be8-108">The interface has a single <xref:System.Activities.Presentation.IActivityTemplateFactory.Create%2A> method with which you can create and configure the activity instances used in the template.</span></span>

## <a name="to-create-a-template-for-the-delay-activity"></a><span data-ttu-id="94be8-109">So erstellen Sie eine Vorlage für die Delay-Aktivität</span><span class="sxs-lookup"><span data-stu-id="94be8-109">To create a template for the Delay activity</span></span>

1.  <span data-ttu-id="94be8-110">Starten Sie Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="94be8-110">Start Visual Studio 2010.</span></span>

2.  <span data-ttu-id="94be8-111">Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="94be8-111">On the **File** menu, point to **New**, and then select **Project**.</span></span>

     <span data-ttu-id="94be8-112">Das Dialogfeld **Neues Projekt** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="94be8-112">The **New Project** dialog box opens.</span></span>

3.  <span data-ttu-id="94be8-113">In der **Projekttypen** wählen Sie im Bereich **Workflow** entweder die **Visual C#-** Projekte oder **Visual Basic** Gruppierungen je Ihre Bevorzugte Sprache.</span><span class="sxs-lookup"><span data-stu-id="94be8-113">In the **Project Types** pane, select **Workflow** from either the **Visual C#** projects or **Visual Basic** groupings depending on your language preference.</span></span>

4.  <span data-ttu-id="94be8-114">In der **Vorlagen** wählen Sie im Bereich **Aktivitätsbibliothek**.</span><span class="sxs-lookup"><span data-stu-id="94be8-114">In the **Templates** pane, select **Activity Library**.</span></span>

5.  <span data-ttu-id="94be8-115">In der **Namen** geben `DelayActivityTemplate`.</span><span class="sxs-lookup"><span data-stu-id="94be8-115">In the **Name** box, enter `DelayActivityTemplate`.</span></span>

6.  <span data-ttu-id="94be8-116">Übernehmen Sie die Standardwerte in den **Speicherort** und **Projektmappenname** Textfelder, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="94be8-116">Accept the defaults in the **Location** and **Solution name** text boxes, and then click **OK**.</span></span>

7.  <span data-ttu-id="94be8-117">Mit der rechten Maustaste in das Verzeichnis "Verweise" des DelayActivityTemplate-Projekts in **Projektmappen-Explorer** , und wählen Sie **Verweis hinzufügen** zum Öffnen der **Verweis hinzufügen** Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="94be8-117">Right-click the References directory of the DelayActivityTemplate project in **Solution Explorer** and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>

8.  <span data-ttu-id="94be8-118">Wechseln Sie zu der **.NET** Registerkarte, und wählen Sie **PresentationFramework** aus der **Komponentenname** Spalte auf der linken Seite und auf **OK** zum Hinzufügen eines Verweises in der Datei "PresentationFramework.dll".</span><span class="sxs-lookup"><span data-stu-id="94be8-118">Go to the **.NET** tab and select **PresentationFramework** from the **Component Name** column on the left and click **OK** to add a reference to the PresentationFramework.dll file.</span></span>

9. <span data-ttu-id="94be8-119">Wiederholen Sie dieses Verfahren, um Verweise auf die Dateien "System.Activities.Presentation.dll" und "WindowsBase.dll" hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="94be8-119">Repeat this procedure to add references to the System.Activities.Presentation.dll and the WindowsBase.dll files.</span></span>

10. <span data-ttu-id="94be8-120">Mit der rechten Maustaste in des Projekts "delayactivitytemplate" im **Projektmappen-Explorer** , und wählen Sie **hinzufügen** und dann **neues Element** zum Öffnen der **neues Element hinzufügen**Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="94be8-120">Right-click the DelayActivityTemplate project in **Solution Explorer** and choose **Add** and then **New Item** to open the **Add New Item** dialog box.</span></span>

11. <span data-ttu-id="94be8-121">Wählen Sie die **Klasse** -Vorlage aus, nennen Sie sie "mydelaytemplate", und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="94be8-121">Select the **Class** template, name it MyDelayTemplate, and then click **OK**.</span></span>

12. <span data-ttu-id="94be8-122">Öffnen Sie die Datei "MyDelayTemplate.cs", und fügen Sie die folgenden Anweisungen hinzu.</span><span class="sxs-lookup"><span data-stu-id="94be8-122">Open the MyDelayTemplate.cs file and add the following statements.</span></span>

    ```
    //Namespaces added
    using System.Activities;
    using System.Activities.Statements;
    using System.Activities.Presentation;
    using System.Windows;
    ```

13. <span data-ttu-id="94be8-123">Implementieren Sie <xref:System.Activities.Presentation.IActivityTemplateFactory> mit der `MyDelayActivity`-Klasse mit dem folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="94be8-123">Implement the <xref:System.Activities.Presentation.IActivityTemplateFactory> with the `MyDelayActivity` class with the following code.</span></span> <span data-ttu-id="94be8-124">Damit wird die Verzögerung mit einer Dauer von 10 Sekunden konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="94be8-124">This configures the delay to have a duration of 10 seconds.</span></span>

    ```
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

14. <span data-ttu-id="94be8-125">Wählen Sie **Projektmappe** aus der **erstellen** Menü, um die Datei "DelayActivityTemplate.dll" zu generieren.</span><span class="sxs-lookup"><span data-stu-id="94be8-125">Select **Build Solution** from the **Build** menu to generate the DelayActivityTemplate.dll file.</span></span>

### <a name="to-make-the-template-available-in-a-workflow-designer"></a><span data-ttu-id="94be8-126">So machen Sie die Vorlage in einem Workflow-Designer verfügbar</span><span class="sxs-lookup"><span data-stu-id="94be8-126">To make the template available in a Workflow Designer</span></span>

1.  <span data-ttu-id="94be8-127">Mit der rechten Maustaste in der Projektmappe "delayactivitytemplate" im **Projektmappen-Explorer** , und wählen Sie **hinzufügen** und dann **neues Projekt** zum Öffnen der **neues Projekt hinzufügen** Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="94be8-127">Right-click the DelayActivityTemplate solution in **Solution Explorer** and choose **Add** and then **New Project** to open the **Add New Project** dialog box.</span></span>

2.  <span data-ttu-id="94be8-128">Wählen Sie die **Konsolenanwendung für Workflows** Vorlage, nennen Sie sie `CustomActivityTemplateApp`, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="94be8-128">Select the **Workflow Console Application** template, name it `CustomActivityTemplateApp`, and then click **OK**.</span></span>

3.  <span data-ttu-id="94be8-129">Mit der rechten Maustaste in das Verzeichnis "Verweise" des CustomActivityTemplateApp-Projekts in **Projektmappen-Explorer** , und wählen Sie **Verweis hinzufügen** zum Öffnen der **Verweis hinzufügen** Dialogfeld Box.</span><span class="sxs-lookup"><span data-stu-id="94be8-129">Right-click the References directory of the CustomActivityTemplateApp project in **Solution Explorer** and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>

4.  <span data-ttu-id="94be8-130">Wechseln Sie zu der **Projekte** Registerkarte, und wählen Sie **"delayactivitytemplate"** aus der **Projektname** Spalte auf der linken Seite und auf **OK** Hinzufügen einer Ein Verweis auf die Datei "DelayActivityTemplate.dll", die Sie im ersten Verfahren erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="94be8-130">Go to the **Projects** tab and select **DelayActivityTemplate** from the **Project Name** column on the left and click **OK** to add a reference to the DelayActivityTemplate.dll file that you created in the first procedure.</span></span>

5.  <span data-ttu-id="94be8-131">Mit der rechten Maustaste in des Projekts "customactivitytemplateapp" im **Projektmappen-Explorer** , und wählen Sie **erstellen** zum Kompilieren der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="94be8-131">Right-click the CustomActivityTemplateApp project in **Solution Explorer** and choose **Build** to compile the application.</span></span>

6.  <span data-ttu-id="94be8-132">Mit der rechten Maustaste in des Projekts "customactivitytemplateapp" im **Projektmappen-Explorer** , und wählen Sie **als Startprojekt festlegen**.</span><span class="sxs-lookup"><span data-stu-id="94be8-132">Right-click the CustomActivityTemplateApp project in **Solution Explorer** and choose **Set as Startup Project**.</span></span>

7.  <span data-ttu-id="94be8-133">Wählen Sie **Starten ohne Debugging** aus der **Debuggen** Menü, und drücken Sie eine beliebige Taste, um fortgesetzt, wenn Sie aufgefordert, aus dem cmd.exe-Fenster.</span><span class="sxs-lookup"><span data-stu-id="94be8-133">Select **Start Without Debugging** from the **Debug** menu and press any key to continue when prompted from the cmd.exe window.</span></span>

8.  <span data-ttu-id="94be8-134">Öffnen Sie die Datei "Workflow1.xaml", und öffnen Sie die **Toolbox**.</span><span class="sxs-lookup"><span data-stu-id="94be8-134">Open the Workflow1.xaml file and open the **Toolbox**.</span></span>

9. <span data-ttu-id="94be8-135">Suchen Sie die **MyDelayActivity** Vorlage in der **"delayactivitytemplate"** Kategorie.</span><span class="sxs-lookup"><span data-stu-id="94be8-135">Locate the **MyDelayActivity** template in the **DelayActivityTemplate** category.</span></span> <span data-ttu-id="94be8-136">Ziehen Sie sie auf die Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="94be8-136">Drag it onto the design surface.</span></span> <span data-ttu-id="94be8-137">Vergewissern Sie sich der **Eigenschaften** Fenster, die die `Duration` -Eigenschaft auf 10 Sekunden festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="94be8-137">Confirm in the **Properties** window that the `Duration` property has been set to 10 seconds.</span></span>

## <a name="example"></a><span data-ttu-id="94be8-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="94be8-138">Example</span></span>
 <span data-ttu-id="94be8-139">Die Datei "MyDelayActivity.cs" sollte den folgenden Code enthalten.</span><span class="sxs-lookup"><span data-stu-id="94be8-139">The MyDelayActivity.cs file should contain the following code.</span></span>

```
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

## <a name="see-also"></a><span data-ttu-id="94be8-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94be8-140">See also</span></span>

- <xref:System.Activities.Presentation.IActivityTemplateFactory>
- [<span data-ttu-id="94be8-141">Anpassen des Workflowentwurfsvorgangs</span><span class="sxs-lookup"><span data-stu-id="94be8-141">Customizing the Workflow Design Experience</span></span>](../../../docs/framework/windows-workflow-foundation/customizing-the-workflow-design-experience.md)