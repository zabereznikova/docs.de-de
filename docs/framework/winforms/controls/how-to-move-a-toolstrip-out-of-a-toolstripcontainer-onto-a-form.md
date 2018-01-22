---
title: 'Gewusst wie: Verschieben eines ToolStrip aus einem ToolStripContainer auf ein Formular'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ToolStrip control [Windows Forms], parenting to forms
- Windows Forms, parenting ToolStrip controls
ms.assetid: a1c94a7f-6fc5-4e4c-84cf-ff11dc573d33
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 97d65abf38ee434218fa9bec0d8a9cade31fb687
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a>Gewusst wie: Verschieben eines ToolStrip aus einem ToolStripContainer auf ein Formular
Verwenden Sie das folgende Verfahren zum Verschieben einer <xref:System.Windows.Forms.ToolStrip> aus einem <xref:System.Windows.Forms.ToolStripContainer> auf ein Formular.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a>Verschieben ein ToolStrip aus einem ToolStripContainer auf ein Formular  
  
1.  Wählen Sie das <xref:System.Windows.Forms.ToolStrip>-Steuerelement aus.  
  
2.  Ausschneiden der <xref:System.Windows.Forms.ToolStrip> durch Drücken von STRG + X drücken oder mit der rechten Maustaste die <xref:System.Windows.Forms.ToolStrip> , und wählen Sie **Ausschneiden** aus dem Kontextmenü.  
  
3.  Wählen Sie das Formular aus.  
  
4.  Fügen Sie der <xref:System.Windows.Forms.ToolStrip> durch Drücken von STRG + V, oder wählen Sie **einfügen** aus der **bearbeiten** Menü.  
  
5.  Festlegen der <xref:System.Windows.Forms.ToolStrip.Dock%2A> Eigenschaft von der <xref:System.Windows.Forms.ToolStrip> auf **oben**.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripContainer>  
 [Übersicht über das ToolStrip-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
