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
ms.openlocfilehash: a1129e3778763a4e2cd06759c5a5ad7656244934
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720973"
---
# <a name="handling-user-input"></a>Behandeln von Benutzereingaben
In diesem Thema wird beschrieben, die wichtigsten Tastatur- und Mausereignisse Ereignisse gebotenen <xref:System.Windows.Forms.Control?displayProperty=nameWithType>. Beim Bearbeiten eines Ereignisses sollten Autoren von Steuerelementen die geschützte Methode `On`*EventName* überschreiben, statt einen Delegaten an das Ereignis anzuhängen. Zum Überprüfen der Ereignisse siehe [Auslösen von Ereignissen aus einer Komponente](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).  
  
> [!NOTE]
>  Wenn es keine Daten, die einem Ereignis, eine Instanz der Basisklasse zugeordneten sind <xref:System.EventArgs> wird als Argument übergeben, die `On` *EventName* Methode.  
  
## <a name="keyboard-events"></a>Tastaturereignisse  
 Sind die allgemeinen Tastaturereignisse, die das Steuerelement bearbeiten <xref:System.Windows.Forms.Control.KeyDown>, <xref:System.Windows.Forms.Control.KeyPress>, und <xref:System.Windows.Forms.Control.KeyUp>.  
  
|Ereignisname|Zu überschreibende Methode|Beschreibung des Ereignisses|  
|----------------|------------------------|--------------------------|  
|`KeyDown`|`void OnKeyDown(KeyEventArgs)`|Wird nur ausgelöst, wenn anfangs eine Taste gedrückt wird.|  
|`KeyPress`|`void OnKeyPress`<br /><br /> `(KeyPressEventArgs)`|Wird jedes Mal ausgelöst, wenn eine Taste gedrückt wird. Wenn eine Taste gedrückt gehalten wird, wird eine <xref:System.Windows.Forms.Control.KeyPress> Ereignis wird ausgelöst, auf die vom Betriebssystem definierten Wiederholungsrate.|  
|`KeyUp`|`void OnKeyUp(KeyEventArgs)`|Wird ausgelöst, wenn eine Taste losgelassen wird.|  
  
> [!NOTE]
>  Das Bearbeiten von Tastatureingaben ist wesentlich komplexer als das Überschreiben der Ereignisse in der obigen Tabelle und würde Rahmen dieses Themas sprengen. Weitere Informationen finden Sie unter [Benutzereingaben in Windows Forms](../user-input-in-windows-forms.md).  
  
## <a name="mouse-events"></a>Mausereignisse  
 Die Mausereignisse, die das Steuerelement behandeln kann sind <xref:System.Windows.Forms.Control.MouseDown>, <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseHover>, <xref:System.Windows.Forms.Control.MouseLeave>, <xref:System.Windows.Forms.Control.MouseMove>, und <xref:System.Windows.Forms.Control.MouseUp>.  
  
|Ereignisname|Zu überschreibende Methode|Beschreibung des Ereignisses|  
|----------------|------------------------|--------------------------|  
|`MouseDown`|`void OnMouseDown(MouseEventArgs)`|Wird ausgelöst, wenn sich der Mauszeiger über dem Steuerelement befindet und eine Maustaste gedrückt wird.|  
|`MouseEnter`|`void OnMouseEnter(EventArgs)`|Wird ausgelöst, wenn der Mauszeiger zunächst auf den Bereich des Steuerelements trifft.|  
|`MouseHover`|`void OnMouseHover(EventArgs)`|Wird ausgelöst, wenn der Mauszeiger über das Steuerelement bewegt wird.|  
|`MouseLeave`|`void OnMouseLeave(EventArgs)`|Wird ausgelöst, wenn der Mauszeiger den Bereich des Steuerelements verlässt.|  
|`MouseMove`|`void OnMouseMove(MouseEventArgs)`|Wird ausgelöst, wenn der Mauszeiger in den Bereich des Steuerelements wechselt.|  
|`MouseUp`|`void OnMouseUp(MouseEventArgs)`|Wird ausgelöst, wenn die Maustaste losgelassen wird, während sich der Mauszeiger über dem Steuerelement befindet oder den Bereich des Steuerelements verlässt.|  
  
 Das folgende Codefragment zeigt ein Beispiel zum Überschreiben der <xref:System.Windows.Forms.Control.MouseDown> Ereignis.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#7)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#7)]  
  
 Das folgende Codefragment zeigt ein Beispiel zum Überschreiben der <xref:System.Windows.Forms.Control.MouseMove> Ereignis.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#8](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#8)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#8](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#8)]  
  
 Das folgende Codefragment zeigt ein Beispiel zum Überschreiben der <xref:System.Windows.Forms.Control.MouseUp> Ereignis.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#9)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#9)]  
  
 Für den vollständigen Quellcode für die `FlashTrackBar` zugreifen können, finden Sie unter [Vorgehensweise: Erstellen ein Windows Forms-Steuerelements, die Status anzeigt](how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
## <a name="see-also"></a>Siehe auch
- [Ereignisse in Windows Forms-Steuerelementen](events-in-windows-forms-controls.md)
- [Definieren eines Ereignisses](defining-an-event-in-windows-forms-controls.md)
- [Ereignisse](../../../standard/events/index.md)
- [Benutzereingaben in Windows Forms](../user-input-in-windows-forms.md)
