---
title: Hosten eines Windows Forms-Steuer Elements in WPF mithilfe von XAML
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
ms.openlocfilehash: 2c5764ac2dfd9f5747087cc76e3971c002f12b90
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794192"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml"></a><span data-ttu-id="62612-102">Exemplarische Vorgehensweise: Hosten eines Windows Forms-Steuerelements in WPF mithilfe von XAML</span><span class="sxs-lookup"><span data-stu-id="62612-102">Walkthrough: Hosting a Windows Forms Control in WPF by Using XAML</span></span>
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="62612-103">stellt viele Steuerelemente mit einem großen Funktionsumfang bereit.</span><span class="sxs-lookup"><span data-stu-id="62612-103">provides many controls with a rich feature set.</span></span> <span data-ttu-id="62612-104">Es kann jedoch vorkommen, dass Sie Windows Forms-Steuerelemente auf Ihren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Seiten verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="62612-104">However, you may sometimes want to use Windows Forms controls on your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pages.</span></span> <span data-ttu-id="62612-105">Beispielsweise haben Sie möglicherweise beträchtliche Investitionen in vorhandene Windows Forms-Steuerelemente, oder Sie verfügen über ein Windows Forms-Steuerelement, das eindeutige Funktionen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="62612-105">For example, you may have a substantial investment in existing Windows Forms controls, or you may have a Windows Forms control that provides unique functionality.</span></span>  
  
 <span data-ttu-id="62612-106">In dieser exemplarischen Vorgehensweise wird gezeigt, wie Sie mithilfe [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]ein Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType>-Steuerelement auf einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Seite hosten.</span><span class="sxs-lookup"><span data-stu-id="62612-106">This walkthrough shows you how to host a Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 <span data-ttu-id="62612-107">Eine vollständige Code Auflistung der in dieser exemplarischen Vorgehensweise gezeigten Aufgaben finden [Sie unter Hosting a Windows Forms Control in WPF using XAML Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml).</span><span class="sxs-lookup"><span data-stu-id="62612-107">For a complete code listing of the tasks shown in this walkthrough, see [Hosting a Windows Forms Control in WPF by Using XAML Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml).</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="62612-108">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="62612-108">Prerequisites</span></span>  

<span data-ttu-id="62612-109">Für diese exemplarische Vorgehensweise benötigen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="62612-109">You need Visual Studio to complete this walkthrough.</span></span>  
  
## <a name="hosting-the-windows-forms-control"></a><span data-ttu-id="62612-110">Hosten des Windows Forms-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="62612-110">Hosting the Windows Forms Control</span></span>  
  
#### <a name="to-host-the-maskedtextbox-control"></a><span data-ttu-id="62612-111">So hosten Sie das MaskedTextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="62612-111">To host the MaskedTextBox control</span></span>  
  
1. <span data-ttu-id="62612-112">Erstellen Sie ein WPF-Anwendungsprojekt mit dem Namen `HostingWfInWpfWithXaml`.</span><span class="sxs-lookup"><span data-stu-id="62612-112">Create a WPF Application project named `HostingWfInWpfWithXaml`.</span></span>  
  
2. <span data-ttu-id="62612-113">Fügen Sie Verweise auf die folgenden Assemblys hinzu.</span><span class="sxs-lookup"><span data-stu-id="62612-113">Add references to the following assemblies.</span></span>  
  
    - <span data-ttu-id="62612-114">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="62612-114">WindowsFormsIntegration</span></span>  
  
    - <span data-ttu-id="62612-115">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="62612-115">System.Windows.Forms</span></span>  
  
3. <span data-ttu-id="62612-116">Öffnen Sie die Datei "MainWindow. XAML" im WPF-Designer.</span><span class="sxs-lookup"><span data-stu-id="62612-116">Open MainWindow.xaml in the WPF Designer.</span></span>  
  
4. <span data-ttu-id="62612-117">Fügen Sie im <xref:System.Windows.Window>-Element die folgende Namespace Zuordnung hinzu.</span><span class="sxs-lookup"><span data-stu-id="62612-117">In the <xref:System.Windows.Window> element, add the following namespace mapping.</span></span> <span data-ttu-id="62612-118">Die `wf`-Namespace Zuordnung legt einen Verweis auf die Assembly fest, die das Windows Forms Steuerelement enthält.</span><span class="sxs-lookup"><span data-stu-id="62612-118">The `wf` namespace mapping establishes a reference to the assembly that contains the Windows Forms control.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5. <span data-ttu-id="62612-119">Fügen Sie im <xref:System.Windows.Controls.Grid>-Element den folgenden XAML-Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="62612-119">In the <xref:System.Windows.Controls.Grid> element add the following XAML.</span></span>  
  
     <span data-ttu-id="62612-120">Das <xref:System.Windows.Forms.MaskedTextBox> Steuerelement wird als untergeordnetes Element des <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuer Elements erstellt.</span><span class="sxs-lookup"><span data-stu-id="62612-120">The <xref:System.Windows.Forms.MaskedTextBox> control is created as a child of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control.</span></span>  
  
     [!code-xaml[HostingWfInWpfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6. <span data-ttu-id="62612-121">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="62612-121">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62612-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62612-122">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="62612-123">Entwerfen von XAML-Code in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="62612-123">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="62612-124">Exemplarische Vorgehensweise: Hosten eines Windows Forms-Steuerelements in WPF</span><span class="sxs-lookup"><span data-stu-id="62612-124">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [<span data-ttu-id="62612-125">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF</span><span class="sxs-lookup"><span data-stu-id="62612-125">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="62612-126">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="62612-126">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="62612-127">Windows Forms-Steuerelemente und entsprechende WPF-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="62612-127">Windows Forms Controls and Equivalent WPF Controls</span></span>](windows-forms-controls-and-equivalent-wpf-controls.md)
- [<span data-ttu-id="62612-128">Hosting eines Windows Forms-Steuer Elements in WPF mithilfe von XAML-Beispiel</span><span class="sxs-lookup"><span data-stu-id="62612-128">Hosting a Windows Forms Control in WPF by Using XAML Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160000)
