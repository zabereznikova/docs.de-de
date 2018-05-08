---
title: 'Gewusst wie: Ausblenden des Steuerelements zur Laufzeit'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], making invisible at run time
- invisible controls
- user controls [Windows Forms], invisible
- custom controls [Windows Forms], invisible
- run time [Windows Forms], making controls invisible
ms.assetid: 69eb2e72-32f5-4f79-a157-c2c5f60c1628
ms.openlocfilehash: 51e804c7f01b55ed7504837042b6c32bf47d9405
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-make-your-control-invisible-at-run-time"></a>Gewusst wie: Ausblenden des Steuerelements zur Laufzeit
Es gibt Situationen, wenn Sie möchten möglicherweise ein benutzerdefiniertes Steuerelement zu erstellen, die zur Laufzeit nicht sichtbar ist. Ein Steuerelement, das einen Wecker möglicherweise z. B. nicht sichtbar, außer wenn das Warnsignal. Dies erfolgt einfach durch Festlegen der <xref:System.Windows.Forms.Control.Visible%2A> Eigenschaft. Wenn die <xref:System.Windows.Forms.Control.Visible%2A> Eigenschaft `true`, erscheint das Steuerelement wie gewohnt. Wenn `false`, wird das Steuerelement ausgeblendet werden. Obwohl Code in das Steuerelement beim unsichtbar weiter ausgeführt werden kann, werden Sie nicht mit dem Steuerelement über die Benutzeroberfläche interagieren können. Wenn Sie ein Steuerelement erstellen, das weiterhin auf eine Benutzereingabe (z. B. Mausklicks) reagiert möchten, sollten Sie ein transparente Steuerelement erstellen. Weitere Informationen finden Sie unter [Verwenden eines transparenten Hintergrunds für ein Steuerelement](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md).  
  
### <a name="to-make-your-control-invisible-at-run-time"></a>Um das Steuerelement zur Laufzeit unsichtbar zu machen  
  
1.  Legen Sie die <xref:System.Windows.Forms.Control.Visible%2A>-Eigenschaft auf `false` fest.  
  
    ```vb  
    ' To set the Visible property from within your object's own code.  
    Me.Visible = False  
    ' To set the Visible property from another object.  
    myControl1.Visible = False  
    ```  
  
    ```csharp  
    // To set the Visible property from within your object's own code.  
    this.Visible = false;  
    // To set the Visible property from another object.  
    myControl1.Visible = false;  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Control.Visible%2A>  
 [Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [Gewusst wie: Verwenden eines transparenten Hintergrunds für ein Steuerelement](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)
