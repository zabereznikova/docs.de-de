---
title: "Windows Forms-Steuerelemente und &#228;quivalente WPF-Steuerelemente | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Interoperabilität [WPF], Windows Forms"
  - "Windows Forms [WPF], Interoperabilität mit"
  - "Windows Forms, WPF-Interoperation"
ms.assetid: 8a157e6b-8054-46db-a5cf-a78966acc7a1
caps.latest.revision: 27
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 27
---
# Windows Forms-Steuerelemente und &#228;quivalente WPF-Steuerelemente
Viele [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelemente verfügen über äquivalente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Steuerelemente, aber einige [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelemente weisen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] keine Entsprechungen auf.  In diesem Thema werden die Steuerelementtypen verglichen, die von den beiden Technologien bereitgestellt werden.  
  
 Sie haben immer die Möglichkeit, die Interoperation zum Hosten von [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelementen zu verwenden, die in Ihren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-basierten Anwendungen nicht über Entsprechungen verfügen.  
  
 Die folgende Tabelle zeigt, welche [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelemente und \-Komponenten über eine äquivalente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Steuerelementfunktionalität verfügen.  
  
|Windows Forms\-Steuerelement|Entsprechendes WPF\-Steuerelement|Hinweise|  
|----------------------------------|---------------------------------------|--------------|  
|<xref:System.Windows.Forms.BindingNavigator>|Kein äquivalentes Steuerelement.||  
|<xref:System.Windows.Forms.BindingSource>|<xref:System.Windows.Data.CollectionViewSource>||  
|<xref:System.Windows.Forms.Button>|<xref:System.Windows.Controls.Button>||  
|<xref:System.Windows.Forms.CheckBox>|<xref:System.Windows.Controls.CheckBox>||  
|<xref:System.Windows.Forms.CheckedListBox>|<xref:System.Windows.Controls.ListBox> mit Komposition.||  
|<xref:System.Windows.Forms.ColorDialog>|Kein äquivalentes Steuerelement.||  
|<xref:System.Windows.Forms.ComboBox>|<xref:System.Windows.Controls.ComboBox>|<xref:System.Windows.Controls.ComboBox> unterstützt die automatische Vervollständigung nicht.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<xref:System.Windows.Controls.ContextMenu>||  
|<xref:System.Windows.Forms.DataGridView>|<xref:System.Windows.Controls.DataGrid>||  
|<xref:System.Windows.Forms.DateTimePicker>|<xref:System.Windows.Controls.DatePicker>||  
|<xref:System.Windows.Forms.DomainUpDown>|<xref:System.Windows.Controls.TextBox> und zwei <xref:System.Windows.Controls.Primitives.RepeatButton>\-Steuerelemente.||  
|<xref:System.Windows.Forms.ErrorProvider>|Kein äquivalentes Steuerelement.||  
|<xref:System.Windows.Forms.FlowLayoutPanel>|<xref:System.Windows.Controls.WrapPanel> oder <xref:System.Windows.Controls.StackPanel>||  
|<xref:System.Windows.Forms.FolderBrowserDialog>|Kein äquivalentes Steuerelement.||  
|<xref:System.Windows.Forms.FontDialog>|Kein äquivalentes Steuerelement.||  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Window>|<xref:System.Windows.Window> unterstützt keine untergeordneten Fenster.|  
|<xref:System.Windows.Forms.GroupBox>|<xref:System.Windows.Controls.GroupBox>||  
|<xref:System.Windows.Forms.HelpProvider>|Kein äquivalentes Steuerelement.|Keine F1\-Hilfe. "  Direkthilfe" wird durch QuickInfos ersetzt.|  
|<xref:System.Windows.Forms.HScrollBar>|<xref:System.Windows.Controls.Primitives.ScrollBar>|Die Bildlauffunktion ist in Containersteuerelemente integriert.|  
|<xref:System.Windows.Forms.ImageList>|Kein äquivalentes Steuerelement.||  
|<xref:System.Windows.Forms.Label>|<xref:System.Windows.Controls.Label>||  
|<xref:System.Windows.Forms.LinkLabel>|Kein äquivalentes Steuerelement.|Sie können die <xref:System.Windows.Documents.Hyperlink>\-Klasse verwenden, um Links im fortlaufenden Inhalt zu hosten.|  
|<xref:System.Windows.Forms.ListBox>|<xref:System.Windows.Controls.ListBox>||  
|<xref:System.Windows.Forms.ListView>|<xref:System.Windows.Controls.ListView>|Das <xref:System.Windows.Controls.ListView>\-Steuerelement stellt eine schreibgeschützte Detailansicht bereit.|  
|<xref:System.Windows.Forms.MaskedTextBox>|Kein äquivalentes Steuerelement.||  
|<xref:System.Windows.Forms.MenuStrip>|<xref:System.Windows.Controls.Menu>|Die Formatierung des <xref:System.Windows.Controls.Menu>\-Steuerelements kann das Verhalten und Aussehen der <xref:System.Windows.Forms.ToolStripProfessionalRenderer?displayProperty=fullName>\-Klasse annähern.|  
|<xref:System.Windows.Forms.MonthCalendar>|<xref:System.Windows.Controls.Calendar>||  
|<xref:System.Windows.Forms.NotifyIcon>|Kein äquivalentes Steuerelement.||  
|<xref:System.Windows.Forms.NumericUpDown>|<xref:System.Windows.Controls.TextBox> und zwei <xref:System.Windows.Controls.Primitives.RepeatButton>\-Steuerelemente.||  
|<xref:System.Windows.Forms.OpenFileDialog>|<xref:Microsoft.Win32.OpenFileDialog>|Die <xref:Microsoft.Win32.OpenFileDialog>\-Klasse ist ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Wrapper um das [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Steuerelement.|  
|<xref:System.Windows.Forms.PageSetupDialog>|Kein äquivalentes Steuerelement.||  
|<xref:System.Windows.Forms.Panel>|<xref:System.Windows.Controls.Canvas>||  
|<xref:System.Windows.Forms.PictureBox>|<xref:System.Windows.Controls.Image>||  
|<xref:System.Windows.Forms.PrintDialog>|<xref:System.Windows.Controls.PrintDialog>||  
|<xref:System.Drawing.Printing.PrintDocument>|Kein äquivalentes Steuerelement.||  
|<xref:System.Windows.Forms.PrintPreviewControl>|<xref:System.Windows.Controls.DocumentViewer>||  
|<xref:System.Windows.Forms.PrintPreviewDialog>|Kein äquivalentes Steuerelement.||  
|<xref:System.Windows.Forms.ProgressBar>|<xref:System.Windows.Controls.ProgressBar>||  
|<xref:System.Windows.Forms.PropertyGrid>|Kein äquivalentes Steuerelement.||  
|<xref:System.Windows.Forms.RadioButton>|<xref:System.Windows.Controls.RadioButton>||  
|<xref:System.Windows.Forms.RichTextBox>|<xref:System.Windows.Controls.RichTextBox>||  
|<xref:System.Windows.Forms.SaveFileDialog>|<xref:Microsoft.Win32.SaveFileDialog>|Die <xref:Microsoft.Win32.SaveFileDialog>\-Klasse ist ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Wrapper um das [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Steuerelement.|  
|<xref:System.Windows.Forms.ScrollableControl>|<xref:System.Windows.Controls.ScrollViewer>||  
|<xref:System.Media.SoundPlayer>|<xref:System.Windows.Media.MediaPlayer>||  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Controls.GridSplitter>||  
|<xref:System.Windows.Forms.StatusStrip>|<xref:System.Windows.Controls.Primitives.StatusBar>||  
|<xref:System.Windows.Forms.TabControl>|<xref:System.Windows.Controls.TabControl>||  
|<xref:System.Windows.Forms.TableLayoutPanel>|<xref:System.Windows.Controls.Grid>||  
|<xref:System.Windows.Forms.TextBox>|<xref:System.Windows.Controls.TextBox>||  
|<xref:System.Windows.Forms.Timer>|<xref:System.Windows.Threading.DispatcherTimer>||  
|<xref:System.Windows.Forms.ToolStrip>|<xref:System.Windows.Controls.ToolBar>||  
|<xref:System.Windows.Forms.ToolStripContainer>|<xref:System.Windows.Controls.ToolBar> mit Komposition.||  
|<xref:System.Windows.Forms.ToolStripDropDown>|<xref:System.Windows.Controls.ToolBar> mit Komposition.||  
|<xref:System.Windows.Forms.ToolStripDropDownMenu>|<xref:System.Windows.Controls.ToolBar> mit Komposition.||  
|<xref:System.Windows.Forms.ToolStripPanel>|<xref:System.Windows.Controls.ToolBar> mit Komposition.||  
|<xref:System.Windows.Forms.ToolTip>|<xref:System.Windows.Controls.ToolTip>||  
|<xref:System.Windows.Forms.TrackBar>|<xref:System.Windows.Controls.Slider>||  
|<xref:System.Windows.Forms.TreeView>|<xref:System.Windows.Controls.TreeView>||  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Controls.UserControl>||  
|<xref:System.Windows.Forms.VScrollBar>|<xref:System.Windows.Controls.Primitives.ScrollBar>|Die Bildlauffunktion ist in Containersteuerelemente integriert.|  
|<xref:System.Windows.Forms.WebBrowser>|<xref:System.Windows.Controls.Frame>, <xref:System.Windows.Controls.WebBrowser?displayProperty=fullName>|Das <xref:System.Windows.Controls.Frame>\-Steuerelement kann HTML\-Seiten hosten.<br /><br /> Ab [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)] kann das <xref:System.Windows.Controls.WebBrowser?displayProperty=fullName>\-Steuerelement HTML\-Seiten hosten und bietet darüber hinaus Unterstützung für das <xref:System.Windows.Controls.Frame>\-Steuerelement.|  
  
## Siehe auch  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Der WPF\-Designer für Windows Forms\-Entwickler](http://msdn.microsoft.com/de-de/47ad0909-e89b-4996-b4ac-874d929f94ca)   
 [Exemplarische Vorgehensweise: Hosten eines Windows Forms\-Steuerelements in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)   
 [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF\-Steuerelements in Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)   
 [Migration und Interoperabilität](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)