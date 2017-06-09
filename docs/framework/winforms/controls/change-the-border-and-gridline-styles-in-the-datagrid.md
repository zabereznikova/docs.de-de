---
title: "Gewusst wie: &#196;ndern des Rahmen- und Rasterlinienstils im DataGridView-Steuerelement in Windows Forms | Microsoft Docs"
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
  - "Datenblätter, Ändern von Rahmenstilen"
  - "Datenblätter, Ändern von Datenblattlinienstilen"
  - "DataGridView-Steuerelement [Windows Forms], Rahmenarten"
  - "DataGridView-Steuerelement [Windows Forms], Datenblattlinienstile"
  - "Datenblattlinien, Ändern von Formaten"
ms.assetid: 2f413c7a-4025-4171-8e3a-66ef908ea583
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: &#196;ndern des Rahmen- und Rasterlinienstils im DataGridView-Steuerelement in Windows Forms
Mit dem <xref:System.Windows.Forms.DataGridView>\-Steuerelement können Sie das Aussehen des Rahmens und der Rasterlinien des Steuerelements anpassen, um die Benutzererfahrung zu verbessern.  Neben den Rahmenstilen für die Zellen im Steuerelement können Sie die Rasterlinienfarbe und den Rahmenstil des Steuerelements selbst ändern.  Darüber hinaus können Sie verschiedene Zellrahmenstile auf normale Zellen, Zeilenheaderzellen und Spaltenheaderzellen anwenden.  
  
> [!NOTE]
>  Die Rasterlinienfarbe wird ausschließlich mit den Werten <xref:System.Windows.Forms.DataGridViewCellBorderStyle>, <xref:System.Windows.Forms.DataGridViewCellBorderStyle> und <xref:System.Windows.Forms.DataGridViewCellBorderStyle> der <xref:System.Windows.Forms.DataGridViewCellBorderStyle>\-Enumeration und dem <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle>\-Wert der <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle>\-Enumeration verwendet.  Die anderen Werte dieser Enumerationen verwenden Farben, die durch das Betriebssystem festgelegt sind.  Wenn außerdem visuelle Stile unter Windows XP und der Windows Server 2003\-Familie über die <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=fullName>\-Methode aktiviert sind, wird der <xref:System.Windows.Forms.DataGridView.GridColor%2A>\-Eigenschaftswert nicht verwendet.  
  
### So ändern Sie die Rasterlinienfarbe programmgesteuert  
  
-   Legen Sie die <xref:System.Windows.Forms.DataGridView.GridColor%2A>\-Eigenschaft fest.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#031](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#031)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#031](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#031)]  
  
### So ändern Sie den Rahmenstil des gesamten DataGridView\-Steuerelements programmgesteuert  
  
-   Legen Sie die <xref:System.Windows.Forms.DataGridView.BorderStyle%2A>\-Eigenschaft auf einen der <xref:System.Windows.Forms.BorderStyle>\-Enumerationswerte fest.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#032](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#032)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#032](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#032)]  
  
### So ändern Sie die Rahmenstile für DataGridView\-Zellen programmgesteuert  
  
-   Legen Sie die Eigenschaften <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A>, <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A> und <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A> fest.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#033](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#033)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#033](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#033)]  
  
## Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#030](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#030)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#030](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#030)]  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement mit dem Namen`dataGridView1` muss vorhanden sein.  
  
-   Verweise auf die Assemblys <xref:System?displayProperty=fullName>, <xref:System.Windows.Forms?displayProperty=fullName> und <xref:System.Drawing?displayProperty=fullName>.  
  
## Siehe auch  
 <xref:System.Windows.Forms.BorderStyle>   
 <xref:System.Windows.Forms.DataGridView.BorderStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.GridColor%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewCellBorderStyle>   
 <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle>   
 [Grundlegende Formatierungen und Formate im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)