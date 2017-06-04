---
title: "Windows&#160;Forms-Steuerelemente nach Funktion | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Steuerelemente [Windows Forms], Nach Funktion"
  - "Windows Forms-Steuerelemente, Liste"
  - "Windows Forms, Steuerelemente nach Funktion"
ms.assetid: 5e65a6c3-5d6f-480d-beb8-b28f865f07e3
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Windows&#160;Forms-Steuerelemente nach Funktion
Windows Forms bietet Steuerelemente und Komponenten zur Ausführung verschiedener Funktionen.  In der folgenden Tabelle sind die Windows Forms\-Steuerelemente und \-Komponenten nach der allgemeinen Funktion aufgelistet.  Wenn darüber hinaus mehrere Steuerelemente für dieselbe Funktion vorhanden sind, wird das empfohlene Steuerelement mit einem Hinweis auf das ersetzte Steuerelement aufgeführt.  In einer separaten nachfolgenden Tabelle werden die ersetzten Steuerelemente mit ihren empfohlenen Ersetzungen aufgelistet.  
  
> [!NOTE]
>  In der folgenden Tabelle sind nicht alle in Windows Forms verwendbaren Steuerelemente oder Komponenten aufgeführt. Eine umfassendere Liste finden Sie unter [Steuerelemente für Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md).  
  
## Empfohlene Steuerelemente und Komponenten nach Funktion  
  
|Funktion|Steuerelement|Beschreibung|  
|--------------|-------------------|------------------|  
|Datenanzeige|<xref:System.Windows.Forms.DataGridView>\-Steuerelement|Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement stellt eine anpassbare Tabelle zum Anzeigen von Daten bereit.  Die <xref:System.Windows.Forms.DataGridView>\-Klasse ermöglicht die Anpassung von Zellen, Zeilen, Spalten und Rahmen. **Note:**  Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement stellt zahlreiche grundlegende und erweiterte Features bereit, die das <xref:System.Windows.Forms.DataGrid>\-Steuerelement nicht aufweist.  Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView\-Steuerelement und dem DataGrid\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)|  
|Datenbindung und Navigation|<xref:System.Windows.Forms.BindingSource>\-Komponente|Vereinfacht das Binden von Steuerelementen an Daten in einem Formular durch Positionsverwaltung, Änderungsbenachrichtigung und andere Dienste.|  
||<xref:System.Windows.Forms.BindingNavigator>\-Steuerelement|Stellt eine Oberfläche in Form einer Symbolleiste bereit, um durch Daten in einem Formular zu navigieren und diese zu bearbeiten.|  
|Textbearbeitung|<xref:System.Windows.Forms.TextBox>\-Steuerelement|Zeigt zur Entwurfszeit eingegebenen Text an, der zur Laufzeit von den Benutzern bearbeitet oder programmgesteuert geändert werden kann.|  
||<xref:System.Windows.Forms.RichTextBox>\-Steuerelement|Text kann im Nur\-Text\- oder im Rich\-Text\-Format \(RTF\) angezeigt werden.|  
||<xref:System.Windows.Forms.MaskedTextBox>\-Steuerelement|Schränkt das Format der Benutzereingabe ein.|  
|Informationsanzeige \(schreibgeschützt\)|<xref:System.Windows.Forms.Label>\-Steuerelement|Zeigt Text an, den Benutzer nicht direkt bearbeiten können.|  
||<xref:System.Windows.Forms.LinkLabel>\-Steuerelement|Zeigt Text als Link an und löst ein Ereignis aus, wenn die Benutzer auf den Text klicken.  In der Regel stellt der Text einen Link zu einem anderen Fenster oder einer Website dar.|  
||<xref:System.Windows.Forms.StatusStrip>\-Steuerelement|Zeigt Informationen über den aktuellen Zustand der Anwendung in einem Rahmenbereich an, normalerweise am unteren Rand eines übergeordneten Formulars.|  
||<xref:System.Windows.Forms.ProgressBar>\-Steuerelement|Zeigt den aktuellen Fortschritt eines Vorgangs für den Benutzer an.|  
|Webseitenanzeige|<xref:System.Windows.Forms.WebBrowser>\-Steuerelement|Ermöglicht es dem Benutzer, innerhalb des Formulars durch Webseiten zu navigieren.|  
|Auswahl aus einer Liste|<xref:System.Windows.Forms.CheckedListBox>\-Steuerelement|Zeigt eine bildlauffähige Liste von Elementen an, neben denen jeweils ein Kontrollkästchen steht.|  
||<xref:System.Windows.Forms.ComboBox>\-Steuerelement|Zeigt eine Dropdownliste von Elementen an.|  
||<xref:System.Windows.Forms.DomainUpDown>\-Steuerelement|Zeigt eine Liste von Textelementen an, in der Benutzer mit den Schaltflächen **Nach oben** bzw. **Nach unten** einen Bildlauf durchführen können.|  
||<xref:System.Windows.Forms.ListBox>\-Steuerelement|Zeigt eine Liste von Text\- und Grafikelementen \(Symbolen\) an.|  
||<xref:System.Windows.Forms.ListView>\-Steuerelement|Zeigt Elemente in einer von vier verschiedenen Ansichten an:  Diese Ansichten umfassen nur Text, Text mit kleinen Symbolen, Text mit großen Symbolen und eine Detailansicht.|  
||<xref:System.Windows.Forms.NumericUpDown>\-Steuerelement|Zeigt eine Liste von Nummernzeichen an, in der Benutzer mit den Schaltflächen **Nach oben** bzw. **Nach unten** einen Bildlauf durchführen können.|  
||<xref:System.Windows.Forms.TreeView>\-Steuerelement|Zeigt eine hierarchische Auflistung von Knotenobjekten an, die aus Text mit optionalen Kontrollkästchen oder Symbolen bestehen können.|  
|Grafikanzeige|<xref:System.Windows.Forms.PictureBox>\-Steuerelement|Zeigt Grafikdateien, z. B. Bitmaps und Symbole, in einem Rahmen an.|  
|Speichern von Grafiken|<xref:System.Windows.Forms.ImageList>\-Steuerelement|Dient als Repository für Bilder.  <xref:System.Windows.Forms.ImageList>\-Steuerelemente und die darin enthaltenen Bilder können zwischen Anwendungen wiederverwendet werden.|  
|Festlegen von Werten|<xref:System.Windows.Forms.CheckBox>\-Steuerelement|Zeigt ein Kontrollkästchen und eine Textbezeichnung an.  In der Regel wird dieses Steuerelement zum Einstellen von Optionen verwendet.|  
||<xref:System.Windows.Forms.CheckedListBox>\-Steuerelement|Zeigt eine bildlauffähige Liste von Elementen an, neben denen jeweils ein Kontrollkästchen steht.|  
||<xref:System.Windows.Forms.RadioButton>\-Steuerelement|Zeigt eine Schaltfläche an, die aktiviert oder deaktiviert werden kann.|  
||<xref:System.Windows.Forms.TrackBar>\-Steuerelement|Benutzer können auf einer Skala mit einem Ziehpunkt Werte einstellen.|  
|Datumseinstellung|<xref:System.Windows.Forms.DateTimePicker>\-Steuerelement|Zeigt einen grafischen Kalender an, in dem Benutzer ein Datum oder eine Uhrzeit auswählen können.|  
||<xref:System.Windows.Forms.MonthCalendar>\-Steuerelement|Zeigt einen grafischen Kalender an, in dem Benutzer einen Datumsbereich auswählen können.|  
|Dialogfelder|<xref:System.Windows.Forms.ColorDialog>\-Steuerelement|Zeigt das Dialogfeld zur Farbauswahl an, in dem Benutzer die Farbe eines Oberflächenelements einstellen können.|  
||<xref:System.Windows.Forms.FontDialog>\-Steuerelement|Zeigt ein Dialogfeld an, in dem Benutzer eine Schriftart und deren Attribute einstellen können.|  
||<xref:System.Windows.Forms.OpenFileDialog>\-Steuerelement|Zeigt ein Dialogfeld an, in dem Benutzer zu einer Datei navigieren und diese auswählen können.|  
||<xref:System.Windows.Forms.PrintDialog>\-Steuerelement|Zeigt ein Dialogfeld an, in dem Benutzer einen Drucker auswählen und dessen Attribute einstellen können.|  
||<xref:System.Windows.Forms.PrintPreviewDialog>\-Steuerelement|Zeigt ein Dialogfeld mit der Seitenvorschau einer <xref:System.Drawing.Printing.PrintDocument>\-Steuerelementkomponente an.|  
||<xref:System.Windows.Forms.FolderBrowserDialog>\-Steuerelement|Zeigt ein Dialogfeld an, in dem Benutzer Ordner durchsuchen, erstellen und schließlich auswählen können.|  
||<xref:System.Windows.Forms.SaveFileDialog>\-Steuerelement|Zeigt ein Dialogfeld an, in dem Benutzer eine Datei speichern können.|  
|Menüsteuerelemente|<xref:System.Windows.Forms.MenuStrip>\-Steuerelement|Erstellt benutzerdefinierte Menüs. **Note:**  <xref:System.Windows.Forms.MenuStrip> ersetzt das <xref:System.Windows.Forms.MainMenu>\-Steuerelement.|  
||<xref:System.Windows.Forms.ContextMenuStrip>\-Steuerelement|Erstellt benutzerdefinierte Kontextmenüs. **Note:**  <xref:System.Windows.Forms.ContextMenuStrip> ersetzt das <xref:System.Windows.Forms.ContextMenu>\-Steuerelement.|  
|Befehle|<xref:System.Windows.Forms.Button>\-Steuerelement|Startet einen Prozess, hält ihn an oder unterbricht ihn.|  
||<xref:System.Windows.Forms.LinkLabel>\-Steuerelement|Zeigt Text als Link an und löst ein Ereignis aus, wenn die Benutzer auf den Text klicken.  In der Regel stellt der Text einen Link zu einem anderen Fenster oder einer Website dar.|  
||<xref:System.Windows.Forms.NotifyIcon>\-Steuerelement|Im Statusbereich der Taskleiste wird ein Symbol für eine im Hintergrund ausgeführte Anwendung angezeigt.|  
||<xref:System.Windows.Forms.ToolStrip>\-Steuerelement|Erstellt Symbolleisten, die über das Aussehen und Verhalten von Microsoft Windows XP, Microsoft Office, Microsoft Internet Explorer oder über ein benutzerdefiniertes Aussehen und Verhalten und optional über Designs verfügen können und Überläufe sowie das Neuanordnen von Elementen zur Laufzeit unterstützen. **Note:**  Das <xref:System.Windows.Forms.ToolStrip>\-Steuerelement ersetzt das <xref:System.Windows.Forms.ToolBar>\-Steuerelement.|  
|Benutzerhilfe|<xref:System.Windows.Forms.HelpProvider>\-Komponente|Stellt eine Popup\- oder Onlinehilfe für Steuerelemente bereit.|  
||<xref:System.Windows.Forms.ToolTip>\-Komponente|Stellt ein kleines Popupfenster bereit, in dem eine kurze Beschreibung zum Verwendungszweck des Steuerelements angezeigt wird, wenn mit dem Mauszeiger auf das Steuerelement gezeigt wird.|  
|Gruppierung weiterer Steuerelemente|<xref:System.Windows.Forms.Panel>\-Steuerelement|Gruppiert einen Satz von Steuerelementen auf einem bildlauffähigen Rahmen ohne Bezeichnung.|  
||<xref:System.Windows.Forms.GroupBox>\-Steuerelement|Gruppiert einen Satz von Steuerelementen \(z. B. Optionsfelder\) auf einem nicht bildlauffähigen Rahmen mit Bezeichnung.|  
||<xref:System.Windows.Forms.TabControl>\-Steuerelement|Stellt eine Seite mit Registerkarten zum effizienten Organisieren von und Zugreifen auf gruppierte\(n\) Objekte\(n\) bereit.|  
||<xref:System.Windows.Forms.SplitContainer>\-Steuerelement|Stellt zwei durch eine verschiebbare Leiste unterteilte Bereiche bereit. **Note:**  Das <xref:System.Windows.Forms.SplitContainer>\-Steuerelement ersetzt das <xref:System.Windows.Forms.Splitter>\-Steuerelement.|  
||<xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement|Stellt einen Bereich dar, dessen Inhalt dynamisch in einem aus Zeilen und Spalten bestehenden Raster angeordnet wird.|  
||<xref:System.Windows.Forms.FlowLayoutPanel>\-Steuerelement|Stellt einen Bereich dar, dessen Inhalt auf dynamische Weise horizontal oder vertikal angeordnet wird.|  
|Audio|<xref:System.Media.SoundPlayer>\-Steuerelement|Spielt Sounddateien im WAV\-Format ab.  Sounds können asynchron geladen oder abgespielt werden.|  
  
## Ersetzte Steuerelemente und Komponenten nach Funktion gegliedert  
  
|Funktion|Ersetztes Steuerelement|Empfohlene Ersetzung|  
|--------------|-----------------------------|--------------------------|  
|Datenanzeige|<xref:System.Windows.Forms.DataGrid>|<xref:System.Windows.Forms.DataGridView>|  
|Informationsanzeige \(schreibgeschützte Steuerelemente\)|<xref:System.Windows.Forms.StatusBar>|<xref:System.Windows.Forms.StatusStrip>|  
|Menüsteuerelemente|<xref:System.Windows.Forms.ContextMenu>|<xref:System.Windows.Forms.ContextMenuStrip>|  
||<xref:System.Windows.Forms.MainMenu>|<xref:System.Windows.Forms.MenuStrip>|  
|Befehle|<xref:System.Windows.Forms.ToolBar>|<xref:System.Windows.Forms.ToolStrip>|  
||<xref:System.Windows.Forms.StatusBar>|<xref:System.Windows.Forms.StatusStrip>|  
|Formularlayout|<xref:System.Windows.Forms.Splitter>|<xref:System.Windows.Forms.SplitContainer>|  
  
## Siehe auch  
 [Steuerelemente für Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)   
 [Entwickeln benutzerdefinierter Windows Forms\-Steuerelemente mit .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)