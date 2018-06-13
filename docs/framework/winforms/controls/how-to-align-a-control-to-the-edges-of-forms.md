---
title: 'Gewusst wie: Ausrichten eines Steuerelements an Formularrändern'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dock property [Windows Forms], aligning controls (using code)
- forms [Windows Forms], aligning controls
- controls [Windows Forms], aligning on forms
- custom controls [Windows Forms], docking using code
ms.assetid: 5994cb59-242b-4e75-bd0e-62879c34d702
ms.openlocfilehash: a8571f668de2714511a8732772443a8897043cf2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526513"
---
# <a name="how-to-align-a-control-to-the-edges-of-forms"></a>Gewusst wie: Ausrichten eines Steuerelements an Formularrändern
Sie können ein Steuerelement am Formularrand ausrichten, indem Sie die <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft festlegen. Diese Eigenschaft legt fest, wo auf dem Formular das Steuerelement sich befindet. Die <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft kann auf einen der folgenden Werte festgelegt werden:  
  
|Einstellung|Auswirkung auf das Steuerelement|  
|-------------|----------------------------|  
|<xref:System.Windows.Forms.DockStyle.Bottom>|Wird im unteren Bereich des Formulars angedockt.|  
|<xref:System.Windows.Forms.DockStyle.Fill>|Füllt den gesamten verbleibenden Platz im Formular aus.|  
|<xref:System.Windows.Forms.DockStyle.Left>|Wird an der linken Seite des Formulars angedockt.|  
|<xref:System.Windows.Forms.DockStyle.None>|Wird nicht angedockt und wird an der mit der <xref:System.Windows.Forms.Control.Location%2A>-Eigenschaft angegebenen Position angezeigt.|  
|<xref:System.Windows.Forms.DockStyle.Right>|Wird an der rechten Seite des Formulars angedockt.|  
|<xref:System.Windows.Forms.DockStyle.Top>|Wird im oberen Bereich des Formulars angedockt.|  
  
 Diese Funktion wird zur Entwurfszeit in Visual Studio unterstützt.  
  
### <a name="to-set-the-dock-property-for-your-control-at-run-time"></a>So legen Sie die Dock-Eigenschaft für das Steuerelement zur Laufzeit fest  
  
1.  Legen Sie die <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft im Code auf den geeigneten Wert fest.  
  
    ```vb  
    ' To set the Dock property internally.  
    Me.Dock = DockStyle.Top  
    ' To set the Dock property from another object.  
    UserControl1.Dock = DockStyle.Top  
    ```  
  
    ```csharp  
    // To set the Dock property internally.  
    this.Dock = DockStyle.Top;  
    // To set the Dock property from another object.  
    UserControl1.Dock = DockStyle.Top;  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType>  
 [Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [Gewusst wie: Verankern und Andocken von untergeordneten Steuerelementen in einem FlowLayoutPanel-Steuerelement](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)  
 [Gewusst wie: Verankern und Andocken von untergeordneten Steuerelementen in einem TableLayoutPanel-Steuerelement](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [Übersicht über die AutoSize-Eigenschaft](../../../../docs/framework/winforms/controls/autosize-property-overview.md)
