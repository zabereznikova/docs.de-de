---
title: Windows Forms-Steuerelemente nach Funktion
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], by function
- Windows Forms, controls by function
- Windows Forms controls, list of
ms.assetid: 5e65a6c3-5d6f-480d-beb8-b28f865f07e3
ms.openlocfilehash: 058a18878b89991bd8124bd69e18476d4f1479d6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="windows-forms-controls-by-function"></a>Windows Forms-Steuerelemente nach Funktion
Windows Forms bietet Steuerelemente und Komponenten, die eine Reihe von Funktionen ausführen. Die folgende Tabelle enthält die Windows Forms-Steuerelemente und Komponenten gemäß allgemeine Funktion. Darüber hinaus mehrere Steuerelemente vorhanden sind, die die gleiche Funktion dienen, ist das empfohlene Steuerelement mit einem Hinweis auf das Steuerelement aufgelistet, ersetzte. In einer separaten nachfolgenden Tabelle sind die Abgelöste Steuerelemente mit ihren empfohlene Ersatz aufgeführt.  
  
> [!NOTE]
>  Die folgenden Tabellen sind nicht enthalten, jedes Steuerelement bzw. Komponente aus, die Sie in Windows Forms verwenden können; eine umfangreichere Liste finden Sie unter [Steuerelemente für Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
  
## <a name="recommended-controls-and-components-by-function"></a>Empfohlene Steuerelemente und Komponenten von-Funktion  
  
|Funktion|Steuerelement|Beschreibung|  
|--------------|-------------|-----------------|  
|Darstellung der Daten|<xref:System.Windows.Forms.DataGridView>-Steuerelement|Die <xref:System.Windows.Forms.DataGridView> Steuerelement stellt eine anpassbare Tabelle zum Anzeigen von Daten. Die <xref:System.Windows.Forms.DataGridView> Klasse ermöglicht die Anpassung von Zellen, Zeilen, Spalten und Rahmen. **Hinweis:** der <xref:System.Windows.Forms.DataGridView> Steuerelement bietet zahlreiche grundlegende und erweiterte Funktionen, die fehlen in der <xref:System.Windows.Forms.DataGrid> Steuerelement. Weitere Informationen finden Sie unter [Unterschiede zwischen dem Windows Forms DataGridView-Steuerelement und dem DataGrid-Steuerelement](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)|  
|Datenbindung und navigation|<xref:System.Windows.Forms.BindingSource> Komponente|Vereinfacht das Binden von Steuerelementen in einem Formular an Daten indem währungsverwaltung, änderungsbenachrichtigung und andere Dienste.|  
||<xref:System.Windows.Forms.BindingNavigator>-Steuerelement|Enthält eine Symbolleiste-Schnittstelle zum Navigieren und Bearbeiten von Daten in einem Formular an.|  
|Bearbeiten von Text|<xref:System.Windows.Forms.TextBox>-Steuerelement|Zeigt Text eingegeben haben, zur Entwurfszeit, die zur Laufzeit von den Benutzern bearbeitet oder programmgesteuert geändert werden kann.|  
||<xref:System.Windows.Forms.RichTextBox>-Steuerelement|Ermöglicht mit Formatierung in nur-Text oder Rich-Text-Format (RTF) anzuzeigende Text.|  
||<xref:System.Windows.Forms.MaskedTextBox>-Steuerelement|Schränkt das Format der Benutzereingabe|  
|Die angezeigten Informationen (schreibgeschützt)|<xref:System.Windows.Forms.Label>-Steuerelement|Zeigt Text an, den Benutzer nicht direkt bearbeiten können.|  
||<xref:System.Windows.Forms.LinkLabel>-Steuerelement|Zeigt Text als Link Webstil, und löst ein Ereignis aus, klickt der Benutzer den Text. In der Regel ist der Text, einen Link zu einem anderen Fenster oder eine Website.|  
||<xref:System.Windows.Forms.StatusStrip>-Steuerelement|Zeigt Informationen zum aktuellen Zustand der Anwendung in eine begrenzte Fläche in der Regel am unteren Rand eines übergeordneten Formulars verwenden.|  
||<xref:System.Windows.Forms.ProgressBar>-Steuerelement|Zeigt den aktuellen Status eines Vorgangs für den Benutzer an.|  
|Anzeigen der Webseite|<xref:System.Windows.Forms.WebBrowser>-Steuerelement|Ermöglicht dem Benutzer, zu Webseiten innerhalb eines Formulars zu navigieren.|  
|Auswahl aus einer Liste|<xref:System.Windows.Forms.CheckedListBox>-Steuerelement|Zeigt eine Übersicht der Elemente, jeweils durch ein Kontrollkästchen begleitet.|  
||<xref:System.Windows.Forms.ComboBox>-Steuerelement|Zeigt eine Dropdown-Liste von Elementen.|  
||<xref:System.Windows.Forms.DomainUpDown>-Steuerelement|Zeigt eine Liste von Textelemente, die Benutzer mit den nach oben oder unten Schaltflächen einen Bildlauf durchführen können.|  
||<xref:System.Windows.Forms.ListBox>-Steuerelement|Zeigt eine Liste von Text und Grafikelementen (Symbolen).|  
||<xref:System.Windows.Forms.ListView>-Steuerelement|Zeigt die Elemente in einem der vier verschiedene Ansichten. Sichten umfassen nur-Text, Text mit kleinen Symbolen, Text mit großen Symbolen und eine Detailansicht.|  
||<xref:System.Windows.Forms.NumericUpDown>-Steuerelement|Zeigt eine Liste von Zahlen, die Benutzer mit den nach oben oder unten Schaltflächen einen Bildlauf durchführen können.|  
||<xref:System.Windows.Forms.TreeView>-Steuerelement|Zeigt eine hierarchische Auflistung der Knotenobjekten, die von Text mit optionalen Kontrollkästchen oder Symbolen bestehen können.|  
|Anzeige von Grafiken|<xref:System.Windows.Forms.PictureBox>-Steuerelement|Zeigt grafische Dateien, z. B. Bitmaps und Symbole, in einem Frame.|  
|Speichern von Grafiken|<xref:System.Windows.Forms.ImageList>-Steuerelement|Dient als Repository für Images. <xref:System.Windows.Forms.ImageList> Steuerelemente und die darin enthaltenen Bilder können von einer Anwendung zur nächsten wiederverwendet werden.|  
|Wert festlegen|<xref:System.Windows.Forms.CheckBox>-Steuerelement|Zeigt ein Kontrollkästchen und eine Bezeichnung für den Text an. Im Allgemeinen verwendet, um Optionen festzulegen.|  
||<xref:System.Windows.Forms.CheckedListBox>-Steuerelement|Zeigt eine Übersicht der Elemente, jeweils durch ein Kontrollkästchen begleitet.|  
||<xref:System.Windows.Forms.RadioButton>-Steuerelement|Zeigt eine Schaltfläche, die ein- oder ausgeschaltet werden kann.|  
||<xref:System.Windows.Forms.TrackBar>-Steuerelement|Ermöglicht es Benutzern, Werte auf einer Skala festlegen, durch einen 'Ziehpunkt' auf einer Skala verschieben.|  
|Datumseinstellung|<xref:System.Windows.Forms.DateTimePicker>-Steuerelement|Zeigt einen grafischen Kalender, um den Benutzern ermöglichen, ein Datum oder eine Uhrzeit auszuwählen.|  
||<xref:System.Windows.Forms.MonthCalendar>-Steuerelement|Zeigt einen grafischen Kalender, um den Benutzern ermöglichen, einen Datumsbereich auszuwählen.|  
|Dialogfelder|<xref:System.Windows.Forms.ColorDialog>-Steuerelement|Zeigt Auswahldialogfeld für die Farbe, die Benutzern ermöglicht, die Farbe der ein Element der Debuggerbenutzeroberfläche festlegen.|  
||<xref:System.Windows.Forms.FontDialog>-Steuerelement|Zeigt ein Dialogfeld, das Benutzern ermöglicht, eine Schriftart und die zugehörigen Attribute festgelegt.|  
||<xref:System.Windows.Forms.OpenFileDialog>-Steuerelement|Zeigt ein Dialogfeld, mit dem Benutzer zu navigieren, und wählen Sie eine Datei an.|  
||<xref:System.Windows.Forms.PrintDialog>-Steuerelement|Zeigt ein Dialogfeld, das ermöglicht Benutzern das Auswählen eines Druckers, und legen Sie seine Attribute.|  
||<xref:System.Windows.Forms.PrintPreviewDialog>-Steuerelement|Zeigt ein Dialogfeld, das wie ein Steuerelement anzeigt <xref:System.Drawing.Printing.PrintDocument> Komponente wird angezeigt, wenn gedruckt.|  
||<xref:System.Windows.Forms.FolderBrowserDialog>-Steuerelement|Zeigt ein Dialogfeld, mit dem Benutzer zu durchsuchen, erstellen und schließlich wählen Sie einen Ordner|  
||<xref:System.Windows.Forms.SaveFileDialog>-Steuerelement|Zeigt ein Dialogfeld, das Benutzern ermöglicht, eine Datei zu speichern.|  
|Menüsteuerelemente|<xref:System.Windows.Forms.MenuStrip>-Steuerelement|Benutzerdefinierte Menüs wird erstellt. **Hinweis:** der <xref:System.Windows.Forms.MenuStrip> dient zum Ersetzen der <xref:System.Windows.Forms.MainMenu> Steuerelement.|  
||<xref:System.Windows.Forms.ContextMenuStrip>-Steuerelement|Erstellt die benutzerdefinierte Kontextmenüs zu sehen. **Hinweis:** der <xref:System.Windows.Forms.ContextMenuStrip> dient zum Ersetzen der <xref:System.Windows.Forms.ContextMenu> Steuerelement.|  
|Befehle|<xref:System.Windows.Forms.Button>-Steuerelement|Startet, beendet oder einen Prozess unterbricht.|  
||<xref:System.Windows.Forms.LinkLabel>-Steuerelement|Zeigt Text als Link Webstil, und löst ein Ereignis aus, klickt der Benutzer den Text. In der Regel ist der Text, einen Link zu einem anderen Fenster oder eine Website.|  
||<xref:System.Windows.Forms.NotifyIcon>-Steuerelement|Zeigt ein Symbol im Statusbereich der Taskleiste, die im Hintergrund ausgeführte Anwendung darstellt.|  
||<xref:System.Windows.Forms.ToolStrip>-Steuerelement|Erstellt die Symbolleisten, die ein Microsoft Windows XP, Microsoft Office, Microsoft Internet Explorer oder benutzerdefinierte Aussehen und Verhalten, mit oder ohne Designs und Unterstützung für Überlauf und zur Laufzeit Neuordnung aufweisen können. **Hinweis:** der <xref:System.Windows.Forms.ToolStrip> Steuerelement dient zum Ersetzen der <xref:System.Windows.Forms.ToolBar> Steuerelement.|  
|Benutzerhilfe|<xref:System.Windows.Forms.HelpProvider> Komponente|Stellt Popup-oder Onlinehilfe für Steuerelemente bereit.|  
||<xref:System.Windows.Forms.ToolTip> Komponente|Stellt ein Popupfenster, in dem eine kurze Beschreibung des Zwecks eines Steuerelements angezeigt, wenn der Benutzer den Zeiger auf dem Steuerelement verbleibt.|  
|Gruppieren von anderen Steuerelementen|<xref:System.Windows.Forms.Panel>-Steuerelement|Gruppiert einen Satz von Steuerelementen in einem bildlauffähigen Rahmen ohne Bezeichnung.|  
||<xref:System.Windows.Forms.GroupBox>-Steuerelement|Gruppiert einen Satz von Steuerelementen (z. B. Optionsfelder) auf einem mit der Bezeichnung, bildlauffähiger Frame.|  
||<xref:System.Windows.Forms.TabControl>-Steuerelement|Bietet eine Seite im Registerformat zum Organisieren von und Zugreifen auf Objekte effizient gruppiert.|  
||<xref:System.Windows.Forms.SplitContainer>-Steuerelement|Enthält zwei Bereiche, die durch eine verschiebbare Leiste getrennt. **Hinweis:** der <xref:System.Windows.Forms.SplitContainer> Steuerelement dient zum Ersetzen der <xref:System.Windows.Forms.Splitter> Steuerelement.|  
||<xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement|Stellt einen Bereich dar, dessen Inhalt dynamisch in einem aus Zeilen und Spalten bestehenden Raster angeordnet wird.|  
||<xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement|Stellt einen Bereich dar, dessen Inhalt auf dynamische Weise horizontal oder vertikal angeordnet wird.|  
|Audio|<xref:System.Media.SoundPlayer>-Steuerelement|Spielt Sounddateien im WAV-Format. Sounds können geladen oder asynchron wiedergegeben werden.|  
  
## <a name="superseded-controls-and-components-by-function"></a>Abgelöst, Steuerelemente und Komponenten von-Funktion  
  
|Funktion|Ersetzte Steuerelement|Empfohlene Ersatz|  
|--------------|------------------------|-----------------------------|  
|Darstellung der Daten|<xref:System.Windows.Forms.DataGrid>|<xref:System.Windows.Forms.DataGridView>|  
|Angezeigten Informationen (schreibgeschützte Steuerelemente)|<xref:System.Windows.Forms.StatusBar>|<xref:System.Windows.Forms.StatusStrip>|  
|Menüsteuerelemente|<xref:System.Windows.Forms.ContextMenu>|<xref:System.Windows.Forms.ContextMenuStrip>|  
||<xref:System.Windows.Forms.MainMenu>|<xref:System.Windows.Forms.MenuStrip>|  
|Befehle|<xref:System.Windows.Forms.ToolBar>|<xref:System.Windows.Forms.ToolStrip>|  
||<xref:System.Windows.Forms.StatusBar>|<xref:System.Windows.Forms.StatusStrip>|  
|Formularlayout|<xref:System.Windows.Forms.Splitter>|<xref:System.Windows.Forms.SplitContainer>|  
  
## <a name="see-also"></a>Siehe auch  
 [Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)
