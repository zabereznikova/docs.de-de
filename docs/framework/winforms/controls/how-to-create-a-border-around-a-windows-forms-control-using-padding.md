---
title: 'Vorgehensweise: Erstellen eines Rahmens um ein Windows Forms Steuerelement mithilfe von Abständen'
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
ms.openlocfilehash: 26d5dd086828df94c1ea0808d2f72723344b0702
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54614653"
---
# <a name="how-to-create-a-border-around-a-windows-forms-control-using-padding"></a>Vorgehensweise: Erstellen eines Rahmens um ein Windows Forms Steuerelement mithilfe von Abständen
Im folgenden Codebeispiel wird veranschaulicht, wie zum Erstellen eines Rahmens oder eine Kontur um eine <xref:System.Windows.Forms.RichTextBox> Steuerelement. Im Beispiel wird den Wert des einem <xref:System.Windows.Forms.Panel> des Steuerelements <xref:System.Windows.Forms.Padding> -Eigenschaft auf 5 und legt die <xref:System.Windows.Forms.Control.Dock%2A> Eigenschaft eines untergeordneten Elements <xref:System.Windows.Forms.RichTextBox> die Steuerung an <xref:System.Windows.Forms.DockStyle.Fill>. Die <xref:System.Windows.Forms.Control.BackColor%2A> von der <xref:System.Windows.Forms.Panel> -Steuerelement so eingestellt ist, dass <xref:System.Drawing.Color.Blue%2A>, erstellt einen blauen Rahmen um die <xref:System.Windows.Forms.RichTextBox> Steuerelement.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.Padding#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Padding/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.Padding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Padding/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.Padding>
- [Rand und Abstand in Windows Forms-Steuerelementen](../../../../docs/framework/winforms/controls/margin-and-padding-in-windows-forms-controls.md)
