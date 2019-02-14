---
title: 'Vorgehensweise: Verknüpfen von ToolStripPanels'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], joining together
- ToolStripPanel control [Windows Forms], joining together
ms.assetid: 4eadda6d-e3b8-4151-aaf2-a8d564fbe6b3
ms.openlocfilehash: cebfcb417dc011ed8990e9d536cd165c2a92cb68
ms.sourcegitcommit: af0a22a4eb11bbcd33baec49150d551955b50a16
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2019
ms.locfileid: "56260737"
---
# <a name="how-to-join-toolstrippanels"></a>Vorgehensweise: Verknüpfen von ToolStripPanels
Sie können <xref:System.Windows.Forms.ToolStrip>-Steuerelemente zur Laufzeit mit einer <xref:System.Windows.Forms.ToolStripPanel>-Instanz verknüpfen, wodurch Sie die Flexibilität von MDI-Anwendungen (Multiple Document Interface, Schnittstelle für mehrere Dokumente) erhalten.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie <xref:System.Windows.Forms.ToolStrip>-Steuerelemente mit einer <xref:System.Windows.Forms.ToolStripPanel>-Instanz verknüpft werden.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#11)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#11)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System.Design", "System.Drawing" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripPanel>
- [Vorgehensweise: Verwenden von ToolStripPanels für MDI](../../../../docs/framework/winforms/controls/how-to-use-toolstrippanels-for-mdi.md)
