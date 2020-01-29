---
title: Windows Forms-Steuerelemente und entsprechende WPF-Steuerelemente
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
ms.assetid: 8a157e6b-8054-46db-a5cf-a78966acc7a1
ms.openlocfilehash: 7f531b60d8b31181688f3d0a6753b234ffc6c7dd
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735210"
---
# <a name="windows-forms-controls-and-equivalent-wpf-controls"></a><span data-ttu-id="0c31c-102">Windows Forms-Steuerelemente und entsprechende WPF-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="0c31c-102">Windows Forms Controls and Equivalent WPF Controls</span></span>
<span data-ttu-id="0c31c-103">Viele [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente verfügen über äquivalente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelemente, einige [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente haben jedoch keine Entsprechungen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c31c-103">Many [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have equivalent [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controls, but some [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have no equivalents in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="0c31c-104">In diesem Thema werden die von den beiden Technologien bereitgestellten Steuerelement Typen verglichen.</span><span class="sxs-lookup"><span data-stu-id="0c31c-104">This topic compares control types provided by the two technologies.</span></span>  
  
 <span data-ttu-id="0c31c-105">Sie können jederzeit Interoperation verwenden, um [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente zu hosten, die keine Entsprechungen in ihren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]basierten Anwendungen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="0c31c-105">You can always use interoperation to host [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls that do not have equivalents in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>  
  
 <span data-ttu-id="0c31c-106">In der folgenden Tabelle wird gezeigt, welche [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Steuerelemente und-Komponenten über äquivalente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerungsfunktionen verfügen</span><span class="sxs-lookup"><span data-stu-id="0c31c-106">The following table shows which [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls and components have equivalent [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control functionality.</span></span>  
  
|<span data-ttu-id="0c31c-107">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="0c31c-107">Windows Forms control</span></span>|<span data-ttu-id="0c31c-108">Entsprechendes WPF-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="0c31c-108">WPF equivalent control</span></span>|<span data-ttu-id="0c31c-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0c31c-109">Remarks</span></span>|  
|---------------------------|----------------------------|-------------|  
|<xref:System.Windows.Forms.BindingNavigator>|<span data-ttu-id="0c31c-110">Kein entsprechendes Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0c31c-110">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.BindingSource>|<xref:System.Windows.Data.CollectionViewSource>||  
|<xref:System.Windows.Forms.Button>|<xref:System.Windows.Controls.Button>||  
|<xref:System.Windows.Forms.CheckBox>|<xref:System.Windows.Controls.CheckBox>||  
|<xref:System.Windows.Forms.CheckedListBox>|<span data-ttu-id="0c31c-111"><xref:System.Windows.Controls.ListBox> mit Komposition.</span><span class="sxs-lookup"><span data-stu-id="0c31c-111"><xref:System.Windows.Controls.ListBox> with composition.</span></span>||  
|<xref:System.Windows.Forms.ColorDialog>|<span data-ttu-id="0c31c-112">Kein entsprechendes Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0c31c-112">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.ComboBox>|<xref:System.Windows.Controls.ComboBox>|<span data-ttu-id="0c31c-113">die automatische Vervollständigung wird <xref:System.Windows.Controls.ComboBox> nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0c31c-113"><xref:System.Windows.Controls.ComboBox> does not support auto-complete.</span></span>|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<xref:System.Windows.Controls.ContextMenu>||  
|<xref:System.Windows.Forms.DataGridView>|<xref:System.Windows.Controls.DataGrid>||  
|<xref:System.Windows.Forms.DateTimePicker>|<xref:System.Windows.Controls.DatePicker>||  
|<xref:System.Windows.Forms.DomainUpDown>|<span data-ttu-id="0c31c-114"><xref:System.Windows.Controls.TextBox> und zwei <xref:System.Windows.Controls.Primitives.RepeatButton>-Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="0c31c-114"><xref:System.Windows.Controls.TextBox> and two <xref:System.Windows.Controls.Primitives.RepeatButton> controls.</span></span>||  
|<xref:System.Windows.Forms.ErrorProvider>|<span data-ttu-id="0c31c-115">Kein entsprechendes Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0c31c-115">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.FlowLayoutPanel>|<span data-ttu-id="0c31c-116"><xref:System.Windows.Controls.WrapPanel> oder <xref:System.Windows.Controls.StackPanel></span><span class="sxs-lookup"><span data-stu-id="0c31c-116"><xref:System.Windows.Controls.WrapPanel> or <xref:System.Windows.Controls.StackPanel></span></span>||  
|<xref:System.Windows.Forms.FolderBrowserDialog>|<span data-ttu-id="0c31c-117">Kein entsprechendes Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0c31c-117">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.FontDialog>|<span data-ttu-id="0c31c-118">Kein entsprechendes Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0c31c-118">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Window>|<span data-ttu-id="0c31c-119"><xref:System.Windows.Window> unterstützt keine untergeordneten Fenster.</span><span class="sxs-lookup"><span data-stu-id="0c31c-119"><xref:System.Windows.Window> does not support child windows.</span></span>|  
|<xref:System.Windows.Forms.GroupBox>|<xref:System.Windows.Controls.GroupBox>||  
|<xref:System.Windows.Forms.HelpProvider>|<span data-ttu-id="0c31c-120">Kein entsprechendes Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0c31c-120">No equivalent control.</span></span>|<span data-ttu-id="0c31c-121">Keine F1-Hilfe.</span><span class="sxs-lookup"><span data-stu-id="0c31c-121">No F1 Help.</span></span> <span data-ttu-id="0c31c-122">"Was ist die"-Hilfe wird durch Quick Infos ersetzt.</span><span class="sxs-lookup"><span data-stu-id="0c31c-122">"What's This" Help is replaced by ToolTips.</span></span>|  
|<xref:System.Windows.Forms.HScrollBar>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="0c31c-123">Der Bildlauf ist in Container Steuerelemente integriert.</span><span class="sxs-lookup"><span data-stu-id="0c31c-123">Scrolling is built into container controls.</span></span>|  
|<xref:System.Windows.Forms.ImageList>|<span data-ttu-id="0c31c-124">Kein entsprechendes Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0c31c-124">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.Label>|<xref:System.Windows.Controls.Label>||  
|<xref:System.Windows.Forms.LinkLabel>|<span data-ttu-id="0c31c-125">Kein entsprechendes Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0c31c-125">No equivalent control.</span></span>|<span data-ttu-id="0c31c-126">Sie können die <xref:System.Windows.Documents.Hyperlink>-Klasse verwenden, um Hyperlinks innerhalb des fortlaufenden Inhalts zu hosten.</span><span class="sxs-lookup"><span data-stu-id="0c31c-126">You can use the <xref:System.Windows.Documents.Hyperlink> class to host hyperlinks within flow content.</span></span>|  
|<xref:System.Windows.Forms.ListBox>|<xref:System.Windows.Controls.ListBox>||  
|<xref:System.Windows.Forms.ListView>|<xref:System.Windows.Controls.ListView>|<span data-ttu-id="0c31c-127">Das <xref:System.Windows.Controls.ListView>-Steuerelement stellt eine schreibgeschützte Detailansicht bereit.</span><span class="sxs-lookup"><span data-stu-id="0c31c-127">The <xref:System.Windows.Controls.ListView> control provides a read-only details view.</span></span>|  
|<xref:System.Windows.Forms.MaskedTextBox>|<span data-ttu-id="0c31c-128">Kein entsprechendes Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0c31c-128">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.MenuStrip>|<xref:System.Windows.Controls.Menu>|<span data-ttu-id="0c31c-129">das Formatieren von <xref:System.Windows.Controls.Menu> Steuerelementen kann das Verhalten und die Darstellung der <xref:System.Windows.Forms.ToolStripProfessionalRenderer?displayProperty=nameWithType> Klasse annähern.</span><span class="sxs-lookup"><span data-stu-id="0c31c-129"><xref:System.Windows.Controls.Menu> control styling can approximate the behavior and appearance of the <xref:System.Windows.Forms.ToolStripProfessionalRenderer?displayProperty=nameWithType> class.</span></span>|  
|<xref:System.Windows.Forms.MonthCalendar>|<xref:System.Windows.Controls.Calendar>||  
|<xref:System.Windows.Forms.NotifyIcon>|<span data-ttu-id="0c31c-130">Kein entsprechendes Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0c31c-130">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.NumericUpDown>|<span data-ttu-id="0c31c-131"><xref:System.Windows.Controls.TextBox> und zwei <xref:System.Windows.Controls.Primitives.RepeatButton>-Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="0c31c-131"><xref:System.Windows.Controls.TextBox> and two <xref:System.Windows.Controls.Primitives.RepeatButton> controls.</span></span>||  
|<xref:System.Windows.Forms.OpenFileDialog>|<xref:Microsoft.Win32.OpenFileDialog>|<span data-ttu-id="0c31c-132">Die <xref:Microsoft.Win32.OpenFileDialog>-Klasse ist ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Wrapper um das Win32-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0c31c-132">The <xref:Microsoft.Win32.OpenFileDialog> class is a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wrapper around the Win32 control.</span></span>|  
|<xref:System.Windows.Forms.PageSetupDialog>|<span data-ttu-id="0c31c-133">Kein entsprechendes Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0c31c-133">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.Panel>|<xref:System.Windows.Controls.Canvas>||  
|<xref:System.Windows.Forms.PictureBox>|<xref:System.Windows.Controls.Image>||  
|<xref:System.Windows.Forms.PrintDialog>|<xref:System.Windows.Controls.PrintDialog>||  
|<xref:System.Drawing.Printing.PrintDocument>|<span data-ttu-id="0c31c-134">Kein entsprechendes Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0c31c-134">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.PrintPreviewControl>|<xref:System.Windows.Controls.DocumentViewer>||  
|<xref:System.Windows.Forms.PrintPreviewDialog>|<span data-ttu-id="0c31c-135">Kein entsprechendes Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0c31c-135">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.ProgressBar>|<xref:System.Windows.Controls.ProgressBar>||  
|<xref:System.Windows.Forms.PropertyGrid>|<span data-ttu-id="0c31c-136">Kein entsprechendes Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0c31c-136">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.RadioButton>|<xref:System.Windows.Controls.RadioButton>||  
|<xref:System.Windows.Forms.RichTextBox>|<xref:System.Windows.Controls.RichTextBox>||  
|<xref:System.Windows.Forms.SaveFileDialog>|<xref:Microsoft.Win32.SaveFileDialog>|<span data-ttu-id="0c31c-137">Die <xref:Microsoft.Win32.SaveFileDialog>-Klasse ist ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Wrapper um das Win32-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0c31c-137">The <xref:Microsoft.Win32.SaveFileDialog> class is a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wrapper around the Win32 control.</span></span>|  
|<xref:System.Windows.Forms.ScrollableControl>|<xref:System.Windows.Controls.ScrollViewer>||  
|<xref:System.Media.SoundPlayer>|<xref:System.Windows.Media.MediaPlayer>||  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Controls.GridSplitter>||  
|<xref:System.Windows.Forms.StatusStrip>|<xref:System.Windows.Controls.Primitives.StatusBar>||  
|<xref:System.Windows.Forms.TabControl>|<xref:System.Windows.Controls.TabControl>||  
|<xref:System.Windows.Forms.TableLayoutPanel>|<xref:System.Windows.Controls.Grid>||  
|<xref:System.Windows.Forms.TextBox>|<xref:System.Windows.Controls.TextBox>||  
|<xref:System.Windows.Forms.Timer>|<xref:System.Windows.Threading.DispatcherTimer>||  
|<xref:System.Windows.Forms.ToolStrip>|<xref:System.Windows.Controls.ToolBar>||  
|<xref:System.Windows.Forms.ToolStripContainer>|<span data-ttu-id="0c31c-138"><xref:System.Windows.Controls.ToolBar> mit Komposition.</span><span class="sxs-lookup"><span data-stu-id="0c31c-138"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolStripDropDown>|<span data-ttu-id="0c31c-139"><xref:System.Windows.Controls.ToolBar> mit Komposition.</span><span class="sxs-lookup"><span data-stu-id="0c31c-139"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolStripDropDownMenu>|<span data-ttu-id="0c31c-140"><xref:System.Windows.Controls.ToolBar> mit Komposition.</span><span class="sxs-lookup"><span data-stu-id="0c31c-140"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolStripPanel>|<span data-ttu-id="0c31c-141"><xref:System.Windows.Controls.ToolBar> mit Komposition.</span><span class="sxs-lookup"><span data-stu-id="0c31c-141"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolTip>|<xref:System.Windows.Controls.ToolTip>||  
|<xref:System.Windows.Forms.TrackBar>|<xref:System.Windows.Controls.Slider>||  
|<xref:System.Windows.Forms.TreeView>|<xref:System.Windows.Controls.TreeView>||  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Controls.UserControl>||  
|<xref:System.Windows.Forms.VScrollBar>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="0c31c-142">Der Bildlauf ist in Container Steuerelemente integriert.</span><span class="sxs-lookup"><span data-stu-id="0c31c-142">Scrolling is built into container controls.</span></span>|  
|<xref:System.Windows.Forms.WebBrowser>|<span data-ttu-id="0c31c-143"><xref:System.Windows.Controls.Frame>, <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="0c31c-143"><xref:System.Windows.Controls.Frame>, <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType></span></span>|<span data-ttu-id="0c31c-144">Das <xref:System.Windows.Controls.Frame> Steuerelement kann HTML-Seiten hosten.</span><span class="sxs-lookup"><span data-stu-id="0c31c-144">The <xref:System.Windows.Controls.Frame> control can host HTML pages.</span></span><br /><br /> <span data-ttu-id="0c31c-145">Beginnend mit dem .NET Framework 3,5 SP1 kann das <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType>-Steuerelement HTML-Seiten hosten und auch das <xref:System.Windows.Controls.Frame>-Steuerelement unterstützen.</span><span class="sxs-lookup"><span data-stu-id="0c31c-145">Starting in the .NET Framework 3.5 SP1, the <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType> control can host HTML pages and also backs the <xref:System.Windows.Controls.Frame> control.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0c31c-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c31c-146">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- <span data-ttu-id="0c31c-147">[WPF-Designer für Windows Forms-Entwickler](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cc165605(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="0c31c-147">[WPF Designer for Windows Forms Developers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cc165605(v=vs.100))</span></span>
- [<span data-ttu-id="0c31c-148">Exemplarische Vorgehensweise: Hosten eines Windows Forms-Steuerelements in WPF</span><span class="sxs-lookup"><span data-stu-id="0c31c-148">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [<span data-ttu-id="0c31c-149">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0c31c-149">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="0c31c-150">Migration und Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="0c31c-150">Migration and Interoperability</span></span>](migration-and-interoperability.md)
