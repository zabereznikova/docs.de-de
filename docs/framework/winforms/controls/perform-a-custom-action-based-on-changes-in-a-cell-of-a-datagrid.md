---
title: "Gewusst wie: Ausf&#252;hren einer benutzerdefinierten Aktion aufgrund von &#196;nderungen in einer Zelle des DataGridView-Steuerelements in Windows Forms | Microsoft Docs"
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
  - "Zellen, Erkennen von Änderungen"
  - "Datenblätter, Erkennen von Änderungen in Zellen"
  - "DataGridView-Steuerelement [Windows Forms], Erkennen von Änderungen in Zellen"
ms.assetid: 7fa44d01-97f4-4ccb-a149-bc72628d2c36
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Ausf&#252;hren einer benutzerdefinierten Aktion aufgrund von &#196;nderungen in einer Zelle des DataGridView-Steuerelements in Windows Forms
Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement verfügt über eine Reihe von Ereignissen, mit denen Sie Änderungen am Zustand von <xref:System.Windows.Forms.DataGridView>\-Zellen erkennen können.  Zwei der am häufigsten verwendeten Ereignisse sind das <xref:System.Windows.Forms.DataGridView.CellValueChanged>\-Ereignis und das <xref:System.Windows.Forms.DataGridView.CellStateChanged>\-Ereignis.  
  
### So erkennen Sie Änderungen an den Werten von DataGridView\-Zellen  
  
-   Schreiben Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.CellValueChanged>\-Ereignis.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#130)]  
  
### So erkennen Sie Änderungen an den Zuständen von DataGridView\-Zellen  
  
-   Schreiben Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.CellStateChanged>\-Ereignis.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#135](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#135)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#135](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#135)]  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement mit dem Namen`dataGridView1` muss vorhanden sein.  Für C\# müssen die Ereignishandler mit den entsprechenden Ereignissen verbunden werden.  
  
-   Verweise auf die <xref:System?displayProperty=fullName>\-Assembly und die <xref:System.Windows.Forms?displayProperty=fullName>\-Assembly.  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.CellValueChanged?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.CellStateChanged?displayProperty=fullName>   
 [Programmieren mit Zellen, Zeilen und Spalten im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)   
 [Exemplarische Vorgehensweise: Validieren von Daten im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)