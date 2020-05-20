---
title: 'Vorgehensweise: Erstellen eines benutzerdefinierten Aktivitätsdesigners'
description: In diesem Artikel wird beschrieben, wie ein benutzerdefinierter Workflow Foundation-Aktivitäts Designer erstellt wird, der über eine Ablage Zone verfügt, in der eine beliebige Aktivität platziert werden kann.
ms.date: 03/30/2017
ms.assetid: 2f3aade6-facc-44ef-9657-a407ef8b9b31
ms.openlocfilehash: 015efd1e482e2b531d28b9caec411c76116c9653
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419784"
---
# <a name="how-to-create-a-custom-activity-designer"></a><span data-ttu-id="b5388-103">Vorgehensweise: Erstellen eines benutzerdefinierten Aktivitätsdesigners</span><span class="sxs-lookup"><span data-stu-id="b5388-103">How to: Create a Custom Activity Designer</span></span>

<span data-ttu-id="b5388-104">Benutzerdefinierte Aktivitätsdesigner werden in der Regel implementiert, um die zugehörigen Aktivitäten mit anderen Aktivitäten zusammenzusetzen, deren Designer mit ihnen auf der Entwurfsoberfläche abgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="b5388-104">Custom activity designers are typically implemented so that their associated activities are composable with other activities whose designers can be dropped on to the design surface with them.</span></span> <span data-ttu-id="b5388-105">Diese Funktion erfordert, dass ein benutzerdefinierter Aktivitäts Designer eine "Ablage Zone" bereitstellt, in der eine beliebige Aktivität platziert werden kann, und auch die Möglichkeit, die resultierende Auflistung von Elementen auf der Entwurfs Oberfläche zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="b5388-105">This functionality requires that a custom activity designer provide a "drop zone" where an arbitrary activity can be placed and also the means to manage the resulting collection of elements on the design surface.</span></span> <span data-ttu-id="b5388-106">In diesem Thema wird beschrieben, wie ein benutzerdefinierter Aktivitätsdesigner erstellt wird, der eine solche Ablagezone enthält und die Bearbeitungsfunktionen zur Verwaltung der Auflistung von Designerelementen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="b5388-106">This topic describes how to create a custom activity designer that contains such a drop zone and how to create a custom activity designer that provides that editing functionality needed to manage the collection of designer elements.</span></span>

<span data-ttu-id="b5388-107">Benutzerdefinierte Aktivitätsdesigner erben in der Regel von <xref:System.Activities.Presentation.ActivityDesigner>. Dies ist der standardmäßige Designertyp für alle Aktivitäten ohne bestimmten Designer.</span><span class="sxs-lookup"><span data-stu-id="b5388-107">Custom activity designers typically inherit from <xref:System.Activities.Presentation.ActivityDesigner> which is the default base activity designer type for any activities without a specific designer.</span></span> <span data-ttu-id="b5388-108">Dieser Typ stellt Entwurfszeitfunktionen für die Interaktion mit dem Eigenschaftenraster und die Konfiguration von grundlegenden Aspekten wie Farbe und Symbole bereit.</span><span class="sxs-lookup"><span data-stu-id="b5388-108">This type provides the design-time experience of interacting with the property grid and configuring basic aspects such as managing colors and icons.</span></span>

<span data-ttu-id="b5388-109"><xref:System.Activities.Presentation.ActivityDesigner> verwendet zwei Hilfssteuerelemente (<xref:System.Activities.Presentation.WorkflowItemPresenter> und <xref:System.Activities.Presentation.WorkflowItemsPresenter>), die das Entwickeln benutzerdefinierter Aktivitätsdesigner vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="b5388-109"><xref:System.Activities.Presentation.ActivityDesigner> uses two helper controls, <xref:System.Activities.Presentation.WorkflowItemPresenter> and <xref:System.Activities.Presentation.WorkflowItemsPresenter> to make it easier to develop custom activity designers.</span></span> <span data-ttu-id="b5388-110">Sie behandeln die allgemeine Funktionalität wie Ziehen und Ablegen von untergeordneten Elementen sowie Löschen, Auswählen und Hinzufügen dieser untergeordneten Elemente.</span><span class="sxs-lookup"><span data-stu-id="b5388-110">They handle common functionality like dragging and dropping of child elements, deletion, selection, and addition of those child elements.</span></span> <span data-ttu-id="b5388-111">Das- <xref:System.Activities.Presentation.WorkflowItemPresenter> Element ermöglicht ein einzelnes untergeordnetes Benutzeroberflächen Element in, das die "Ablage Zone" bereitstellt, während der <xref:System.Activities.Presentation.WorkflowItemsPresenter> Unterstützung für mehrere Benutzeroberflächen Elemente bereitstellen kann, einschließlich zusätzlicher Funktionen wie das Anordnen, verschieben, löschen und Hinzufügen von untergeordneten Elementen.</span><span class="sxs-lookup"><span data-stu-id="b5388-111">The <xref:System.Activities.Presentation.WorkflowItemPresenter> allows a single child UI element inside, providing the "drop zone", it while the <xref:System.Activities.Presentation.WorkflowItemsPresenter> can provide support multiple UI elements, including additional functionality like the ordering, moving, deleting, and adding of child elements.</span></span>

<span data-ttu-id="b5388-112">Der andere wichtige Teil der Story, der in der Implementierung eines benutzerdefinierten Aktivitäts Designers hervorgehoben werden muss, bezieht sich auf die Art und Weise, in der die visuellen Bearbeitungen mithilfe der WPF-Datenbindung an die Instanz gebunden werden, die im Arbeitsspeicher des Designers gespeichert ist</span><span class="sxs-lookup"><span data-stu-id="b5388-112">The other key part of the story that needs highlighting in the implementation of a custom activity designer concerns the way in which the visual edits are bound using WPF data binding to the instance stored in memory of what we are editing in the designer.</span></span> <span data-ttu-id="b5388-113">Hierzu dient die Modellelementstruktur, die auch zur Aktivierung der Änderungsbenachrichtigung und der Nachverfolgung von Ereignissen wie Zustandsänderungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b5388-113">This is accomplished by the Model Item tree, which is also responsible for enabling change notification and the tracking of events like changes in states.</span></span>

<span data-ttu-id="b5388-114">In diesem Thema werden zwei Prozeduren beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b5388-114">This topic outlines two procedures.</span></span>

1. <span data-ttu-id="b5388-115">Die erste Prozedur beschreibt, wie ein benutzerdefinierter Aktivitätsdesigner mit <xref:System.Activities.Presentation.WorkflowItemPresenter> erstellt wird, der die Ablagezone für andere Aktivitäten bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="b5388-115">The first procedure describes how to create a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemPresenter> that provides the drop zone that receives other activities.</span></span> <span data-ttu-id="b5388-116">Dieses Verfahren basiert auf dem Beispiel [benutzerdefinierte zusammengesetzte Designer-Workflow Element Presenter](./samples/custom-composite-designers-workflow-item-presenter.md) .</span><span class="sxs-lookup"><span data-stu-id="b5388-116">This procedure is based on the [Custom Composite Designers - Workflow Item Presenter](./samples/custom-composite-designers-workflow-item-presenter.md) sample.</span></span>

2. <span data-ttu-id="b5388-117">Die zweite Prozedur beschreibt, wie ein benutzerdefinierter Aktivitätsdesigner mit <xref:System.Activities.Presentation.WorkflowItemsPresenter> erstellt wird, der die zur Bearbeitung einer Auflistung von Elementen benötigten Funktionen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="b5388-117">The second procedure describes how to create a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemsPresenter> that provides the functionality needed to edit of a collection of contained elements.</span></span> <span data-ttu-id="b5388-118">Dieses Verfahren basiert auf dem Beispiel [benutzerdefinierte zusammengesetzte Designer-Workflow Items Presenter](./samples/custom-composite-designers-workflow-items-presenter.md) .</span><span class="sxs-lookup"><span data-stu-id="b5388-118">This procedure is based on the [Custom Composite Designers - Workflow Items Presenter](./samples/custom-composite-designers-workflow-items-presenter.md) sample.</span></span>

## <a name="to-create-a-custom-activity-designer-with-a-drop-zone-using-workflowitempresenter"></a><span data-ttu-id="b5388-119">So erstellen Sie einen benutzerdefinierten Aktivitätsdesigner, der eine Ablagezone bereitstellt, mit WorkflowItemPresenter</span><span class="sxs-lookup"><span data-stu-id="b5388-119">To create a custom activity designer with a drop zone using WorkflowItemPresenter</span></span>

1. <span data-ttu-id="b5388-120">Starten Sie Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="b5388-120">Start Visual Studio 2010.</span></span>

2. <span data-ttu-id="b5388-121">Zeigen Sie im Menü **Datei** auf **neu**, und wählen Sie dann **Projekt...** aus.</span><span class="sxs-lookup"><span data-stu-id="b5388-121">On the **File** menu, point to **New**, and then select **Project…**.</span></span>

     <span data-ttu-id="b5388-122">Das Dialogfeld **Neues Projekt** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b5388-122">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="b5388-123">Wählen Sie im Bereich **installierte Vorlagen** in der Kategorie bevorzugte Sprache die Option **Windows** aus.</span><span class="sxs-lookup"><span data-stu-id="b5388-123">In the **Installed Templates** pane, select **Windows** from your preferred language category.</span></span>

4. <span data-ttu-id="b5388-124">Wählen Sie im Bereich **Vorlagen** die Option **WPF-Anwendung**aus.</span><span class="sxs-lookup"><span data-stu-id="b5388-124">In the **Templates** pane, select **WPF Application**.</span></span>

5. <span data-ttu-id="b5388-125">Geben Sie im Feld **Name den Namen** ein `UsingWorkflowItemPresenter` .</span><span class="sxs-lookup"><span data-stu-id="b5388-125">In the **Name** box, enter `UsingWorkflowItemPresenter`.</span></span>

6. <span data-ttu-id="b5388-126">Geben Sie im Feld **Speicherort** das Verzeichnis ein, in dem Sie das Projekt speichern möchten, oder klicken Sie auf **Durchsuchen** , um zu diesem Verzeichnis zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="b5388-126">In the **Location** box, enter the directory in which you want to save your project, or click **Browse** to navigate to it.</span></span>

7. <span data-ttu-id="b5388-127">Übernehmen Sie **im Feldprojekt Mappe den Standard** Wert.</span><span class="sxs-lookup"><span data-stu-id="b5388-127">In the **Solution** box, accept the default value.</span></span>

8. <span data-ttu-id="b5388-128">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b5388-128">Click **OK**.</span></span>

9. <span data-ttu-id="b5388-129">Klicken Sie im **Projektmappen-Explorer**mit der rechten Maustaste auf die Datei " *mainwindows. XAML* ", und wählen Sie im Dialogfeld **Microsoft Visual Studio** die Option **Löschen** und **OK** bestätigen aus.</span><span class="sxs-lookup"><span data-stu-id="b5388-129">Right-click the *MainWindows.xaml* file in the **Solution Explorer**, select **Delete** and confirm **OK** in the **Microsoft Visual Studio** dialog box.</span></span>

10. <span data-ttu-id="b5388-130">Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt usingworkflowitempresenter, wählen Sie **Hinzufügen**und dann **Neues Element... aus.**</span><span class="sxs-lookup"><span data-stu-id="b5388-130">Right-click the UsingWorkflowItemPresenter project in **Solution Explorer**, select **Add**, then **New Item…**</span></span> <span data-ttu-id="b5388-131">um das Dialogfeld **Neues Element hinzufügen** aufzubringen, und wählen Sie im Abschnitt **installierte Vorlagen** auf der linken Seite die Kategorie **WPF** aus.</span><span class="sxs-lookup"><span data-stu-id="b5388-131">to bring up the **Add New Item** dialog and select the **WPF** category from the **Installed Templates** section on the left.</span></span>

11. <span data-ttu-id="b5388-132">Wählen Sie die Vorlage **Fenster (WPF)** aus, benennen Sie Sie `RehostingWFDesigner` , und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="b5388-132">Select the  **Window (WPF)** template, name it `RehostingWFDesigner`, and click **Add**.</span></span>

12. <span data-ttu-id="b5388-133">Öffnen Sie die Datei " *rehostingwfdesigner. XAML* ", und fügen Sie den folgenden Code in die Datei ein, um die Benutzeroberfläche für die Anwendung zu definieren:</span><span class="sxs-lookup"><span data-stu-id="b5388-133">Open the *RehostingWFDesigner.xaml* file and paste the following code into it to define the UI for the application:</span></span>

    ```xaml
    <Window x:Class=" UsingWorkflowItemPresenter.RehostingWFDesigner"
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
            xmlns:sapt="clr-namespace:System.Activities.Presentation.Toolbox;assembly=System.Activities.Presentation"
            xmlns:sys="clr-namespace:System;assembly=mscorlib"
            Title="Window1" Height="600" Width="900">
        <Window.Resources>
            <sys:String x:Key="AssemblyName">System.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35</sys:String>
        </Window.Resources>
        <Grid>
            <Grid.ColumnDefinitions>
                <ColumnDefinition Width="2*"/>
                <ColumnDefinition Width="7*"/>
                <ColumnDefinition Width="3*"/>
            </Grid.ColumnDefinitions>
            <Border Grid.Column="0">
                <sapt:ToolboxControl Name="Toolbox">
                    <sapt:ToolboxCategory CategoryName="Basic">
                        <sapt:ToolboxItemWrapper AssemblyName="{StaticResource AssemblyName}" >
                            <sapt:ToolboxItemWrapper.ToolName>
                                System.Activities.Statements.Sequence
                            </sapt:ToolboxItemWrapper.ToolName>
                           </sapt:ToolboxItemWrapper>
                        <sapt:ToolboxItemWrapper  AssemblyName="{StaticResource AssemblyName}">
                            <sapt:ToolboxItemWrapper.ToolName>
                                System.Activities.Statements.WriteLine
                            </sapt:ToolboxItemWrapper.ToolName>

                        </sapt:ToolboxItemWrapper>
                        <sapt:ToolboxItemWrapper  AssemblyName="{StaticResource AssemblyName}">
                            <sapt:ToolboxItemWrapper.ToolName>
                                System.Activities.Statements.If
                            </sapt:ToolboxItemWrapper.ToolName>

                        </sapt:ToolboxItemWrapper>
                        <sapt:ToolboxItemWrapper  AssemblyName="{StaticResource AssemblyName}">
                            <sapt:ToolboxItemWrapper.ToolName>
                                System.Activities.Statements.While
                            </sapt:ToolboxItemWrapper.ToolName>

                        </sapt:ToolboxItemWrapper>
                    </sapt:ToolboxCategory>
                </sapt:ToolboxControl>
            </Border>
            <Border Grid.Column="1" Name="DesignerBorder"/>
            <Border Grid.Column="2" Name="PropertyBorder"/>
        </Grid>
    </Window>
    ```

13. <span data-ttu-id="b5388-134">Um einem Aktivitätsdesigner einen Aktivitätstyp zuzuordnen, müssen Sie den Aktivitätsdesigner im Metadatenspeicher registrieren.</span><span class="sxs-lookup"><span data-stu-id="b5388-134">To associate an activity designer with an activity type, you must register that activity designer with the metadata store.</span></span> <span data-ttu-id="b5388-135">Fügen Sie hierzu der `RegisterMetadata`-Klasse die `RehostingWFDesigner`-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="b5388-135">To do this, add the `RegisterMetadata` method to the `RehostingWFDesigner` class.</span></span> <span data-ttu-id="b5388-136">Erstellen Sie innerhalb des Bereichs der `RegisterMetadata`-Methode ein <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder>-Objekt, und rufen Sie die <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder.AddCustomAttributes%2A>-Methode auf, um dem Objekt die Attribute hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b5388-136">Within the scope of the  `RegisterMetadata` method, create an <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder> object and call the <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder.AddCustomAttributes%2A> method to add the attributes to it.</span></span> <span data-ttu-id="b5388-137">Rufen Sie die <xref:System.Activities.Presentation.Metadata.MetadataStore.AddAttributeTable%2A>-Methode auf, um dem Metadatenspeicher das <xref:System.Activities.Presentation.Metadata.AttributeTable>-Objekt hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b5388-137">Call the <xref:System.Activities.Presentation.Metadata.MetadataStore.AddAttributeTable%2A> method to add the <xref:System.Activities.Presentation.Metadata.AttributeTable> to the metadata store.</span></span> <span data-ttu-id="b5388-138">Der folgende Code enthält die Rehosting-Logik für den Designer.</span><span class="sxs-lookup"><span data-stu-id="b5388-138">The following code contains the rehosting logic for the designer.</span></span> <span data-ttu-id="b5388-139">Damit werden die Metadaten registriert, die `SimpleNativeActivity` wird in die Toolbox eingefügt und der Workflow wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="b5388-139">It registers the metadata, puts the `SimpleNativeActivity` into the toolbox, and creates the workflow.</span></span> <span data-ttu-id="b5388-140">Fügen Sie diesen Code in die *RehostingWFDesigner.XAML.cs* -Datei ein.</span><span class="sxs-lookup"><span data-stu-id="b5388-140">Put this code into the *RehostingWFDesigner.xaml.cs* file.</span></span>

    ```csharp
    using System;
    using System.Activities.Core.Presentation;
    using System.Activities.Presentation;
    using System.Activities.Presentation.Metadata;
    using System.Activities.Presentation.Toolbox;
    using System.Activities.Statements;
    using System.ComponentModel;
    using System.Windows;

    namespace UsingWorkflowItemPresenter
    {
        // Interaction logic for RehostingWFDesigner.xaml
        public partial class RehostingWFDesigner
        {
            public RehostingWFDesigner()
            {
                InitializeComponent();
            }

            protected override void OnInitialized(EventArgs e)
            {
                base.OnInitialized(e);
                // Register metadata.
                (new DesignerMetadata()).Register();
                RegisterCustomMetadata();
                // Add custom activity to toolbox.
                Toolbox.Categories.Add(new ToolboxCategory("Custom activities"));
                Toolbox.Categories[1].Add(new ToolboxItemWrapper(typeof(SimpleNativeActivity)));

                // Create the workflow designer.
                var wd = new WorkflowDesigner();
                wd.Load(new Sequence());
                DesignerBorder.Child = wd.View;
                PropertyBorder.Child = wd.PropertyInspectorView;

            }

            void RegisterCustomMetadata()
            {
                var builder = new AttributeTableBuilder();
                builder.AddCustomAttributes(typeof(SimpleNativeActivity), new DesignerAttribute(typeof(SimpleNativeDesigner)));
                MetadataStore.AddAttributeTable(builder.CreateTable());
            }
        }
    }
    ```

14. <span data-ttu-id="b5388-141">Klicken Sie in Projektmappen-Explorer mit der rechten Maustaste auf das Verzeichnis Verweise, und wählen Sie **Verweis hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="b5388-141">Right-click the References directory in Solution Explorer and select **Add Reference …**</span></span> <span data-ttu-id="b5388-142">, wenn das Dialogfeld **Verweis hinzufügen** angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b5388-142">to bring up the **Add Reference** dialog.</span></span>

15. <span data-ttu-id="b5388-143">Klicken Sie auf die Registerkarte **.net** , suchen Sie die Assembly **System. Activities. Core. Presentation**, wählen Sie Sie aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b5388-143">Click the **.NET** tab, locate the assembly named **System.Activities.Core.Presentation**, select it and click **OK**.</span></span>

16. <span data-ttu-id="b5388-144">Fügen Sie auf die gleiche Weise den folgenden Assemblys Verweise hinzu:</span><span class="sxs-lookup"><span data-stu-id="b5388-144">Using the same procedure, add references to the following assemblies:</span></span>

    1. <span data-ttu-id="b5388-145">System.Data.DataSetExtensions.dll</span><span class="sxs-lookup"><span data-stu-id="b5388-145">System.Data.DataSetExtensions.dll</span></span>

    2. <span data-ttu-id="b5388-146">System.Activities.Presentation.dll</span><span class="sxs-lookup"><span data-stu-id="b5388-146">System.Activities.Presentation.dll</span></span>

    3. <span data-ttu-id="b5388-147">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="b5388-147">System.ServiceModel.Activities.dll</span></span>

17. <span data-ttu-id="b5388-148">Öffnen Sie die Datei " *app. XAML* ", und ändern Sie den Wert von StartupUri in "rehostingwfdesigner. XAML".</span><span class="sxs-lookup"><span data-stu-id="b5388-148">Open the *App.xaml* file and change the value of the StartUpUri to "RehostingWFDesigner.xaml".</span></span>

18. <span data-ttu-id="b5388-149">Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt usingworkflowitempresenter, wählen Sie **Hinzufügen**und dann **Neues Element... aus.**</span><span class="sxs-lookup"><span data-stu-id="b5388-149">Right-click the UsingWorkflowItemPresenter project in **Solution Explorer**, select **Add**, then **New Item…**</span></span> <span data-ttu-id="b5388-150">um das Dialogfeld **Neues Element hinzufügen** zu aktivieren, wählen Sie im Abschnitt **installierte Vorlagen** auf der linken Seite die **Workflow** Kategorie aus.</span><span class="sxs-lookup"><span data-stu-id="b5388-150">to bring up the **Add New Item** dialog and select the **Workflow** category form the **Installed Templates** section on the left.</span></span>

19. <span data-ttu-id="b5388-151">Wählen Sie die Vorlage **Aktivitäts Designer** aus, benennen Sie Sie `SimpleNativeDesigner` , und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="b5388-151">Select the **Activity Designer** template, name it `SimpleNativeDesigner`, and click **Add**.</span></span>

20. <span data-ttu-id="b5388-152">Öffnen Sie die Datei *simplenativedesigner. XAML* , und fügen Sie den folgenden Code in die Datei ein.</span><span class="sxs-lookup"><span data-stu-id="b5388-152">Open the *SimpleNativeDesigner.xaml* file and paste the following code into it.</span></span> <span data-ttu-id="b5388-153">Beachten Sie, dass in diesem Code <xref:System.Activities.Presentation.ActivityDesigner> als Stammelement verwendet wird. Er zeigt, wie <xref:System.Activities.Presentation.WorkflowItemPresenter> mithilfe von Bindung in Ihren Designer integriert wird, sodass im zusammengesetzten Aktivitätsdesigner ein untergeordneter Typ angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="b5388-153">Note this code uses <xref:System.Activities.Presentation.ActivityDesigner> as your root element and shows how binding is used to integrate <xref:System.Activities.Presentation.WorkflowItemPresenter> into your designer so a child type can be displayed in your composite activity designer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b5388-154">Mit dem Schema für <xref:System.Activities.Presentation.ActivityDesigner> können Sie dem benutzerdefinierten Aktivitätsdesigner nur ein untergeordnetes Element hinzufügen. Bei diesem Element kann es sich jedoch um ein `StackPanel`, ein `Grid` oder um ein anderes zusammengesetztes Benutzeroberflächenelement handeln.</span><span class="sxs-lookup"><span data-stu-id="b5388-154">The schema for <xref:System.Activities.Presentation.ActivityDesigner> allows the addition of only one child element to your custom activity designer definition; however, this element could be a `StackPanel`, `Grid`, or some other composite UI element.</span></span>

    ```xaml
    <sap:ActivityDesigner x:Class=" UsingWorkflowItemPresenter.SimpleNativeDesigner"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:sap="clr-namespace:System.Activities.Presentation;assembly=System.Activities.Presentation"
        xmlns:sapv="clr-namespace:System.Activities.Presentation.View;assembly=System.Activities.Presentation">
        <sap:ActivityDesigner.Resources>
            <DataTemplate x:Key="Collapsed">
                <StackPanel>
                    <TextBlock>This is the collapsed view</TextBlock>
                </StackPanel>
            </DataTemplate>
            <DataTemplate x:Key="Expanded">
                <StackPanel>
                    <TextBlock>Custom Text</TextBlock>
                    <sap:WorkflowItemPresenter Item="{Binding Path=ModelItem.Body, Mode=TwoWay}"
                                            HintText="Please drop an activity here" />
                </StackPanel>
            </DataTemplate>
            <Style x:Key="ExpandOrCollapsedStyle" TargetType="{x:Type ContentPresenter}">
                <Setter Property="ContentTemplate" Value="{DynamicResource Collapsed}"/>
                <Style.Triggers>
                    <DataTrigger Binding="{Binding Path=ShowExpanded}" Value="true">
                        <Setter Property="ContentTemplate" Value="{DynamicResource Expanded}"/>
                    </DataTrigger>
                </Style.Triggers>
            </Style>
        </sap:ActivityDesigner.Resources>
        <Grid>
            <ContentPresenter Style="{DynamicResource ExpandOrCollapsedStyle}" Content="{Binding}" />
        </Grid>
    </sap:ActivityDesigner>
    ```

21. <span data-ttu-id="b5388-155">Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt usingworkflowitempresenter, wählen Sie **Hinzufügen**und dann **Neues Element... aus.**</span><span class="sxs-lookup"><span data-stu-id="b5388-155">Right-click the UsingWorkflowItemPresenter project in **Solution Explorer**, select **Add**, then **New Item…**</span></span> <span data-ttu-id="b5388-156">um das Dialogfeld **Neues Element hinzufügen** zu aktivieren, wählen Sie im Abschnitt **installierte Vorlagen** auf der linken Seite die **Workflow** Kategorie aus.</span><span class="sxs-lookup"><span data-stu-id="b5388-156">to bring up the **Add New Item** dialog and select the **Workflow** category form the **Installed Templates** section on the left.</span></span>

22. <span data-ttu-id="b5388-157">Wählen Sie die Vorlage **Code Aktivität** aus, benennen Sie Sie `SimpleNativeActivity` , und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="b5388-157">Select the  **Code Activity** template, name it `SimpleNativeActivity`, and click **Add**.</span></span>

23. <span data-ttu-id="b5388-158">Implementieren Sie die- `SimpleNativeActivity` Klasse, indem Sie den folgenden Code in die *SimpleNativeActivity.cs* -Datei eingeben:</span><span class="sxs-lookup"><span data-stu-id="b5388-158">Implement the `SimpleNativeActivity` class by entering the following code into the *SimpleNativeActivity.cs* file:</span></span>

    ```csharp
    using System.Activities;

    namespace UsingWorkflowItemPresenter
    {
        public sealed class SimpleNativeActivity : NativeActivity
        {
            // this property contains an activity that will be scheduled in the execute method
            // the WorkflowItemPresenter in the designer is bound to this to enable editing
            // of the value
            public Activity Body { get; set; }

            protected override void CacheMetadata(NativeActivityMetadata metadata)
            {
               metadata.AddChild(Body);
               base.CacheMetadata(metadata);

            }

            protected override void Execute(NativeActivityContext context)
            {
                context.ScheduleActivity(Body);
            }
        }
    }
    ```

24. <span data-ttu-id="b5388-159">Wählen Sie im Menü **Erstellen** die Option Projekt Mappe **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="b5388-159">Select **Build Solution** from the **Build** menu.</span></span>

25. <span data-ttu-id="b5388-160">Klicken Sie im Menü **Debuggen** auf **Starten ohne Debugging** , um das neu gehostete benutzerdefinierte Entwurfs Fenster zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b5388-160">Select **Start Without Debugging** from the **Debug** menu to open the rehosted custom design window.</span></span>

### <a name="to-create-a-custom-activity-designer-using-workflowitemspresenter"></a><span data-ttu-id="b5388-161">So erstellen Sie einen benutzerdefinierten Aktivitätsdesigner mit WorkflowItemsPresenter</span><span class="sxs-lookup"><span data-stu-id="b5388-161">To create a custom activity designer using WorkflowItemsPresenter</span></span>

1. <span data-ttu-id="b5388-162">Die Prozedur für den zweiten benutzerdefinierten Aktivitäts Designer ist der parallele der erste mit einigen Änderungen, der erste besteht darin, die zweite Anwendung zu benennen `UsingWorkflowItemsPresenter` .</span><span class="sxs-lookup"><span data-stu-id="b5388-162">The procedure for the second custom activity designer is the parallels the first with a few modifications, the first of which is to name the second application `UsingWorkflowItemsPresenter`.</span></span> <span data-ttu-id="b5388-163">Außerdem wird mit dieser Anwendung keine neue benutzerdefinierte Aktivität definiert.</span><span class="sxs-lookup"><span data-stu-id="b5388-163">Also this application does not define a new custom activity.</span></span>

2. <span data-ttu-id="b5388-164">Wichtige Unterschiede sind in den Dateien " *customparalleldesigner. XAML* " und " *RehostingWFDesigner.XAML.cs* " enthalten.</span><span class="sxs-lookup"><span data-stu-id="b5388-164">Key differences are contained in the *CustomParallelDesigner.xaml* and *RehostingWFDesigner.xaml.cs* files.</span></span> <span data-ttu-id="b5388-165">Im folgenden finden Sie den Code aus der Datei " *customparalleldesigner. XAML* ", die die Benutzeroberfläche definiert:</span><span class="sxs-lookup"><span data-stu-id="b5388-165">Here is the code from the *CustomParallelDesigner.xaml* file that defines the UI:</span></span>

    ```xaml
    <sap:ActivityDesigner x:Class=" UsingWorkflowItemsPresenter.CustomParallelDesigner"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:sap="clr-namespace:System.Activities.Presentation;assembly=System.Activities.Presentation"
        xmlns:sapv="clr-namespace:System.Activities.Presentation.View;assembly=System.Activities.Presentation">
        <sap:ActivityDesigner.Resources>
            <DataTemplate x:Key="Collapsed">
                <TextBlock>This is the Collapsed View</TextBlock>
            </DataTemplate>
            <DataTemplate x:Key="Expanded">
                <StackPanel>
                    <TextBlock HorizontalAlignment="Center">This is the</TextBlock>
                    <TextBlock HorizontalAlignment="Center">extended view</TextBlock>
                    <sap:WorkflowItemsPresenter HintText="Drop Activities Here"
                                        Items="{Binding Path=ModelItem.Branches}">
                        <sap:WorkflowItemsPresenter.SpacerTemplate>
                            <DataTemplate>
                                <Ellipse Width="10" Height="10" Fill="Black"/>
                            </DataTemplate>
                        </sap:WorkflowItemsPresenter.SpacerTemplate>
                        <sap:WorkflowItemsPresenter.ItemsPanel>
                            <ItemsPanelTemplate>
                                <StackPanel Orientation="Horizontal"/>
                            </ItemsPanelTemplate>
                        </sap:WorkflowItemsPresenter.ItemsPanel>
                    </sap:WorkflowItemsPresenter>
                </StackPanel>
            </DataTemplate>
            <Style x:Key="ExpandOrCollapsedStyle" TargetType="{x:Type ContentPresenter}">
                <Setter Property="ContentTemplate" Value="{DynamicResource Collapsed}"/>
                <Style.Triggers>
                    <DataTrigger Binding="{Binding Path=ShowExpanded}" Value="true">
                        <Setter Property="ContentTemplate" Value="{DynamicResource Expanded}"/>
                    </DataTrigger>
                </Style.Triggers>
            </Style>
        </sap:ActivityDesigner.Resources>
        <Grid>
            <ContentPresenter Style="{DynamicResource ExpandOrCollapsedStyle}" Content="{Binding}"/>
        </Grid>
    </sap:ActivityDesigner>
    ```

3. <span data-ttu-id="b5388-166">Im folgenden finden Sie den Code aus der *RehostingWFDesigner.XAML.cs* -Datei, die die neuhostinglogik bereitstellt:</span><span class="sxs-lookup"><span data-stu-id="b5388-166">Here is the code from the *RehostingWFDesigner.xaml.cs* file that provides the rehosting logic:</span></span>

    ```csharp
    using System;
    using System.Activities.Core.Presentation;
    using System.Activities.Presentation;
    using System.Activities.Presentation.Metadata;
    using System.Activities.Statements;
    using System.ComponentModel;
    using System.Windows;

    namespaceUsingWorkflowItemsPresenter
    {
        public partial class RehostingWfDesigner : Window
        {
            public RehostingWfDesigner()
            {
                InitializeComponent();
            }

            protected override void OnInitialized(EventArgs e)
            {
                base.OnInitialized(e);
                // Register metadata.
                (new DesignerMetadata()).Register();
                RegisterCustomMetadata();

                // Create the workflow designer.
                var wd = new WorkflowDesigner();
                wd.Load(new Sequence());
                DesignerBorder.Child = wd.View;
                PropertyBorder.Child = wd.PropertyInspectorView;

            }

            void RegisterCustomMetadata()
            {
                var builder = new AttributeTableBuilder();
                builder.AddCustomAttributes(typeof(Parallel), new DesignerAttribute(typeof(CustomParallelDesigner)));
                MetadataStore.AddAttributeTable(builder.CreateTable());
            }
        }
    }
    ```

## <a name="see-also"></a><span data-ttu-id="b5388-167">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b5388-167">See also</span></span>

- <xref:System.Activities.Presentation.ActivityDesigner>
- <xref:System.Activities.Presentation.WorkflowItemPresenter>
- <xref:System.Activities.Presentation.WorkflowItemsPresenter>
- <xref:System.Activities.Presentation.WorkflowViewElement>
- <xref:System.Activities.Presentation.Model.ModelItem>
- [<span data-ttu-id="b5388-168">Anpassen des Workflowentwurfsvorgangs</span><span class="sxs-lookup"><span data-stu-id="b5388-168">Customizing the Workflow Design Experience</span></span>](customizing-the-workflow-design-experience.md)
