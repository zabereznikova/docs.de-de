---
title: "Architektur des DataGridView-Steuerelements (Windows Forms) | Microsoft Docs"
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
  - "DataGridView-Steuerelement [Windows Forms], Architektur"
ms.assetid: 1c6cabf0-02ee-4bbc-9574-b54bb7f5b19e
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Architektur des DataGridView-Steuerelements (Windows Forms)
Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement und seine verwandten Klassen wurden als flexibles, erweiterbares System zur Anzeige und Bearbeitung von Tabellendaten entwickelt.  Sämtliche Klassen sind im <xref:System.Windows.Forms?displayProperty=fullName>\-Namespace enthalten und verfügen über das Präfix "DataGridView" in ihrem Namen.  
  
## Architekturelemente  
 Die primären <xref:System.Windows.Forms.DataGridView>\-Assistentenklassen werden von <xref:System.Windows.Forms.DataGridViewElement> abgeleitet.  Das folgende Objektmodell veranschaulicht die Vererbungshierarchie des <xref:System.Windows.Forms.DataGridViewElement>.  
  
 ![DataGridViewElement&#45;Objektmodell](../../../../docs/framework/winforms/controls/media/datagridviewelement.png "DataGridViewElement")  
DataGridViewElement\-Objektmodell  
  
 Die <xref:System.Windows.Forms.DataGridViewElement>\-Klasse stellt einen Verweis auf das übergeordnete <xref:System.Windows.Forms.DataGridView>\-Steuerelement bereit und verfügt über die <xref:System.Windows.Forms.DataGridViewElement.State%2A>\-Eigenschaft mit einem Wert, der eine Kombination der Werte aus der <xref:System.Windows.Forms.DataGridViewElementStates>\-Enumeration darstellt.  
  
 In den folgenden Abschnitten werden die <xref:System.Windows.Forms.DataGridView>\-Assistentenklassen ausführlicher beschrieben.  
  
### DataGridViewElementStates  
 Die <xref:System.Windows.Forms.DataGridViewElementStates>\-Enumeration verfügt über folgende Werte.  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates>  
  
 Die Werte dieser Enumeration können mit bitweisen logischen Operatoren kombiniert werden, sodass die <xref:System.Windows.Forms.DataGridViewElement.State%2A>\-Eigenschaft mehrere Zustände gleichzeitig wiedergeben kann.  Beispielsweise kann <xref:System.Windows.Forms.DataGridViewElement> gleichzeitig <xref:System.Windows.Forms.DataGridViewElementStates>, <xref:System.Windows.Forms.DataGridViewElementStates> und <xref:System.Windows.Forms.DataGridViewElementStates> entsprechen.  
  
### Zellen und Bänder  
 Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement umfasst zwei grundlegende Objekttypen: Zellen und Bänder.  Alle Zellen werden von der <xref:System.Windows.Forms.DataGridViewCell>\-Basisklasse abgeleitet.  Die beiden Bandtypen <xref:System.Windows.Forms.DataGridViewColumn> und <xref:System.Windows.Forms.DataGridViewRow> werden von der <xref:System.Windows.Forms.DataGridViewBand>\-Basisklasse abgeleitet.  
  
 Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement wirkt mit mehreren Klassen, am häufigsten jedoch mit <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn> und <xref:System.Windows.Forms.DataGridViewRow> zusammen.  
  
### DataGridViewCell  
 Die Zelle stellt die grundlegende Interaktionseinheit für <xref:System.Windows.Forms.DataGridView> dar.  Die Anzeige beruht auf Zellen, und auch für die Dateneingabe werden häufig Zellen verwendet.  Für den Zugriff auf Zellen verwenden Sie die <xref:System.Windows.Forms.DataGridViewRow.Cells%2A>\-Auflistung der <xref:System.Windows.Forms.DataGridViewRow>\-Klasse und für den Zugriff auf ausgewählte Zellen die <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>\-Auflistung des <xref:System.Windows.Forms.DataGridView>\-Steuerelements.  Das folgende Objektmodell veranschaulicht diese Verwendungsmöglichkeit und stellt die Vererbungshierarchie des <xref:System.Windows.Forms.DataGridViewCell> dar.  
  
 ![DataGridViewCell&#45;Objektmodell](../../../../docs/framework/winforms/controls/media/datagridviewcell.png "DataGridViewCell")  
DataGridViewCell\-Objektmodell  
  
 Der Typ <xref:System.Windows.Forms.DataGridViewCell> ist eine abstrakte Basisklasse, von der alle Zellentypen abgeleitet werden.  <xref:System.Windows.Forms.DataGridViewCell> und die zugehörigen abgeleiteten Typen sind keine Windows Forms\-Steuerelemente, einige Typen fungieren jedoch als Host für Windows Forms\-Steuerelemente.  Jede von einer Zelle unterstützte Bearbeitungsfunktion wird üblicherweise von einem gehosteten Steuerelement behandelt.  
  
 <xref:System.Windows.Forms.DataGridViewCell>\-Objekte sind nicht in der Lage, ihre Darstellungs\- und Zeichenfeatures auf dieselbe Weise wie Windows Forms\-Steuerelemente zu steuern.  Stattdessen ist <xref:System.Windows.Forms.DataGridView> für die Darstellung der <xref:System.Windows.Forms.DataGridViewCell>\-Objekte zuständig.  Durch die Interaktion mit den Eigenschaften und Ereignissen des <xref:System.Windows.Forms.DataGridView>\-Steuerelements können Sie die Darstellung und das Verhalten von Zellen entscheidend beeinflussen.  Wenn Sie spezielle Anpassungen vornehmen möchten, die über die Fähigkeiten des <xref:System.Windows.Forms.DataGridView>\-Steuerelements hinausgehen, können Sie eine eigene Klasse implementieren, die von <xref:System.Windows.Forms.DataGridViewCell> oder einer der untergeordneten Klassen abgeleitet wird.  
  
 Die folgende Liste enthält die von <xref:System.Windows.Forms.DataGridViewCell> abgeleiteten Klassen:  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewButtonCell>  
  
-   <xref:System.Windows.Forms.DataGridViewLinkCell>  
  
-   <xref:System.Windows.Forms.DataGridViewCheckBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewImageCell>  
  
-   <xref:System.Windows.Forms.DataGridViewHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewRowHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewColumnHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewTopLeftHeaderCell>  
  
-   Benutzerdefinierte Zellentypen  
  
### DataGridViewColumn  
 Das Schema des an das <xref:System.Windows.Forms.DataGridView>\-Steuerelement angefügten Datenspeichers wird in den Spalten des <xref:System.Windows.Forms.DataGridView>\-Steuerelements angegeben.  Für den Zugriff auf die Spalten des <xref:System.Windows.Forms.DataGridView>\-Steuerelements verwenden Sie die <xref:System.Windows.Forms.DataGridView.Columns%2A>\-Auflistung.  Für den Zugriff auf ausgewählte Spalten verwenden Sie die <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>\-Auflistung.  Das folgende Objektmodell veranschaulicht diese Verwendungsmöglichkeit und stellt die Vererbungshierarchie des <xref:System.Windows.Forms.DataGridViewColumn> dar.  
  
 ![DataGridViewColumn&#45;Objektmodell](../../../../docs/framework/winforms/controls/media/datagridviewcolumn.png "DataGridViewColumn")  
DataGridViewColumn\-Objektmodell  
  
 Einige der wichtigsten Zellentypen verfügen über entsprechende Spaltentypen.  Diese werden von der <xref:System.Windows.Forms.DataGridViewColumn>\-Basisklasse abgeleitet.  
  
 Die folgende Liste enthält die von <xref:System.Windows.Forms.DataGridViewColumn> abgeleiteten Klassen:  
  
-   <xref:System.Windows.Forms.DataGridViewButtonColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewImageColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewLinkColumn>  
  
-   Benutzerdefinierte Spaltentypen  
  
### DataGridView\-Bearbeitungssteuerelemente  
 Zellen, die erweiterte Bearbeitungsfunktionen unterstützen, verwenden normalerweise ein von einem Windows Forms\-Steuerelement abgeleitetes, gehostetes Steuerelement.  Von diesen Steuerelementen wird auch die <xref:System.Windows.Forms.IDataGridViewEditingControl>\-Schnittstelle implementiert.  Das folgende Objektmodell veranschaulicht die Verwendung dieser Steuerelemente.  
  
 ![Objektmodell des DataGridView&#45;Bearbeitungssteuerelements](../../../../docs/framework/winforms/controls/media/datagridviewediting.png "DataGridViewEditing")  
Objektmodell für das DataGridView\-Bearbeitungssteuerelement  
  
 Die folgenden Bearbeitungssteuerelemente werden mit dem <xref:System.Windows.Forms.DataGridView>\-Steuerelement bereitgestellt:  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>  
  
 Informationen zum Erstellen eigener Bearbeitungssteuerelemente finden Sie unter [Gewusst wie: Hosten von Steuerelementen in DataGridView\-Zellen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md).  
  
 In der folgenden Tabelle werden die Beziehungen zwischen Zellentypen, Spaltentypen und Bearbeitungssteuerelementen veranschaulicht.  
  
|Zellentyp|Gehostetes Steuerelement|Spaltentyp|  
|---------------|------------------------------|----------------|  
|<xref:System.Windows.Forms.DataGridViewButtonCell>|nicht verfügbar|<xref:System.Windows.Forms.DataGridViewButtonColumn>|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxCell>|nicht verfügbar|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewComboBoxCell>|<xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewImageCell>|nicht verfügbar|<xref:System.Windows.Forms.DataGridViewImageColumn>|  
|<xref:System.Windows.Forms.DataGridViewLinkCell>|nicht verfügbar|<xref:System.Windows.Forms.DataGridViewLinkColumn>|  
|<xref:System.Windows.Forms.DataGridViewTextBoxCell>|<xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|  
  
### DataGridViewRow  
 Durch die <xref:System.Windows.Forms.DataGridViewRow>\-Klasse werden die Datenfelder eines Datensatzes aus dem Datenspeicher angezeigt, an den das <xref:System.Windows.Forms.DataGridView>\-Steuerelement angefügt ist.  Für den Zugriff auf die Zeilen des <xref:System.Windows.Forms.DataGridView>\-Steuerelements verwenden Sie die <xref:System.Windows.Forms.DataGridView.Rows%2A>\-Auflistung.  Für den Zugriff auf ausgewählte Zeilen verwenden Sie die <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>\-Auflistung.  Das folgende Objektmodell veranschaulicht diese Verwendungsmöglichkeit und stellt die Vererbungshierarchie des <xref:System.Windows.Forms.DataGridViewRow> dar.  
  
 ![DataGridViewRow&#45;Objektmodell](../../../../docs/framework/winforms/controls/media/datagridviewrow.png "DataGridViewRow")  
DataGridViewRow\-Objektmodell  
  
 Sie können eigene Typen von der <xref:System.Windows.Forms.DataGridViewRow>\-Klasse ableiten, obwohl dies normalerweise nicht notwendig ist.  Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement verfügt über mehrere zeilenbezogene Ereignisse und Eigenschaften zum Anpassen des Verhaltens seiner <xref:System.Windows.Forms.DataGridViewRow>\-Objekte.  
  
 Wenn Sie für das <xref:System.Windows.Forms.DataGridView>\-Steuerelement die <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A>\-Eigenschaft aktivieren, wird an letzter Position eine spezielle Zeile zum Hinzufügen neuer Zeilen eingeblendet.  Diese Zeile gehört zwar zur <xref:System.Windows.Forms.DataGridView.Rows%2A>\-Auflistung, verfügt jedoch über spezielle Funktionen, die u. U. beachtet werden müssen.  Weitere Informationen finden Sie unter [Verwenden der Zeile für neue Datensätze im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md).  
  
## Siehe auch  
 [Übersicht über das DataGridView\-Steuerelement](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)   
 [Anpassen des DataGridView\-Steuerelements von Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)   
 [Verwenden der Zeile für neue Datensätze im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)