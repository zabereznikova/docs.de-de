---
title: Benutzeroberflächenautomatisierungs-Unterstützung für Standardsteuerelemente
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: c59352f908c5f4a1fd2ca6dd631d26bb5d69f09a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441227"
---
# <a name="ui-automation-support-for-standard-controls"></a>Benutzeroberflächenautomatisierungs-Unterstützung für Standardsteuerelemente
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 Dieses Thema enthält Informationen zur [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] -Unterstützung für Standardsteuerelemente in Anwendungen für die Frameworks [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]und [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] .  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a>WPF-Steuerelemente (Windows Presentation Foundation)  
 Alle [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] -Steuerelemente, die Informationen enthalten oder Benutzerinteraktionen unterstützen, verfügen über eine vollständige systemeigene Unterstützung für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]. Andere Elemente (wie Bereiche) sind für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]nicht sichtbar.  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a>Win32-Steuerelemente  
 Die meisten [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] -Steuerelemente werden über clientseitige Anbieter in „UIAutomationClientsideProviders.dll“ für [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] verfügbar gemacht. Diese Assembly wird automatisch für die Verwendung mit Benutzeroberflächenautomatisierungs-Clientanwendungen registriert.  
  
 Vollständige Unterstützung gibt es nur für Steuerelemente von Version 6 von „ComCtrl32.dll“ (ab [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] verfügbar).  
  
 Die folgenden Steuerelemente werden unterstützt:  
  
|Klassenname|Steuerelementtyp|  
|----------------|------------------|  
|Schaltfläche|Schaltfläche|  
|Schaltfläche|RadioButton|  
|Schaltfläche|Gruppe|  
|Schaltfläche|CheckBox|  
|Schaltfläche|Link|  
|Schaltfläche|SplitButton|  
|Schaltfläche|CheckBox|  
|ComboBoxEx32|ComboBox|  
|ComboBox|ComboBox|  
|Bearbeiten|Dokument|  
|Bearbeiten|Bearbeiten|  
|SysLink|Link|  
|Static|Text|  
|Static|Bild|  
|SysIPAddress32|Benutzerdefiniert|  
|SysHeader32|Header/HeaderItem|  
|SysListView32|DataGrid|  
|SysListView32|Liste|  
|ListBox|Liste|  
|ListBox|ListItem|  
|#32768|Menü|  
|#32768|MenuItem|  
|msctls_progress32|Statusanzeige|  
|RichEdit|Dokument. Siehe Hinweis.|  
|RichEdit20A|Dokument|  
|RichEdit20W|Dokument|  
|RichEdit50W|Dokument|  
|ScrollBar|Schieberegler|  
|msctls_trackbar32|Schieberegler|  
|msctls_updown32|Spinner|  
|msctls_statusbar32|StatusBar|  
|SysTabControl32|Registerkarte|  
|SysTabControl32|TabItem|  
|ToolbarWindow32|ToolBar|  
|ToolbarWindow32|MenuItem|  
|ToolbarWindow32|Schaltfläche|  
|ToolbarWindow32|CheckBox|  
|ToolbarWindow32|RadioButton|  
|ToolbarWindow32|Trennzeichen|  
|tooltips_class32|ToolTip|  
|#32774|ToolTip|  
|ReBarWindow32|Symbolleiste|  
|SysTreeView32|Struktur|  
|SysTreeView32|TreeItem|  
  
 **Hinweis** Das RichEdit-Steuerelement wird nur für Versionen unterstützt, die mit Windows Vista ausgeliefert werden (in Riched20. dll, Version 3,1 und höher, und MSF Tedit. dll, Version 4,1 und höher).  
  
 Die folgenden Steuerelemente werden nicht unterstützt:  
  
|Klassenname|Steuerelementtyp|  
|----------------|------------------|  
|SysAnimate32|Bild|  
|SysPager|Spinner|  
|SysDateTimePick32|Benutzerdefiniert|  
|SysMonthCal32|Kalender|  
|MS_WINNOTE|Tooltip|  
|VBBubble|Tooltip|  
|ScrollBar (wenn als eigenständiges Steuerelement verwendet)|Schieberegler|  
|SuperGrid|Benutzerdefiniert|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a>Steuerelemente für Windows Forms  
 Windows Forms Steuerelemente werden über Client seitige Anbieter in "UIAutomationClientsideProviders. dll" [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] bereitgestellt. Diese Assembly wird automatisch für die Verwendung mit Benutzeroberflächenautomatisierungs-Clientanwendungen registriert.  
  
 In der Regel werden Windows Forms Steuerelemente, die verwaltete Wrapper für [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] allgemeine Steuerelemente sind, von [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]unterstützt. Die folgenden Steuerelemente werden unterstützt:  
  
|Klassenname|  
|----------------|  
|Schaltfläche|  
|CheckBox|  
|CheckedListBox|  
|ColorDialog|  
|ComboBox|  
|FolderBrowser|  
|FontDialog|  
|GroupBox|  
|HscrollBar|  
|ImageList|  
|Label|  
|ListBox|  
|ListView|  
|MainMenu/ContextMenu|  
|MonthCalendar|  
|NotifyIcon|  
|OpenFileDialog|  
|PageSetupDialog|  
|PrintDialog|  
|Statusanzeige|  
|RadioButton|  
|RichTextBox|  
|SaveFileDialog|  
|ScrollableControl|  
|SoundPlayer|  
|StatusBar|  
|TabControl/TabPage|  
|TextBox|  
|Zeitgeber|  
|Symbolleiste|  
|ToolTip|  
|TrackBar|  
|TreeView|  
|VscrollBar|  
|Webbrowser|  
  
 Die folgenden Steuerelemente sind nur für die Unterstützung von Microsoft Active Accessibility verfügbar [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]. Möglicherweise sind nicht alle Funktionen verfügbar.  
  
|Steuerelementname|  
|------------------|  
|BindingSource|  
|DataGrid|  
|DataGridView|  
|DataNavigator|  
|DomainUpDown|  
|ErrorProvider|  
|FlowLayoutPanel|  
|Formular|  
|LinkLabel|  
|HelpProvider|  
|MaskedTextBox|  
|MenuStrip/ContextMenuStrip|  
|NumericUpDown|  
|Bereich|  
|PictureBox|  
|PrintDocument|  
|PrintPreview-Control|  
|PrintPreview-Dialog|  
|PropertyGrid|  
|UserControl|  
|ToolStrip|  
|TableLayoutPanel|  
|SplitContainer/SplitterPanel|  
|Teilungsfunktion (Splitter)|  
|RaftingContainer|  
|StatusStrip|  
  
## <a name="see-also"></a>Siehe auch

- [UI Automation Control Types](ui-automation-control-types.md)
