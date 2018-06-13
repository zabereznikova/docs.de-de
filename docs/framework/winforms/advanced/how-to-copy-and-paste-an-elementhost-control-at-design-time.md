---
title: 'Gewusst wie: Kopieren und Einfügen eines ElementHost-Steuerelements zur Entwurfszeit'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
ms.openlocfilehash: 1a9938500287b3b44f13f0aa664da85b7fdb4675
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524851"
---
# <a name="how-to-copy-and-paste-an-elementhost-control-at-design-time"></a><span data-ttu-id="7cd33-102">Gewusst wie: Kopieren und Einfügen eines ElementHost-Steuerelements zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="7cd33-102">How to: Copy and Paste an ElementHost Control at Design Time</span></span>
<span data-ttu-id="7cd33-103">Dieses Verfahren wird gezeigt, wie ein Windows Presentation Foundation (WPF)-Steuerelement in einem Windows Form zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="7cd33-103">This procedure shows you how to copy a Windows Presentation Foundation (WPF) control on a Windows Form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7cd33-104">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="7cd33-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="7cd33-105">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="7cd33-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="7cd33-106">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="7cd33-106">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-copy-and-paste-an-elementhost-control-at-design-time"></a><span data-ttu-id="7cd33-107">Kopieren und Einfügen eines ElementHost-Steuerelements zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="7cd33-107">To copy and paste an ElementHost control at design time</span></span>  
  
1.  <span data-ttu-id="7cd33-108">Fügen Sie eine neue WPF <xref:System.Windows.Controls.UserControl> dem Windows Forms-Projekt.</span><span class="sxs-lookup"><span data-stu-id="7cd33-108">Add a new WPF <xref:System.Windows.Controls.UserControl> to your Windows Forms project.</span></span> <span data-ttu-id="7cd33-109">Verwenden Sie den Standardnamen (`UserControl1.xaml`) für den Steuerelementtyp.</span><span class="sxs-lookup"><span data-stu-id="7cd33-109">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="7cd33-110">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen neuen WPF-Inhalts in Windows Forms zur Entwurfszeit](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="7cd33-110">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2.  <span data-ttu-id="7cd33-111">In der **Eigenschaften** Fenster, legen Sie den Wert von der <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften des `UserControl1` auf `200`.</span><span class="sxs-lookup"><span data-stu-id="7cd33-111">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties of `UserControl1` to `200`.</span></span>  
  
3.  <span data-ttu-id="7cd33-112">Legen Sie den Wert der <xref:System.Windows.Controls.Control.Background%2A>-Eigenschaft auf `Blue` fest.</span><span class="sxs-lookup"><span data-stu-id="7cd33-112">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to `Blue`.</span></span>  
  
4.  <span data-ttu-id="7cd33-113">Erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="7cd33-113">Build the project.</span></span>  
  
5.  <span data-ttu-id="7cd33-114">Öffnen Sie `Form1` im Windows Forms-Designer.</span><span class="sxs-lookup"><span data-stu-id="7cd33-114">Open `Form1` in the Windows Forms Designer.</span></span>  
  
6.  <span data-ttu-id="7cd33-115">Aus der **Toolbox**, ziehen Sie eine Instanz des `UserControl1` auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="7cd33-115">From the **Toolbox**, drag an instance of `UserControl1` onto the form.</span></span>  
  
     <span data-ttu-id="7cd33-116">Eine Instanz von `UserControl1` wird in einem neuen <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement namens `elementHost1` gehostet.</span><span class="sxs-lookup"><span data-stu-id="7cd33-116">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
7.  <span data-ttu-id="7cd33-117">Während `elementHost1` ausgewählt ist, drücken Sie STRG + C, um das Steuerelement in die Zwischenablage zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="7cd33-117">With `elementHost1` selected, press CTRL+C to copy it to the clipboard.</span></span>  
  
8.  <span data-ttu-id="7cd33-118">Drücken Sie STRG + V, um das kopierte Steuerelement auf das Formular einfügen.</span><span class="sxs-lookup"><span data-stu-id="7cd33-118">Press CTRL+V to paste the copied control onto the form.</span></span>  
  
     <span data-ttu-id="7cd33-119">Ein neues <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement namens `elementHost2` wird auf dem Formular erstellt.</span><span class="sxs-lookup"><span data-stu-id="7cd33-119">A new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost2` is created on the form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cd33-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7cd33-120">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="7cd33-121">Exemplarische Vorgehensweise: Kopieren und Einfügen eines ElementHost-Steuerelements in separate Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7cd33-121">Walkthrough: Copying and Pasting an ElementHost Control into Separate Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/copy--paste-an-elementhost-control-into-forms.md)  
 [<span data-ttu-id="7cd33-122">Migration und Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="7cd33-122">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [<span data-ttu-id="7cd33-123">Verwenden von WPF-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="7cd33-123">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [<span data-ttu-id="7cd33-124">WPF-Designer</span><span class="sxs-lookup"><span data-stu-id="7cd33-124">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)
