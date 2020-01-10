---
title: Benutzeroberflächenautomatisierungs-Unterstützung für Standardsteuerelemente
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: ed5e4f6ab23fe9ae77c94616a668da8accb46d4b
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "75741698"
---
# <a name="ui-automation-support-for-standard-controls"></a>Benutzeroberflächenautomatisierungs-Unterstützung für Standardsteuerelemente
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 Dieses Thema enthält Informationen über [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Unterstützung für Standard Steuerelemente in Anwendungen, die für die Frameworks [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], Win32 und [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] entwickelt wurden.  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a>WPF-Steuerelemente (Windows Presentation Foundation)  
 Alle [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] -Steuerelemente, die Informationen enthalten oder Benutzerinteraktionen unterstützen, verfügen über eine vollständige systemeigene Unterstützung für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]. Andere Elemente (wie Bereiche) sind für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]nicht sichtbar.  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a>Win32-Steuerelemente  
 Die meisten Win32-Steuerelemente werden über Client seitige Anbieter in "UIAutomationClientsideProviders. dll" [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]. Diese Assembly wird automatisch für die Verwendung mit Benutzeroberflächenautomatisierungs-Clientanwendungen registriert.  
  
 Vollständige Unterstützung wird nur für Steuerelemente der Version 6 von *"ComCtrl32. dll*bereitgestellt.  
  
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
|Edit|Dokumentieren|  
|Edit|Edit|  
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
|RichEdit20A|Dokumentieren|  
|RichEdit20W|Dokumentieren|  
|RichEdit50W|Dokumentieren|  
|ScrollBar|Slider|  
|msctls_trackbar32|Slider|  
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
|tooltips_class32|QuickInfo|  
|#32774|QuickInfo|  
|ReBarWindow32|ToolBar|  
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
|MS_WINNOTE|QuickInfo|  
|VBBubble|QuickInfo|  
|ScrollBar (wenn als eigenständiges Steuerelement verwendet)|Slider|  
|SuperGrid|Benutzerdefiniert|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a>Windows Forms-Steuerelemente  
 Windows Forms Steuerelemente werden über Client seitige Anbieter in "UIAutomationClientsideProviders. dll" [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] bereitgestellt. Diese Assembly wird automatisch für die Verwendung mit Benutzeroberflächenautomatisierungs-Clientanwendungen registriert.  
  
 In der Regel werden Windows Forms Steuerelemente, die verwaltete Wrapper für allgemeine Win32-Steuerelemente sind, von [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]unterstützt. Die folgenden Steuerelemente werden unterstützt:  
  
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
|Bezeichnung|  
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
|Timer|  
|ToolBar|  
|QuickInfo|  
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
|Splitter|  
|RaftingContainer|  
|StatusStrip|  
  
## <a name="see-also"></a>Siehe auch

- [UI Automation Control Types](ui-automation-control-types.md)
