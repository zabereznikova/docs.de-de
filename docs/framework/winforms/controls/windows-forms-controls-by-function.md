---
title: Steuerelemente nach Funktion
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], by function
- Windows Forms, controls by function
- Windows Forms controls, list of
ms.assetid: 5e65a6c3-5d6f-480d-beb8-b28f865f07e3
ms.openlocfilehash: f2341d49513b418c244ee7ab93c0858899502487
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741580"
---
# <a name="windows-forms-controls-by-function"></a>Windows Forms-Steuerelemente nach Funktion
Windows Forms bietet Steuerelemente und Komponenten, die eine Reihe von Funktionen ausführen. In der folgenden Tabelle werden die Windows Forms-Steuerelemente und-Komponenten entsprechend der allgemeinen Funktion aufgelistet. Wenn mehrere Steuerelemente vorhanden sind, die dieselbe Funktion erfüllen, wird außerdem das empfohlene Steuerelement mit einem Hinweis auf das Steuerelement aufgelistet, das es ersetzt hat. In einer separaten nachfolgenden Tabelle werden die abgelösten Steuerelemente mit den empfohlenen Ersetzungen aufgelistet.  
  
> [!NOTE]
> In den folgenden Tabellen sind nicht alle Steuerelemente oder Komponenten aufgelistet, die Sie in Windows Forms verwenden können. eine umfassendere Liste finden [Sie unter zu verwendende Steuerelemente auf Windows Forms](controls-to-use-on-windows-forms.md)  
  
## <a name="recommended-controls-and-components-by-function"></a>Empfohlene Steuerelemente und Komponenten nach Funktion  
  
|Funktion|Control|BESCHREIBUNG|  
|--------------|-------------|-----------------|  
|Datenanzeige|<xref:System.Windows.Forms.DataGridView>-Steuerelement|Das <xref:System.Windows.Forms.DataGridView>-Steuerelement stellt eine anpassbare Tabelle zum Anzeigen von Daten bereit. Die <xref:System.Windows.Forms.DataGridView>-Klasse ermöglicht die Anpassung von Zellen, Zeilen, Spalten und Rahmen. **Hinweis:**  Das <xref:System.Windows.Forms.DataGridView>-Steuerelement bietet zahlreiche grundlegende und erweiterte Funktionen, die im <xref:System.Windows.Forms.DataGrid>-Steuerelement fehlen. Weitere Informationen finden Sie [unter Unterschiede zwischen dem Windows Forms DataGridView-Steuerelement und dem DataGrid-](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) Steuerelement|  
|Datenbindung und-Navigation|<xref:System.Windows.Forms.BindingSource>-Komponente|Vereinfacht das Binden von Steuerelementen in einem Formular an Daten durch Bereitstellen von Währungsmanagement, Änderungs Benachrichtigung und anderen Diensten.|  
||<xref:System.Windows.Forms.BindingNavigator>-Steuerelement|Stellt eine Schnittstelle vom Typ Toolbar zum Navigieren und Bearbeiten von Daten in einem Formular bereit.|  
|Text Bearbeitung|<xref:System.Windows.Forms.TextBox>-Steuerelement|Zeigt Text an, der zur Entwurfszeit eingegeben wurde und von Benutzern zur Laufzeit bearbeitet oder Programm gesteuert geändert werden kann.|  
||<xref:System.Windows.Forms.RichTextBox>-Steuerelement|Ermöglicht das Anzeigen von Text mit Formatierungen im nur-Text-Format oder im Rich-Text-Format (RTF).|  
||<xref:System.Windows.Forms.MaskedTextBox>-Steuerelement|Schränkt das Format der Benutzereingabe ein.|  
|Anzeige von Informationen (schreibgeschützt)|<xref:System.Windows.Forms.Label>-Steuerelement|Zeigt Text an, den Benutzer nicht direkt bearbeiten können.|  
||<xref:System.Windows.Forms.LinkLabel>-Steuerelement|Zeigt Text als Link im Webstil an und löst ein Ereignis aus, wenn der Benutzer auf den speziellen Text klickt. Normalerweise ist der Text ein Link zu einem anderen Fenster oder einer Website.|  
||<xref:System.Windows.Forms.StatusStrip>-Steuerelement|Zeigt Informationen zum aktuellen Zustand der Anwendung mit einem eingerahmten Bereich an, in der Regel am unteren Rand eines übergeordneten Formulars.|  
||<xref:System.Windows.Forms.ProgressBar>-Steuerelement|Zeigt den aktuellen Status eines Vorgangs an den Benutzer an.|  
|Webseiten Anzeige|<xref:System.Windows.Forms.WebBrowser>-Steuerelement|Ermöglicht dem Benutzer, zu Webseiten innerhalb eines Formulars zu navigieren.|  
|Auswahl aus einer Liste|<xref:System.Windows.Forms.CheckedListBox>-Steuerelement|Zeigt eine Bild lauffähigen Liste von Elementen an, die jeweils von einem Kontrollkästchen begleitet werden.|  
||<xref:System.Windows.Forms.ComboBox>-Steuerelement|Zeigt eine Dropdown Liste mit Elementen an.|  
||<xref:System.Windows.Forms.DomainUpDown>-Steuerelement|Zeigt eine Liste von Textelementen an, durch die Benutzer mit den Schaltflächen nach oben und unten scrollen können|  
||<xref:System.Windows.Forms.ListBox>-Steuerelement|Zeigt eine Liste von Text und grafischen Elementen an (Symbole).|  
||<xref:System.Windows.Forms.ListView>-Steuerelement|Zeigt Elemente in einer von vier verschiedenen Ansichten an. Sichten enthalten nur Text, Text mit kleinen Symbolen, Text mit großen Symbolen und eine Detailansicht.|  
||<xref:System.Windows.Forms.NumericUpDown>-Steuerelement|Zeigt eine Liste von Ziffern an, die Benutzer durch die nach-oben-und nach-unten-Schaltfläche scrollen können|  
||<xref:System.Windows.Forms.TreeView>-Steuerelement|Zeigt eine hierarchische Auflistung von Knoten Objekten an, die aus Text mit optionalen Kontrollkästchen oder Symbolen bestehen können.|  
|Grafik Anzeige|<xref:System.Windows.Forms.PictureBox>-Steuerelement|Zeigt grafische Dateien, z. b. Bitmaps und Symbole, in einem Rahmen an.|  
|Grafikspeicher|<xref:System.Windows.Forms.ImageList>-Steuerelement|Dient als Repository für Bilder. <xref:System.Windows.Forms.ImageList> Steuerelemente und die darin enthaltenen Bilder können von einer Anwendung zur nächsten wieder verwendet werden.|  
|Wert Einstellung|<xref:System.Windows.Forms.CheckBox>-Steuerelement|Zeigt ein Kontrollkästchen und eine Bezeichnung für Text an. Wird im Allgemeinen verwendet, um Optionen festzulegen.|  
||<xref:System.Windows.Forms.CheckedListBox>-Steuerelement|Zeigt eine Bild lauffähigen Liste von Elementen an, die jeweils von einem Kontrollkästchen begleitet werden.|  
||<xref:System.Windows.Forms.RadioButton>-Steuerelement|Zeigt eine Schaltfläche an, die aktiviert oder deaktiviert werden kann.|  
||<xref:System.Windows.Forms.TrackBar>-Steuerelement|Ermöglicht es Benutzern, Werte für eine Skala festzulegen, indem Sie einen "Thumb"-Wert entlang einer Skala bewegen.|  
|Datumseinstellung|<xref:System.Windows.Forms.DateTimePicker>-Steuerelement|Zeigt einen grafischen Kalender an, mit dem Benutzer ein Datum oder eine Uhrzeit auswählen können.|  
||<xref:System.Windows.Forms.MonthCalendar>-Steuerelement|Zeigt einen grafischen Kalender an, mit dem Benutzer einen Datumsbereich auswählen können.|  
|Dialogfelder|<xref:System.Windows.Forms.ColorDialog>-Steuerelement|Zeigt das Dialogfeld Farbauswahl an, in dem Benutzer die Farbe eines Schnittstellen Elements festlegen können.|  
||<xref:System.Windows.Forms.FontDialog>-Steuerelement|Zeigt ein Dialogfeld an, in dem Benutzer eine Schriftart und deren Attribute festlegen können.|  
||<xref:System.Windows.Forms.OpenFileDialog>-Steuerelement|Zeigt ein Dialogfeld an, in dem Benutzer zu einer Datei navigieren und diese auswählen können.|  
||<xref:System.Windows.Forms.PrintDialog>-Steuerelement|Zeigt ein Dialogfeld an, in dem Benutzer einen Drucker auswählen und seine Attribute festlegen können.|  
||<xref:System.Windows.Forms.PrintPreviewDialog>-Steuerelement|Zeigt ein Dialogfeld an, in dem angezeigt wird, wie ein Steuerelement <xref:System.Drawing.Printing.PrintDocument> Komponente beim Drucken angezeigt wird.|  
||<xref:System.Windows.Forms.FolderBrowserDialog>-Steuerelement|Zeigt ein Dialogfeld an, in dem Benutzer einen Ordner durchsuchen, erstellen und schließlich auswählen können.|  
||<xref:System.Windows.Forms.SaveFileDialog>-Steuerelement|Zeigt ein Dialogfeld an, in dem Benutzer eine Datei speichern können.|  
|Menü Steuerelemente|<xref:System.Windows.Forms.MenuStrip>-Steuerelement|Erstellt benutzerdefinierte Menüs. **Hinweis:**  Der <xref:System.Windows.Forms.MenuStrip> ist so konzipiert, dass er das <xref:System.Windows.Forms.MainMenu> Steuerelement ersetzt.|  
||<xref:System.Windows.Forms.ContextMenuStrip>-Steuerelement|Erstellt benutzerdefinierte Kontextmenüs. **Hinweis:**  Der <xref:System.Windows.Forms.ContextMenuStrip> ist so konzipiert, dass er das <xref:System.Windows.Forms.ContextMenu> Steuerelement ersetzt.|  
|Befehle|<xref:System.Windows.Forms.Button>-Steuerelement|Startet, beendet oder unterbricht einen Prozess.|  
||<xref:System.Windows.Forms.LinkLabel>-Steuerelement|Zeigt Text als Link im Webstil an und löst ein Ereignis aus, wenn der Benutzer auf den speziellen Text klickt. Normalerweise ist der Text ein Link zu einem anderen Fenster oder einer Website.|  
||<xref:System.Windows.Forms.NotifyIcon>-Steuerelement|Zeigt ein Symbol im Status Benachrichtigungsbereich der Taskleiste an, die eine Anwendung darstellt, die im Hintergrund ausgeführt wird.|  
||<xref:System.Windows.Forms.ToolStrip>-Steuerelement|Erstellt Symbolleisten, die über eine Microsoft Windows XP, Microsoft Office, Microsoft Internet Explorer oder ein benutzerdefiniertes Aussehen und Gefühl verfügen, mit oder ohne Designs und mit Unterstützung für Überlauf-und Lauf Zeitelement Neuanordnen. **Hinweis:**  Das <xref:System.Windows.Forms.ToolStrip> Steuerelement ist so konzipiert, dass es das <xref:System.Windows.Forms.ToolBar> Steuerelement ersetzt.|  
|Hilfe für Benutzer|<xref:System.Windows.Forms.HelpProvider>-Komponente|Stellt Popup- oder Onlinehilfe für Steuerelemente bereit.|  
||<xref:System.Windows.Forms.ToolTip>-Komponente|Stellt ein Popup Fenster bereit, in dem eine kurze Beschreibung des Zwecks eines Steuer Elements angezeigt wird, wenn der Benutzer den Zeiger auf das Steuerelement zeigt.|  
|Gruppieren von anderen Steuerelementen|<xref:System.Windows.Forms.Panel>-Steuerelement|Gruppiert eine Reihe von Steuerelementen auf einen nicht beschrifteten Bild lauffähigen Frame.|  
||<xref:System.Windows.Forms.GroupBox>-Steuerelement|Gruppiert einen Satz von Steuerelementen (z. b. Options Felder) in einem beschrifteten, nicht Bild lauffähigen Frame.|  
||<xref:System.Windows.Forms.TabControl>-Steuerelement|Stellt eine Seite im Register Format zum effizienten organisieren und Zugreifen auf gruppierte Objekte bereit.|  
||<xref:System.Windows.Forms.SplitContainer>-Steuerelement|Bietet zwei Bereiche, die durch eine verschiebbare Leiste getrennt sind. **Hinweis:**  Das <xref:System.Windows.Forms.SplitContainer> Steuerelement ist so konzipiert, dass es das <xref:System.Windows.Forms.Splitter> Steuerelement ersetzt.|  
||<xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement|Stellt einen Bereich dar, dessen Inhalt dynamisch in einem aus Zeilen und Spalten bestehenden Raster angeordnet wird.|  
||<xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement|Stellt einen Bereich dar, dessen Inhalt auf dynamische Weise horizontal oder vertikal angeordnet wird.|  
|Audio|<xref:System.Media.SoundPlayer>-Steuerelement|Gibt Sounddateien im WAV-Format wieder. Sounds können asynchron geladen oder wiedergegeben werden.|  
  
## <a name="superseded-controls-and-components-by-function"></a>Ersetzte Steuerelemente und Komponenten nach Funktion  
  
|Funktion|Abgelösten Steuerelement|Empfohlener Ersatz|  
|--------------|------------------------|-----------------------------|  
|Datenanzeige|<xref:System.Windows.Forms.DataGrid>|<xref:System.Windows.Forms.DataGridView>|  
|Anzeige von Informationen (schreibgeschützte Steuerelemente)|<xref:System.Windows.Forms.StatusBar>|<xref:System.Windows.Forms.StatusStrip>|  
|Menü Steuerelemente|<xref:System.Windows.Forms.ContextMenu>|<xref:System.Windows.Forms.ContextMenuStrip>|  
||<xref:System.Windows.Forms.MainMenu>|<xref:System.Windows.Forms.MenuStrip>|  
|Befehle|<xref:System.Windows.Forms.ToolBar>|<xref:System.Windows.Forms.ToolStrip>|  
||<xref:System.Windows.Forms.StatusBar>|<xref:System.Windows.Forms.StatusStrip>|  
|Formularlayout|<xref:System.Windows.Forms.Splitter>|<xref:System.Windows.Forms.SplitContainer>|  
  
## <a name="see-also"></a>Weitere Informationen

- [Steuerelemente für Windows Forms](controls-to-use-on-windows-forms.md)
- [Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework](developing-custom-windows-forms-controls.md)
