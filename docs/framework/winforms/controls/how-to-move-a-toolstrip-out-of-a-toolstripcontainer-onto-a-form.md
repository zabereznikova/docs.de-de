---
title: 'Gewusst wie: Verschieben eines ToolStrip aus einem ToolStripContainer auf ein Formular'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], parenting to forms
- Windows Forms, parenting ToolStrip controls
ms.assetid: a1c94a7f-6fc5-4e4c-84cf-ff11dc573d33
ms.openlocfilehash: a4b6e3bbc0750ba69607b5c0f96bdbb542aea1be
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43424092"
---
# <a name="how-to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a>Gewusst wie: Verschieben eines ToolStrip aus einem ToolStripContainer auf ein Formular
Verwenden Sie das folgende Verfahren zum Verschieben einer <xref:System.Windows.Forms.ToolStrip> aus einem <xref:System.Windows.Forms.ToolStripContainer> auf ein Formular.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a>Verschieben ein ToolStrip aus einem ToolStripContainer auf ein Formular  
  
1.  Wählen Sie das <xref:System.Windows.Forms.ToolStrip>-Steuerelement aus.  
  
2.  Ausschneiden der <xref:System.Windows.Forms.ToolStrip> durch Drücken von STRG + X oder mit der rechten Maustaste die <xref:System.Windows.Forms.ToolStrip> , und wählen Sie **Ausschneiden** aus dem Kontextmenü.  
  
3.  Wählen Sie das Formular.  
  
4.  Fügen Sie der <xref:System.Windows.Forms.ToolStrip> durch Drücken von STRG + V, oder wählen Sie **einfügen** aus der **bearbeiten** Menü.  
  
5.  Legen Sie die <xref:System.Windows.Forms.ToolStrip.Dock%2A> Eigenschaft der <xref:System.Windows.Forms.ToolStrip> zu **oben**.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripContainer>  
 [Übersicht über das ToolStrip-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
