---
title: Behandeln von Benutzereingaben
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], user input using code
- custom controls [Windows Forms], keyboard events using code
- custom controls [Windows Forms], mouse events using code
ms.assetid: d9b12787-86f6-4022-8e0f-e12d312c4af2
ms.openlocfilehash: f92b742c3f6feec72e5b3150204d7d984636281d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934092"
---
# <a name="handling-user-input"></a>Behandeln von Benutzereingaben
Dieses Thema beschreibt die Haupt Tastatur-und Mausereignisse, <xref:System.Windows.Forms.Control?displayProperty=nameWithType>die von bereitgestellt werden. Beim Bearbeiten eines Ereignisses sollten Autoren von Steuerelementen die geschützte Methode `On`*EventName* überschreiben, statt einen Delegaten an das Ereignis anzuhängen. Zum Überprüfen der Ereignisse siehe [Auslösen von Ereignissen aus einer Komponente](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).  
  
> [!NOTE]
> Wenn einem Ereignis keine Daten zugeordnet sind, wird eine Instanz der Basisklasse <xref:System.EventArgs> als Argument an die `On`EventName-Methode übermittelt.  
  
## <a name="keyboard-events"></a>Tastaturereignisse  
 Die gängigen Tastatur Ereignisse, die von Ihrem Steuerelement <xref:System.Windows.Forms.Control.KeyDown>behandelt <xref:System.Windows.Forms.Control.KeyPress>werden können <xref:System.Windows.Forms.Control.KeyUp>, sind, und.  
  
|Ereignisname|Zu überschreibende Methode|Beschreibung des Ereignisses|  
|----------------|------------------------|--------------------------|  
|`KeyDown`|`void OnKeyDown(KeyEventArgs)`|Wird nur ausgelöst, wenn anfangs eine Taste gedrückt wird.|  
|`KeyPress`|`void OnKeyPress`<br /><br /> `(KeyPressEventArgs)`|Wird jedes Mal ausgelöst, wenn eine Taste gedrückt wird. Wenn eine Taste angehalten wird, wird <xref:System.Windows.Forms.Control.KeyPress> ein-Ereignis mit der Wiederholungsrate ausgelöst, die vom Betriebssystem festgelegt wird.|  
|`KeyUp`|`void OnKeyUp(KeyEventArgs)`|Wird ausgelöst, wenn eine Taste losgelassen wird.|  
  
> [!NOTE]
> Das Bearbeiten von Tastatureingaben ist wesentlich komplexer als das Überschreiben der Ereignisse in der obigen Tabelle und würde Rahmen dieses Themas sprengen. Weitere Informationen finden Sie unter [Benutzereingaben in Windows Forms](../user-input-in-windows-forms.md).  
  
## <a name="mouse-events"></a>Mausereignisse  
 Die Mausereignisse, die von Ihrem Steuerelement <xref:System.Windows.Forms.Control.MouseDown>behandelt werden können, <xref:System.Windows.Forms.Control.MouseMove>sind, <xref:System.Windows.Forms.Control.MouseUp> <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseHover>, <xref:System.Windows.Forms.Control.MouseLeave>, und.  
  
|Ereignisname|Zu überschreibende Methode|Beschreibung des Ereignisses|  
|----------------|------------------------|--------------------------|  
|`MouseDown`|`void OnMouseDown(MouseEventArgs)`|Wird ausgelöst, wenn sich der Mauszeiger über dem Steuerelement befindet und eine Maustaste gedrückt wird.|  
|`MouseEnter`|`void OnMouseEnter(EventArgs)`|Wird ausgelöst, wenn der Mauszeiger zunächst auf den Bereich des Steuerelements trifft.|  
|`MouseHover`|`void OnMouseHover(EventArgs)`|Wird ausgelöst, wenn der Mauszeiger über das Steuerelement bewegt wird.|  
|`MouseLeave`|`void OnMouseLeave(EventArgs)`|Wird ausgelöst, wenn der Mauszeiger den Bereich des Steuerelements verlässt.|  
|`MouseMove`|`void OnMouseMove(MouseEventArgs)`|Wird ausgelöst, wenn der Mauszeiger in den Bereich des Steuerelements wechselt.|  
|`MouseUp`|`void OnMouseUp(MouseEventArgs)`|Wird ausgelöst, wenn die Maustaste losgelassen wird, während sich der Mauszeiger über dem Steuerelement befindet oder den Bereich des Steuerelements verlässt.|  
  
 Das folgende Code Fragment zeigt ein Beispiel für das über <xref:System.Windows.Forms.Control.MouseDown> Schreiben des Ereignisses.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#7)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#7)]  
  
 Das folgende Code Fragment zeigt ein Beispiel für das über <xref:System.Windows.Forms.Control.MouseMove> Schreiben des Ereignisses.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#8](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#8)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#8](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#8)]  
  
 Das folgende Code Fragment zeigt ein Beispiel für das über <xref:System.Windows.Forms.Control.MouseUp> Schreiben des Ereignisses.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#9)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#9)]  
  
 Den gesamten Quellcode für das `FlashTrackBar` Beispiel finden [Sie unter Gewusst wie: Erstellt ein Windows Forms Steuerelement, das](how-to-create-a-windows-forms-control-that-shows-progress.md)den Fortschritt anzeigt.  
  
## <a name="see-also"></a>Siehe auch

- [Ereignisse in Windows Forms-Steuerelementen](events-in-windows-forms-controls.md)
- [Definieren eines Ereignisses](defining-an-event-in-windows-forms-controls.md)
- [Ereignisse](../../../standard/events/index.md)
- [Benutzereingaben in Windows Forms](../user-input-in-windows-forms.md)
