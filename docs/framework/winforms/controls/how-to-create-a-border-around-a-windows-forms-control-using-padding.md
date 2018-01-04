---
title: "Gewusst wie: Erstellen eines Rahmens um ein Windows Forms-Steuerelement mithilfe von Abständen"
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
helpviewer_keywords:
- margins
- controls [Windows Forms], Margin property
- padding [Windows Forms], Windows Forms
- controls [Windows Forms], Padding property
- controls [Windows Forms], outlining
- Padding property [Windows Forms]
- margins [Windows Forms], Windows Forms
- Margin property [Windows Forms]
ms.assetid: bac7ed4d-a163-4259-98bd-155a36345890
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7b8fc8774e1f861db989b05678235ea34e38318c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-border-around-a-windows-forms-control-using-padding"></a>Gewusst wie: Erstellen eines Rahmens um ein Windows Forms-Steuerelement mithilfe von Abständen
Im folgenden Codebeispiel wird veranschaulicht, wie erstellen einen Rahmen oder Kontur um eine <xref:System.Windows.Forms.RichTextBox> Steuerelement. Im Beispiel wird der Wert von einer <xref:System.Windows.Forms.Panel> des Steuerelements <xref:System.Windows.Forms.Padding> -Eigenschaft auf 5 und legt die <xref:System.Windows.Forms.Control.Dock%2A> Eigenschaft eines untergeordneten Elements <xref:System.Windows.Forms.RichTextBox> die Steuerung an <xref:System.Windows.Forms.DockStyle.Fill>. Die <xref:System.Windows.Forms.Control.BackColor%2A> von der <xref:System.Windows.Forms.Panel> Steuerelement festgelegt ist, um <xref:System.Drawing.Color.Blue%2A>, einen blauen Rahmen erstellt die <xref:System.Windows.Forms.RichTextBox> Steuerelement.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.Padding#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Padding/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.Padding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Padding/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Padding>  
 [Rand und Abstand in Windows Forms-Steuerelementen](../../../../docs/framework/winforms/controls/margin-and-padding-in-windows-forms-controls.md)
