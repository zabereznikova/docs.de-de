---
title: "Gewusst wie: Fixieren von Spalten im DataGridView-Steuerelement in Windows Forms | Microsoft Docs"
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
  - "Spalten [Windows Forms], Fixieren"
  - "DataGridView-Steuerelement [Windows Forms], Spalten immer sichtbar"
  - "DataGridView-Steuerelement [Windows Forms], Fixieren von Spalten"
ms.assetid: 2ef8b1de-782e-4867-af8d-58171ab5c106
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Gewusst wie: Fixieren von Spalten im DataGridView-Steuerelement in Windows Forms
Wenn Benutzer Daten anzeigen, die in einem <xref:System.Windows.Forms.DataGridView>\-Steuerelement in Windows Forms angezeigt werden, müssen sie mitunter häufig auf eine bestimmte Spalte oder Gruppe von Spalten zugreifen.  Wenn Sie beispielsweise eine Tabelle mit Kundendaten anzeigen, die viele Spalten enthält, ist es hilfreich, wenn die Namen der Kunden immer angezeigt werden, während andere Spalten außerhalb des sichtbaren Bereichs liegen.  
  
 Zu diesem Zweck können Sie Spalten im Steuerelement fixieren.  Wenn Sie eine Spalte fixieren, werden automatisch auch alle Spalten links daneben \(bzw. rechts daneben in von rechts nach links geschriebenen Sprachen\) fixiert.  Fixierte Spalten behalten ihre Position bei, während alle anderen Spalten bei einem Bildlauf mitwandern.  
  
> [!NOTE]
>  Wenn die Neuanordnung von Spalten aktiviert ist, werden die fixierten Spalten als eine Gruppe im Unterschied zu den nicht fixierten Spalten behandelt.  Benutzer können Spalten in beiden Gruppen neu positionieren, jedoch keine Spalte aus einer Gruppe in die andere verschieben.  
  
 Die <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A>\-Eigenschaft einer Spalte bestimmt, ob die Spalte immer innerhalb des Rasters sichtbar ist.  
  
 Visual Studio bietet Unterstützung für diese Aufgabe.  Siehe auch [Gewusst wie: Fixieren von Spalten im DataGridView\-Steuerelement in Windows Forms mithilfe des Designers](http://msdn.microsoft.com/library/717ss6s6\(v=vs.110\)).  
  
### So fixieren Sie eine Spalte programmgesteuert  
  
-   Legen Sie die <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=fullName>\-Eigenschaft auf `true` fest.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#061](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#061)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#061](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#061)]  
  
## Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement mit dem Namen `dataGridView1`, das eine Spalte mit dem Namen `AddToCartButton` enthält.  
  
-   Verweise auf die Assemblys <xref:System?displayProperty=fullName> und <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView>   
 [Grundlegende Spalten\-, Zeilen\- und Zellfeatures im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)   
 [Gewusst wie: Aktivieren der Neuanordnung von Spalten im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-enable-column-reordering-in-the-windows-forms-datagridview-control.md)