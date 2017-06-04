---
title: "Gewusst wie: Entfernen von automatisch generierten Spalten aus einem DataGridView-Steuerelement in Windows Forms | Microsoft Docs"
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
  - "Spalten [Windows Forms], Entfernen"
  - "DataGridView-Steuerelement [Windows Forms], Entfernen von Spalten"
ms.assetid: 92e28d98-95a3-446c-9150-41b7c7e5be15
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Entfernen von automatisch generierten Spalten aus einem DataGridView-Steuerelement in Windows Forms
Wenn das <xref:System.Windows.Forms.DataGridView>\-Steuerelement so festgelegt ist, dass es Spalten automatisch anhand von Daten aus der Datenquelle generiert, können Sie bestimmte Spalten wahlweise unterdrücken.  Zu diesem Zweck können Sie die <xref:System.Windows.Forms.DataGridViewColumnCollection.Remove%2A>\-Methode für die <xref:System.Windows.Forms.DataGridView.Columns%2A>\-Auflistung aufrufen.  Wahlweise können Sie Spalten aus der Ansicht ausblenden, indem Sie die <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A>\-Eigenschaft auf `false` festlegen.  Diese Methode ist hilfreich, wenn Sie die ausgeblendeten Spalten unter bestimmten Bedingungen anzeigen möchten, oder wenn Sie auf die Daten in den Spalten zugreifen müssen, ohne sie anzuzeigen.  
  
### So entfernen Sie automatisch generierte Spalten  
  
-   Rufen Sie die <xref:System.Windows.Forms.DataGridViewColumnCollection.Remove%2A>\-Methode der <xref:System.Windows.Forms.DataGridView.Columns%2A>\-Auflistung auf.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#111](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#111)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#111](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#111)]  
  
### So blenden Sie automatisch generierte Spalten aus  
  
-   Legen Sie die <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A>\-Eigenschaft der Spalte auf den Wert `false` fest.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#112](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#112)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#112](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#112)]  
  
## Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#110)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#110)]  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement mit dem Namen `dataGridView1`, das an eine Tabelle mit den Spalten `Fax` und `CustomerID` gebunden ist, beispielsweise die Tabelle `Customers` in der Beispieldatenbank Northwind.  
  
-   Verweise auf die <xref:System?displayProperty=fullName>\-Assembly und die <xref:System.Windows.Forms?displayProperty=fullName>\-Assembly.  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumnCollection.Remove%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=fullName>   
 [Anzeigen von Daten im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)