---
title: 'Vorgehensweise: Verwenden von ToolStripPanels für MDI'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MDI [Windows Forms], using ToolStripPanels [Windows Forms]
- ToolStripPanel control [Windows Forms], using for MDI
- toolbars [Windows Forms], using for MDI
ms.assetid: d6b884fc-0846-465f-83c3-5dc0fe93b00f
ms.openlocfilehash: e0565bc106982a9c2972c40291a9c30b74f95527
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54729852"
---
# <a name="how-to-use-toolstrippanels-for-mdi"></a>Vorgehensweise: Verwenden von ToolStripPanels für MDI
Das <xref:System.Windows.Forms.ToolStripPanel> bietet die Flexibilität für MDI-Anwendungen (Multiple Document Interface), indem die <xref:System.Windows.Forms.ToolStripPanel.Join%2A>-Methode verwendet wird.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie Sie <xref:System.Windows.Forms.ToolStripPanel>-Steuerelemente für MDI verwenden können.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#10)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#10)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System.Design", "System.Drawing" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.  Weitere Informationen hierzu finden Sie auch unter [Gewusst wie: Kompilieren und Ausführen einer vollständigen Windows Forms-Codebeispiels mit Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.ToolStripPanel>
- [Vorgehensweise: Verknüpfen von ToolStripPanels](../../../../docs/framework/winforms/controls/how-to-join-toolstrippanels.md)
