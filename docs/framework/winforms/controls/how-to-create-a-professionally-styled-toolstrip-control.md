---
title: 'Vorgehensweise: Erstellen eines professionellen ToolStrip-Steuerelements'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: c208b2f6-8105-474b-9075-d582e1792870
ms.openlocfilehash: 4e4e899d583eb87b3ced7161f1fd274c0bcc591c
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586556"
---
# <a name="how-to-create-a-professionally-styled-toolstrip-control"></a>Vorgehensweise: Erstellen eines professionellen ToolStrip-Steuerelements
Sie können den <xref:System.Windows.Forms.ToolStrip>-Steuerelementen Ihrer Anwendung ein professionelles Aussehen und Verhalten ("Look and Feel") verleihen, indem Sie eine eigene Klasse schreiben, die vom Typ <xref:System.Windows.Forms.ToolStripProfessionalRenderer> abgeleitet ist.  
  
 Bietet umfassende Unterstützung für dieses Feature in Visual Studio.  
  
 Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen eines professionellen ToolStrip-Steuerelements](walkthrough-creating-a-professionally-styled-toolstrip-control.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie Sie mit <xref:System.Windows.Forms.ToolStrip> Steuerelemente ein zusammengesetztes Steuerelements zu erstellen, die imitiert die **Navigationsbereich** von Microsoft® Outlook® bereitgestellten.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StackView#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StackView#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Verweise auf die Assemblys ""System.Drawing" und "System.Windows.Forms".  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [ToolStrip-Steuerelement](toolstrip-control-windows-forms.md)
- [Vorgehensweise: Bereitstellen von Standardmenüelementen für ein Formular](how-to-provide-standard-menu-items-to-a-form.md)
