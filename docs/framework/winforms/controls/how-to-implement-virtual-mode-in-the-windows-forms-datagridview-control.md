---
title: "Gewusst wie: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms | Microsoft Docs"
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
  - "Daten [Windows Forms], Verwalten von großen Datasets"
  - "DataGridView-Steuerelement [Windows Forms], Große Datasets"
  - "DataGridView-Steuerelement [Windows Forms], Virtueller Modus"
  - "Virtueller Modus"
ms.assetid: 98236267-f08e-4918-bcf9-77acf050a3ca
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms
Im folgenden Codebeispiel wird veranschaulicht, wie große Datenmengen mithilfe eines <xref:System.Windows.Forms.DataGridView>\-Steuerelements verwaltet werden, dessen <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>\-Eigenschaft auf `true` festgelegt ist.  
  
 Eine vollständige Erläuterung dieses Codebeispiels finden Sie unter [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
## Beispiel  
 [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#000](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#000)]
 [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#000)]  
  
## Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] finden Sie unter [Erstellen von der Befehlszeile aus](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) oder [Erstellen über die Befehlszeile mit csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms\-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>   
 <xref:System.Windows.Forms.DataGridView.CellValueNeeded>   
 <xref:System.Windows.Forms.DataGridView.CellValuePushed>   
 <xref:System.Windows.Forms.DataGridView.NewRowNeeded>   
 <xref:System.Windows.Forms.DataGridView.RowValidated>   
 <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>   
 <xref:System.Windows.Forms.DataGridView.CancelRowEdit>   
 <xref:System.Windows.Forms.DataGridView.UserDeletingRow>   
 [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)   
 [Leistungsoptimierung im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)   
 [Virtueller Modus im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)