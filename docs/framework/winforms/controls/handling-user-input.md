---
title: Behandeln von Benutzereingaben
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
helpviewer_keywords:
- custom controls [Windows Forms], user input using code
- custom controls [Windows Forms], keyboard events using code
- custom controls [Windows Forms], mouse events using code
ms.assetid: d9b12787-86f6-4022-8e0f-e12d312c4af2
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7c3da2c4661acdb358c38fb871de70fd470f7991
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="handling-user-input"></a>Behandeln von Benutzereingaben
Dieses Thema beschreibt die wichtigsten Tastatur und Maus Ereignisse, die von bereitgestellten <xref:System.Windows.Forms.Control?displayProperty=nameWithType>. Beim Bearbeiten eines Ereignisses sollten Autoren von Steuerelementen die geschützte Methode `On`*EventName* überschreiben, statt einen Delegaten an das Ereignis anzuhängen. Zum Überprüfen der Ereignisse siehe [Auslösen von Ereignissen aus einer Komponente](http://msdn.microsoft.com/library/9aebf605-a87d-470b-b7c8-f9abfc8360a0).  
  
> [!NOTE]
>  Wenn es keine Daten, die einem Ereignis, eine Instanz der Basisklasse zugeordneten sind <xref:System.EventArgs> wird als Argument übergeben, die `On` *EventName* Methode.  
  
## <a name="keyboard-events"></a>Tastaturereignisse  
 Der Standardtastaturereignisse, die das Steuerelement behandeln kann sind <xref:System.Windows.Forms.Control.KeyDown>, <xref:System.Windows.Forms.Control.KeyPress>, und <xref:System.Windows.Forms.Control.KeyUp>.  
  
|Ereignisname|Zu überschreibende Methode|Beschreibung des Ereignisses|  
|----------------|------------------------|--------------------------|  
|`KeyDown`|`void OnKeyDown(KeyEventArgs)`|Wird nur ausgelöst, wenn anfangs eine Taste gedrückt wird.|  
|`KeyPress`|`void OnKeyPress`<br /><br /> `(KeyPressEventArgs)`|Wird jedes Mal ausgelöst, wenn eine Taste gedrückt wird. Wenn eine Taste gedrückt gehalten wird, wird ein <xref:System.Windows.Forms.Control.KeyPress> Ereignis wird vom Betriebssystem definierten Wiederholungsrate.|  
|`KeyUp`|`void OnKeyUp(KeyEventArgs)`|Wird ausgelöst, wenn eine Taste losgelassen wird.|  
  
> [!NOTE]
>  Das Bearbeiten von Tastatureingaben ist wesentlich komplexer als das Überschreiben der Ereignisse in der obigen Tabelle und würde Rahmen dieses Themas sprengen. Weitere Informationen finden Sie unter [Benutzereingaben in Windows Forms](../../../../docs/framework/winforms/user-input-in-windows-forms.md).  
  
## <a name="mouse-events"></a>Mausereignisse  
 Die Mausereignisse, die das Steuerelement behandeln kann, sind <xref:System.Windows.Forms.Control.MouseDown>, <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseHover>, <xref:System.Windows.Forms.Control.MouseLeave>, <xref:System.Windows.Forms.Control.MouseMove>, und <xref:System.Windows.Forms.Control.MouseUp>.  
  
|Ereignisname|Zu überschreibende Methode|Beschreibung des Ereignisses|  
|----------------|------------------------|--------------------------|  
|`MouseDown`|`void OnMouseDown(MouseEventArgs)`|Wird ausgelöst, wenn sich der Mauszeiger über dem Steuerelement befindet und eine Maustaste gedrückt wird.|  
|`MouseEnter`|`void OnMouseEnter(EventArgs)`|Wird ausgelöst, wenn der Mauszeiger zunächst auf den Bereich des Steuerelements trifft.|  
|`MouseHover`|`void OnMouseHover(EventArgs)`|Wird ausgelöst, wenn der Mauszeiger über das Steuerelement bewegt wird.|  
|`MouseLeave`|`void OnMouseLeave(EventArgs)`|Wird ausgelöst, wenn der Mauszeiger den Bereich des Steuerelements verlässt.|  
|`MouseMove`|`void OnMouseMove(MouseEventArgs)`|Wird ausgelöst, wenn der Mauszeiger in den Bereich des Steuerelements wechselt.|  
|`MouseUp`|`void OnMouseUp(MouseEventArgs)`|Wird ausgelöst, wenn die Maustaste losgelassen wird, während sich der Mauszeiger über dem Steuerelement befindet oder den Bereich des Steuerelements verlässt.|  
  
 Das folgende Codefragment zeigt ein Beispiel zum Überschreiben der <xref:System.Windows.Forms.Control.MouseDown> Ereignis.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#7)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#7)]  
  
 Das folgende Codefragment zeigt ein Beispiel zum Überschreiben der <xref:System.Windows.Forms.Control.MouseMove> Ereignis.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#8)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#8)]  
  
 Das folgende Codefragment zeigt ein Beispiel zum Überschreiben der <xref:System.Windows.Forms.Control.MouseUp> Ereignis.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#9)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#9)]  
  
 Für den vollständigen Quellencode für das `FlashTrackBar`-Beispiel siehe [Vorgehensweise: Erstellen eines Windows Forms-Steuerelement, das den Fortschritt anzeigt](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Ereignisse in Windows Forms-Steuerelementen](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)  
 [Definieren eines Ereignisses](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)  
 [Ereignisse](../../../../docs/standard/events/index.md)  
 [Benutzereingaben in Windows Forms](../../../../docs/framework/winforms/user-input-in-windows-forms.md)
