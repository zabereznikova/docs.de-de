---
title: 'Vorgehensweise: Festlegen von QuickInfos für Steuerelemente auf einem Windows Form zur Entwurfszeit'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
ms.openlocfilehash: cc8f8c620516a943d6d70187e19b72f5a2a99888
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59301333"
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a>Vorgehensweise: Festlegen von QuickInfos für Steuerelemente auf einem Windows Form zur Entwurfszeit
Sie können festlegen, eine <xref:System.Windows.Forms.ToolTip> Zeichenfolge im Code oder in der Windows Forms-Designer. Weitere Informationen zu den <xref:System.Windows.Forms.ToolTip> Komponente finden Sie unter [Übersicht über die ToolTip-Komponente](tooltip-component-overview-windows-forms.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-set-a-tooltip-programmatically"></a>So legen Sie eine QuickInfo programmgesteuert fest  
  
1. Fügen Sie das Steuerelement, das die QuickInfo angezeigt wird.  
  
2. Verwenden der <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> Methode der <xref:System.Windows.Forms.ToolTip> Komponente.  
  
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
  
### <a name="to-set-a-tooltip-in-the-designer"></a>Festlegen eine QuickInfo im designer  
  
1. Fügen Sie eine <xref:System.Windows.Forms.ToolTip>-Komponente zum Formular hinzu.  
  
2. Wählen Sie das Steuerelement, das die QuickInfo angezeigt, oder fügen Sie es dem Formular hinzu.  
  
3. In der **Eigenschaften** legen die **QuickInfo auf ToolTip1** Wert, der eine entsprechende Zeichenfolge des Texts.  

### <a name="to-remove-a-tooltip-programmatically"></a>Das programmgesteuerte Entfernen von einer QuickInfo  
  
1. Verwenden der <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> Methode der <xref:System.Windows.Forms.ToolTip> Komponente.  
  
    ```vb  
    ' In this example, Button1 is the control displaying the ToolTip.  
    ToolTip1.SetToolTip(Button1, Nothing)  
    ```  
  
    ```csharp  
    // In this example, button1 is the control displaying the ToolTip.  
    toolTip1.SetToolTip(button1, null);  
    ```  
  
    ```cpp  
    // In this example, button1 is the control displaying the ToolTip.  
    toolTip1->SetToolTip(button1, NULL);  
    ```  
  
### <a name="to-remove-a-tooltip-in-the-designer"></a>So entfernen Sie eine QuickInfo im designer  
  
1. Wählen Sie das Steuerelement, das die QuickInfo angezeigt wird.  
  
2. In der **Eigenschaften** Fenster, löschen Sie den Text in die **QuickInfo auf ToolTip1**.  

## <a name="see-also"></a>Siehe auch

- [Übersicht über die ToolTip-Komponente](tooltip-component-overview-windows-forms.md)
- [Vorgehensweise: Ändern der Verzögerung der ToolTip-Komponente in Windows Forms](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
- [ToolTip-Komponente](tooltip-component-windows-forms.md)
