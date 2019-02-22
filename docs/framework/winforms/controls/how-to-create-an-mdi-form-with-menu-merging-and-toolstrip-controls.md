---
title: 'Vorgehensweise: Erstellen eines MDI-Formulars mit Zusammenführen von Menüs und ToolStrip-Steuerelemente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
ms.assetid: 64992ed9-44af-4baf-b45f-863e6ab35711
ms.openlocfilehash: 2a6b8669717e8f07d9c7acd624e77a5c35a4eb7e
ms.sourcegitcommit: 07c4368273b446555cb2c85397ea266b39d5fe50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2019
ms.locfileid: "56583458"
---
# <a name="how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a>Vorgehensweise: Erstellen eines MDI-Formulars mit Zusammenführen von Menüs und ToolStrip-Steuerelemente
Der <xref:System.Windows.Forms?displayProperty=nameWithType>-Namespace unterstützt MDI-Anwendungen (Multiple Document Interface, Schnittstelle für mehrere Dokumente), und das <xref:System.Windows.Forms.MenuStrip>-Steuerelement unterstützt das Zusammenführen von Menüs. MDI-Formulare können auch <xref:System.Windows.Forms.ToolStrip>-Steuerelemente enthalten.  
  
 Bietet umfassende Unterstützung für dieses Feature in Visual Studio.  
  
 Siehe auch [Exemplarische Vorgehensweise: Erstellen eines MDI-Formulars mit das Zusammenführen von Menüs und ToolStrip-Steuerelemente](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie Sie <xref:System.Windows.Forms.ToolStripPanel>-Steuerelemente mit einem MDI-Formular verwenden können. Das Formular unterstützt auch Zusammenführen von Menüs mit untergeordneten Menüs.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Codebeispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys ""System.Drawing" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.  
  
## <a name="see-also"></a>Siehe auch
- [ToolStrip-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
