---
title: 'Vorgehensweise: Fügen Sie dem Steuerelement einen transparenten Hintergrund'
ms.date: 03/30/2017
helpviewer_keywords:
- transparent backgrounds [Windows Forms], custom controls
- custom controls [Windows Forms], transparent background
- transparency [Windows Forms], Windows Forms custom controls
ms.assetid: 32433e63-f4e9-4305-9857-6de3edeb944a
ms.openlocfilehash: 5a54b76eb92c7d3f518b9bf13e154e6faf58de63
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718167"
---
# <a name="how-to-give-your-control-a-transparent-background"></a>Vorgehensweise: Fügen Sie dem Steuerelement einen transparenten Hintergrund
In früheren Versionen von .NET Framework wird für Steuerelemente ein Festlegen auf transparente Hintergrundfarben nur dann unterstützt, wenn zunächst die <xref:System.Windows.Forms.Control.SetStyle%2A> -Methode im Konstruktor der Formulare festgelegt wurde. In der aktuellen Framework-Version kann die Hintergrundfarbe für die meisten Steuerelemente zur Entwurfszeit im Fenster <xref:System.Drawing.Color.Transparent%2A> Eigenschaften **oder in Code im Konstruktor des Formulars auf** festgelegt werden.  
  
> [!NOTE]
>  Windows Forms-Steuerelemente unterstützen keine echte Transparenz. Der Hintergrund eines transparenten Windows Forms-Steuerelements wird von seinem übergeordneten Element gezeichnet.  
  
> [!NOTE]
>  Das <xref:System.Windows.Controls.Button> -Steuerelement unterstützt keine transparente Hintergrundfarbe, selbst wenn die <xref:System.Windows.Forms.ButtonBase.BackColor%2A> -Eigenschaft auf <xref:System.Drawing.Color.Transparent%2A>festgelegt ist.  
  
### <a name="to-give-your-control-a-transparent-backcolor"></a>So weisen Sie dem Steuerelement eine transparente Hintergrundfarbe zu  
  
-   Wählen Sie im Eigenschaftenfenster die <xref:System.Windows.Forms.ButtonBase.BackColor%2A> -Eigenschaft aus, und legen Sie diese auf <xref:System.Drawing.Color.Transparent%2A>fest.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Drawing.Color.FromArgb%2A>
- [Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework](developing-custom-windows-forms-controls.md)
- [Verwenden von verwalteten Grafikklassen](../advanced/using-managed-graphics-classes.md)
- [Vorgehensweise: Zeichnen Sie deckender und halbtransparente Linien](../advanced/how-to-draw-opaque-and-semitransparent-lines.md)
