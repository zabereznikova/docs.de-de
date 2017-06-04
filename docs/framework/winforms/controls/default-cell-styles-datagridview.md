---
title: "Gewusst wie: Festlegen von standardm&#228;&#223;igen Zellenstilen und Datenformaten f&#252;r das DataGridView-Steuerelement in Windows Forms mithilfe des Designers | Microsoft Docs"
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
  - "Zellen, Einstellen von Stilen"
  - "Daten [Windows Forms], Einstellen von Formaten"
  - "Datenformate"
  - "DataGridView-Steuerelement [Windows Forms], Zellenstile"
ms.assetid: fc6da49f-8942-41da-b49f-b2afc38cc656
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Gewusst wie: Festlegen von standardm&#228;&#223;igen Zellenstilen und Datenformaten f&#252;r das DataGridView-Steuerelement in Windows Forms mithilfe des Designers
Mit dem <xref:System.Windows.Forms.DataGridView>\-Steuerelement können Sie standardmäßige Zellenstile und Zelldatenformate für das gesamte Steuerelement, für bestimmte Spalten, für Zeilen\- oder Spaltenheader und für abwechselnde Zeilen festlegen, um einen Ledger\-Effekt zu erzielen.  Standardstile, die für das gesamte Steuerelement festgelegt sind, werden von Standardstilen überschrieben, die für Spalten und abwechselnde Zeilen festgelegt sind.  Außerdem überschreiben Stile, die Sie in Code für einzelne Zeilen und Zellen festlegen, die Standardstile.  
  
 Weitere Informationen über Zellenstile finden Sie unter [Zellstile im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  Informationen über das Festlegen von Stilen für abwechselnde Zeilen finden Sie unter [Gewusst wie: Festlegen von abwechselnden Zeilenstilen für das Windows Forms\-Steuerelement DataGridView mithilfe des Designers](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md).  
  
 Sie können Stile auch mithilfe der <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>\-Eigenschaft festlegen. Auf diese Weise werden die Stile auf alle Zeilen angewendet, die dem Steuerelement hinzugefügt werden.  Weitere Informationen über die Zeilenvorlage finden Sie unter [Gewusst wie: Verwenden der Zeilenvorlage zum Anpassen von Zeilen im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/use-the-row-template-to-customize-rows-in-the-datagrid.md).  
  
 Für die folgenden Prozeduren ist ein **Windows\-Anwendung**\-Projekt mit einem Formular erforderlich, das ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement enthält.  Weitere Informationen zum Einrichten eines solchen Projekts finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa) und [Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So legen Sie Standardstile für alle Zellen im Steuerelement fest  
  
1.  Wählen Sie das <xref:System.Windows.Forms.DataGridView>\-Steuerelement im Designer aus.  
  
2.  Klicken Sie im **Eigenschaftenfenster** auf die Schaltfläche mit den Auslassungszeichen \(![VisualStudioEllipsesButton&#45;Bildschirmabbildung](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) neben der Eigenschaft <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> oder <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>.  Das Dialogfeld **CellStyle\-Generator** wird angezeigt.  
  
3.  Definieren Sie den Stil, indem Sie die Eigenschaften festlegen und Ihre Auswahl im Bereich **Vorschau** bestätigen.  
  
> [!NOTE]
>  Wenn visuelle Stile aktiviert sind, wird auf die Zeilen\- und Spaltenheader \(mit Ausnahme der <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>\) automatisch das aktuelle Design angewendet, das die Werte für die <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>\-Eigenschaft und die <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>\-Eigenschaft überschreibt.  
>   
>  Mit dem Designer können Sie Zellenstile für mehrere ausgewählte <xref:System.Windows.Forms.DataGridView>\-Steuerelemente festlegen, vorausgesetzt, sie verfügen über identische Werte für die Zellenstileigenschaft, die Sie ändern möchten.  Wenn einer der Zellenstile für diese Eigenschaft abweicht, ist das **Eigenschaftenfenster** des Dialogfelds **CellStyle\-Generator** leer.  
  
### So legen Sie Standardstile für Zellen in einzelnen Spalten fest  
  
1.  Klicken Sie im Designer mit der rechten Maustaste auf das <xref:System.Windows.Forms.DataGridView>\-Steuerelement, und wählen Sie **Spalten bearbeiten** aus.  
  
2.  Wählen Sie eine Spalte aus der Liste **Ausgewählte Spalten** aus.  
  
3.  Klicken Sie im Raster **Spalteneigenschaften** auf die Schaltfläche mit den Auslassungszeichen \(![VisualStudioEllipsesButton&#45;Bildschirmabbildung](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) neben der <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A>\-Eigenschaft.  Das Dialogfeld **CellStyle\-Generator** wird angezeigt.  
  
4.  Definieren Sie den Stil, indem Sie die Eigenschaften festlegen und Ihre Auswahl im Bereich **Vorschau** bestätigen.  
  
### So formatieren Sie Daten in Zellen  
  
1.  Zeigen Sie mit einer der voranstehenden Prozeduren ein Dialogfeld **CellStyle\-Generator** an, das zu einer standardmäßigen Zellenstileigenschaft gehört.  
  
2.  Klicken Sie im Dialogfeld **CellStyle\-Generator** auf die Schaltfläche mit den Auslassungszeichen \(![VisualStudioEllipsesButton&#45;Bildschirmabbildung](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) neben der <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A>\-Eigenschaft.  Das Dialogfeld **Formatierungszeichenfolge** wird angezeigt.  
  
3.  Wählen Sie einen Formattyp aus, und ändern Sie anschließend die Details des Typs \(z. B. die Anzahl der anzuzeigenden Dezimalstellen\), wobei Sie Ihre Auswahl mithilfe des Felds **Beispiel** bestätigen.  
  
4.  Wenn Sie das <xref:System.Windows.Forms.DataGridView>\-Steuerelement an eine Datenquelle binden, die voraussichtlich keine Werte enthält, füllen Sie das Textfeld **NULL\-Wert** aus.  Dieser Wert wird angezeigt, wenn der Zellenwert mit einem Nullverweis \(`Nothing` in Visual Basic\) oder <xref:System.DBNull.Value?displayProperty=fullName> identisch ist.  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewCellStyle>   
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A?displayProperty=fullName>   
 [Zellstile im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)   
 [Gewusst wie: Festlegen von abwechselnden Zeilenstilen für das Windows Forms\-Steuerelement DataGridView mithilfe des Designers](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md)   
 [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa)   
 [Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)