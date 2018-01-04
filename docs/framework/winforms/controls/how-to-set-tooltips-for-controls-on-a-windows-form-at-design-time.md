---
title: "Gewusst wie: Festlegen von QuickInfos für Steuerelemente auf einem Windows Form zur Entwurfszeit"
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
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b296dc6ce929733d6e076cfa676ea6ab5624f45c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a>Gewusst wie: Festlegen von QuickInfos für Steuerelemente auf einem Windows Form zur Entwurfszeit
Sie können festlegen, eine <xref:System.Windows.Forms.ToolTip> Zeichenfolge im Code oder in Windows Forms-Designer. Weitere Informationen zu den <xref:System.Windows.Forms.ToolTip> Komponente finden Sie unter [Übersicht über die ToolTip-Komponente](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-set-a-tooltip-programmatically"></a>So legen Sie eine QuickInfo programmgesteuert fest  
  
1.  Fügen Sie das Steuerelement, das in der QuickInfo angezeigt wird.  
  
2.  Verwenden der <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> Methode der <xref:System.Windows.Forms.ToolTip> Komponente.  
  
    ```vb  
    ' In this example, Button1 is the control to display the ToolTip.  
    ToolTip1.SetToolTip(Button1, "Save changes")  
    ```  
  
    ```csharp  
    // In this example, button1 is the control to display the ToolTip.  
    toolTip1.SetToolTip(button1, "Save changes");  
    ```  
  
    ```cpp  
    // In this example, button1 is the control to display the ToolTip.  
    toolTip1->SetToolTip(button1, "Save changes");  
    ```  
  
### <a name="to-set-a-tooltip-in-the-designer"></a>Um eine QuickInfo im Designer festgelegt.  
  
1.  Fügen Sie eine <xref:System.Windows.Forms.ToolTip>-Komponente zum Formular hinzu.  
  
2.  Wählen Sie das Steuerelement, das die QuickInfo angezeigt werden, oder fügen es in das Formular.  
  
3.  In der **Eigenschaften** legen die **QuickInfo auf ToolTip1** Wert in eine entsprechende Zeichenfolge des Texts.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die ToolTip-Komponente](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md)  
 [Gewusst wie: Ändern der Verzögerung der ToolTip-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)  
 [ToolTip-Komponente](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)
