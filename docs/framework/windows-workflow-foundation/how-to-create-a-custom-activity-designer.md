---
title: "Vorgehensweise: Erstellen eines benutzerdefinierten Aktivitätsdesigners"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2f3aade6-facc-44ef-9657-a407ef8b9b31
caps.latest.revision: "25"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cdf64dd7aca82fb0d0b3111832aca863a327270b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-custom-activity-designer"></a><span data-ttu-id="a7680-102">Vorgehensweise: Erstellen eines benutzerdefinierten Aktivitätsdesigners</span><span class="sxs-lookup"><span data-stu-id="a7680-102">How to: Create a Custom Activity Designer</span></span>
<span data-ttu-id="a7680-103">Benutzerdefinierte Aktivitätsdesigner werden in der Regel implementiert, um die zugehörigen Aktivitäten mit anderen Aktivitäten zusammenzusetzen, deren Designer mit ihnen auf der Entwurfsoberfläche abgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="a7680-103">Custom activity designers are typically implemented so that their associated activities are composable with other activities whose designers can be dropped on to the design surface with them.</span></span> <span data-ttu-id="a7680-104">Diese Funktionalität muss ein benutzerdefinierter Aktivitätsdesigner bereitstellen, eine "Ablagezone", in denen eine beliebige Aktivität platziert werden kann, sowie die Möglichkeit zum Verwalten der resultierenden Auflistung von Elementen auf der Entwurfsoberfläche angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a7680-104">This functionality requires that a custom activity designer provide a "drop zone" where an arbitrary activity can be placed and also the means to manage the resulting collection of elements on the design surface.</span></span> <span data-ttu-id="a7680-105">In diesem Thema wird beschrieben, wie ein benutzerdefinierter Aktivitätsdesigner erstellt wird, der eine solche Ablagezone enthält und die Bearbeitungsfunktionen zur Verwaltung der Auflistung von Designerelementen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="a7680-105">This topic describes how to create a custom activity designer that contains such a drop zone and how to create a custom activity designer that provides that editing functionality needed to manage the collection of designer elements.</span></span>  
  
 <span data-ttu-id="a7680-106">Benutzerdefinierte Aktivitätsdesigner erben in der Regel von <xref:System.Activities.Presentation.ActivityDesigner>. Dies ist der standardmäßige Designertyp für alle Aktivitäten ohne bestimmten Designer.</span><span class="sxs-lookup"><span data-stu-id="a7680-106">Custom activity designers typically inherit from <xref:System.Activities.Presentation.ActivityDesigner> which is the default base activity designer type for any activities without a specific designer.</span></span> <span data-ttu-id="a7680-107">Dieser Typ stellt Entwurfszeitfunktionen für die Interaktion mit dem Eigenschaftenraster und die Konfiguration von grundlegenden Aspekten wie Farbe und Symbole bereit.</span><span class="sxs-lookup"><span data-stu-id="a7680-107">This type provides the design-time experience of interacting with the property grid and configuring basic aspects such as managing colors and icons.</span></span>  
  
 <span data-ttu-id="a7680-108"><xref:System.Activities.Presentation.ActivityDesigner> verwendet zwei Hilfssteuerelemente (<xref:System.Activities.Presentation.WorkflowItemPresenter> und <xref:System.Activities.Presentation.WorkflowItemsPresenter>), die das Entwickeln benutzerdefinierter Aktivitätsdesigner vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="a7680-108"><xref:System.Activities.Presentation.ActivityDesigner> uses two helper controls, <xref:System.Activities.Presentation.WorkflowItemPresenter> and <xref:System.Activities.Presentation.WorkflowItemsPresenter> to make it easier to develop custom activity designers.</span></span> <span data-ttu-id="a7680-109">Sie behandeln die allgemeine Funktionalität wie Ziehen und Ablegen von untergeordneten Elementen sowie Löschen, Auswählen und Hinzufügen dieser untergeordneten Elemente.</span><span class="sxs-lookup"><span data-stu-id="a7680-109">They handle common functionality like dragging and dropping of child elements, deletion, selection, and addition of those child elements.</span></span> <span data-ttu-id="a7680-110">Die <xref:System.Activities.Presentation.WorkflowItemPresenter> unterstützt ein einzelnes untergeordnetes Benutzeroberflächenelement, "Ablagezone" bereitstellt es während der <xref:System.Activities.Presentation.WorkflowItemsPresenter> unterstützt mehrere Benutzeroberflächenelemente, darunter zusätzliche Funktionalität z. B. zum Sortieren, verschieben, löschen und Hinzufügen von untergeordneten Elementen.</span><span class="sxs-lookup"><span data-stu-id="a7680-110">The <xref:System.Activities.Presentation.WorkflowItemPresenter> allows a single child UI element inside, providing the "drop zone", it while the <xref:System.Activities.Presentation.WorkflowItemsPresenter> can provide support multiple UI elements, including additional functionality like the ordering, moving, deleting, and adding of child elements.</span></span>  
  
 <span data-ttu-id="a7680-111">Der zweite Hauptaspekt bei der Implementierung eines benutzerdefinierten Aktivitätsdesigners betrifft die Methode zur Bindung der grafischen Bearbeitungen an die Instanz der im Designer bearbeiteten Objekte im Arbeitsspeicher mit der [!INCLUDE[avalon2](../../../includes/avalon2-md.md)]-Datenbindung.</span><span class="sxs-lookup"><span data-stu-id="a7680-111">The other key part of the story that needs highlighting in the implementation of a custom activity designer concerns the way in which the visual edits are bound using [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] data binding to the instance stored in memory of what we are editing in the designer.</span></span> <span data-ttu-id="a7680-112">Hierzu dient die Modellelementstruktur, die auch zur Aktivierung der Änderungsbenachrichtigung und der Nachverfolgung von Ereignissen wie Zustandsänderungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a7680-112">This is accomplished by the Model Item tree, which is also responsible for enabling change notification and the tracking of events like changes in states.</span></span>  
  
 <span data-ttu-id="a7680-113">In diesem Thema werden zwei Prozeduren beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a7680-113">This topic outlines two procedures.</span></span>  
  
1.  <span data-ttu-id="a7680-114">Die erste Prozedur beschreibt, wie ein benutzerdefinierter Aktivitätsdesigner mit <xref:System.Activities.Presentation.WorkflowItemPresenter> erstellt wird, der die Ablagezone für andere Aktivitäten bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="a7680-114">The first procedure describes how to create a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemPresenter> that provides the drop zone that receives other activities.</span></span> <span data-ttu-id="a7680-115">Dieses Verfahren basiert auf der [benutzerdefinierte zusammengesetzte Designer - Workflow Element Vortragende](../../../docs/framework/windows-workflow-foundation/samples/custom-composite-designers-workflow-item-presenter.md) Beispiel.</span><span class="sxs-lookup"><span data-stu-id="a7680-115">This procedure is based on the [Custom Composite Designers - Workflow Item Presenter](../../../docs/framework/windows-workflow-foundation/samples/custom-composite-designers-workflow-item-presenter.md) sample.</span></span>  
  
2.  <span data-ttu-id="a7680-116">Die zweite Prozedur beschreibt, wie ein benutzerdefinierter Aktivitätsdesigner mit <xref:System.Activities.Presentation.WorkflowItemsPresenter> erstellt wird, der die zur Bearbeitung einer Auflistung von Elementen benötigten Funktionen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="a7680-116">The second procedure describes how to create a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemsPresenter> that provides the functionality needed to edit of a collection of contained elements.</span></span> <span data-ttu-id="a7680-117">Dieses Verfahren basiert auf der [benutzerdefinierte zusammengesetzte Designer - Workflowelementpräsentation](../../../docs/framework/windows-workflow-foundation/samples/custom-composite-designers-workflow-items-presenter.md) Beispiel.</span><span class="sxs-lookup"><span data-stu-id="a7680-117">This procedure is based on the [Custom Composite Designers - Workflow Items Presenter](../../../docs/framework/windows-workflow-foundation/samples/custom-composite-designers-workflow-items-presenter.md) sample.</span></span>  
  
### <a name="to-create-a-custom-activity-designer-with-a-drop-zone-using-workflowitempresenter"></a><span data-ttu-id="a7680-118">So erstellen Sie einen benutzerdefinierten Aktivitätsdesigner, der eine Ablagezone bereitstellt, mit WorkflowItemPresenter</span><span class="sxs-lookup"><span data-stu-id="a7680-118">To create a custom activity designer with a drop zone using WorkflowItemPresenter</span></span>  
  
1.  <span data-ttu-id="a7680-119">Starten Sie [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7680-119">Start [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="a7680-120">Auf der **Datei** Sie im Menü **neu**, und wählen Sie dann **Projekt...** .</span><span class="sxs-lookup"><span data-stu-id="a7680-120">On the **File** menu, point to **New**, and then select **Project…**.</span></span>  
  
     <span data-ttu-id="a7680-121">Das Dialogfeld **Neues Projekt** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a7680-121">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="a7680-122">In der **installierte Vorlagen** klicken Sie im Bereich **Windows** von Ihnen bevorzugten Sprachkategorie.</span><span class="sxs-lookup"><span data-stu-id="a7680-122">In the **Installed Templates** pane, select **Windows** from your preferred language category.</span></span>  
  
4.  <span data-ttu-id="a7680-123">In der **Vorlagen** klicken Sie im Bereich **WPF-Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="a7680-123">In the **Templates** pane, select **WPF Application**.</span></span>  
  
5.  <span data-ttu-id="a7680-124">In der **Namen** geben `UsingWorkflowItemPresenter`.</span><span class="sxs-lookup"><span data-stu-id="a7680-124">In the **Name** box, enter `UsingWorkflowItemPresenter`.</span></span>  
  
6.  <span data-ttu-id="a7680-125">In der **Speicherort** Geben Sie das Verzeichnis, in dem Sie das Projekt gespeichert werden soll, oder klicken möchten **Durchsuchen** navigieren.</span><span class="sxs-lookup"><span data-stu-id="a7680-125">In the **Location** box, enter the directory in which you want to save your project, or click **Browse** to navigate to it.</span></span>  
  
7.  <span data-ttu-id="a7680-126">In der **Lösung** Feld, akzeptieren Sie den Standardwert.</span><span class="sxs-lookup"><span data-stu-id="a7680-126">In the **Solution** box, accept the default value.</span></span>  
  
8.  <span data-ttu-id="a7680-127">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a7680-127">Click **OK**.</span></span>  
  
9. <span data-ttu-id="a7680-128">Mit der rechten Maustaste in der Datei "MainWindows.xaml" in der **Projektmappen-Explorer**Option **löschen** und vergewissern Sie sich **OK** in die **Microsoft Visual Studio**im Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="a7680-128">Right-click the MainWindows.xaml file in the **Solution Explorer**, select **Delete** and confirm **OK** in the **Microsoft Visual Studio** dialogue box.</span></span>  
  
10. <span data-ttu-id="a7680-129">Mit der rechten Maustaste des Projekts "UsingWorkflowItemPresenter" im **Projektmappen-Explorer**Option **hinzufügen**, klicken Sie dann **neues Element...**</span><span class="sxs-lookup"><span data-stu-id="a7680-129">Right-click the UsingWorkflowItemPresenter project in **Solution Explorer**, select **Add**, then **New Item…**</span></span> <span data-ttu-id="a7680-130">um die **neues Element hinzufügen** Dialog, und wählen Sie die **WPF** Kategorie aus der **installierte Vorlagen** Abschnitt auf der linken Seite.</span><span class="sxs-lookup"><span data-stu-id="a7680-130">to bring up the **Add New Item** dialogue and select the **WPF** category from the **Installed Templates** section on the left.</span></span>  
  
11. <span data-ttu-id="a7680-131">Wählen Sie die **Fenster (WPF)** Vorlage, nennen Sie sie `RehostingWFDesigner`, und klicken Sie auf **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a7680-131">Select the  **Window (WPF)** template, name it `RehostingWFDesigner`, and click **Add**.</span></span>  
  
12. <span data-ttu-id="a7680-132">Öffnen Sie die Datei "RehostingWFDesigner.xaml", und fügen Sie den folgenden Code ein, um die Benutzeroberfläche für die Anwendung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="a7680-132">Open the RehostingWFDesigner.xaml file and paste the following code into it to define the UI for the application.</span></span>  
  
    ```xml  
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
  
13. <span data-ttu-id="a7680-133">Um einem Aktivitätsdesigner einen Aktivitätstyp zuzuordnen, müssen Sie den Aktivitätsdesigner im Metadatenspeicher registrieren.</span><span class="sxs-lookup"><span data-stu-id="a7680-133">To associate an activity designer with an activity type, you must register that activity designer with the metadata store.</span></span> <span data-ttu-id="a7680-134">Fügen Sie hierzu der `RegisterMetadata`-Klasse die `RehostingWFDesigner`-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="a7680-134">To do this, add the `RegisterMetadata` method to the `RehostingWFDesigner` class.</span></span> <span data-ttu-id="a7680-135">Erstellen Sie innerhalb des Bereichs der `RegisterMetadata`-Methode ein <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder>-Objekt, und rufen Sie die <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder.AddCustomAttributes%2A>-Methode auf, um dem Objekt die Attribute hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="a7680-135">Within the scope of the  `RegisterMetadata` method, create an <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder> object and call the <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder.AddCustomAttributes%2A> method to add the attributes to it.</span></span> <span data-ttu-id="a7680-136">Rufen Sie die <xref:System.Activities.Presentation.Metadata.MetadataStore.AddAttributeTable%2A>-Methode auf, um dem Metadatenspeicher das <xref:System.Activities.Presentation.Metadata.AttributeTable>-Objekt hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="a7680-136">Call the <xref:System.Activities.Presentation.Metadata.MetadataStore.AddAttributeTable%2A> method to add the <xref:System.Activities.Presentation.Metadata.AttributeTable> to the metadata store.</span></span> <span data-ttu-id="a7680-137">Der folgende Code enthält die Rehosting-Logik für den Designer.</span><span class="sxs-lookup"><span data-stu-id="a7680-137">The following code contains the rehosting logic for the designer.</span></span> <span data-ttu-id="a7680-138">Damit werden die Metadaten registriert, die `SimpleNativeActivity` wird in die Toolbox eingefügt und der Workflow wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="a7680-138">It registers the metadata, puts the `SimpleNativeActivity` into the toolbox, and creates the workflow.</span></span> <span data-ttu-id="a7680-139">Fügen Sie diesen Code in die Datei "RehostingWFDesigner.xaml.cs" ein.</span><span class="sxs-lookup"><span data-stu-id="a7680-139">Put this code into the RehostingWFDesigner.xaml.cs file.</span></span>  
  
    ```  
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
                // register metadata  
                (new DesignerMetadata()).Register();  
                RegisterCustomMetadata();  
                // add custom activity to toolbox  
                Toolbox.Categories.Add(new ToolboxCategory("Custom activities"));  
                Toolbox.Categories[1].Add(new ToolboxItemWrapper(typeof(SimpleNativeActivity)));  
  
                // create the workflow designer  
                WorkflowDesigner wd = new WorkflowDesigner();  
                wd.Load(new Sequence());  
                DesignerBorder.Child = wd.View;  
                PropertyBorder.Child = wd.PropertyInspectorView;  
  
            }  
  
            void RegisterCustomMetadata()  
            {  
                AttributeTableBuilder builder = new AttributeTableBuilder();  
                builder.AddCustomAttributes(typeof(SimpleNativeActivity), new DesignerAttribute(typeof(SimpleNativeDesigner)));  
                MetadataStore.AddAttributeTable(builder.CreateTable());  
            }  
        }  
    }  
    ```  
  
14. <span data-ttu-id="a7680-140">Mit der rechten Maustaste in das Verzeichnis "Verweise" im Projektmappen-Explorer, und wählen Sie **Verweis hinzufügen...**</span><span class="sxs-lookup"><span data-stu-id="a7680-140">Right-click the References directory in Solution Explorer and select **Add Reference …**</span></span> <span data-ttu-id="a7680-141">um die **Verweis hinzufügen** Dialog.</span><span class="sxs-lookup"><span data-stu-id="a7680-141">to bring up the **Add Reference** dialogue.</span></span>  
  
15. <span data-ttu-id="a7680-142">Klicken Sie auf die **.NET** Registerkarte, suchen Sie die Assembly mit dem Namen **System.Activities.Core.Presentation**, wählen Sie ihn, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a7680-142">Click the **.NET** tab, locate the assembly named **System.Activities.Core.Presentation**, select it and click **OK**.</span></span>  
  
16. <span data-ttu-id="a7680-143">Fügen Sie auf die gleiche Weise den folgenden Assemblys Verweise hinzu:</span><span class="sxs-lookup"><span data-stu-id="a7680-143">Using the same procedure, add references to the following assemblies:</span></span>  
  
    1.  <span data-ttu-id="a7680-144">System.Data.DataSetExtensions.dll</span><span class="sxs-lookup"><span data-stu-id="a7680-144">System.Data.DataSetExtensions.dll</span></span>  
  
    2.  <span data-ttu-id="a7680-145">System.Activities.Presentation.dll</span><span class="sxs-lookup"><span data-stu-id="a7680-145">System.Activities.Presentation.dll</span></span>  
  
    3.  <span data-ttu-id="a7680-146">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="a7680-146">System.ServiceModel.Activities.dll</span></span>  
  
17. <span data-ttu-id="a7680-147">Öffnen Sie die Datei "App.xaml", und ändern Sie den Wert, der den StartupUri-Wert in "RehostingWFDesigner.xaml".</span><span class="sxs-lookup"><span data-stu-id="a7680-147">Open the App.xaml file and change the value of the StartUpUri to "RehostingWFDesigner.xaml".</span></span>  
  
18. <span data-ttu-id="a7680-148">Mit der rechten Maustaste des Projekts "UsingWorkflowItemPresenter" im **Projektmappen-Explorer**Option **hinzufügen**, klicken Sie dann **neues Element...**</span><span class="sxs-lookup"><span data-stu-id="a7680-148">Right-click the UsingWorkflowItemPresenter project in **Solution Explorer**, select **Add**, then **New Item…**</span></span> <span data-ttu-id="a7680-149">um die **neues Element hinzufügen** Dialog, und wählen Sie die **Workflow** Kategorie Form der **installierte Vorlagen** Abschnitt auf der linken Seite.</span><span class="sxs-lookup"><span data-stu-id="a7680-149">to bring up the **Add New Item** dialogue and select the **Workflow** category form the **Installed Templates** section on the left.</span></span>  
  
19. <span data-ttu-id="a7680-150">Wählen Sie die **Aktivitäts-Designer** Vorlage, nennen Sie sie `SimpleNativeDesigner`, und klicken Sie auf **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a7680-150">Select the **Activity Designer** template, name it `SimpleNativeDesigner`, and click **Add**.</span></span>  
  
20. <span data-ttu-id="a7680-151">Öffnen Sie die Datei "SimpleNativeDesigner.xaml", und fügen Sie den folgenden Code ein.</span><span class="sxs-lookup"><span data-stu-id="a7680-151">Open the SimpleNativeDesigner.xaml file and paste the following code into it.</span></span> <span data-ttu-id="a7680-152">Beachten Sie, dass in diesem Code <xref:System.Activities.Presentation.ActivityDesigner> als Stammelement verwendet wird. Er zeigt, wie <xref:System.Activities.Presentation.WorkflowItemPresenter> mithilfe von Bindung in Ihren Designer integriert wird, sodass im zusammengesetzten Aktivitätsdesigner ein untergeordneter Typ angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="a7680-152">Note this code uses <xref:System.Activities.Presentation.ActivityDesigner> as your root element and shows how binding is used to integrate <xref:System.Activities.Presentation.WorkflowItemPresenter> into your designer so a child type can be displayed in your composite activity designer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a7680-153">Mit dem Schema für <xref:System.Activities.Presentation.ActivityDesigner> können Sie dem benutzerdefinierten Aktivitätsdesigner nur ein untergeordnetes Element hinzufügen. Bei diesem Element kann es sich jedoch um ein `StackPanel`, ein `Grid` oder um ein anderes zusammengesetztes Benutzeroberflächenelement handeln.</span><span class="sxs-lookup"><span data-stu-id="a7680-153">The schema for <xref:System.Activities.Presentation.ActivityDesigner> allows the addition of only one child element to your custom activity designer definition; however, this element could be a `StackPanel`, `Grid`, or some other composite UI element.</span></span>  
  
    ```xml  
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
  
21. <span data-ttu-id="a7680-154">Mit der rechten Maustaste des Projekts "UsingWorkflowItemPresenter" im **Projektmappen-Explorer**Option **hinzufügen**, klicken Sie dann **neues Element...**</span><span class="sxs-lookup"><span data-stu-id="a7680-154">Right-click the UsingWorkflowItemPresenter project in **Solution Explorer**, select **Add**, then **New Item…**</span></span> <span data-ttu-id="a7680-155">um die **neues Element hinzufügen** Dialog, und wählen Sie die **Workflow** Kategorie Form der **installierte Vorlagen** Abschnitt auf der linken Seite.</span><span class="sxs-lookup"><span data-stu-id="a7680-155">to bring up the **Add New Item** dialogue and select the **Workflow** category form the **Installed Templates** section on the left.</span></span>  
  
22. <span data-ttu-id="a7680-156">Wählen Sie die **Codeaktivität** Vorlage, nennen Sie sie `SimpleNativeActivity`, und klicken Sie auf **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a7680-156">Select the  **Code Activity** template, name it `SimpleNativeActivity`, and click **Add**.</span></span>  
  
23. <span data-ttu-id="a7680-157">Implementieren Sie die `SimpleNativeActivity`-Klasse, indem Sie den folgenden Code in die Datei "SimpleNativeActivity.cs" einfügen.</span><span class="sxs-lookup"><span data-stu-id="a7680-157">Implement the `SimpleNativeActivity` class by entering the following code into the SimpleNativeActivity.cs file.</span></span>  
  
    ```  
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
  
24. <span data-ttu-id="a7680-158">Wählen Sie **Projektmappe** aus der **erstellen** Menü.</span><span class="sxs-lookup"><span data-stu-id="a7680-158">Select **Build Solution** from the **Build** menu.</span></span>  
  
25. <span data-ttu-id="a7680-159">Wählen Sie **Starten ohne Debugging** aus der **Debuggen** Menü, um das neu gehostete benutzerdefinierte Entwurfsfenster zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a7680-159">Select **Start Without Debugging** from the **Debug** menu to open the rehosted custom design window.</span></span>  
  
### <a name="to-create-a-custom-activity-designer-using-workflowitemspresenter"></a><span data-ttu-id="a7680-160">So erstellen Sie einen benutzerdefinierten Aktivitätsdesigner mit WorkflowItemsPresenter</span><span class="sxs-lookup"><span data-stu-id="a7680-160">To create a custom activity designer using WorkflowItemsPresenter</span></span>  
  
1.  <span data-ttu-id="a7680-161">Die Prozedur für den zweiten benutzerdefinierten Aktivitätsdesigner ist die erste mit wenigen Änderungen, von denen der erste besteht in der zweiten Anwendung den Namen `UsingWorkflowItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="a7680-161">The procedure for the second custom activity designer is the parallels the first with a few modifications, the first of which is to name the second application `UsingWorkflowItemsPresenter`.</span></span> <span data-ttu-id="a7680-162">Außerdem wird mit dieser Anwendung keine neue benutzerdefinierte Aktivität definiert.</span><span class="sxs-lookup"><span data-stu-id="a7680-162">Also this application does not define a new custom activity.</span></span>  
  
2.  <span data-ttu-id="a7680-163">Die Hauptunterschiede sind in den Dateien "CustomParallelDesigner.xaml" und "RehostingWFDesigner.xaml.cs" enthalten.</span><span class="sxs-lookup"><span data-stu-id="a7680-163">Key differences are contained in the CustomParallelDesigner.xaml and RehostingWFDesigner.xaml.cs files.</span></span> <span data-ttu-id="a7680-164">Hier stammt der Code aus der Datei "CustomParallelDesigne.xaml" zur Definition der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="a7680-164">Here is the code from the CustomParallelDesigne.xaml file that defines the UI.</span></span>  
  
    ```xml  
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
  
3.  <span data-ttu-id="a7680-165">Hier stammt der Code aus der Datei "RehostingWFDesigner.xaml.cs" zur Bereitstellung der Rehosting-Logik.</span><span class="sxs-lookup"><span data-stu-id="a7680-165">Here is the code from the RehostingWFDesigner.xaml.cs file that provides the rehosting logic.</span></span>  
  
    ```  
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
                // register metadata  
                (new DesignerMetadata()).Register();  
                RegisterCustomMetadata();  
  
                // create the workflow designer  
                WorkflowDesigner wd = new WorkflowDesigner();  
                wd.Load(new Sequence());  
                DesignerBorder.Child = wd.View;  
                PropertyBorder.Child = wd.PropertyInspectorView;  
  
            }  
  
            void RegisterCustomMetadata()  
            {  
                AttributeTableBuilder builder = new AttributeTableBuilder();  
                builder.AddCustomAttributes(typeof(Parallel), new DesignerAttribute(typeof(CustomParallelDesigner)));  
                MetadataStore.AddAttributeTable(builder.CreateTable());  
            }  
        }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a7680-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7680-166">See Also</span></span>  
 <xref:System.Activities.Presentation.ActivityDesigner>  
 <xref:System.Activities.Presentation.WorkflowItemPresenter>  
 <xref:System.Activities.Presentation.WorkflowItemsPresenter>  
 <xref:System.Activities.Presentation.WorkflowViewElement>  
 <xref:System.Activities.Presentation.Model.ModelItem>  
 [<span data-ttu-id="a7680-167">Anpassen des Workflowentwurfsvorgangs</span><span class="sxs-lookup"><span data-stu-id="a7680-167">Customizing the Workflow Design Experience</span></span>](../../../docs/framework/windows-workflow-foundation/customizing-the-workflow-design-experience.md)
