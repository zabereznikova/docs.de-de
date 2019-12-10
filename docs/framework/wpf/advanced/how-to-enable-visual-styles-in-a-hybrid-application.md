---
title: 'Gewusst wie: Aktivieren von visuellen Stilen in einer Hybridanwendung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- visual styles [Windows Forms]
ms.assetid: 95de9b9c-d804-405c-b2d1-49a88c1e0fe1
ms.openlocfilehash: 251c53a8665d2eae7c3b5bb23b0a388009362dcc
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960111"
---
# <a name="how-to-enable-visual-styles-in-a-hybrid-application"></a><span data-ttu-id="4d6ed-102">Gewusst wie: Aktivieren von visuellen Stilen in einer Hybridanwendung</span><span class="sxs-lookup"><span data-stu-id="4d6ed-102">How to: Enable Visual Styles in a Hybrid Application</span></span>
<span data-ttu-id="4d6ed-103">In diesem Thema wird gezeigt, wie Sie visuelle Stile für ein [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement aktivieren, das in einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]basierten Anwendung gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="4d6ed-103">This topic shows how to enable visual styles on a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control hosted in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span>  
  
 <span data-ttu-id="4d6ed-104">Wenn die Anwendung die <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>-Methode aufruft, werden die meisten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente automatisch visuelle Stile verwenden.</span><span class="sxs-lookup"><span data-stu-id="4d6ed-104">If your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method, most of your [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls will automatically use visual styles.</span></span> <span data-ttu-id="4d6ed-105">Weitere Informationen finden Sie unter [Rendering von Steuerelementen mit visuellen Stilen](../../winforms/controls/rendering-controls-with-visual-styles.md).</span><span class="sxs-lookup"><span data-stu-id="4d6ed-105">For more information, see [Rendering Controls with Visual Styles](../../winforms/controls/rendering-controls-with-visual-styles.md).</span></span>  
  
 <span data-ttu-id="4d6ed-106">Eine umfassende Code Auflistung der in diesem Thema dargestellten Aufgaben finden Sie unter [Aktivieren von visuellen Stilen in Hybrid Anwendungen](https://go.microsoft.com/fwlink/?LinkID=159986).</span><span class="sxs-lookup"><span data-stu-id="4d6ed-106">For a complete code listing of the tasks illustrated in this topic, see [Enabling Visual Styles in a Hybrid Application Sample](https://go.microsoft.com/fwlink/?LinkID=159986).</span></span>  
  
## <a name="enabling-windows-forms-visual-styles"></a><span data-ttu-id="4d6ed-107">Aktivieren visueller Windows Forms-Stile</span><span class="sxs-lookup"><span data-stu-id="4d6ed-107">Enabling Windows Forms Visual Styles</span></span>  
  
#### <a name="to-enable-windows-forms-visual-styles"></a><span data-ttu-id="4d6ed-108">Aktivieren visueller Windows Forms-Stile</span><span class="sxs-lookup"><span data-stu-id="4d6ed-108">To enable Windows Forms visual styles</span></span>  
  
1. <span data-ttu-id="4d6ed-109">Erstellen Sie ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungsprojekt mit dem Namen `HostingWfWithVisualStyles`.</span><span class="sxs-lookup"><span data-stu-id="4d6ed-109">Create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Application project named `HostingWfWithVisualStyles`.</span></span>  
  
2. <span data-ttu-id="4d6ed-110">Fügen Sie im Projektmappen-Explorer Verweise auf die folgenden Assemblys hinzu.</span><span class="sxs-lookup"><span data-stu-id="4d6ed-110">In Solution Explorer, add references to the following assemblies.</span></span>  
  
    - <span data-ttu-id="4d6ed-111">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="4d6ed-111">WindowsFormsIntegration</span></span>  
  
    - <span data-ttu-id="4d6ed-112">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="4d6ed-112">System.Windows.Forms</span></span>  
  
3. <span data-ttu-id="4d6ed-113">Doppelklicken Sie in der Toolbox auf das <xref:System.Windows.Controls.Grid> Symbol, um ein <xref:System.Windows.Controls.Grid> Element auf der Entwurfs Oberfläche zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="4d6ed-113">In the Toolbox, double-click the <xref:System.Windows.Controls.Grid> icon to place a <xref:System.Windows.Controls.Grid> element on the design surface.</span></span>  
  
4. <span data-ttu-id="4d6ed-114">Legen Sie im Eigenschaftenfenster die Werte der Eigenschaften <xref:System.Windows.FrameworkElement.Height%2A> und <xref:System.Windows.FrameworkElement.Width%2A> auf **Auto**fest.</span><span class="sxs-lookup"><span data-stu-id="4d6ed-114">In the Properties window, set the values of the <xref:System.Windows.FrameworkElement.Height%2A> and <xref:System.Windows.FrameworkElement.Width%2A> properties to **Auto**.</span></span>  
  
5. <span data-ttu-id="4d6ed-115">Wählen Sie in Designansicht-oder XAML-Ansicht den <xref:System.Windows.Window>aus.</span><span class="sxs-lookup"><span data-stu-id="4d6ed-115">In Design view or XAML view, select the <xref:System.Windows.Window>.</span></span>  
  
6. <span data-ttu-id="4d6ed-116">Klicken Sie im Eigenschaftenfenster auf die Registerkarte **Ereignisse** .</span><span class="sxs-lookup"><span data-stu-id="4d6ed-116">In the Properties window, click the **Events** tab.</span></span>  
  
7. <span data-ttu-id="4d6ed-117">Doppelklicken Sie auf das <xref:System.Windows.FrameworkElement.Loaded> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="4d6ed-117">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>
  
8. <span data-ttu-id="4d6ed-118">Fügen Sie in MainWindow. XAML. vb oder MainWindow.XAML.cs den folgenden Code ein, um das <xref:System.Windows.FrameworkElement.Loaded>-Ereignis zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="4d6ed-118">In MainWindow.xaml.vb or MainWindow.xaml.cs, insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>  
  
     [!code-csharp[HostingWfWithVisualStyles#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfWithVisualStyles/CSharp/HostingWfWithVisualStyles/Window1.xaml.cs#11)]
     [!code-vb[HostingWfWithVisualStyles#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfWithVisualStyles/VisualBasic/HostingWfWithVisualStyles/Window1.xaml.vb#11)]  
  
9. <span data-ttu-id="4d6ed-119">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4d6ed-119">Press F5 to build and run the application.</span></span>  
  
     <span data-ttu-id="4d6ed-120">Das [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement wird mit visuellen Stilen gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="4d6ed-120">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is painted with visual styles.</span></span>  
  
## <a name="disabling-windows-forms-visual-styles"></a><span data-ttu-id="4d6ed-121">Deaktivieren visueller Windows Forms-Stile</span><span class="sxs-lookup"><span data-stu-id="4d6ed-121">Disabling Windows Forms Visual Styles</span></span>  
 <span data-ttu-id="4d6ed-122">Wenn Sie visuelle Stile deaktivieren möchten, entfernen Sie einfach den aufzurufenden <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="4d6ed-122">To disable visual styles, simply remove the call to the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>  
  
#### <a name="to-disable-windows-forms-visual-styles"></a><span data-ttu-id="4d6ed-123">So deaktivieren Sie visuelle Stile für Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4d6ed-123">To disable Windows Forms visual styles</span></span>  
  
1. <span data-ttu-id="4d6ed-124">Öffnen Sie „MainWindow.Xaml.vb“ bzw. „MainWindow.Xaml.cs“ im Code-Editor.</span><span class="sxs-lookup"><span data-stu-id="4d6ed-124">Open MainWindow.xaml.vb or MainWindow.xaml.cs in the Code Editor.</span></span>  
  
2. <span data-ttu-id="4d6ed-125">Kommentieren Sie den aufzurufenden <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> Methode aus.</span><span class="sxs-lookup"><span data-stu-id="4d6ed-125">Comment out the call to the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>  
  
3. <span data-ttu-id="4d6ed-126">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4d6ed-126">Press F5 to build and run the application.</span></span>  
  
     <span data-ttu-id="4d6ed-127">Das [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement wird mit dem Standard Systemstil gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="4d6ed-127">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is painted with the default system style.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d6ed-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d6ed-128">See also</span></span>

- <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>
- <xref:System.Windows.Forms.VisualStyles>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="4d6ed-129">Rendering von Steuerelementen mit visuellen Stilen</span><span class="sxs-lookup"><span data-stu-id="4d6ed-129">Rendering Controls with Visual Styles</span></span>](../../winforms/controls/rendering-controls-with-visual-styles.md)
- [<span data-ttu-id="4d6ed-130">Exemplarische Vorgehensweise: Hosten eines Windows Forms-Steuerelements in WPF</span><span class="sxs-lookup"><span data-stu-id="4d6ed-130">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
