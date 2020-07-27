---
title: Benutzeroberflächenautomatisierungs-Unterstützung für Standardsteuerelemente
description: Hier finden Sie Informationen zur Benutzeroberflächenautomatisierungs-Unterstützung für Standard Steuerelemente in Anwendungen, die für Windows Presentation Foundation (WPF), Win32 und Windows Forms entwickelt wurden.
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 17916a6978008439e91caae00d8b6f26045f9018
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166116"
---
# <a name="ui-automation-support-for-standard-controls"></a>Benutzeroberflächenautomatisierungs-Unterstützung für Standardsteuerelemente
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 Dieses Thema enthält Informationen zur- [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Unterstützung für Standard Steuerelemente in Anwendungen, die für die [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] Frameworks, Win32 und Windows Forms entwickelt wurden.  
  
<a name="Windows_Presentation_Foundation_Controls"></a>
## <a name="windows-presentation-foundation-controls"></a>WPF-Steuerelemente (Windows Presentation Foundation)  
 Alle [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] -Steuerelemente, die Informationen enthalten oder Benutzerinteraktionen unterstützen, verfügen über eine vollständige systemeigene Unterstützung für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]. Andere Elemente (wie Bereiche) sind für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]nicht sichtbar.  
  
<a name="Win32_Controls"></a>
## <a name="win32-controls"></a>Win32-Steuerelemente  
 Die meisten Win32-Steuerelemente werden [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] über Client seitige Anbieter in UIAutomationClientsideProviders.dll bereitgestellt. Diese Assembly wird automatisch für die Verwendung mit Benutzeroberflächenautomatisierungs-Clientanwendungen registriert.  
  
 Vollständige Unterstützung wird nur für Steuerelemente ab Version 6 von *ComCtrl32.dll*bereitgestellt.  
  
 Die folgenden Steuerelemente werden unterstützt:  
  
|Klassenname|Steuerelementtyp|  
|----------------|------------------|  
|Schaltfläche|Schaltfläche|  
|Schaltfläche|RadioButton|  
|Schaltfläche|Group|  
|Schaltfläche|CheckBox|  
|Schaltfläche|Hyperlink|  
|Schaltfläche|SplitButton|  
|Schaltfläche|CheckBox|  
|ComboBoxEx32|ComboBox|  
|ComboBox|ComboBox|  
|Bearbeiten|Dokument|  
|Bearbeiten|Bearbeiten|  
|SysLink|Hyperlink|  
|statischen|Text|  
|statischen|Image|  
|SysIPAddress32|Benutzerdefiniert|  
|SysHeader32|Header/HeaderItem|  
|SysListView32|DataGrid|  
|SysListView32|List|  
|ListBox|List|  
|ListBox|ListItem|  
|#32768|Menü|  
|#32768|MenuItem|  
|msctls_progress32|ProgressBar|  
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
|tooltips_class32|QuickInfo|  
|#32774|QuickInfo|  
|ReBarWindow32|Symbolleiste|  
|SysTreeView32|Struktur|  
|SysTreeView32|TreeItem|  
  
 **Hinweis** Das RichEdit-Steuerelement wird nur für Versionen unterstützt, die mit Windows Vista ausgeliefert wurden (in RichEd20.dll Version 3,1 und höher sowie MsftEdit.dll Version 4,1 und höher).  
  
 Die folgenden Steuerelemente werden nicht unterstützt:  
  
|Klassenname|Steuerelementtyp|  
|----------------|------------------|  
|SysAnimate32|Image|  
|SysPager|Spinner|  
|SysDateTimePick32|Benutzerdefiniert|  
|SysMonthCal32|Kalender|  
|MS_WINNOTE|QuickInfo|  
|VBBubble|QuickInfo|  
|ScrollBar (wenn als eigenständiges Steuerelement verwendet)|Schieberegler|  
|SuperGrid|Benutzerdefiniert|  
  
<a name="Windows_Forms_Controls"></a>
## <a name="windows-forms-controls"></a>Windows Forms-Steuerelemente  
 Windows Forms-Steuerelemente werden [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] über Client seitige Anbieter in UIAutomationClientsideProviders.dll bereitgestellt. Diese Assembly wird automatisch für die Verwendung mit Benutzeroberflächenautomatisierungs-Clientanwendungen registriert.  
  
 In der Regel werden Windows Forms Steuerelemente, die verwaltete Wrapper für allgemeine Win32-Steuerelemente sind, von unterstützt [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] . Die folgenden Steuerelemente werden unterstützt:  
  
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
|ProgressBar|  
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
|QuickInfo|  
|TrackBar|  
|TreeView|  
|VscrollBar|  
|WebBrowser|  
  
 Die folgenden Steuerelemente sind nur für die [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Unterstützung von Microsoft Active Accessibility verfügbar. Möglicherweise sind nicht alle Funktionen verfügbar.  
  
|Name des Steuerelements|  
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
|Aufteilung|  
|RaftingContainer|  
|StatusStrip|  
  
## <a name="see-also"></a>Weitere Informationen

- [Steuerelementtypen der Benutzeroberflächenautomatisierung](ui-automation-control-types.md)
