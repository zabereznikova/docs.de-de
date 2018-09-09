---
title: 'Exemplarische Vorgehensweise: Hosten eines Windows Forms-Steuerelements in WPF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 9cb88415-39b0-4c46-80c4-ff325b674286
ms.openlocfilehash: fcf2b4bd552a8c718ebd4d3f5c06ad7af8efd2a2
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2018
ms.locfileid: "44228012"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf"></a><span data-ttu-id="7faab-102">Exemplarische Vorgehensweise: Hosten eines Windows Forms-Steuerelements in WPF</span><span class="sxs-lookup"><span data-stu-id="7faab-102">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="7faab-103"> stellt viele Steuerelemente mit einem großen Funktionsumfang bereit.</span><span class="sxs-lookup"><span data-stu-id="7faab-103"> provides many controls with a rich feature set.</span></span> <span data-ttu-id="7faab-104">Allerdings unter Umständen möchten Sie verwenden [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] steuert, die auf Ihre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Seiten.</span><span class="sxs-lookup"><span data-stu-id="7faab-104">However, you may sometimes want to use [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls on your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pages.</span></span> <span data-ttu-id="7faab-105">Angenommen, Sie müssen möglicherweise eine erhebliche Investition in vorhandenen [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente, oder Sie haben möglicherweise eine [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] -Steuerelement, das einzigartige Funktionen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="7faab-105">For example, you may have a substantial investment in existing [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls, or you may have a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control that provides unique functionality.</span></span>  
  
 <span data-ttu-id="7faab-106">In dieser exemplarischen Vorgehensweise erfahren Sie, wie zum Hosten einer [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control für eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Seite mithilfe von Code.</span><span class="sxs-lookup"><span data-stu-id="7faab-106">This walkthrough shows you how to host a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page by using code.</span></span>  
  
 <span data-ttu-id="7faab-107">Eine vollständige codeauflistung der Aufgaben in dieser exemplarischen Vorgehensweise veranschaulicht, finden Sie unter [Hosten eines Windows Forms-Steuerelements in WPF-Beispiel](https://go.microsoft.com/fwlink/?LinkID=160057).</span><span class="sxs-lookup"><span data-stu-id="7faab-107">For a complete code listing of the tasks shown in this walkthrough, see [Hosting a Windows Forms Control in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=160057).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7faab-108">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="7faab-108">Prerequisites</span></span>  
 <span data-ttu-id="7faab-109">Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="7faab-109">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]  
  
## <a name="hosting-the-windows-forms-control"></a><span data-ttu-id="7faab-111">Hosten des Windows Forms-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="7faab-111">Hosting the Windows Forms Control</span></span>  
  
#### <a name="to-host-the-maskedtextbox-control"></a><span data-ttu-id="7faab-112">So hosten Sie das MaskedTextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="7faab-112">To host the MaskedTextBox control</span></span>  
  
1.  <span data-ttu-id="7faab-113">Erstellen einer WPF-Anwendungsprojekt mit dem Namen `HostingWfInWpf`.</span><span class="sxs-lookup"><span data-stu-id="7faab-113">Create a WPF Application project named `HostingWfInWpf`.</span></span>  
  
2.  <span data-ttu-id="7faab-114">Fügen Sie Verweise auf die folgenden Assemblys hinzu.</span><span class="sxs-lookup"><span data-stu-id="7faab-114">Add references to the following assemblies.</span></span>  
  
    -   <span data-ttu-id="7faab-115">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="7faab-115">WindowsFormsIntegration</span></span>  
  
    -   <span data-ttu-id="7faab-116">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="7faab-116">System.Windows.Forms</span></span>  
  
3.  <span data-ttu-id="7faab-117">Öffnen Sie "MainWindow.xaml" in der [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7faab-117">Open MainWindow.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
4.  <span data-ttu-id="7faab-118">Name der <xref:System.Windows.Controls.Grid> Element `grid1`.</span><span class="sxs-lookup"><span data-stu-id="7faab-118">Name the <xref:System.Windows.Controls.Grid> element `grid1`.</span></span>  
  
     [!code-xaml[HostingWfInWPF#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml#1)]  
  
5.  <span data-ttu-id="7faab-119">Wählen Sie in der Entwurfsansicht oder XAML-Ansicht der <xref:System.Windows.Window> Element.</span><span class="sxs-lookup"><span data-stu-id="7faab-119">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>  
  
6.  <span data-ttu-id="7faab-120">Klicken Sie im Eigenschaftenfenster auf die **Ereignisse** Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="7faab-120">In the Properties window, click the **Events** tab.</span></span>  
  
7.  <span data-ttu-id="7faab-121">Doppelklicken Sie auf die <xref:System.Windows.FrameworkElement.Loaded> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="7faab-121">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>  
  
8.  <span data-ttu-id="7faab-122">Fügen Sie den folgenden Code zum Behandeln der <xref:System.Windows.FrameworkElement.Loaded> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="7faab-122">Insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>  
  
     [!code-csharp[HostingWfInWPF#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#10)]
     [!code-vb[HostingWfInWPF#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#10)]  
  
9. <span data-ttu-id="7faab-123">Fügen Sie am Anfang der Datei, die folgenden `Imports` oder `using` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="7faab-123">At the top of the file, add the following `Imports` or `using` statement.</span></span>  
  
     [!code-csharp[HostingWfInWPF#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#11)]
     [!code-vb[HostingWfInWPF#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#11)]  
  
10. <span data-ttu-id="7faab-124">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7faab-124">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7faab-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7faab-125">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="7faab-126">Entwerfen von XAML-Code in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7faab-126">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)  
 [<span data-ttu-id="7faab-127">Exemplarische Vorgehensweise: Hosten eines Windows Forms-Steuerelements in WPF mithilfe von XAML</span><span class="sxs-lookup"><span data-stu-id="7faab-127">Walkthrough: Hosting a Windows Forms Control in WPF by Using XAML</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml.md)  
 [<span data-ttu-id="7faab-128">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF</span><span class="sxs-lookup"><span data-stu-id="7faab-128">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [<span data-ttu-id="7faab-129">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7faab-129">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)  
 [<span data-ttu-id="7faab-130">Windows Forms-Steuerelemente und entsprechende WPF-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="7faab-130">Windows Forms Controls and Equivalent WPF Controls</span></span>](../../../../docs/framework/wpf/advanced/windows-forms-controls-and-equivalent-wpf-controls.md)  
 [<span data-ttu-id="7faab-131">Beispiel zum Hosten eines Windows Forms-Steuerelements in WPF</span><span class="sxs-lookup"><span data-stu-id="7faab-131">Hosting a Windows Forms Control in WPF Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160057)
