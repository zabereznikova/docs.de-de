---
title: 'Gewusst wie: Hinzufügen von ToolStripContainer zu einem Formular'
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
- toolbars [Windows Forms], built-in rafting
- ToolStrip control [Windows Forms], built-in rafting
- ToolStripContainer control [Windows Forms], adding to Windows Forms
ms.assetid: d0f55095-a833-453e-be5a-644906d75d54
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d0da8f1363a4dd1bfaa3dec9dd2a1db6e22191b3
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-add-a-toolstripcontainer-to-a-form"></a>Gewusst wie: Hinzufügen von ToolStripContainer zu einem Formular
Sie können einer Windows Form programmgesteuert einen <xref:System.Windows.Forms.ToolStripContainer> hinzufügen und diesen mit Steuerelementen füllen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel zeigt, wie einer Windows Form ein <xref:System.Windows.Forms.ToolStripContainer> und ein <xref:System.Windows.Forms.ToolStrip> hinzugefügt wird, wie dem <xref:System.Windows.Forms.ToolStrip> Elemente hinzugefügt werden und wie der <xref:System.Windows.Forms.ToolStrip> zum <xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A> des <xref:System.Windows.Forms.ToolStripContainer> hinzugefügt wird.  
  
 [!code-csharp[System.Windows.Forms.ToolStripContainer2#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.toolstripcontainer2/cs/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStripContainer2#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.toolstripcontainer2/vb/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Codebeispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System.Drawing", "System.Text" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch [Vorgehensweise: Kompilieren und Ausführen eines vollständigen Windows Forms-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)) oder [Dialogfeld „ToolStripContainer-Aufgaben“](http://msdn.microsoft.com/library/ms233647\(v=vs.110\)).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ToolStripContainer>  
 [ToolStripContainer-Steuerelement](../../../../docs/framework/winforms/controls/toolstripcontainer-control.md)  
 [ToolStrip-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
