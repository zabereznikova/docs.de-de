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
ms.openlocfilehash: f4684e277335a119d41d5bd79d504ed37a76d6fc
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2018
ms.locfileid: "45675794"
---
# <a name="how-to-enable-visual-styles-in-a-hybrid-application"></a><span data-ttu-id="22dc9-102">Gewusst wie: Aktivieren von visuellen Stilen in einer Hybridanwendung</span><span class="sxs-lookup"><span data-stu-id="22dc9-102">How to: Enable Visual Styles in a Hybrid Application</span></span>
<span data-ttu-id="22dc9-103">In diesem Thema zeigt, wie Sie aktivieren [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] visuelle Stile für eine [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement, das in eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-basierten Anwendung.</span><span class="sxs-lookup"><span data-stu-id="22dc9-103">This topic shows how to enable [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] visual styles on a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control hosted in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span>  
  
 <span data-ttu-id="22dc9-104">Wenn Ihre Anwendung aufruft, die <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> -Methode, die meisten Ihrer [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] -Steuerelemente automatisch visuelle Stile verwenden, wenn Ihre Anwendung ausgeführt wird, auf [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="22dc9-104">If your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method, most of your [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls will automatically use visual styles when your application is run on [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)].</span></span> <span data-ttu-id="22dc9-105">Weitere Informationen finden Sie unter [Rendering von Steuerelementen mit visuellen Stilen](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md).</span><span class="sxs-lookup"><span data-stu-id="22dc9-105">For more information, see [Rendering Controls with Visual Styles](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md).</span></span>  
  
 <span data-ttu-id="22dc9-106">Eine vollständige codeauflistung der Aufgaben in diesem Thema veranschaulicht, finden Sie unter [Aktivieren von visuellen Stilen in einer Hybrid Application Sample](https://go.microsoft.com/fwlink/?LinkID=159986).</span><span class="sxs-lookup"><span data-stu-id="22dc9-106">For a complete code listing of the tasks illustrated in this topic, see [Enabling Visual Styles in a Hybrid Application Sample](https://go.microsoft.com/fwlink/?LinkID=159986).</span></span>  
  
## <a name="enabling-windows-forms-visual-styles"></a><span data-ttu-id="22dc9-107">Aktivieren visueller Windows Forms-Stile</span><span class="sxs-lookup"><span data-stu-id="22dc9-107">Enabling Windows Forms Visual Styles</span></span>  
  
#### <a name="to-enable-windows-forms-visual-styles"></a><span data-ttu-id="22dc9-108">Aktivieren visueller Windows Forms-Stile</span><span class="sxs-lookup"><span data-stu-id="22dc9-108">To enable Windows Forms visual styles</span></span>  
  
1.  <span data-ttu-id="22dc9-109">Erstellen Sie eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Anwendungsprojekt mit dem Namen `HostingWfWithVisualStyles`.</span><span class="sxs-lookup"><span data-stu-id="22dc9-109">Create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Application project named `HostingWfWithVisualStyles`.</span></span>  
  
2.  <span data-ttu-id="22dc9-110">Fügen Sie im Projektmappen-Explorer Verweise auf die folgenden Assemblys hinzu.</span><span class="sxs-lookup"><span data-stu-id="22dc9-110">In Solution Explorer, add references to the following assemblies.</span></span>  
  
    -   <span data-ttu-id="22dc9-111">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="22dc9-111">WindowsFormsIntegration</span></span>  
  
    -   <span data-ttu-id="22dc9-112">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="22dc9-112">System.Windows.Forms</span></span>  
  
3.  <span data-ttu-id="22dc9-113">Doppelklicken Sie in der Toolbox auf die <xref:System.Windows.Controls.Grid> Symbol für das Platzieren einer <xref:System.Windows.Controls.Grid> Element auf der Entwurfsoberfläche angezeigt.</span><span class="sxs-lookup"><span data-stu-id="22dc9-113">In the Toolbox, double-click the <xref:System.Windows.Controls.Grid> icon to place a <xref:System.Windows.Controls.Grid> element on the design surface.</span></span>  
  
4.  <span data-ttu-id="22dc9-114">Legen Sie im Fenster Eigenschaften die Werte von der <xref:System.Windows.FrameworkElement.Height%2A> und <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaften **automatisch**.</span><span class="sxs-lookup"><span data-stu-id="22dc9-114">In the Properties window, set the values of the <xref:System.Windows.FrameworkElement.Height%2A> and <xref:System.Windows.FrameworkElement.Width%2A> properties to **Auto**.</span></span>  
  
5.  <span data-ttu-id="22dc9-115">Wählen Sie in der Entwurfsansicht oder XAML-Ansicht der <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="22dc9-115">In Design view or XAML view, select the <xref:System.Windows.Window>.</span></span>  
  
6.  <span data-ttu-id="22dc9-116">Klicken Sie im Eigenschaftenfenster auf die **Ereignisse** Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="22dc9-116">In the Properties window, click the **Events** tab.</span></span>  
  
7.  <span data-ttu-id="22dc9-117">Doppelklicken Sie auf die <xref:System.Windows.FrameworkElement.Loaded> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="22dc9-117">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>
  
8.  <span data-ttu-id="22dc9-118">Fügen Sie in "MainWindow.Xaml.vb" bzw. "MainWindow.Xaml.cs" den folgenden Code zum Behandeln der <xref:System.Windows.FrameworkElement.Loaded> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="22dc9-118">In MainWindow.xaml.vb or MainWindow.xaml.cs, insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>  
  
     [!code-csharp[HostingWfWithVisualStyles#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfWithVisualStyles/CSharp/HostingWfWithVisualStyles/Window1.xaml.cs#11)]
     [!code-vb[HostingWfWithVisualStyles#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfWithVisualStyles/VisualBasic/HostingWfWithVisualStyles/Window1.xaml.vb#11)]  
  
9. <span data-ttu-id="22dc9-119">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="22dc9-119">Press F5 to build and run the application.</span></span>  
  
     <span data-ttu-id="22dc9-120">Die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement mit visuellen Stilen gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="22dc9-120">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is painted with visual styles.</span></span>  
  
## <a name="disabling-windows-forms-visual-styles"></a><span data-ttu-id="22dc9-121">Deaktivieren visueller Windows Forms-Stile</span><span class="sxs-lookup"><span data-stu-id="22dc9-121">Disabling Windows Forms Visual Styles</span></span>  
 <span data-ttu-id="22dc9-122">Um visuelle Stile zu deaktivieren, entfernen Sie einfach den Aufruf der <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="22dc9-122">To disable visual styles, simply remove the call to the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>  
  
#### <a name="to-disable-windows-forms-visual-styles"></a><span data-ttu-id="22dc9-123">So deaktivieren Sie visuelle Stile für Windows Forms</span><span class="sxs-lookup"><span data-stu-id="22dc9-123">To disable Windows Forms visual styles</span></span>  
  
1.  <span data-ttu-id="22dc9-124">Öffnen Sie „MainWindow.Xaml.vb“ bzw. „MainWindow.Xaml.cs“ im Code-Editor.</span><span class="sxs-lookup"><span data-stu-id="22dc9-124">Open MainWindow.xaml.vb or MainWindow.xaml.cs in the Code Editor.</span></span>  
  
2.  <span data-ttu-id="22dc9-125">Kommentieren Sie den Aufruf der <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="22dc9-125">Comment out the call to the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>  
  
3.  <span data-ttu-id="22dc9-126">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="22dc9-126">Press F5 to build and run the application.</span></span>  
  
     <span data-ttu-id="22dc9-127">Die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] -Steuerelement mit dem Standardsystemstil gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="22dc9-127">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is painted with the default system style.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22dc9-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="22dc9-128">See Also</span></span>  
 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>  
 <xref:System.Windows.Forms.VisualStyles>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="22dc9-129">Rendering von Steuerelementen mit visuellen Stilen</span><span class="sxs-lookup"><span data-stu-id="22dc9-129">Rendering Controls with Visual Styles</span></span>](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)  
 [<span data-ttu-id="22dc9-130">Exemplarische Vorgehensweise: Hosten eines Windows Forms-Steuerelements in WPF</span><span class="sxs-lookup"><span data-stu-id="22dc9-130">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)
