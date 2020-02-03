---
title: Wählen Sie WPF-Steuerelemente für Windows Forms
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], assigning at design time
- ElementHost control [Windows Forms], assigning WPF content at design time
- interoperability [WPF]
- Windows Forms, content assignments
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: b3e9ef93-7e0f-4a2f-8f1e-3437609a1eb7
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 19f1dfec282b025f5a1fa367ec5fa9a52472c691
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746811"
---
# <a name="walkthrough-assign-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="779e0-102">Exemplarische Vorgehensweise: Zuweisen von WPF-Inhalt zu Windows Forms zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="779e0-102">Walkthrough: Assign WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="779e0-103">In diesem Artikel wird gezeigt, wie Sie die Windows Presentation Foundation (WPF)-Steuerelement Typen auswählen, die auf dem Formular angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="779e0-103">This article show you how to select the Windows Presentation Foundation (WPF) control types you want to display on your form.</span></span> <span data-ttu-id="779e0-104">Sie können beliebige WPF-Steuerelement Typen auswählen, die in Ihrem Projekt enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="779e0-104">You can select any WPF control types that are included in your project.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="779e0-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="779e0-105">Prerequisites</span></span>

<span data-ttu-id="779e0-106">Für diese exemplarische Vorgehensweise benötigen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="779e0-106">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="779e0-107">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="779e0-107">Create the project</span></span>

<span data-ttu-id="779e0-108">Öffnen Sie Visual Studio, und erstellen Sie ein neues Windows Forms-Anwendungsprojekt C# in Visual Basic oder Visual mit dem Namen `SelectingWpfContent`.</span><span class="sxs-lookup"><span data-stu-id="779e0-108">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `SelectingWpfContent`.</span></span>

> [!NOTE]
> <span data-ttu-id="779e0-109">Beim Hosten von WPF-Inhalt werden nur C#- und Visual Basic-Projekte unterstützt.</span><span class="sxs-lookup"><span data-stu-id="779e0-109">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control-types"></a><span data-ttu-id="779e0-110">Erstellen der WPF-Steuerelement Typen</span><span class="sxs-lookup"><span data-stu-id="779e0-110">Create the WPF control types</span></span>

<span data-ttu-id="779e0-111">Nachdem Sie dem Projekt WPF-Steuerelementtypen hinzugefügt haben, können Sie diese in verschiedenen <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelementen hosten.</span><span class="sxs-lookup"><span data-stu-id="779e0-111">After you add WPF control types to the project, you can host them in different <xref:System.Windows.Forms.Integration.ElementHost> controls.</span></span>

1. <span data-ttu-id="779e0-112">Fügen Sie der Projektmappe ein neues WPF-<xref:System.Windows.Controls.UserControl>-Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="779e0-112">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="779e0-113">Verwenden Sie den Standardnamen, `UserControl1.xaml`, für den Steuerelementtyp.</span><span class="sxs-lookup"><span data-stu-id="779e0-113">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="779e0-114">Weitere Informationen finden Sie unter Exemplarische Vorgehensweise [: Erstellen eines neuen WPF-Inhalts auf Windows Forms zur Entwurfszeit](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="779e0-114">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="779e0-115">Stellen Sie in der Entwurfsansicht sicher, dass `UserControl1` ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="779e0-115">In Design view, make sure that `UserControl1` is selected.</span></span>

3. <span data-ttu-id="779e0-116">Legen Sie im Fenster **Eigenschaften** den Wert der Eigenschaften <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> auf **200**fest.</span><span class="sxs-lookup"><span data-stu-id="779e0-116">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="779e0-117">Fügen Sie der <xref:System.Windows.Controls.UserControl> ein <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>-Steuerelement hinzu, und legen Sie den Wert der Eigenschaft <xref:System.Windows.Controls.TextBox.Text%2A> auf **gehosteten Inhalt**fest.</span><span class="sxs-lookup"><span data-stu-id="779e0-117">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>

5. <span data-ttu-id="779e0-118">Fügen Sie dem Projekt ein zweites WPF-<xref:System.Windows.Controls.UserControl> hinzu.</span><span class="sxs-lookup"><span data-stu-id="779e0-118">Add a second WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="779e0-119">Verwenden Sie den Standardnamen, `UserControl2.xaml`, für den Steuerelementtyp.</span><span class="sxs-lookup"><span data-stu-id="779e0-119">Use the default name for the control type, `UserControl2.xaml`.</span></span>

6. <span data-ttu-id="779e0-120">Legen Sie im Fenster **Eigenschaften** den Wert der Eigenschaften <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> auf **200**fest.</span><span class="sxs-lookup"><span data-stu-id="779e0-120">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

7. <span data-ttu-id="779e0-121">Fügen Sie der <xref:System.Windows.Controls.UserControl> ein <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>-Steuerelement hinzu, und legen Sie den Wert der <xref:System.Windows.Controls.TextBox.Text%2A>-Eigenschaft auf **Hosted Content 2**fest.</span><span class="sxs-lookup"><span data-stu-id="779e0-121">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content 2**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="779e0-122">Normalerweise sollten Sie anspruchsvolleren WPF-Inhalt hosten.</span><span class="sxs-lookup"><span data-stu-id="779e0-122">In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="779e0-123"><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>-Steuerelement wird hier nur zur Veranschaulichung verwendet.</span><span class="sxs-lookup"><span data-stu-id="779e0-123">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>

8. <span data-ttu-id="779e0-124">Erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="779e0-124">Build the project.</span></span>

## <a name="select-wpf-controls"></a><span data-ttu-id="779e0-125">WPF-Steuerelemente auswählen</span><span class="sxs-lookup"><span data-stu-id="779e0-125">Select WPF controls</span></span>

<span data-ttu-id="779e0-126">Sie können einem <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement, das bereits Inhalte hostet, verschiedene WPF-Inhalte zuweisen.</span><span class="sxs-lookup"><span data-stu-id="779e0-126">You can assign different WPF content to an <xref:System.Windows.Forms.Integration.ElementHost> control, which is already hosting content.</span></span>

1. <span data-ttu-id="779e0-127">Öffnen Sie `Form1` im Windows Forms-Designer.</span><span class="sxs-lookup"><span data-stu-id="779e0-127">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="779e0-128">Doppelklicken Sie in der **Toolbox**auf `UserControl1`, um eine Instanz von `UserControl1` im Formular zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="779e0-128">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>

   <span data-ttu-id="779e0-129">Eine Instanz von `UserControl1` wird in einem neuen <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement namens `elementHost1` gehostet.</span><span class="sxs-lookup"><span data-stu-id="779e0-129">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

3. <span data-ttu-id="779e0-130">Öffnen Sie im Smarttagbereich für `elementHost1`die Dropdown Liste **gehostete Inhalte auswählen** .</span><span class="sxs-lookup"><span data-stu-id="779e0-130">In the smart tag panel for `elementHost1`, open the **Select Hosted Content** drop-down list.</span></span>

4. <span data-ttu-id="779e0-131">Wählen Sie **UserControl2** aus dem Dropdown-Listenfeld aus.</span><span class="sxs-lookup"><span data-stu-id="779e0-131">Select **UserControl2** from the drop-down list box.</span></span>

   <span data-ttu-id="779e0-132">Das `elementHost1`-Steuerelement hostet jetzt eine Instanz des `UserControl2`-Typs.</span><span class="sxs-lookup"><span data-stu-id="779e0-132">The `elementHost1` control now hosts an instance of the `UserControl2` type.</span></span>

5. <span data-ttu-id="779e0-133">Vergewissern Sie sich im **Eigenschaften** Fenster, dass die <xref:System.Windows.Forms.Integration.ElementHost.Child%2A>-Eigenschaft auf **UserControl2**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="779e0-133">In the **Properties** window, confirm that the <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl2**.</span></span>

6. <span data-ttu-id="779e0-134">Ziehen Sie aus der **Toolbox**in der **WPF-Interoperabilitäts** Gruppe ein <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="779e0-134">From the **Toolbox**, in the **WPF Interoperability** group, drag an <xref:System.Windows.Forms.Integration.ElementHost> control onto the form.</span></span>

   <span data-ttu-id="779e0-135">Der Standardname für das neue Steuerelement ist `elementHost2`.</span><span class="sxs-lookup"><span data-stu-id="779e0-135">The default name for the new control is `elementHost2`.</span></span>

7. <span data-ttu-id="779e0-136">Öffnen Sie im Smarttagbereich für `elementHost2`die Dropdown Liste **gehostete Inhalte auswählen** .</span><span class="sxs-lookup"><span data-stu-id="779e0-136">In the smart tag panel for `elementHost2`, open the **Select Hosted Content** drop-down list.</span></span>

8. <span data-ttu-id="779e0-137">Wählen Sie in der Dropdown Liste **UserControl1** aus.</span><span class="sxs-lookup"><span data-stu-id="779e0-137">Select **UserControl1** from the drop-down list.</span></span>

9. <span data-ttu-id="779e0-138">Das `elementHost2`-Steuerelement hostet jetzt eine Instanz des `UserControl1`-Typs.</span><span class="sxs-lookup"><span data-stu-id="779e0-138">The `elementHost2` control now hosts an instance of the `UserControl1` type.</span></span>

## <a name="see-also"></a><span data-ttu-id="779e0-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="779e0-139">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="779e0-140">Migration und Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="779e0-140">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="779e0-141">Verwenden von WPF-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="779e0-141">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="779e0-142">Entwerfen von XAML-Code in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="779e0-142">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
