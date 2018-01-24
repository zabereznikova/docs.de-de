---
title: "Gewusst wie: Festlegen von standardmäßigen Zellenstilen und Datenformaten für das DataGridView-Steuerelement in Windows Forms mithilfe des Designers"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], setting styles
- data formats
- data [Windows Forms], setting formats
ms.assetid: fc6da49f-8942-41da-b49f-b2afc38cc656
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 65f876742526d13093a852e99f4e6a069c3fba47
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-set-default-cell-styles-and-data-formats-for-the-windows-forms-datagridview-control-using-the-designer"></a>Gewusst wie: Festlegen von standardmäßigen Zellenstilen und Datenformaten für das DataGridView-Steuerelement in Windows Forms mithilfe des Designers
Die <xref:System.Windows.Forms.DataGridView> -Steuerelement können Sie das Festlegen von standardmäßigen Zellenstilen und Datenformaten für das gesamte Steuerelement, für bestimmte Spalten, für die Zeilen- und Spaltenüberschriften und für abwechselnde Zeilen, um einen Ledger-Effekt zu erstellen von Zellen. Standardstile für das gesamte Steuerelement festgelegt werden standardmäßig überschrieben, die Stile für abwechselnde Zeilen und Spalten festgelegt. Darüber hinaus überschreiben die Stile, die Sie im Code für einzelne Zeilen und Zellen festlegen Standardstile.  
  
 Weitere Informationen zu Zellenstile, finden Sie unter [Zellstile im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md). Festlegen von Stilen für abwechselnde Zeilen finden Sie unter [Vorgehensweise: abwechselnden Zeilenstilen für das Windows Forms DataGridView-Steuerelement mithilfe des Designers festlegen](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md).  
  
 Sie können auch festlegen, Stile, die mit der <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> Eigenschaft, um zu beeinflussen, alle Zeilen, die dem Steuerelement hinzugefügt werden. Weitere Informationen über die Zeilenvorlage finden Sie unter [Vorgehensweise: Verwenden der Zeilenvorlage zum Anpassen von Zeilen im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/use-the-row-template-to-customize-rows-in-the-datagrid.md).  
  
 Erfordern die folgenden Verfahren eine **Windows-Anwendung** Projekt ein Formular mit einem <xref:System.Windows.Forms.DataGridView> Steuerelement. Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows-Anwendungsprojekts](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) und [wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-set-default-styles-for-all-cells-in-the-control"></a>Standardstile für alle Zellen im Steuerelement festlegen  
  
1.  Wählen Sie die <xref:System.Windows.Forms.DataGridView> Steuerelement im Designer.  
  
2.  In der **Eigenschaften** Fenster, klicken Sie auf die Schaltfläche mit den Auslassungspunkten (![von VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "VbEllipsesButton")) neben dem <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>, oder <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> Eigenschaft. Die **CellStyle-Generator** Dialogfeld wird angezeigt.  
  
3.  Definieren Sie durch Festlegen der Eigenschaften, die mit den Stil der **Vorschau** Bereich, um Ihre Auswahl zu bestätigen.  
  
> [!NOTE]
>  Wenn visuelle Stile aktiviert sind, die Zeilen- und Spaltenüberschriften (mit Ausnahme der <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>) sind durch das aktuelle Design automatisch formatiert überschreiben die <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> und <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> Eigenschaftswerte.  
>   
>  Zellenstile für mehrere ausgewählte einstellbaren <xref:System.Windows.Forms.DataGridView> steuert den Designer, jedoch nur verwenden, vorausgesetzt, Sie verfügen über identische Werte für die Zelle Style-Eigenschaft, die Sie ändern möchten. Wenn einer der Zellenstile für diese Eigenschaft unterscheiden sich die **Eigenschaften** -Fenster die **CellStyle-Generator** wird das Dialogfeld leer sein.  
  
### <a name="to-set-default-styles-for-cells-in-individual-columns"></a>Standardstile für Zellen in den einzelnen Spalten festlegen  
  
1.  Mit der rechten Maustaste die <xref:System.Windows.Forms.DataGridView> -Steuerelement in den Designer, und wählen Sie **Spalten bearbeiten**.  
  
2.  Wählen Sie eine Spalte aus der **ausgewählte Spalten** Liste.  
  
3.  In der **Spalteneigenschaften** Raster, klicken Sie auf die Schaltfläche mit den Auslassungspunkten (![von VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "VbEllipsesButton")) neben dem <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> Eigenschaft. Die **CellStyle-Generator** Dialogfeld wird angezeigt.  
  
4.  Definieren Sie durch Festlegen der Eigenschaften, die mit den Stil der **Vorschau** Bereich, um Ihre Auswahl zu bestätigen.  
  
### <a name="to-format-data-in-cells"></a>So formatieren Sie Daten in Zellen  
  
1.  Verwenden Sie eines der vorangehenden Verfahren zum Anzeigen einer **CellStyle-Generator** Dialogfeld im Zusammenhang mit einer Standard-Zelle-Style-Eigenschaft.  
  
2.  In der **CellStyle-Generator** Dialogfeld klicken Sie auf die Schaltfläche mit den Auslassungspunkten (![von VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "VbEllipsesButton")) neben dem <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> Diese Eigenschaft. Die **Formatzeichenfolge** Dialogfeld wird angezeigt.  
  
3.  Wählen Sie ein Format aus, und ändern Sie die Details des Typs (z. B. die Anzahl der anzuzeigenden Dezimalstellen), mit der **Beispiel** Feld, um Ihre Auswahl zu bestätigen.  
  
4.  Wenn Sie binden die <xref:System.Windows.Forms.DataGridView> Steuerelement mit einer Datenquelle, die vermutlich auf null-Werte enthalten, "füllen" der **Null-Wert** Textfeld. Dieser Wert wird angezeigt, wenn der Wert der Zelle gleich einem null-Verweis ist (`Nothing` in Visual Basic) oder <xref:System.DBNull.Value?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A?displayProperty=nameWithType>  
 [Zellstile im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [Gewusst wie: Festlegen von abwechselnden Zeilenstilen für das Windows Forms-Steuerelement DataGridView mithilfe des Designers](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md)  
 [Vorgehensweise: Erstellen eines Windows-Anwendungsprojekts](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
