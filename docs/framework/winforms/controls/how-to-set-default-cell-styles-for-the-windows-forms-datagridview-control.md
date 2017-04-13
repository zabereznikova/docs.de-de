---
title: "Gewusst wie: Festlegen von Standardzellenformaten f&#252;r das DataGridView-Steuerelement in Windows Forms | Microsoft Docs"
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
  - "Zellen, Formate"
  - "Datenblätter, Zellenstile"
  - "DataGridView-Steuerelement [Windows Forms], Zellenstile"
ms.assetid: 1aaaca43-5340-447e-99c0-9177d9776aa1
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Gewusst wie: Festlegen von Standardzellenformaten f&#252;r das DataGridView-Steuerelement in Windows Forms
Mit dem <xref:System.Windows.Forms.DataGridView>\-Steuerelement können Sie Standardzellenstile für das gesamte Steuerelement und für bestimmte Spalten und Zeilen angeben.  Diese Standardeinstellungen werden von der Steuerelementebene bis herunter auf die Spaltenebene, dann auf die Zeilenebene und anschließend auf die Zellenebene gefiltert.  Wenn eine bestimmte Eigenschaft <xref:System.Windows.Forms.DataGridViewCellStyle> nicht auf Zellenebene festgelegt ist, wird die standardmäßige Eigenschafteneinstellung auf Zeilenebene verwendet.  Wenn die Eigenschaft auf Zeilenebene ebenfalls nicht festgelegt ist, wird die Standardspalteneinstellung verwendet.  Wenn die Eigenschaft schließlich auf Spaltenebene ebenfalls nicht festgelegt ist, wird die <xref:System.Windows.Forms.DataGridView>\-Standardeinstellung verwendet.  Mit dieser Einstellung können Sie vermeiden, die Eigenschafteneinstellungen auf mehreren Ebenen duplizieren zu müssen.  Geben Sie einfach auf jeder Ebene die Stile an, die sich von den darüber liegenden Ebenen unterscheiden.  Weitere Informationen finden Sie unter [Zellstile im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
 Visual Studio bietet umfassende Unterstützung für diese Aufgabe.  Siehe auch [Gewusst wie: Festlegen von standardmäßigen Zellenstilen und Datenformaten für das DataGridView\-Steuerelement in Windows Forms mithilfe des Designers](http://msdn.microsoft.com/library/95y5fz2x\(v=vs.110\)).  
  
### Die legen Sie Standardzellenstile programmgesteuert fest  
  
1.  Legen Sie die Eigenschaften des <xref:System.Windows.Forms.DataGridViewCellStyle>\-Objekts fest, das über die Eigenschaft <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName> abgerufen wurde.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#141](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#141)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#141](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#141)]  
  
2.  Erstellen und initialisieren Sie neue <xref:System.Windows.Forms.DataGridViewCellStyle>\-Objekte für die Verwendung durch mehreren Zeilen und Spalten.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#142](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#142)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#142](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#142)]  
  
3.  Legen Sie die Eigenschaft `DefaultCellStyle` bestimmter Zeilen und Spalten fest.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#143](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#143)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#143](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#143)]  
  
## Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#140)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#140)]  
  
## Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement namens `dataGridView1`.  
  
-   Verweise auf die Assemblys <xref:System?displayProperty=fullName>, <xref:System.Drawing?displayProperty=fullName> und <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## Robuste Programmierung  
 Um maximale Skalierbarkeit zu erreichen, wenn Sie mit sehr großen Datenmengen arbeiten, sollten Sie <xref:System.Windows.Forms.DataGridViewCellStyle>\-Objekte für mehrere Zeilen, Spalten oder Zellen freigeben, die dieselben Stile verwenden, anstatt die Stileigenschaften für einzelne Elemente separat festzulegen.  Darüber hinaus sollten Sie freigegebene Zeilen erstellen und auf diese zugreifen, indem Sie die Eigenschaft <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=fullName> verwenden.  Weitere Informationen finden Sie unter [Empfohlene Vorgehensweisen für das Skalieren des DataGridView\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewCellStyle>   
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=fullName>   
 [Grundlegende Formatierungen und Formate im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)   
 [Zellstile im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)   
 [Empfohlene Vorgehensweisen für das Skalieren des DataGridView\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)   
 [Gewusst wie: Festlegen von abwechselnden Zeilenstilen für das DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)