---
title: 'Gewusst wie: Formatieren des DataGrid-Steuerelements in Windows Forms'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], DataGrid control
- colors [Windows Forms], applying to DataGrid controls
- DataGrid control [Windows Forms], formatting
- columns [Windows Forms], formatting in DataGrid control
- DataGrid control [Windows Forms], default styles
- tables [Windows Forms], formatting in DataGrid control
- formatting [Windows Forms]
ms.assetid: a50fcc3b-8abf-47ec-9029-7f268af4ddb1
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8518fdcaca7ebed65d0923b9bc1fe1a6797b97c6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-format-the-windows-forms-datagrid-control"></a>Gewusst wie: Formatieren des DataGrid-Steuerelements in Windows Forms
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Verschiedene Farben für verschiedene Teile des Anwenden einer <xref:System.Windows.Forms.DataGrid> bestimmen können, stellen die Informationen in diesem einfacher zu lesen und zu interpretieren. Farbe kann in Zeilen und Spalten angewendet werden. Zeilen und Spalten können auch ausgeblendet oder angezeigt, die in Ihrem eigenen Ermessen.  
  
 Es gibt drei grundlegende Aspekte der Formatierung der <xref:System.Windows.Forms.DataGrid> Steuerelement. Sie können festlegen, dass Eigenschaften herstellen ein Standardformat, in dem Daten angezeigt werden. Auf dieser Basis können Sie dann die Möglichkeit anpassen, die bestimmte Tabellen zur Laufzeit angezeigt werden. Schließlich können Sie ändern, welche Spalten im Datenraster sowie die Farben angezeigt werden, und andere Formatierung aus, die angezeigt wird.  
  
 Als ersten Schritt bei der Formatierung eines Datenrasters können Sie die Eigenschaften der Festlegen der <xref:System.Windows.Forms.DataGrid> selbst. Diese Optionen Farbe und Format bilden eine Basis, von der Sie dann ändert sich je nach den Datentabellen und Spalten angezeigt, können.  
  
### <a name="to-establish-a-default-style-for-the-datagrid-control"></a>Herstellen einer Standardformat für das DataGrid-Steuerelement  
  
1.  Legen Sie die folgenden Eigenschaften nach Bedarf:  
  
    |Eigenschaft|Beschreibung|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|Die <xref:System.Windows.Forms.DataGrid.BackColor%2A> Eigenschaft definiert die Farbe der geraden Zeilen des Rasters. Beim Festlegen der <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> -Eigenschaft auf eine andere Farbe, jeder anderen Zeile in dieser neuen Farbe festgelegt ist (Zeilen 1, 3, 5 und So weiter).|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|Die Hintergrundfarbe der geraden Zeilen des Rasters (Zeilen 0, 2, 4, 6 usw.).|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|Während der <xref:System.Windows.Forms.DataGrid.BackColor%2A> und <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> Eigenschaften bestimmt die Farbe der Zeilen im Raster die <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> Eigenschaft bestimmt die Farbe der Datenblattzeilen, diese Vorgehensweise nur sichtbar ist, wenn das Raster unten Bildlauf durchgeführt wird, oder wenn nur wenige Zeilen enthält das Raster.|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|Die Rahmenart des Datenblatts, eines der <xref:System.Windows.Forms.BorderStyle> Enumerationswerte.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|Farbe des Hintergrunds des Datenblatts fensterbeschriftung unmittelbar oberhalb des Rasters angezeigt wird.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|Die Schriftart der Beschriftung oben im Raster.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|Die Hintergrundfarbe der Beschriftung des Datenblatts.|  
    |<xref:System.Windows.Forms.Control.Font%2A>|Die Schriftart verwendet, um den Text im Raster anzuzeigen.|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|Die Farbe der Schriftart an, durch die Daten in den Zeilen des Datenblatts angezeigt.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|Die Farbe der Datenblattlinien des Datenblatts.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|Der Stil der Linien zwischen den Zellen des Rasters, eines der <xref:System.Windows.Forms.DataGridLineStyle> Enumerationswerte.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|Die Hintergrundfarbe von Zeilen- und Spaltenüberschriften.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|Die für die Spaltenüberschriften verwendete Schriftart.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|Die Vordergrundfarbe der Spaltenköpfe des Datenblatts, z. B. die Spaltenkopftexte und die Plus/Minus-Symbole (zum Erweitern von Zeilen, wenn mehrere verknüpfte Tabellen angezeigt werden).|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|Die Farbe des Texts für alle Verknüpfungen im Datenraster, einschließlich Links zu untergeordneten Tabellen, die Namen der Geschäftsbeziehung usw.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|In einer untergeordneten Tabelle ist dies die Hintergrundfarbe der übergeordneten Zeilen.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|In einer untergeordneten Tabelle ist dies die Vordergrundfarbe der übergeordneten Zeilen.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|Bestimmt, ob die Tabellen- und Spaltennamen in der übergeordneten Zeile, von der angezeigt werden die <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> Enumeration.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|Die Standardbreite der Spalten des Rasters in Pixel. Legen Sie diese Eigenschaft vor dem Zurücksetzen der <xref:System.Windows.Forms.DataGrid.DataSource%2A> und <xref:System.Windows.Forms.DataGrid.DataMember%2A> Eigenschaften (entweder einzeln oder über die <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Methode), oder die Eigenschaft hat keine Auswirkung.<br /><br /> Die Eigenschaft kann nicht auf einen Wert kleiner als 0 festgelegt werden.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|Die Zeilenhöhe (in Pixel) von Zeilen im Raster. Legen Sie diese Eigenschaft vor dem Zurücksetzen der <xref:System.Windows.Forms.DataGrid.DataSource%2A> und <xref:System.Windows.Forms.DataGrid.DataMember%2A> Eigenschaften (entweder einzeln oder über die <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Methode), oder die Eigenschaft hat keine Auswirkung.<br /><br /> Die Eigenschaft kann nicht auf einen Wert kleiner als 0 festgelegt werden.|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|Die Breite der Zeilenheader des Rasters.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|Wenn eine Zeile oder Zelle ausgewählt ist, ist dies die Farbe des Hintergrunds.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|Wenn eine Zeile oder Zelle ausgewählt ist, ist dies die Vordergrundfarbe.|  
  
    > [!NOTE]
    >  Bedenken Sie, wenn die Farben der Steuerelemente anpassen, dass es möglich ist, das Steuerelement zugegriffen werden kann aufgrund einer schlechten Farbauswahl (z. B. "Rot" und "Grün") ist. Verwenden Sie die Farben auf die **Systemfarben** Palette, um dieses Problem zu vermeiden.  
  
     Die folgenden Verfahren gelten für das Formular verfügt über eine <xref:System.Windows.Forms.DataGrid> -Steuerelements an eine Datentabelle gebunden. Weitere Informationen finden Sie unter [Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).  
  
### <a name="to-set-the-table-and-column-style-of-a-data-table-programmatically"></a>So legen Sie den Stil für Tabellen und Spalten einer Datentabelle programmgesteuert fest  
  
1.  Erstellen einer neuen Tabellenformatvorlage, und legen Sie die Eigenschaften.  
  
2.  Erstellen Sie ein Spaltenformat, und legen Sie dessen Eigenschaften.  
  
3.  Fügen Sie das Spaltenformat Auflistung Spaltenformate das Tabellenformat an.  
  
4.  Das Datenraster Tabellenformate der Auflistung das Tabellenformat hinzugefügt.  
  
5.  Im folgenden Beispiel erstellen Sie eine Instanz eines neuen <xref:System.Windows.Forms.DataGridTableStyle> und legen Sie dessen <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> Eigenschaft.  
  
6.  Erstellen Sie eine neue Instanz der eine **GridColumnStyle** und legen Sie dessen **%MappingName** (und einige andere Eigenschaften Layout und die Anzeige).  
  
7.  Wiederholen Sie die Schritte 2 bis 6 für jede Spalte-Formatvorlage, die Sie erstellen möchten.  
  
     Im folgende Beispiel wird veranschaulicht, wie eine <xref:System.Windows.Forms.DataGridTextBoxColumn> wird erstellt, da ein Name ist in der Spalte angezeigt werden. Darüber hinaus fügen Sie das Spaltenformat der <xref:System.Windows.Forms.GridColumnStylesCollection> des Tabellenformats und das Tabellenformat, das Hinzufügen der <xref:System.Windows.Forms.GridTableStylesCollection> des Datenblatts.  
  
    ```vb  
    Private Sub CreateAuthorFirstNameColumn()  
       ' Add a GridTableStyle and set the MappingName   
       ' to the name of the DataTable.  
       Dim TSAuthors As New DataGridTableStyle()  
       TSAuthors.MappingName = "Authors"  
  
       ' Add a GridColumnStyle and set the MappingName   
       ' to the name of a DataColumn in the DataTable.   
       ' Set the HeaderText and Width properties.   
       Dim TCFirstName As New DataGridTextBoxColumn()  
       TCFirstName.MappingName = "AV_FName"  
       TCFirstName.HeaderText = "First Name"  
       TCFirstName.Width = 75  
       TSAuthors.GridColumnStyles.Add(TCFirstName)  
  
       ' Add the DataGridTableStyle instance to   
       ' the GridTableStylesCollection.   
       myDataGrid.TableStyles.Add(TSAuthors)  
    End Sub  
    ```  
  
    ```csharp  
    private void addCustomDataTableStyle()  
    {  
       // Add a GridTableStyle and set the MappingName   
       // to the name of the DataTable.  
       DataGridTableStyle TSAuthors = new DataGridTableStyle();  
       TSAuthors.MappingName = "Authors";  
  
       // Add a GridColumnStyle and set the MappingName   
       // to the name of a DataColumn in the DataTable.   
       // Set the HeaderText and Width properties.   
       DataGridColumnStyle TCFirstName = new DataGridTextBoxColumn();  
       TCFirstName.MappingName = " AV_FName";  
       TCFirstName.HeaderText = "First Name";  
       TCFirstName.Width = 75;  
       TSAuthors.GridColumnStyles.Add(TCFirstName);  
  
       // Add the DataGridTableStyle instance to   
       // the GridTableStylesCollection.   
       dataGrid1.TableStyles.Add(TSAuthors);  
    }  
    ```  
  
    ```cpp  
    private:  
       void addCustomDataTableStyle()  
       {  
          // Add a GridTableStyle and set the MappingName   
          // to the name of the DataTable.  
          DataGridTableStyle^ TSAuthors = new DataGridTableStyle();  
          TSAuthors->MappingName = "Authors";  
  
          // Add a GridColumnStyle and set the MappingName   
          // to the name of a DataColumn in the DataTable.   
          // Set the HeaderText and Width properties.   
          DataGridColumnStyle^ TCFirstName = gcnew DataGridTextBoxColumn();  
          TCFirstName->MappingName = "AV_FName";  
          TCFirstName->HeaderText = "First Name";  
          TCFirstName->Width = 75;  
          TSAuthors->GridColumnStyles->Add(TCFirstName);  
  
          // Add the DataGridTableStyle instance to   
          // the GridTableStylesCollection.   
          dataGrid1->TableStyles->Add(TSAuthors);  
       }  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.GridTableStylesCollection>  
 <xref:System.Windows.Forms.GridColumnStylesCollection>  
 <xref:System.Windows.Forms.DataGrid>  
 [Gewusst wie: Löschen oder Ausblenden von Spalten aus dem DataGrid-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)  
 [DataGrid-Steuerelement](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)
