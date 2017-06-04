---
title: "Gewusst wie: Abrufen und Festlegen der aktuellen Zelle im DataGridView-Steuerelement in Windows Forms | Microsoft Docs"
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
  - "Zellen, Abrufen und Festlegen von aktuellen"
  - "DataGridView-Steuerelement [Windows Forms], Abrufen der aktuellen Zelle"
  - "DataGridView-Steuerelement [Windows Forms], Festlegen der aktuellen Zelle"
ms.assetid: b0e41e57-493a-4bd0-9376-a6f76723540c
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Abrufen und Festlegen der aktuellen Zelle im DataGridView-Steuerelement in Windows Forms
Die Interaktion mit der <xref:System.Windows.Forms.DataGridView> setzt häufig voraus, dass Sie programmgesteuert ermitteln, welche Zelle gerade aktiv ist.  Möglicherweise müssen Sie die aktuelle Zelle auch ändern.  Sie können diese Aufgaben mit der <xref:System.Windows.Forms.DataGridView.CurrentCell%2A>\-Eigenschaft ausführen.  
  
> [!NOTE]
>  Sie können die aktuelle Zelle nicht in einer Zeile oder Spalte festlegen, deren <xref:System.Windows.Forms.DataGridViewBand.Visible%2A>\-Eigenschaft auf `false` festgelegt ist.  
  
 Je nach Auswahlmodus des <xref:System.Windows.Forms.DataGridView>\-Steuerelements kann die Auswahl durch Ändern der aktuellen Zelle ebenfalls geändert werden.  Weitere Informationen finden Sie unter [Auswahlmodi im DataGridView\-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md).  
  
### So rufen Sie die aktuelle Zelle programmgesteuert ab  
  
-   Verwenden Sie die <xref:System.Windows.Forms.DataGridView.CurrentCell%2A>\-Eigenschaft des <xref:System.Windows.Forms.DataGridView>\-Steuerelements.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### So legen Sie die aktuelle Zelle programmgesteuert fest  
  
-   Legen Sie die <xref:System.Windows.Forms.DataGridView.CurrentCell%2A>\-Eigenschaft des <xref:System.Windows.Forms.DataGridView>\-Steuerelements fest  Im folgenden Codebeispiel wird die aktuelle Zelle auf Zeile 0, Spalte 1 festgelegt.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   <xref:System.Windows.Forms.Button>\-Steuerelemente mit den Namen `getCurrentCellButton` und `setCurrentCellButton`.  In [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] müssen Sie die <xref:System.Windows.Forms.Control.Click>\-Ereignisse für jede Schaltfläche an den zugehörigen Ereignishandler im Beispielcode anfügen.  
  
-   Ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement mit dem Namen`dataGridView1` muss vorhanden sein.  
  
-   Verweise auf die <xref:System?displayProperty=fullName>\-Assembly und die <xref:System.Windows.Forms?displayProperty=fullName>\-Assembly.  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=fullName>   
 [Grundlegende Spalten\-, Zeilen\- und Zellfeatures im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)   
 [Auswahlmodi im DataGridView\-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md)