---
title: "Gewusst wie: Festlegen von Schriftart- und Farbstilen im DataGridView-Steuerelement in Windows Forms | Microsoft Docs"
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
  - "Datenblätter, Farbformate"
  - "Datenblätter, Anpassen von Zellen"
  - "Datenblätter, Schriftartformate"
  - "DataGridView-Steuerelement [Windows Forms], Zellenanpassung"
ms.assetid: 588f2c57-d963-41b1-9c1d-d02d71818113
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Festlegen von Schriftart- und Farbstilen im DataGridView-Steuerelement in Windows Forms
Sie können die visuelle Darstellung von Zellen in einem <xref:System.Windows.Forms.DataGridView>\-Steuerelement angeben, indem Sie die Eigenschaften der <xref:System.Windows.Forms.DataGridViewCellStyle>\-Klasse festlegen.  Sie können Instanzen dieser Klasse aus verschiedenen Eigenschaften der <xref:System.Windows.Forms.DataGridView>\-Klasse und deren Assistentenklassen abrufen, oder Sie können <xref:System.Windows.Forms.DataGridViewCellStyle>\-Objekte instanziieren, um sie diesen Eigenschaften zuzuweisen.  
  
 In den folgenden Vorgehensweisen wird grundsätzlich veranschaulicht, wie die Zellendarstellung mithilfe der <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>\-Eigenschaft angepasst werden kann.  Jede Zelle in dem Steuerelement erbt die Stile, die über diese Eigenschaft angegeben sind, es sei denn, die Stile werden auf Spalten\-, Zeilen\- oder Zellenebene überschrieben.  Ein Beispiel für die Vererbung von Stilen finden Sie unter [Gewusst wie: Festlegen von Standardzellenformaten für das DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).  Informationen über weitere Verwendungsmöglichkeiten der <xref:System.Windows.Forms.DataGridViewCellStyle>\-Klasse finden Sie in den Themen, die im Abschnitt "Siehe auch" aufgeführt sind.  
  
 Visual Studio bietet umfassende Unterstützung für diese Aufgabe.  Siehe auch [Gewusst wie: Festlegen von standardmäßigen Zellenstilen und Datenformaten für das DataGridView\-Steuerelement in Windows Forms mithilfe des Designers](http://msdn.microsoft.com/library/95y5fz2x\(v=vs.110\)).  
  
### So geben Sie die von DataGridView\-Zellen verwendete Schriftart an  
  
-   Legen Sie die <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A>\-Eigenschaft einer <xref:System.Windows.Forms.DataGridViewCellStyle>\-Instanz fest.  Im folgenden Codebeispiel wird die <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>\-Eigenschaft verwendet, um die Schriftart für das gesamte Steuerelement festzulegen.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#101](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#101)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#101](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#101)]  
  
### So geben Sie die Vordergrund\- und Hintergrundfarben von DataGridView\-Zellen an  
  
-   Legen Sie die Eigenschaften <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> und <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> einer <xref:System.Windows.Forms.DataGridViewCellStyle>\-Instanz fest.  Im folgenden Codebeispiel wird die <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>\-Eigenschaft verwendet, um diese Stile für das gesamte Steuerelement festzulegen.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#102](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#102)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#102](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#102)]  
  
### So geben Sie die Vordergrund\- und Hintergrundfarben von ausgewählten DataGridView\-Zellen an  
  
-   Legen Sie die Eigenschaften <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A> und <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> einer <xref:System.Windows.Forms.DataGridViewCellStyle>\-Instanz fest.  Im folgenden Codebeispiel wird die <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>\-Eigenschaft verwendet, um diese Stile für das gesamte Steuerelement festzulegen.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#103](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#103)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#103](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#103)]  
  
## Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#100)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#100)]  
  
## Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement namens `dataGridView1`.  
  
-   Verweise auf die Assemblys <xref:System?displayProperty=fullName>, <xref:System.Drawing?displayProperty=fullName> und <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## Robuste Programmierung  
 Um maximale Skalierbarkeit zu erreichen, sollten Sie <xref:System.Windows.Forms.DataGridViewCellStyle>\-Objekte für mehrere Zeilen, Spalten oder Zellen, in denen dieselben Stile verwendet werden, gemeinsam verwenden, anstatt die Stileigenschaften für jedes einzelne Element festzulegen.  Weitere Informationen finden Sie unter [Empfohlene Vorgehensweisen für das Skalieren des DataGridView\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewCellStyle>   
 [Grundlegende Formatierungen und Formate im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)   
 [Zellstile im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)