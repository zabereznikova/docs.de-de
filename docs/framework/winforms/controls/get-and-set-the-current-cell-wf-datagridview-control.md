---
title: 'Gewusst wie: Abrufen und Festlegen der aktuellen Zelle im DataGridView-Steuerelement in Windows Forms'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], getting current cell
- DataGridView control [Windows Forms], setting current cell
- cells [Windows Forms], getting and setting current
ms.assetid: b0e41e57-493a-4bd0-9376-a6f76723540c
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b53d135a1d019ce20dfc8c5c2c1ba59e5968306e
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-get-and-set-the-current-cell-in-the-windows-forms-datagridview-control"></a>Gewusst wie: Abrufen und Festlegen der aktuellen Zelle im DataGridView-Steuerelement in Windows Forms
Interaktion mit der <xref:System.Windows.Forms.DataGridView> erfordert oft, dass Sie programmgesteuert ermitteln, welche Zelle gerade aktiv ist. Sie müssen möglicherweise auch die aktive Zelle zu ändern. Sie können diese Aufgaben mit der <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> Eigenschaft.  
  
> [!NOTE]
>  Die aktuelle Zelle kann nicht festgelegt werden, in einer Zeile oder Spalte mit seiner <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> -Eigenschaftensatz auf `false`.  
  
 Je nach den <xref:System.Windows.Forms.DataGridView> Auswahlmodus des Steuerelements, Ändern der aktuellen Zelle können Sie die Auswahl ändern. Weitere Informationen finden Sie unter [Auswahlmodi im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md).  
  
### <a name="to-get-the-current-cell-programmatically"></a>Die aktuelle Zelle programmgesteuert abrufen  
  
-   Verwenden der <xref:System.Windows.Forms.DataGridView> des Steuerelements <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> Eigenschaft.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### <a name="to-set-the-current-cell-programmatically"></a>So legen Sie die aktuelle Zelle programmgesteuert fest  
  
-   Legen Sie die <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> Eigenschaft von der <xref:System.Windows.Forms.DataGridView> Steuerelement. Im folgenden Codebeispiel wird die aktive Zelle 0, Spalte 1 Zeile festgelegt.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   <xref:System.Windows.Forms.Button> -Steuerelemente namens `getCurrentCellButton` und `setCurrentCellButton`. In Visual c# Anfügen muss der <xref:System.Windows.Forms.Control.Click> Ereignisse für jede Schaltfläche an den zugehörigen Ereignishandler im Beispielcode.  
  
-   Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.  
  
-   Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=nameWithType>  
 [Grundlegende Spalten-, Zeilen- und Zellfunktionen im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 [Auswahlmodi im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md)
