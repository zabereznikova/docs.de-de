---
title: 'Exemplarische Vorgehensweise: Zuweisen von WPF-Inhalt in Windows Forms zur Entwurfszeit'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WPF content [Windows Forms], assigning at design time
- ElementHost control [Windows Forms], assigning WPF content at design time
- interoperability [WPF]
- Windows Forms, content assignments
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: b3e9ef93-7e0f-4a2f-8f1e-3437609a1eb7
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 75dee4b230c790e5f1abf6bf7e77af106da0e7f7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-assigning-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="98f42-102">Exemplarische Vorgehensweise: Zuweisen von WPF-Inhalt in Windows Forms zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="98f42-102">Walkthrough: Assigning WPF Content on Windows Forms at Design Time</span></span>
<span data-ttu-id="98f42-103">In dieser exemplarischen Vorgehensweise wird gezeigt, wie die WPF-Steuerelementtypen (Windows Presentation Foundation) ausgewählt werden, die im Formular angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="98f42-103">This walkthrough show you how to select the Windows Presentation Foundation (WPF) control types you want to display on your form.</span></span> <span data-ttu-id="98f42-104">Sie können alle WPF-Steuerelementtypen auswählen, die im Projekt enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="98f42-104">You can select any WPF control types which are included in your project.</span></span>  
  
 <span data-ttu-id="98f42-105">Im Verlauf dieser exemplarischen Vorgehensweise führen Sie die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="98f42-105">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="98f42-106">Erstellen des Projekts.</span><span class="sxs-lookup"><span data-stu-id="98f42-106">Create the project.</span></span>  
  
-   <span data-ttu-id="98f42-107">Erstellen der WPF-Steuerelementtypen.</span><span class="sxs-lookup"><span data-stu-id="98f42-107">Create the WPF control types.</span></span>  
  
-   <span data-ttu-id="98f42-108">Auswählen der WPF-Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="98f42-108">Select WPF controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="98f42-109">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="98f42-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="98f42-110">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="98f42-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="98f42-111">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="98f42-111">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="98f42-112">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="98f42-112">Prerequisites</span></span>  
 <span data-ttu-id="98f42-113">Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="98f42-113">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)]<span data-ttu-id="98f42-114">.</span><span class="sxs-lookup"><span data-stu-id="98f42-114">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="98f42-115">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="98f42-115">Creating the Project</span></span>  
 <span data-ttu-id="98f42-116">Zunächst muss das Windows Forms-Projekt erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="98f42-116">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="98f42-117">Beim Hosten von WPF-Inhalt werden nur C#- und Visual Basic-Projekte unterstützt.</span><span class="sxs-lookup"><span data-stu-id="98f42-117">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="98f42-118">So erstellen Sie das Projekt</span><span class="sxs-lookup"><span data-stu-id="98f42-118">To create the project</span></span>  
  
-   <span data-ttu-id="98f42-119">Erstellen Sie ein neues Windows Forms-Anwendungsprojekt in Visual Basic oder Visual c# mit dem Namen `SelectingWpfContent`.</span><span class="sxs-lookup"><span data-stu-id="98f42-119">Create a new Windows Forms Application project in Visual Basic or Visual C# named `SelectingWpfContent`.</span></span>  
  
## <a name="creating-the-wpf-control-types"></a><span data-ttu-id="98f42-120">Erstellen der WPF-Steuerelementtypen</span><span class="sxs-lookup"><span data-stu-id="98f42-120">Creating the WPF Control Types</span></span>  
 <span data-ttu-id="98f42-121">Nachdem Sie dem Projekt WPF-Steuerelementtypen hinzugefügt haben, können Sie diese in verschiedenen <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelementen hosten.</span><span class="sxs-lookup"><span data-stu-id="98f42-121">After you add WPF control types to the project, you can host them in different <xref:System.Windows.Forms.Integration.ElementHost> controls.</span></span>  
  
#### <a name="to-create-wpf-control-types"></a><span data-ttu-id="98f42-122">So erstellen Sie WPF-Steuerelementtypen</span><span class="sxs-lookup"><span data-stu-id="98f42-122">To create WPF control types</span></span>  
  
1.  <span data-ttu-id="98f42-123">Fügen Sie der Projektmappe ein neues WPF-<xref:System.Windows.Controls.UserControl>-Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="98f42-123">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="98f42-124">Verwenden Sie den Standardnamen (`UserControl1.xaml`) für den Steuerelementtyp.</span><span class="sxs-lookup"><span data-stu-id="98f42-124">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="98f42-125">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen neuen WPF-Inhalts in Windows Forms zur Entwurfszeit](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="98f42-125">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2.  <span data-ttu-id="98f42-126">Stellen Sie in der Entwurfsansicht sicher, dass `UserControl1` ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="98f42-126">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="98f42-127">Weitere Informationen finden Sie unter [Vorgehensweise: auswählen und Verschieben von Elementen auf der Entwurfsoberfläche](http://msdn.microsoft.com/en-us/54cb70b6-b35b-46e4-a0cc-65189399c474).</span><span class="sxs-lookup"><span data-stu-id="98f42-127">For more information, see [How to: Select and Move Elements on the Design Surface](http://msdn.microsoft.com/en-us/54cb70b6-b35b-46e4-a0cc-65189399c474).</span></span>  
  
3.  <span data-ttu-id="98f42-128">In der **Eigenschaften** Fenster, legen Sie den Wert von der <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften `200`.</span><span class="sxs-lookup"><span data-stu-id="98f42-128">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>  
  
4.  <span data-ttu-id="98f42-129">Hinzufügen einer <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> die Steuerung an die <xref:System.Windows.Controls.UserControl> und legen Sie den Wert von der <xref:System.Windows.Controls.TextBox.Text%2A> Eigenschaft, um **gehosteten Inhalt**.</span><span class="sxs-lookup"><span data-stu-id="98f42-129">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>  
  
5.  <span data-ttu-id="98f42-130">Fügen Sie dem Projekt ein zweites WPF-<xref:System.Windows.Controls.UserControl> hinzu.</span><span class="sxs-lookup"><span data-stu-id="98f42-130">Add a second WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="98f42-131">Verwenden Sie den Standardnamen (`UserControl2.xaml`) für den Steuerelementtyp.</span><span class="sxs-lookup"><span data-stu-id="98f42-131">Use the default name for the control type, `UserControl2.xaml`.</span></span>  
  
6.  <span data-ttu-id="98f42-132">In der **Eigenschaften** Fenster, legen Sie den Wert von der <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften `200`.</span><span class="sxs-lookup"><span data-stu-id="98f42-132">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>  
  
7.  <span data-ttu-id="98f42-133">Hinzufügen einer <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> die Steuerung an die <xref:System.Windows.Controls.UserControl> und legen Sie den Wert von der <xref:System.Windows.Controls.TextBox.Text%2A> Eigenschaft, um **Hosted Content 2**.</span><span class="sxs-lookup"><span data-stu-id="98f42-133">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content 2**.</span></span>  
  
 <span data-ttu-id="98f42-134">**Hinweis** im Allgemeinen sollten Sie anspruchsvolleren WPF-Inhalt hosten.</span><span class="sxs-lookup"><span data-stu-id="98f42-134">**Note** In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="98f42-135">Das <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>-Steuerelement wird hier nur zur Veranschaulichung verwendet. </span><span class="sxs-lookup"><span data-stu-id="98f42-135">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>  
  
1.  <span data-ttu-id="98f42-136">Erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="98f42-136">Build the project.</span></span>  
  
## <a name="selecting-wpf-controls"></a><span data-ttu-id="98f42-137">Auswählen von WPF-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="98f42-137">Selecting WPF Controls</span></span>  
 <span data-ttu-id="98f42-138">Sie können einem <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement, das bereits Inhalte hostet, verschiedene WPF-Inhalte zuweisen.</span><span class="sxs-lookup"><span data-stu-id="98f42-138">You can assign different WPF content to an <xref:System.Windows.Forms.Integration.ElementHost> control, which is already hosting content.</span></span>  
  
#### <a name="to-select-wpf-controls"></a><span data-ttu-id="98f42-139">So wählen Sie WPF-Steuerelemente aus</span><span class="sxs-lookup"><span data-stu-id="98f42-139">To select WPF controls</span></span>  
  
1.  <span data-ttu-id="98f42-140">Öffnen Sie `Form1` im Windows Forms-Designer.</span><span class="sxs-lookup"><span data-stu-id="98f42-140">Open `Form1` in the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="98f42-141">In der **Toolbox**, doppelklicken Sie auf `UserControl1` zum Erstellen einer Instanz von `UserControl1` auf dem Formular.</span><span class="sxs-lookup"><span data-stu-id="98f42-141">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>  
  
     <span data-ttu-id="98f42-142">Eine Instanz von `UserControl1` wird in einem neuen <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement namens `elementHost1` gehostet.</span><span class="sxs-lookup"><span data-stu-id="98f42-142">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
3.  <span data-ttu-id="98f42-143">Klicken Sie im Smarttagbereich für `elementHost1`öffnen die **gehosteten Inhalt auswählen** Dropdown-Liste.</span><span class="sxs-lookup"><span data-stu-id="98f42-143">In the smart tag panel for `elementHost1`, open the **Select Hosted Content** drop-down list.</span></span>  
  
4.  <span data-ttu-id="98f42-144">Wählen Sie **UserControl2** aus dem Dropdown-Listenfeld.</span><span class="sxs-lookup"><span data-stu-id="98f42-144">Select **UserControl2** from the drop-down list box.</span></span>  
  
     <span data-ttu-id="98f42-145">Das `elementHost1`-Steuerelement hostet jetzt eine Instanz des `UserControl2`-Typs.</span><span class="sxs-lookup"><span data-stu-id="98f42-145">The `elementHost1` control now hosts an instance of the `UserControl2` type.</span></span>  
  
5.  <span data-ttu-id="98f42-146">In der **Eigenschaften** Fenster, überprüfen Sie, ob die <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> -Eigenschaftensatz auf **UserControl2**.</span><span class="sxs-lookup"><span data-stu-id="98f42-146">In the **Properties** window, confirm that the <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl2**.</span></span>  
  
6.  <span data-ttu-id="98f42-147">Aus der **Toolbox**in der **WPF-Interoperabilität** gruppieren, ziehen Sie ein <xref:System.Windows.Forms.Integration.ElementHost> -Steuerelement auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="98f42-147">From the **Toolbox**, in the **WPF Interoperability** group, drag an <xref:System.Windows.Forms.Integration.ElementHost> control onto the form.</span></span>  
  
     <span data-ttu-id="98f42-148">Der Standardname für das neue Steuerelement ist `elementHost2`.</span><span class="sxs-lookup"><span data-stu-id="98f42-148">The default name for the new control is `elementHost2`.</span></span>  
  
7.  <span data-ttu-id="98f42-149">Klicken Sie im Smarttagbereich für `elementHost2`öffnen die **gehosteten Inhalt auswählen** Dropdown-Liste.</span><span class="sxs-lookup"><span data-stu-id="98f42-149">In the smart tag panel for `elementHost2`, open the **Select Hosted Content** drop-down list.</span></span>  
  
8.  <span data-ttu-id="98f42-150">Wählen Sie **"UserControl1"** aus der Dropdown-Liste.</span><span class="sxs-lookup"><span data-stu-id="98f42-150">Select **UserControl1** from the drop-down list.</span></span>  
  
9. <span data-ttu-id="98f42-151">Das `elementHost2`-Steuerelement hostet jetzt eine Instanz des `UserControl1`-Typs.</span><span class="sxs-lookup"><span data-stu-id="98f42-151">The `elementHost2` control now hosts an instance of the `UserControl1` type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98f42-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="98f42-152">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="98f42-153">Migration und Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="98f42-153">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [<span data-ttu-id="98f42-154">Verwenden von WPF-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="98f42-154">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [<span data-ttu-id="98f42-155">WPF-Designer</span><span class="sxs-lookup"><span data-stu-id="98f42-155">WPF Designer</span></span>](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)
