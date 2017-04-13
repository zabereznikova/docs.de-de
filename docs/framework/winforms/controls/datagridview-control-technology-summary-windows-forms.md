---
title: "Zusammenfassung der DataGridView-Steuerelementtechnologie (Windows Forms) | Microsoft Docs"
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
  - "Datenblätter, Informationen über Datenblätter"
  - "DataGridView-Steuerelement [Windows Forms], Informationen über das DataGridView-Steuerelement"
ms.assetid: 094498c3-a126-4a3f-83fe-f69e96c7717b
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Zusammenfassung der DataGridView-Steuerelementtechnologie (Windows Forms)
In diesem Thema sind Informationen zum `DataGridView`\-Steuerelement und zu den Klassen zusammengefasst, die dessen Verwendung unterstützen.  
  
 Das Anzeigen von Daten in einem tabellarischen Format gehört wahrscheinlich zu den häufiger ausgeführten Aufgaben.  Das `DataGridView`\-Steuerelement bietet die komplette Lösung zur Präsentation von Daten in einem Raster.  
  
## Schlüsselwörter  
 DataGridView, BindingSource, Tabelle, Zelle, Datenbindung, virtueller Modus  
  
## Namespaces  
 <xref:System.Windows.Forms?displayProperty=fullName>  
  
 <xref:System.Data?displayProperty=fullName>  
  
## Verwandte Technologien  
 `BindingSource`  
  
## Hintergrundinformationen  
 Entwickler von Benutzeroberflächen sind oft darauf angewiesen, Benutzern Daten in tabellarischer Form zu präsentieren.  [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] bietet mehrere Möglichkeiten, Daten in einer Tabelle oder einem Raster anzuzeigen.  Das `DataGridView`\-Steuerelement stellt die neueste Weiterentwicklung dieser Technologie für Windows Forms\-Anwendungen dar.  
  
 Das `DataGridView`\-Steuerelement ist in der Lage, Datenzeilen aus einem Datenspeicher anzuzeigen.  Zahlreiche Datenspeichertypen werden unterstützt.  Der Datenspeicher kann einfache, nicht typisierte Daten, beispielsweise ein eindimensionales Array, oder typisierte Daten enthalten, beispielsweise <xref:System.Data.DataSet>.  Weitere Informationen finden Sie unter [Gewusst wie: Binden von Daten an das DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md).  
  
 Das `DataGridView`\-Steuerelement ist ein leistungsstarkes und flexibles Instrument zum Anzeigen von Daten in Tabellenform.  Sie können das Steuerelement zur Anzeige schreibgeschützter oder bearbeitbarer Ansichten mit kleineren bis sehr umfangreichen Datasets verwenden.  
  
 Sie können das `DataGridView`\-Steuerelement auf mehrere Weisen erweitern, um die Anwendungen mit benutzerdefiniertem Verhalten auszustatten.  Beispielsweise können Sie programmgesteuert eigene Sortieralgorithmen festlegen und eigene Zellentypen erstellen.  Die Darstellung des `DataGridView`\-Steuerelements lässt sich problemlos anpassen, indem Sie unter mehreren Eigenschaften auswählen.  Als Datenquelle können zahlreiche Datenspeichertypen genutzt werden. Alternativ kann das `DataGridView`\-Steuerelement auch ausgeführt werden, ohne dass eine Datenquelle daran gebunden ist.  
  
## Implementieren von DataGridView\-Klassen  
 Es gibt mehrere Möglichkeiten, die Erweiterbarkeitsfeatures des `DataGridView`\-Steuerelements optimal zu nutzen.  Viele Aspekte des Steuerelements können durch Ereignisse und Eigenschaften angepasst werden, für einige Anpassungen ist es jedoch erforderlich, neue Klassen zu erstellen, die von vorhandenen `DataGridView`\-Klassen abgeleitet sind.  
  
 Die am häufigsten verwendeten Basisklassen sind `DataGridViewCell` und `DataGridViewColumn`.  Sie können eigene Zellklassen von `DataGridViewCell` oder einer der untergeordneten Klassen ableiten.  Obwohl jeder Spalte ein beliebiger Zellentyp hinzugefügt werden kann, leiten Sie normalerweise auch eine Spaltenassistentenklasse von der `DataGridViewColumn`\-Klasse ab, in der standardmäßig die Zellen des benutzerdefinierten Zellentyps gehostet werden.  
  
 Sie können die `IDataGridViewEditingCell`\-Schnittstelle in der abgeleiteten Zellklasse implementieren, um einen Zellentyp zu erstellen, der Bearbeitungsfunktionen bietet, jedoch keine Steuerelemente im Bearbeitungsmodus hostet.  Zum Erstellen eines Steuerelements, das in einer Zelle im Bearbeitungsmodus gehostet werden kann, implementieren Sie die `IDataGridViewEditingControl`\-Schnittstelle in einer von <xref:System.Windows.Forms.Control> abgeleiteten Klasse.  
  
 Weitere Informationen finden Sie unter [Gewusst wie: Anpassen von Zellen und Spalten im DataGridView\-Steuerelement in Windows Forms durch Erweitern des Aussehens und Verhaltens](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md) und [Gewusst wie: Hosten von Steuerelementen in DataGridView\-Zellen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md).  
  
## DataGridView\-Klassen auf einen Blick  
 <xref:System.Windows.Forms>  
  
|Technologiebereich|Klassen\/Schnittstellen\/Konfigurationselemente|  
|------------------------|-----------------------------------------------------|  
|Datenbindung|<xref:System.Windows.Forms.BindingSource>|  
|Datenpräsentation|<xref:System.Windows.Forms.DataGridView><br /><br /> <xref:System.Windows.Forms.DataGridViewCell> und abgeleitete Klassen<br /><br /> <xref:System.Windows.Forms.DataGridViewRow> und abgeleitete Klassen<br /><br /> <xref:System.Windows.Forms.DataGridViewColumn> und abgeleitete Klassen<br /><br /> <xref:System.Windows.Forms.DataGridViewCellStyle>|  
|Erweiterbarkeit von <xref:System.Windows.Forms.DataGridView>|<xref:System.Windows.Forms.DataGridViewCell> und abgeleitete Klassen<br /><br /> <xref:System.Windows.Forms.DataGridViewColumn> und abgeleitete Klassen<br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingCell><br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingControl>|  
  
## Neues  
 Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement ist als komplette Lösung für die Anzeige von Tabellendaten mit Windows Forms konzipiert.  Beim Entwickeln neuer Anwendungen sollten Sie dem <xref:System.Windows.Forms.DataGridView>\-Steuerelement Vorzug vor anderen Lösungen geben, beispielsweise vor <xref:System.Windows.Forms.DataGrid>.  Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView\-Steuerelement und dem DataGrid\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement kann unmittelbar mit der <xref:System.Windows.Forms.BindingSource>\-Komponente zusammenwirken.  Diese Komponente ist als primäre Datenquelle für Formulare ausgelegt.  Diese Komponente kann die Interaktion zwischen einem <xref:System.Windows.Forms.DataGridView>\-Steuerelement und seiner Datenquelle unabhängig vom Typ der Datenquelle verwalten.  
  
## Siehe auch  
 [Übersicht über das DataGridView\-Steuerelement](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)   
 [Architektur des DataGridView\-Steuerelements](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)   
 [Schützen von Verbindungsinformationen](../../../../docs/framework/data/adonet/protecting-connection-information.md)