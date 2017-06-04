---
title: "Gewusst wie: &#196;ndern der Reihenfolge von Spalten im DataGridView-Steuerelement in Windows Forms | Microsoft Docs"
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
  - "Spalten [Windows Forms], Ändern der Reihenfolge"
  - "Datenblätter, Ändern der Spaltenreihenfolge"
  - "DataGridView-Steuerelement [Windows Forms], Spaltenreihenfolge"
ms.assetid: 5e9ac3bc-b0f0-48cb-a3d5-b005af905395
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Gewusst wie: &#196;ndern der Reihenfolge von Spalten im DataGridView-Steuerelement in Windows Forms
Wenn Sie eine <xref:System.Windows.Forms.DataGridView> verwenden, um Daten aus einer Datenquelle anzuzeigen, werden die Spalten im Schema der Datenquelle manchmal nicht in der von Ihnen gewünschten Reihenfolge angezeigt.  Sie können die Reihenfolge, in der die Spalten angezeigt werden, durch Verwenden der <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A>\-Eigenschaft der <xref:System.Windows.Forms.DataGridViewColumn>\-Klasse ändern.  
  
 Im folgenden Codebeispiel werden einige der Spalten neu angeordnet, die automatisch generiert werden, wenn Sie eine Bindung zur Customers\-Tabelle in der Beispieldatenbank Northwind herstellen.  Weitere Informationen darüber, wie das <xref:System.Windows.Forms.DataGridView>\-Steuerelement an eine Datenbanktabelle gebunden wird, finden Sie unter [Gewusst wie: Binden von Daten an das DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md).  
  
 Visual Studio bietet Unterstützung für diese Aufgabe.  Siehe auch [Gewusst wie: Ändern der Reihenfolge von Spalten des DataGridView\-Steuerelements in Windows Forms mithilfe des Designers](http://msdn.microsoft.com/library/hb1dk7ax\(v=vs.110\))  
  
## Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#040](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#040)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#040](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#040)]  
  
## Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement namens `customersDataGridView`, das an eine Tabelle mit den angegebenen Spaltennamen gebunden ist, beispielsweise die `Customers`\-Tabelle in der Beispieldatenbank Northwind.  
  
-   Verweise auf die Assemblys <xref:System?displayProperty=fullName>, <xref:System.Windows.Forms?displayProperty=fullName>, <xref:System.Data?displayProperty=fullName> und <xref:System.Xml?displayProperty=fullName>.  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewColumn>   
 <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=fullName>   
 [Anzeigen von Daten im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)   
 [Gewusst wie: Binden von Daten an das DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md)