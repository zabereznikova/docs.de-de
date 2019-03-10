---
title: 'Vorgehensweise: Ausblenden des Steuerelements zur Laufzeit'
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
ms.openlocfilehash: 52ea2336bac1ec483cb86e24114090a1b3725038
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708976"
---
# <a name="how-to-make-your-control-invisible-at-run-time"></a>Vorgehensweise: Ausblenden des Steuerelements zur Laufzeit
Es gibt Situationen, wenn Sie möchten möglicherweise ein Benutzersteuerelement zu erstellen, die zur Laufzeit nicht sichtbar ist. Beispielsweise, ein Steuerelement, das einen Wecker ist möglicherweise nicht sichtbar, außer wenn der Wecker klingelt wurde. Dies erfolgt einfach durch Festlegen der <xref:System.Windows.Forms.Control.Visible%2A> Eigenschaft. Wenn die <xref:System.Windows.Forms.Control.Visible%2A> Eigenschaft `true`, das Steuerelement wird normal angezeigt. Wenn `false`, das Steuerelement ausgeblendet wird. Obwohl Code in das Steuerelement beim unsichtbar weiterhin ausgeführt werden kann, werden Sie nicht über die Benutzeroberfläche mit dem Steuerelement interagieren können. Wenn Sie ein Steuerelement zu erstellen, das immer noch auf Benutzereingaben (z. B. Mausklicks) reagiert möchten, sollten Sie transparentes Steuerelement erstellen. Weitere Informationen finden Sie unter [Verwenden eines transparenten Hintergrunds für ein Steuerelement](how-to-give-your-control-a-transparent-background.md).  
  
### <a name="to-make-your-control-invisible-at-run-time"></a>Um das Steuerelement zur Laufzeit unsichtbar zu machen  
  
1.  Legen Sie die <xref:System.Windows.Forms.Control.Visible%2A> -Eigenschaft auf `false`fest.  
  
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
- <xref:System.Windows.Forms.Control.Visible%2A>
- [Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework](developing-custom-windows-forms-controls.md)
- [Vorgehensweise: Fügen Sie dem Steuerelement einen transparenten Hintergrund](how-to-give-your-control-a-transparent-background.md)
