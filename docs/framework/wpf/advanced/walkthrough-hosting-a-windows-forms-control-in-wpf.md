---
title: Hosten eines Windows Forms-Steuer Elements in WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 9cb88415-39b0-4c46-80c4-ff325b674286
ms.openlocfilehash: 5e994f65c0665a5726c4c8c19141da5ea3f5e6f6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794184"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf"></a><span data-ttu-id="d2f68-102">Exemplarische Vorgehensweise: Hosten eines Windows Forms-Steuerelements in WPF</span><span class="sxs-lookup"><span data-stu-id="d2f68-102">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="d2f68-103">stellt viele Steuerelemente mit einem großen Funktionsumfang bereit.</span><span class="sxs-lookup"><span data-stu-id="d2f68-103">provides many controls with a rich feature set.</span></span> <span data-ttu-id="d2f68-104">Es kann jedoch vorkommen, dass Sie Windows Forms-Steuerelemente auf Ihren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Seiten verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="d2f68-104">However, you may sometimes want to use Windows Forms controls on your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pages.</span></span> <span data-ttu-id="d2f68-105">Beispielsweise haben Sie möglicherweise beträchtliche Investitionen in vorhandene Windows Forms-Steuerelemente, oder Sie verfügen über ein Windows Forms-Steuerelement, das eindeutige Funktionen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="d2f68-105">For example, you may have a substantial investment in existing Windows Forms controls, or you may have a Windows Forms control that provides unique functionality.</span></span>

<span data-ttu-id="d2f68-106">In dieser exemplarischen Vorgehensweise wird gezeigt, wie Sie mithilfe von Code eine Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType>-Steuerelement auf einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Seite hosten.</span><span class="sxs-lookup"><span data-stu-id="d2f68-106">This walkthrough shows you how to host a Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page by using code.</span></span>

<span data-ttu-id="d2f68-107">Eine umfassende Code Auflistung der in dieser exemplarischen Vorgehensweise gezeigten Aufgaben finden Sie unter [Hosting a Windows Forms Control in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=160057).</span><span class="sxs-lookup"><span data-stu-id="d2f68-107">For a complete code listing of the tasks shown in this walkthrough, see [Hosting a Windows Forms Control in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=160057).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d2f68-108">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="d2f68-108">Prerequisites</span></span>

<span data-ttu-id="d2f68-109">Für diese exemplarische Vorgehensweise benötigen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d2f68-109">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="hosting-the-windows-forms-control"></a><span data-ttu-id="d2f68-110">Hosten des Windows Forms-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="d2f68-110">Hosting the Windows Forms Control</span></span>

### <a name="to-host-the-maskedtextbox-control"></a><span data-ttu-id="d2f68-111">So hosten Sie das MaskedTextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d2f68-111">To host the MaskedTextBox control</span></span>

1. <span data-ttu-id="d2f68-112">Erstellen Sie ein WPF-Anwendungsprojekt mit dem Namen `HostingWfInWpf`.</span><span class="sxs-lookup"><span data-stu-id="d2f68-112">Create a WPF Application project named `HostingWfInWpf`.</span></span>

2. <span data-ttu-id="d2f68-113">Fügen Sie Verweise auf die folgenden Assemblys hinzu.</span><span class="sxs-lookup"><span data-stu-id="d2f68-113">Add references to the following assemblies.</span></span>

    - <span data-ttu-id="d2f68-114">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="d2f68-114">WindowsFormsIntegration</span></span>

    - <span data-ttu-id="d2f68-115">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="d2f68-115">System.Windows.Forms</span></span>

3. <span data-ttu-id="d2f68-116">Öffnen Sie die Datei "MainWindow. XAML" im WPF-Designer.</span><span class="sxs-lookup"><span data-stu-id="d2f68-116">Open MainWindow.xaml in the WPF Designer.</span></span>

4. <span data-ttu-id="d2f68-117">Benennen Sie das <xref:System.Windows.Controls.Grid> Element `grid1`.</span><span class="sxs-lookup"><span data-stu-id="d2f68-117">Name the <xref:System.Windows.Controls.Grid> element `grid1`.</span></span>

     [!code-xaml[HostingWfInWPF#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml#1)]

5. <span data-ttu-id="d2f68-118">Wählen Sie in Designansicht-oder XAML-Ansicht das <xref:System.Windows.Window> Element aus.</span><span class="sxs-lookup"><span data-stu-id="d2f68-118">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>

6. <span data-ttu-id="d2f68-119">Klicken Sie im Eigenschaftenfenster auf die Registerkarte **Ereignisse** .</span><span class="sxs-lookup"><span data-stu-id="d2f68-119">In the Properties window, click the **Events** tab.</span></span>

7. <span data-ttu-id="d2f68-120">Doppelklicken Sie auf das <xref:System.Windows.FrameworkElement.Loaded> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="d2f68-120">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

8. <span data-ttu-id="d2f68-121">Fügen Sie den folgenden Code ein, um das <xref:System.Windows.FrameworkElement.Loaded>-Ereignis zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="d2f68-121">Insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

     [!code-csharp[HostingWfInWPF#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#10)]
     [!code-vb[HostingWfInWPF#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#10)]

9. <span data-ttu-id="d2f68-122">Fügen Sie am Anfang der Datei die folgende `Imports` oder `using` Anweisung hinzu.</span><span class="sxs-lookup"><span data-stu-id="d2f68-122">At the top of the file, add the following `Imports` or `using` statement.</span></span>

     [!code-csharp[HostingWfInWPF#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#11)]
     [!code-vb[HostingWfInWPF#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#11)]

10. <span data-ttu-id="d2f68-123">Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d2f68-123">Press **F5** to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="d2f68-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2f68-124">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="d2f68-125">Entwerfen von XAML-Code in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d2f68-125">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="d2f68-126">Exemplarische Vorgehensweise: Hosten eines Windows Forms-Steuerelements in WPF mithilfe von XAML</span><span class="sxs-lookup"><span data-stu-id="d2f68-126">Walkthrough: Hosting a Windows Forms Control in WPF by Using XAML</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml.md)
- [<span data-ttu-id="d2f68-127">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF</span><span class="sxs-lookup"><span data-stu-id="d2f68-127">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="d2f68-128">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d2f68-128">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="d2f68-129">Windows Forms-Steuerelemente und entsprechende WPF-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="d2f68-129">Windows Forms Controls and Equivalent WPF Controls</span></span>](windows-forms-controls-and-equivalent-wpf-controls.md)
- [<span data-ttu-id="d2f68-130">Beispiel zum Hosten eines Windows Forms-Steuerelements in WPF</span><span class="sxs-lookup"><span data-stu-id="d2f68-130">Hosting a Windows Forms Control in WPF Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160057)
