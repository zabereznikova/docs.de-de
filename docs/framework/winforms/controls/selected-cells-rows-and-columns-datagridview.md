---
title: "Gewusst wie: Abrufen der ausgew&#228;hlten Zellen, Zeilen und Spalten im DataGridView-Steuerelement in Windows Forms | Microsoft Docs"
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
  - "DataGridView-Steuerelement [Windows Forms], Abrufen der Auswahl"
  - "Abrufen der Auswahl, DataGridView-Steuerelement [Windows Forms]"
  - "Auswahl, DataGridView-Steuerelement [Windows Forms]"
ms.assetid: d93c4b5b-498e-49bc-982a-2229d61778e4
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Gewusst wie: Abrufen der ausgew&#228;hlten Zellen, Zeilen und Spalten im DataGridView-Steuerelement in Windows Forms
Sie können die ausgewählten Zellen, Zeilen oder Spalten aus einem <xref:System.Windows.Forms.DataGridView>\-Steuerelement abrufen, indem Sie die entsprechende Eigenschaft verwenden, nämlich <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> und <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>.  In den folgenden Prozeduren rufen Sie die ausgewählten Zellen ab und zeigen ihren Zeilen\- und Spaltenindex in einer <xref:System.Windows.Forms.MessageBox> an.  
  
### So rufen Sie die ausgewählten Zellen in einem DataGridView\-Steuerelement ab  
  
-   Verwenden Sie die <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>\-Eigenschaft.  
  
    > [!NOTE]
    >  Verwenden Sie die <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>\-Methode, um zu vermeiden, dass eine möglicherweise große Anzahl von Zellen angezeigt wird.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#10)]  
  
### So rufen Sie die ausgewählten Zeilen in einem DataGridView\-Steuerelement ab  
  
-   Verwenden Sie die <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>\-Eigenschaft.  Damit Benutzer Zeilen auswählen können, müssen Sie die <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>\-Eigenschaft auf <xref:System.Windows.Forms.DataGridViewSelectionMode> oder <xref:System.Windows.Forms.DataGridViewSelectionMode> festlegen.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#20)]  
  
### So rufen Sie die ausgewählten Spalten in einem DataGridView\-Steuerelement ab  
  
-   Verwenden Sie die <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>\-Eigenschaft.  Damit Benutzer Spalten auswählen können, müssen Sie die <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>\-Eigenschaft auf <xref:System.Windows.Forms.DataGridViewSelectionMode> oder <xref:System.Windows.Forms.DataGridViewSelectionMode> festlegen.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#30)]  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   <xref:System.Windows.Forms.Button>\-Steuerelemente mit dem Namen `selectedCellsButton`, `selectedRowsButton` und `selectedColumnsButton`, an die Handler für das <xref:System.Windows.Forms.Control.Click>\-Ereignis angefügt sind.  
  
-   Ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement mit dem Namen`dataGridView1` muss vorhanden sein.  
  
-   Verweise auf die Assemblys <xref:System?displayProperty=fullName>, <xref:System.Windows.Forms?displayProperty=fullName> und <xref:System.Text?displayProperty=fullName>.  
  
## Robuste Programmierung  
 Die in diesem Thema beschriebenen Auflistungen können nicht effektiv verwendet werden, wenn viele Zellen, Zeilen oder Spalten ausgewählt sind.  Weitere Informationen über die Verwendung dieser Auflistungen mit großen Datenmengen finden Sie unter [Empfohlene Vorgehensweisen für das Skalieren des DataGridView\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>   
 <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>   
 <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>   
 <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>   
 <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>   
 [Verwendung von Auswahl und Zwischenablage mit dem DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)