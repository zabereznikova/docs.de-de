---
title: 'Exemplarische Vorgehensweise: Hosten eines Windows Forms-Steuerelements in WPF mithilfe von XAML'
ms.date: 03/30/2017
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
ms.openlocfilehash: 61a234a679d9937cb38a753a3d73f2ecc9ec891a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59190365"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml"></a><span data-ttu-id="2a389-102">Exemplarische Vorgehensweise: Hosten eines Windows Forms-Steuerelements in WPF mithilfe von XAML</span><span class="sxs-lookup"><span data-stu-id="2a389-102">Walkthrough: Hosting a Windows Forms Control in WPF by Using XAML</span></span>
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="2a389-103">stellt viele Steuerelemente mit einem großen Funktionsumfang bereit.</span><span class="sxs-lookup"><span data-stu-id="2a389-103">provides many controls with a rich feature set.</span></span> <span data-ttu-id="2a389-104">Allerdings unter Umständen möchten Sie verwenden [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] steuert, die auf Ihre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Seiten.</span><span class="sxs-lookup"><span data-stu-id="2a389-104">However, you may sometimes want to use [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls on your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pages.</span></span> <span data-ttu-id="2a389-105">Angenommen, Sie müssen möglicherweise eine erhebliche Investition in vorhandenen [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente, oder Sie haben möglicherweise eine [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] -Steuerelement, das einzigartige Funktionen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="2a389-105">For example, you may have a substantial investment in existing [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls, or you may have a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control that provides unique functionality.</span></span>  
  
 <span data-ttu-id="2a389-106">In dieser exemplarischen Vorgehensweise erfahren Sie, wie Sie ein Windows Forms hosten <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control für eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Seite mithilfe von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a389-106">This walkthrough shows you how to host a Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 <span data-ttu-id="2a389-107">Eine vollständige codeauflistung der Aufgaben in dieser exemplarischen Vorgehensweise veranschaulicht, finden Sie unter [Hosten eines Windows Forms-Steuerelements in WPF mithilfe von XAML-Beispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml).</span><span class="sxs-lookup"><span data-stu-id="2a389-107">For a complete code listing of the tasks shown in this walkthrough, see [Hosting a Windows Forms Control in WPF by Using XAML Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml).</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="2a389-108">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="2a389-108">Prerequisites</span></span>  

<span data-ttu-id="2a389-109">Für diese exemplarische Vorgehensweise benötigen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2a389-109">You need Visual Studio to complete this walkthrough.</span></span>  
  
## <a name="hosting-the-windows-forms-control"></a><span data-ttu-id="2a389-110">Hosten des Windows Forms-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="2a389-110">Hosting the Windows Forms Control</span></span>  
  
#### <a name="to-host-the-maskedtextbox-control"></a><span data-ttu-id="2a389-111">So hosten Sie das MaskedTextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="2a389-111">To host the MaskedTextBox control</span></span>  
  
1.  <span data-ttu-id="2a389-112">Erstellen einer WPF-Anwendungsprojekt mit dem Namen `HostingWfInWpfWithXaml`.</span><span class="sxs-lookup"><span data-stu-id="2a389-112">Create a WPF Application project named `HostingWfInWpfWithXaml`.</span></span>  
  
2.  <span data-ttu-id="2a389-113">Fügen Sie Verweise auf die folgenden Assemblys hinzu.</span><span class="sxs-lookup"><span data-stu-id="2a389-113">Add references to the following assemblies.</span></span>  
  
    -   <span data-ttu-id="2a389-114">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="2a389-114">WindowsFormsIntegration</span></span>  
  
    -   <span data-ttu-id="2a389-115">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="2a389-115">System.Windows.Forms</span></span>  
  
3.  <span data-ttu-id="2a389-116">Öffnen Sie "MainWindow.xaml" in der [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a389-116">Open MainWindow.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
4.  <span data-ttu-id="2a389-117">In der <xref:System.Windows.Window> -Element, fügen Sie die folgende Namespacezuordnung hinzu.</span><span class="sxs-lookup"><span data-stu-id="2a389-117">In the <xref:System.Windows.Window> element, add the following namespace mapping.</span></span> <span data-ttu-id="2a389-118">Die `wf` Namespace-Zuordnung erstellt einen Verweis auf die Assembly, die das Windows Forms-Steuerelement enthält.</span><span class="sxs-lookup"><span data-stu-id="2a389-118">The `wf` namespace mapping establishes a reference to the assembly that contains the Windows Forms control.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  <span data-ttu-id="2a389-119">In der <xref:System.Windows.Controls.Grid> Element fügen Sie das folgende XAML hinzu.</span><span class="sxs-lookup"><span data-stu-id="2a389-119">In the <xref:System.Windows.Controls.Grid> element add the following XAML.</span></span>  
  
     <span data-ttu-id="2a389-120">Die <xref:System.Windows.Forms.MaskedTextBox> Steuerelement wird erstellt, als untergeordnetes Element der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="2a389-120">The <xref:System.Windows.Forms.MaskedTextBox> control is created as a child of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control.</span></span>  
  
     [!code-xaml[HostingWfInWpfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6.  <span data-ttu-id="2a389-121">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2a389-121">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a389-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2a389-122">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="2a389-123">Entwerfen von XAML-Code in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2a389-123">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="2a389-124">Exemplarische Vorgehensweise: Hosten eines Windows Forms-Steuerelements in WPF</span><span class="sxs-lookup"><span data-stu-id="2a389-124">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [<span data-ttu-id="2a389-125">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF</span><span class="sxs-lookup"><span data-stu-id="2a389-125">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="2a389-126">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2a389-126">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="2a389-127">Windows Forms-Steuerelemente und entsprechende WPF-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="2a389-127">Windows Forms Controls and Equivalent WPF Controls</span></span>](windows-forms-controls-and-equivalent-wpf-controls.md)
- [<span data-ttu-id="2a389-128">Hosten eines Windows Forms-Steuerelements in WPF mit XAML-Beispiel</span><span class="sxs-lookup"><span data-stu-id="2a389-128">Hosting a Windows Forms Control in WPF by Using XAML Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160000)
