---
title: "Gewusst wie: Dynamisches Hinzufügen von ToolStrip-Elementen"
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
- ContextMenuStrip control [Windows Forms]
- toolbars [Windows Forms], adding items dynamically
- ToolStrip control [Windows Forms]
ms.assetid: 0e8dea56-5f46-408b-914d-7e360341a234
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c7287365013ecd32d5ade6fa61d6c13364ce9b97
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-toolstrip-items-dynamically"></a>Gewusst wie: Dynamisches Hinzufügen von ToolStrip-Elementen
Sie können die Auflistung von Menüelementen eines <xref:System.Windows.Forms.ToolStrip>-Steuerelements dynamisch ausfüllen, wenn das Menü geöffnet wird.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie Elemente einem <xref:System.Windows.Forms.ContextMenuStrip>-Steuerelement dynamisch hinzufügt werden. Außerdem wird gezeigt, wie Sie die gleiche <xref:System.Windows.Forms.ContextMenuStrip> für drei verschiedene Steuerelemente im Formular wiederverwenden.  
  
 Im Beispiel füllt ein <xref:System.Windows.Forms.ToolStripDropDown.Opening>-Ereignishandler die Auflistung von Menüelementen aus. Der <xref:System.Windows.Forms.ToolStripDropDown.Opening>-Ereignishandler überprüft die <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A?displayProperty=nameWithType> und die <xref:System.Windows.Forms.ToolStripItem.OwnerItem%2A?displayProperty=nameWithType>-Eigenschaften und fügt eine <xref:System.Windows.Forms.ToolStripItem> hinzu, die die Quellcodeverwaltung beschreibt.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#40)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#40)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys ""System.Drawing" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] finden Sie unter [Erstellen von der Befehlszeile aus](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Erstellen über die Befehlszeile mit „csc.exe“](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripItem>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 <xref:System.Windows.Forms.ToolStripDropDownButton>  
 [ToolStrip-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
