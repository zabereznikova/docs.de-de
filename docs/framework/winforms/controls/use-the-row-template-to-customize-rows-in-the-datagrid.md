---
title: 'Gewusst wie: Verwenden der Zeilenvorlage zum Anpassen von Zeilen im DataGridView-Steuerelement in Windows Forms'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- DataGridView control [Windows Forms], customizing rows
ms.assetid: 6db61607-7e57-4a84-8d63-9d6a7ed7f9ff
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4898ed7ddff6ca1800ba9380707ad989cbec1125
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-row-template-to-customize-rows-in-the-windows-forms-datagridview-control"></a>Gewusst wie: Verwenden der Zeilenvorlage zum Anpassen von Zeilen im DataGridView-Steuerelement in Windows Forms
Die <xref:System.Windows.Forms.DataGridView> Steuerelement verwendet die Zeilenvorlage als Grundlage für alle Zeilen, die an das Steuerelement hinzufügt, über die Datenbindung oder beim Aufrufen der <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> -Methode ohne Angabe einer vorhandenen Zeile verwenden.  
  
 Die Zeilenvorlage bietet Ihnen eine bessere Kontrolle über das Aussehen und Verhalten von Zeilen als die <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> Eigenschaft ermöglicht. Mit der Zeilenvorlage können Sie festlegen, eine <xref:System.Windows.Forms.DataGridViewRow> Eigenschaften, einschließlich <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>.  
  
 Es gibt einige Situationen, in denen Sie die Zeilenvorlage verwenden müssen, um einen bestimmten Effekt zu erzielen. Z. B. kann keine Informationen über die Zeilenhöhe gespeichert werden, einem <xref:System.Windows.Forms.DataGridViewCellStyle>, sodass Sie eine Zeilenvorlage verwenden müssen, um die Standardhöhe verwendet, die für alle Zeilen zu ändern. Die Zeilenvorlage ist auch nützlich, wenn Sie Ihren eigenen Klassen abgeleitet erstellen <xref:System.Windows.Forms.DataGridViewRow> und Ihren benutzerdefinierten Typ verwendet werden, wenn das Steuerelement neue Zeilen hinzugefügt werden sollen.  
  
> [!NOTE]
>  Die Zeilenvorlage wird verwendet, nur, wenn Zeilen hinzugefügt werden. Sie können nicht vorhandene Zeilen ändern, indem Sie die Zeilenvorlage ändern.  
  
### <a name="to-use-the-row-template"></a>Verwenden der Zeilenvorlage  
  
-   Legen Sie Eigenschaften für das Objekt abgerufen, die von der <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> Eigenschaft.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.RowTemplate#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CPP/datagridviewrowtemplate.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridView.RowTemplate#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CS/datagridviewrowtemplate.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridView.RowTemplate#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/VB/datagridviewrowtemplate.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.  
  
-   Verweise auf die Assemblys <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType>  
 [Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 [Zellstile im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)
