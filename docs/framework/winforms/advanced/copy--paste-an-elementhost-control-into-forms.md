---
title: 'Exemplarische Vorgehensweise: Kopieren und Einfügen eines ElementHost-Steuerelements in separate Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 6e81bb13-577c-46c3-a1cf-8d15969fb83e
ms.openlocfilehash: 55b426fbe95bac269183a649ecd839175a8cbdda
ms.sourcegitcommit: 67de6cb5dd66a19f2180ba7e4d7aecc697f8a963
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44337680"
---
# <a name="walkthrough-copying-and-pasting-an-elementhost-control-into-separate-windows-forms"></a><span data-ttu-id="2644b-102">Exemplarische Vorgehensweise: Kopieren und Einfügen eines ElementHost-Steuerelements in separate Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2644b-102">Walkthrough: Copying and Pasting an ElementHost Control into Separate Windows Forms</span></span>
<span data-ttu-id="2644b-103">In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie ein WPF-Steuerelement (Windows Presentation Foundation) von einem Windows Form-Objekt in ein anderes kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="2644b-103">This walkthrough shows you how to copy a Windows Presentation Foundation (WPF) control from one Windows Form to another.</span></span>  
  
 <span data-ttu-id="2644b-104">Im Verlauf dieser exemplarischen Vorgehensweise führen Sie die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="2644b-104">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="2644b-105">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="2644b-105">Create the project.</span></span>  
  
-   <span data-ttu-id="2644b-106">Kopieren eines WPF-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="2644b-106">Copy a WPF Control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2644b-107">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="2644b-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="2644b-108">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="2644b-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="2644b-109">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="2644b-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2644b-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="2644b-110">Prerequisites</span></span>  
 <span data-ttu-id="2644b-111">Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="2644b-111">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)]<span data-ttu-id="2644b-112">.</span><span class="sxs-lookup"><span data-stu-id="2644b-112">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="2644b-113">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="2644b-113">Creating the Project</span></span>  
 <span data-ttu-id="2644b-114">Zunächst muss das Windows Forms-Projekt erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="2644b-114">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2644b-115">Beim Hosten von WPF-Inhalt werden nur C#- und Visual Basic-Projekte unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2644b-115">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="2644b-116">So erstellen Sie das Projekt</span><span class="sxs-lookup"><span data-stu-id="2644b-116">To create the project</span></span>  
  
-   <span data-ttu-id="2644b-117">Erstellen Sie ein neues Windows Forms-Anwendungsprojekt in Visual Basic oder Visual c# mit dem Namen `CopyElementHost`.</span><span class="sxs-lookup"><span data-stu-id="2644b-117">Create a new Windows Forms Application project in Visual Basic or Visual C# named `CopyElementHost`.</span></span>  
  
## <a name="copying-a-wpf-control"></a><span data-ttu-id="2644b-118">Kopieren eines WPF-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="2644b-118">Copying a WPF Control</span></span>  
 <span data-ttu-id="2644b-119">Nachdem Sie dem Projekt ein WPF-Steuerelement hinzugefügt haben, können Sie es auf andere Formulare im Projekt kopieren.</span><span class="sxs-lookup"><span data-stu-id="2644b-119">After you add a WPF control to the project, you can copy it to other forms in the project.</span></span>  
  
#### <a name="to-copy-a-wpf-control"></a><span data-ttu-id="2644b-120">So kopieren Sie ein WPF-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="2644b-120">To copy a WPF control</span></span>  
  
1.  <span data-ttu-id="2644b-121">Fügen Sie der Projektmappe ein neues WPF-<xref:System.Windows.Controls.UserControl>-Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="2644b-121">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="2644b-122">Verwenden Sie den Standardnamen (`UserControl1.xaml`) für den Steuerelementtyp.</span><span class="sxs-lookup"><span data-stu-id="2644b-122">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="2644b-123">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen neuen WPF-Inhalt in Windows Forms zur Entwurfszeit](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="2644b-123">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2.  <span data-ttu-id="2644b-124">Erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="2644b-124">Build the project.</span></span>  
  
3.  <span data-ttu-id="2644b-125">Öffnen Sie `Form1` im Windows Forms-Designer.</span><span class="sxs-lookup"><span data-stu-id="2644b-125">Open `Form1` in the Windows Forms Designer.</span></span>  
  
4.  <span data-ttu-id="2644b-126">Von der **Toolbox**, ziehen Sie eine Instanz des `UserControl1` auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="2644b-126">From the **Toolbox**, drag an instance of `UserControl1` onto the form.</span></span>  
  
     <span data-ttu-id="2644b-127">Eine Instanz von `UserControl1` wird in einem neuen <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement namens `elementHost1` gehostet.</span><span class="sxs-lookup"><span data-stu-id="2644b-127">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
5.  <span data-ttu-id="2644b-128">Während `elementHost1` ausgewählt ist, drücken Sie STRG + C, um das Steuerelement in die Zwischenablage zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="2644b-128">With `elementHost1` selected, press CTRL+C to copy it to the clipboard.</span></span>  
  
6.  <span data-ttu-id="2644b-129">Fügen Sie dem Projekt ein neues Windows Form-Objekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="2644b-129">Add a new Windows Form to the project.</span></span> <span data-ttu-id="2644b-130">Verwenden Sie den Standardnamen für den Formulartyp, `Form2`.</span><span class="sxs-lookup"><span data-stu-id="2644b-130">Use the default name for the form type, `Form2`.</span></span>  
  
7.  <span data-ttu-id="2644b-131">Während `Form2` im Windows Forms-Designer geöffnet ist, drücken Sie STRG+V, um eine Kopie von `elementHost1` auf dem Formular einzufügen.</span><span class="sxs-lookup"><span data-stu-id="2644b-131">With `Form2` open in the Windows Forms Designer, press CTRL+V to paste a copy of `elementHost1` onto the form.</span></span>  
  
     <span data-ttu-id="2644b-132">Das kopierte Steuerelement erhält ebenfalls den Namen `elementHost1`, da es ein privates Feld der `Form2`-Klasse ist.</span><span class="sxs-lookup"><span data-stu-id="2644b-132">The copied control is also named `elementHost1`, because it is a private field of the `Form2` class.</span></span> <span data-ttu-id="2644b-133">Es gibt keinen Namenskonflikt mit `elementHost1` in der `Form1`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="2644b-133">There is no name collision with the `elementHost1` in the `Form1` class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2644b-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2644b-134">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="2644b-135">Migration und Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="2644b-135">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [<span data-ttu-id="2644b-136">Verwenden von WPF-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="2644b-136">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [<span data-ttu-id="2644b-137">Entwerfen von XAML-Code in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2644b-137">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
