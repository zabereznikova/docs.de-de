---
title: Windows Forms-Steuerelemente nach Funktion
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], by function
- Windows Forms, controls by function
- Windows Forms controls, list of
ms.assetid: 5e65a6c3-5d6f-480d-beb8-b28f865f07e3
ms.openlocfilehash: 91da6409eb3a02709332d8d1a5a2d7fe54d3f401
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54543067"
---
# <a name="windows-forms-controls-by-function"></a>Windows Forms-Steuerelemente nach Funktion
Windows Forms bietet Steuerelemente und Komponenten, die eine Reihe von Funktionen ausführen. Die folgende Tabelle enthält die Windows Forms-Steuerelemente und Komponenten entsprechend allgemeine Funktion. Wenn mehrere Steuerelemente vorhanden, die die gleiche Funktion dienen sind, ist das empfohlene Steuerelement darüber hinaus mit einem Hinweis in Bezug auf das Steuerelement aufgeführt, die sie ersetzt. In einer separaten nachfolgenden Tabelle werden die ersetzten Steuerelemente mit ihren empfohlenen Ersetzungen aufgeführt.  
  
> [!NOTE]
>  Die folgenden Tabellen sind nicht enthalten, jedes Steuerelement bzw. jede Komponente aus, die in Windows Forms verwendet werden können; eine umfassendere Liste, finden Sie unter [in Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
  
## <a name="recommended-controls-and-components-by-function"></a>Empfohlene Steuerelemente und Komponenten von-Funktion  
  
|Funktion|Steuerelement|Beschreibung|  
|--------------|-------------|-----------------|  
|Datenanzeige|<xref:System.Windows.Forms.DataGridView>-Steuerelement|Die <xref:System.Windows.Forms.DataGridView> Steuerelement stellt eine anpassbare Tabelle zum Anzeigen von Daten. Die <xref:System.Windows.Forms.DataGridView> Klasse ermöglicht die Anpassung von Zellen, Zeilen, Spalten und Rahmen. **Hinweis**:  Die <xref:System.Windows.Forms.DataGridView> -Steuerelement stellt zahlreiche grundlegenden und erweiterten Features, die fehlen in der <xref:System.Windows.Forms.DataGrid> Steuerelement. Weitere Informationen finden Sie unter [Unterschiede zwischen dem Windows Forms DataGridView-Steuerelement und DataGrid-Steuerelement](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)|  
|Die Datenbindung und navigation|<xref:System.Windows.Forms.BindingSource> Komponente|Vereinfacht Binden von Steuerelementen in einem Formular an Daten durch währungsverwaltung, änderungsbenachrichtigung und andere Dienste.|  
||<xref:System.Windows.Forms.BindingNavigator>-Steuerelement|Bietet eine Symbolleiste-Type-Schnittstelle, um zu navigieren und Bearbeiten von Daten in einem Formular.|  
|Textbearbeitung|<xref:System.Windows.Forms.TextBox>-Steuerelement|Zeigt Text eingegeben haben, zur Entwurfszeit, die zur Laufzeit von den Benutzern bearbeitet oder programmgesteuert geändert werden kann.|  
||<xref:System.Windows.Forms.RichTextBox>-Steuerelement|Ermöglicht es Text, der bei der Formatierung in nur-Text oder Rich-Text-Format (RTF) angezeigt werden.|  
||<xref:System.Windows.Forms.MaskedTextBox>-Steuerelement|Schränkt das Format der Benutzereingabe|  
|Die angezeigten Informationen (schreibgeschützt)|<xref:System.Windows.Forms.Label>-Steuerelement|Zeigt Text an, den Benutzer nicht direkt bearbeiten können.|  
||<xref:System.Windows.Forms.LinkLabel>-Steuerelement|Zeigt Text als Link Webstil, und löst ein Ereignis, wenn der Benutzer den Text klickt. In der Regel ist der Text einen Link zu einem anderen Fenster oder eine Website.|  
||<xref:System.Windows.Forms.StatusStrip>-Steuerelement|Zeigt Informationen zum Zustand der Anwendung des aktuellen Rahmenbereich an, in der Regel am unteren Rand eines übergeordneten Formulars.|  
||<xref:System.Windows.Forms.ProgressBar>-Steuerelement|Zeigt den aktuellen Status eines Vorgangs für den Benutzer an.|  
|Webseite anzeigen|<xref:System.Windows.Forms.WebBrowser>-Steuerelement|Ermöglicht dem Benutzer, zu Webseiten innerhalb eines Formulars zu navigieren.|  
|Auswahl aus einer Liste|<xref:System.Windows.Forms.CheckedListBox>-Steuerelement|Zeigt eine bildlauffähige Liste von Elementen, die jeweils zusammen, indem Sie das Kontrollkästchen.|  
||<xref:System.Windows.Forms.ComboBox>-Steuerelement|Zeigt eine Dropdown-Liste von Elementen.|  
||<xref:System.Windows.Forms.DomainUpDown>-Steuerelement|Zeigt eine Liste der Textelemente, die Benutzer mit den Schaltflächen nach einen Bildlauf durchführen können.|  
||<xref:System.Windows.Forms.ListBox>-Steuerelement|Zeigt eine Liste von Text und grafische Elemente (Symbole).|  
||<xref:System.Windows.Forms.ListView>-Steuerelement|Elemente in einem von vier verschiedenen Ansichten angezeigt. Sichten enthalten, nur-Text, Text mit kleinen Symbolen, Text mit großen Symbolen und eine Detailansicht.|  
||<xref:System.Windows.Forms.NumericUpDown>-Steuerelement|Zeigt eine Liste von Zahlen, die Benutzer mit den Schaltflächen nach einen Bildlauf durchführen können.|  
||<xref:System.Windows.Forms.TreeView>-Steuerelement|Zeigt eine hierarchische Auflistung von Node-Objekte, die Text mit optionalen Kontrollkästchen oder Symbolen bestehen können.|  
|Anzeigen von Grafiken|<xref:System.Windows.Forms.PictureBox>-Steuerelement|Zeigt grafische Dateien, z. B. Bitmaps und Symbole, in einem Rahmen.|  
|Speichern von Grafiken|<xref:System.Windows.Forms.ImageList>-Steuerelement|Dient als Repository für Bilder. <xref:System.Windows.Forms.ImageList> Steuerelemente und die darin enthaltenen Images können von einer Anwendung zur nächsten wiederverwendet werden.|  
|Werteinstellung|<xref:System.Windows.Forms.CheckBox>-Steuerelement|Zeigt ein Kontrollkästchen und eine Bezeichnung für den Text an. Im Allgemeinen verwendet, um Optionen festzulegen.|  
||<xref:System.Windows.Forms.CheckedListBox>-Steuerelement|Zeigt eine bildlauffähige Liste von Elementen, die jeweils zusammen, indem Sie das Kontrollkästchen.|  
||<xref:System.Windows.Forms.RadioButton>-Steuerelement|Zeigt eine Schaltfläche, die aktiviert oder deaktiviert werden kann.|  
||<xref:System.Windows.Forms.TrackBar>-Steuerelement|Ermöglicht Benutzern, die Werte auf einer Skala festlegen, indem Sie einen 'Ziehpunkt' auf einer Skala verschieben.|  
|Datumsformat|<xref:System.Windows.Forms.DateTimePicker>-Steuerelement|Zeigt einen grafische Kalender zum Benutzer ein Datum oder eine Uhrzeit auswählen können.|  
||<xref:System.Windows.Forms.MonthCalendar>-Steuerelement|Zeigt einen grafischen Kalender, um den Benutzern ermöglichen, einen Datumsbereich auszuwählen.|  
|Dialogfelder|<xref:System.Windows.Forms.ColorDialog>-Steuerelement|Zeigt die Auswahl im Dialogfeld Farbe, die Benutzern ermöglicht, Festlegen der Farbe eines Elements der Benutzeroberfläche.|  
||<xref:System.Windows.Forms.FontDialog>-Steuerelement|Zeigt ein Dialogfeld, das Benutzern ermöglicht, eine Schriftart und die zugehörigen Attribute festgelegt.|  
||<xref:System.Windows.Forms.OpenFileDialog>-Steuerelement|Zeigt ein Dialogfeld, mit dem Benutzer zu navigieren, und wählen Sie eine Datei an.|  
||<xref:System.Windows.Forms.PrintDialog>-Steuerelement|Zeigt ein Dialogfeld, mit der Benutzer zum Auswählen eines Druckers, und legen Sie seine Attribute.|  
||<xref:System.Windows.Forms.PrintPreviewDialog>-Steuerelement|Zeigt ein Dialogfeld, das wie ein Steuerelement zeigt <xref:System.Drawing.Printing.PrintDocument> Komponente wird angezeigt, gedruckt.|  
||<xref:System.Windows.Forms.FolderBrowserDialog>-Steuerelement|Zeigt ein Dialogfeld, mit dem Benutzer durchsuchen, zu erstellen, und wählen Sie schließlich einen Ordner|  
||<xref:System.Windows.Forms.SaveFileDialog>-Steuerelement|Zeigt ein Dialogfeld, das Benutzern ermöglicht, eine Datei zu speichern.|  
|Menu-Steuerelemente|<xref:System.Windows.Forms.MenuStrip>-Steuerelement|Erstellt benutzerdefinierte Menüs. **Hinweis**:  Die <xref:System.Windows.Forms.MenuStrip> dient zum Ersetzen der <xref:System.Windows.Forms.MainMenu> Steuerelement.|  
||<xref:System.Windows.Forms.ContextMenuStrip>-Steuerelement|Benutzerdefinierte Kontextmenüs wird erstellt. **Hinweis**:  Die <xref:System.Windows.Forms.ContextMenuStrip> dient zum Ersetzen der <xref:System.Windows.Forms.ContextMenu> Steuerelement.|  
|Befehle|<xref:System.Windows.Forms.Button>-Steuerelement|Startet, beendet oder einen Prozess von Hardwareinterrupts benötigt hat.|  
||<xref:System.Windows.Forms.LinkLabel>-Steuerelement|Zeigt Text als Link Webstil, und löst ein Ereignis, wenn der Benutzer den Text klickt. In der Regel ist der Text einen Link zu einem anderen Fenster oder eine Website.|  
||<xref:System.Windows.Forms.NotifyIcon>-Steuerelement|Zeigt ein Symbol im Statusbereich der Taskleiste dar, die eine Anwendung im Hintergrund ausgeführte darstellt.|  
||<xref:System.Windows.Forms.ToolStrip>-Steuerelement|Erstellt die Symbolleisten, die ein Microsoft Windows XP, Microsoft Office, Microsoft Internet Explorer oder benutzerdefinierten Aussehen und Verhalten, mit oder ohne Designs sowie Unterstützung für Überlauf und Neuanordnen von Elementen zur Laufzeit haben kann. **Hinweis**:  Die <xref:System.Windows.Forms.ToolStrip> dient zum Ersetzen der <xref:System.Windows.Forms.ToolBar> Steuerelement.|  
|Benutzerhilfe|<xref:System.Windows.Forms.HelpProvider> Komponente|Stellt Popup-oder Onlinehilfe für Steuerelemente bereit.|  
||<xref:System.Windows.Forms.ToolTip> Komponente|Stellt ein Popupfenster, das eine kurze Beschreibung des Zwecks eines Steuerelements anzeigt, wenn der Benutzer den Zeiger auf das Steuerelement gezeigt.|  
|Gruppieren von anderen Steuerelementen|<xref:System.Windows.Forms.Panel>-Steuerelement|Gruppiert eine Reihe von Steuerelementen in einem bildlauffähigen Rahmen ohne Bezeichnung.|  
||<xref:System.Windows.Forms.GroupBox>-Steuerelement|Gruppiert einen Satz von Steuerelementen (z. B. Optionsfelder) auf einen mit der Bezeichnung, bildlauffähiger Rahmen.|  
||<xref:System.Windows.Forms.TabControl>-Steuerelement|Bietet eine Seite im Registerformat zum Organisieren von und Zugreifen auf Objekte effizient gruppiert.|  
||<xref:System.Windows.Forms.SplitContainer>-Steuerelement|Enthält zwei Bereiche, die durch eine verschiebbare Leiste getrennt. **Hinweis**:  Die <xref:System.Windows.Forms.SplitContainer> dient zum Ersetzen der <xref:System.Windows.Forms.Splitter> Steuerelement.|  
||<xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement|Stellt einen Bereich dar, dessen Inhalt dynamisch in einem aus Zeilen und Spalten bestehenden Raster angeordnet wird.|  
||<xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement|Stellt einen Bereich dar, dessen Inhalt auf dynamische Weise horizontal oder vertikal angeordnet wird.|  
|Audio|<xref:System.Media.SoundPlayer>-Steuerelement|Spielt Sounddateien im WAV-Format. Sounds können geladen oder asynchron wiedergegeben werden.|  
  
## <a name="superseded-controls-and-components-by-function"></a>Abgelöst von Steuerelementen und Komponenten von-Funktion  
  
|Funktion|Ersetzte Steuerelement|Empfohlene Ersatz|  
|--------------|------------------------|-----------------------------|  
|Datenanzeige|<xref:System.Windows.Forms.DataGrid>|<xref:System.Windows.Forms.DataGridView>|  
|Informationen anzeigen (nur-Lese Steuerelemente)|<xref:System.Windows.Forms.StatusBar>|<xref:System.Windows.Forms.StatusStrip>|  
|Menu-Steuerelemente|<xref:System.Windows.Forms.ContextMenu>|<xref:System.Windows.Forms.ContextMenuStrip>|  
||<xref:System.Windows.Forms.MainMenu>|<xref:System.Windows.Forms.MenuStrip>|  
|Befehle|<xref:System.Windows.Forms.ToolBar>|<xref:System.Windows.Forms.ToolStrip>|  
||<xref:System.Windows.Forms.StatusBar>|<xref:System.Windows.Forms.StatusStrip>|  
|Formularlayout|<xref:System.Windows.Forms.Splitter>|<xref:System.Windows.Forms.SplitContainer>|  
  
## <a name="see-also"></a>Siehe auch
- [Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
- [Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)
