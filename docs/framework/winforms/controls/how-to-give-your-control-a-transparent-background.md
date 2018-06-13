---
title: 'Gewusst wie: Verwenden eines transparenten Hintergrunds für ein Steuerelement'
ms.date: 03/30/2017
helpviewer_keywords:
- transparent backgrounds [Windows Forms], custom controls
- custom controls [Windows Forms], transparent background
- transparency [Windows Forms], Windows Forms custom controls
ms.assetid: 32433e63-f4e9-4305-9857-6de3edeb944a
ms.openlocfilehash: ad814c9179fd33955fe4df2666f8a47606bfbff0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33531816"
---
# <a name="how-to-give-your-control-a-transparent-background"></a>Gewusst wie: Verwenden eines transparenten Hintergrunds für ein Steuerelement
In früheren Versionen von .NET Framework wird für Steuerelemente ein Festlegen auf transparente Hintergrundfarben nur dann unterstützt, wenn zunächst die <xref:System.Windows.Forms.Control.SetStyle%2A> -Methode im Konstruktor der Formulare festgelegt wurde. In der aktuellen Framework-Version kann die Hintergrundfarbe für die meisten Steuerelemente zur Entwurfszeit im Fenster <xref:System.Drawing.Color.Transparent%2A> Eigenschaften **oder in Code im Konstruktor des Formulars auf** festgelegt werden.  
  
> [!NOTE]
>  Windows Forms-Steuerelemente unterstützen keine echte Transparenz. Der Hintergrund eines transparenten Windows Forms-Steuerelements wird von seinem übergeordneten Element gezeichnet.  
  
> [!NOTE]
>  Das <xref:System.Windows.Controls.Button> -Steuerelement unterstützt keine transparente Hintergrundfarbe, selbst wenn die <xref:System.Windows.Forms.ButtonBase.BackColor%2A> -Eigenschaft auf <xref:System.Drawing.Color.Transparent%2A>festgelegt ist.  
  
### <a name="to-give-your-control-a-transparent-backcolor"></a>So weisen Sie dem Steuerelement eine transparente Hintergrundfarbe zu  
  
-   Wählen Sie im Eigenschaftenfenster die <xref:System.Windows.Forms.ButtonBase.BackColor%2A> -Eigenschaft aus, und legen Sie diese auf <xref:System.Drawing.Color.Transparent%2A>fest.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.Color.FromArgb%2A>  
 [Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [Verwenden von verwalteten Grafikklassen](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)  
 [Gewusst wie: Zeichnen deckender und halbtransparenter Linien](../../../../docs/framework/winforms/advanced/how-to-draw-opaque-and-semitransparent-lines.md)
