---
title: Erstellen eines Rahmens um ein Steuerelement mithilfe von Padding
ms.date: 03/30/2017
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
ms.openlocfilehash: 114186ab5784cf892cb01e9fe2648ce22cecc4b7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742190"
---
# <a name="how-to-create-a-border-around-a-windows-forms-control-using-padding"></a>Gewusst wie: Erstellen eines Rahmens um ein Windows Forms-Steuerelement mithilfe von Abständen
Im folgenden Codebeispiel wird veranschaulicht, wie ein Rahmen oder eine Gliederung um ein <xref:System.Windows.Forms.RichTextBox> Steuerelement erstellt wird. Im Beispiel wird der Wert der <xref:System.Windows.Forms.Padding>-Eigenschaft eines <xref:System.Windows.Forms.Panel> Steuer Elements auf 5 festgelegt und die <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft eines untergeordneten <xref:System.Windows.Forms.RichTextBox> Steuer Elements auf <xref:System.Windows.Forms.DockStyle.Fill>festgelegt. Die <xref:System.Windows.Forms.Control.BackColor%2A> des <xref:System.Windows.Forms.Panel> Steuer Elements ist auf <xref:System.Drawing.Color.Blue%2A>festgelegt, wodurch ein blauer Rahmen um das <xref:System.Windows.Forms.RichTextBox> Steuerelement erstellt wird.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.Padding#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Padding/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.Padding#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Padding/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.Padding>
- [Rand und Abstand in Windows Forms-Steuerelementen](margin-and-padding-in-windows-forms-controls.md)
