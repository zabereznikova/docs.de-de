---
title: "Gewusst wie: Formatieren des DataGrid-Steuerelements in Windows Forms mithilfe des Designers | Microsoft Docs"
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
  - "Farben, Anwenden auf DataGrid-Steuerelemente"
  - "Spalten [Windows Forms], DataGrid-Steuerelemente"
  - "DataGrid-Steuerelement [Windows Forms], Standardformate"
  - "DataGrid-Steuerelement [Windows Forms], Formatierung"
  - "Formatieren [Windows Forms]"
  - "Tabellen [Windows Forms], Formatieren im DataGrid-Steuerelement"
ms.assetid: 533b9814-6124-49dc-9fda-085f1502609f
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Formatieren des DataGrid-Steuerelements in Windows Forms mithilfe des Designers
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.DataGridView>\-Steuerelement das <xref:System.Windows.Forms.DataGrid>\-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>\-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView\-Steuerelement und dem DataGrid\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Durch die Anwendung verschiedener Farben auf die unterschiedlichen Teile eines <xref:System.Windows.Forms.DataGrid>\-Steuerelements können Sie die Lesbarkeit und die Verständlichkeit der darin enthaltenen Informationen verbessern.  Farben können sowohl auf Zeilen als auch auf Spalten angewendet werden.  Je nach Bedarf können Zeilen und Spalten auch ausgeblendet oder angezeigt werden.  
  
 Die Formatierung des <xref:System.Windows.Forms.DataGrid>\-Steuerelements umfasst drei grundlegende Aspekte:  
  
-   Mithilfe von Eigenschaften können Sie ein Standardformat für die Datenanzeige einrichten.  
  
-   Auf dieser Basis können Sie anschließend anpassen, wie bestimmte Tabellen zur Laufzeit angezeigt werden.  
  
-   Schließlich können Sie auch festlegen, welche Spalten im Datenblatt angezeigt und welche Farben und Formatierungen dabei verwendet werden.  
  
 Sie können mit der Formatierung des Datenblatts beginnen, indem Sie die Eigenschaften von <xref:System.Windows.Forms.DataGrid> selbst festlegen.  Auf der Grundlage dieser Festlegungen für Farben und Formate können Sie dann je nach den angezeigten Datentabellen und \-spalten weitere Anpassungen vornehmen.  
  
 Für das folgende Verfahren wird ein Projekt vom Typ **Windows\-Anwendung** mit einem Formular benötigt, das ein <xref:System.Windows.Forms.DataGrid>\-Steuerelement enthält.  Weitere Informationen zum Einrichten eines solchen Projekts finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa) und [Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  In [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)] ist das <xref:System.Windows.Forms.DataGrid>\-Steuerelement in der **Toolbox** standardmäßig nicht enthalten.  Weitere Informationen finden Sie unter [How to: Add Items to the Toolbox](http://msdn.microsoft.com/de-de/458e119e-17fe-450b-b889-e31c128bd7e0).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So richten Sie ein Standardformat für das DataGrid\-Steuerelement ein  
  
1.  Wählen Sie das <xref:System.Windows.Forms.DataGrid>\-Steuerelement aus.  
  
2.  Legen Sie im **Eigenschaftenfenster** ggf. die folgenden Eigenschaften fest.  
  
    |Property|Beschreibung|  
    |--------------|------------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|Die `BackColor`\-Eigenschaft legt die Farbe der Zeilen mit geraden Zeilennummern fest.  Wenn Sie für die <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>\-Eigenschaft eine andere Farbe festlegen, werden alle anderen Zeilen in dieser neuen Farbe angezeigt \(Zeilen 1, 3, 5 usw.\).|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|Die Hintergrundfarbe der Rasterzeilen mit geraden Zeilennummern \(Zeilen 0, 2, 4, 6 usw.\).|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|Während die <xref:System.Windows.Forms.DataGrid.BackColor%2A>\-Eigenschaft und die <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>\-Eigenschaft die Farbe der Datenblattzeilen bestimmen, wird durch die <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>\-Eigenschaft die Farbe des Bereichs außerhalb der Zeilen festgelegt, der nur sichtbar ist, wenn Sie einen Bildlauf zum unteren Ende des Datenblatts durchführen oder wenn das Datenblatt nur wenige Zeilen enthält.|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|Das Rahmenformat des Rasters \(einer der <xref:System.Windows.Forms.BorderStyle>\-Enumerationswerte\).|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|Die Hintergrundfarbe der Fensterbeschriftung des Datenblatts, die unmittelbar über dem Datenblatt angezeigt wird.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|Die Schriftart, die für die Fensterbeschriftung über dem Raster verwendet wird.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|Die Hintergrundfarbe der Fensterbeschriftung des Rasters.|  
    |<xref:System.Windows.Forms.Control.Font%2A>|Die zur Anzeige des im Raster enthaltenen Textes verwendete Schriftart.|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|Die Farbe der Schrift, in der die Daten in den Zeilen des Datenblatts angezeigt werden.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|Die Farbe der Rasterzeilen im Datenblatt.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|Die Art der Linien zwischen den Zellen des Rasters, d. h. einer der <xref:System.Windows.Forms.DataGridLineStyle>\-Enumerationswerte.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|Die Hintergrundfarbe von Zeilen\- und Spaltenüberschriften.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|Die für Spaltenüberschriften verwendete Schriftart.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|Die Vordergrundfarbe der Spaltenüberschriften des Rasters, einschließlich des Spaltenüberschriftentextes und der Plus\/Minus\-Symbole zum Erweitern und Reduzieren von Zeilen, wenn mehrere zusammengehörige Tabellen angezeigt werden.|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|Die Textfarbe aller Links innerhalb des Datenblatts, einschließlich der Links zu untergeordneten Tabellen, dem Relationsnamen usw.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|Die Hintergrundfarbe der übergeordneten Zeilen in einer untergeordneten Tabelle.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|Die Vordergrundfarbe der übergeordneten Zeilen in einer untergeordneten Tabelle.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|Legt fest, ob die Tabellen\- und Spaltennamen in der übergeordneten Zeile angezeigt werden. Dazu wird die <xref:System.Windows.Forms.DataGridParentRowsLabelStyle>\-Enumeration verwendet.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|Die Standardbreite der Spalten des Rasters in Pixel.  Legen Sie diese Eigenschaft fest, bevor Sie die <xref:System.Windows.Forms.DataGrid.DataSource%2A>\-Eigenschaft und die <xref:System.Windows.Forms.DataGrid.DataMember%2A>\-Eigenschaft zurücksetzen \(entweder einzeln oder mit der <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>\-Methode\). Andernfalls kann die Eigenschaft nicht angewendet werden.<br /><br /> Für diese Eigenschaft kann kein geringerer Wert als 0 festgelegt werden.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|Die Höhe der Zeilen des Rasters in Pixel.  Legen Sie diese Eigenschaft fest, bevor Sie die <xref:System.Windows.Forms.DataGrid.DataSource%2A>\-Eigenschaft und die <xref:System.Windows.Forms.DataGrid.DataMember%2A>\-Eigenschaft zurücksetzen \(entweder einzeln oder mit der <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>\-Methode\). Andernfalls kann die Eigenschaft nicht angewendet werden.<br /><br /> Für diese Eigenschaft kann kein geringerer Wert als 0 festgelegt werden.|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|Die Breite der Zeilenüberschriften des Rasters.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|Diese Hintergrundfarbe wird beim Auswählen von Zeilen oder Zellen verwendet.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|Diese Vordergrundfarbe wird beim Auswählen von Zeilen oder Zellen verwendet.|  
  
    > [!NOTE]
    >  Wenn Sie Farben für die Steuerelemente anpassen, kann es vorkommen, dass diese nicht mehr aufgerufen werden können, weil nur eine geringe Anzahl von Farben zur Auswahl steht \(beispielsweise Rot und Grün\).  Sie können dieses Problem vermeiden, indem Sie die Farben aus der Palette **Systemfarben** verwenden.  
  
     Für das folgende Verfahren ist ein <xref:System.Windows.Forms.DataGrid>\-Steuerelement erforderlich, das an eine Datentabelle gebunden ist.  Weitere Informationen finden Sie unter [Gewusst wie: Binden des DataGrid\-Steuerelements in Windows Forms an eine Datenquelle](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).  
  
### So legen Sie das Tabellenformat und das Spaltenformat von Datentabellen zur Entwurfszeit fest  
  
1.  Wählen Sie im Formular das <xref:System.Windows.Forms.DataGrid>\-Steuerelement aus.  
  
2.  Wählen Sie im **Eigenschaftenfenster** die <xref:System.Windows.Forms.DataGrid.TableStyles%2A>\-Eigenschaft aus, und klicken Sie auf die Schaltfläche mit dem **Auslassungszeichen** \(![VisualStudioEllipsesButton&#45;Bildschirmabbildung](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\).  
  
3.  Klicken Sie im Dialogfeld **DataGridTableStyle\-Auflistungs\-Editor** auf **Hinzufügen**, um der Auflistung ein Tabellenformat hinzuzufügen.  
  
     Mit dem **DataGridTableStyle\-Auflistungs\-Editor** können Sie Tabellenformate hinzufügen und entfernen, Anzeige\- und Layouteigenschaften festlegen sowie den Zuordnungsnamen für die Tabellenformate festlegen.  
  
4.  Legen Sie die <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A>\-Eigenschaft auf den Zuordnungsnamen der einzelnen Tabellenformate fest.  
  
     Der Zuordnungsname wird verwendet, um anzugeben, welches Tabellenformat für welche Tabelle zu verwenden ist.  
  
5.  Wählen Sie im **DataGridTableStyle\-Auflistungs\-Editor** die <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A>\-Eigenschaft aus, und klicken Sie auf die Schaltfläche mit dem Auslassungszeichen \(![VisualStudioEllipsesButton&#45;Bildschirmabbildung](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\).  
  
6.  Fügen Sie dem erstellten Tabellenformat im Dialogfeld **DataGridColumnStyle\-Auflistungs\-Editor** Spaltenformate hinzu.  
  
     Im **DataGridColumnStyle\-Auflistungs\-Editor** können Sie Spaltenformate hinzufügen und entfernen, Anzeige\- und Layouteigenschaften sowie den Zuordnungsnamen und die Formatierungszeichenfolgen für die Datenspalten festlegen.  
  
    > [!NOTE]
    >  Weitere Informationen zu Formatierungszeichenfolgen finden Sie unter [Formatierung von Typen](../../../../docs/standard/base-types/formatting-types.md).  
  
## Siehe auch  
 <xref:System.Windows.Forms.GridTableStylesCollection>   
 <xref:System.Windows.Forms.GridColumnStylesCollection>   
 <xref:System.Windows.Forms.DataGrid>   
 [Gewusst wie: Löschen oder Ausblenden von Spalten aus dem DataGrid\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)   
 [DataGrid\-Steuerelement](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)