---
title: "Behandeln von Benutzereingaben | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Benutzerdefinierte Steuerelemente [Windows Forms], Tastaturereignisse mit Code"
  - "Benutzerdefinierte Steuerelemente [Windows Forms], Mausereignisse mit Code"
  - "Benutzerdefinierte Steuerelemente [Windows Forms], Benutzereingabe mit Code"
ms.assetid: d9b12787-86f6-4022-8e0f-e12d312c4af2
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Behandeln von Benutzereingaben
In diesem Thema werden die primären Tastatur\- und Mausereignisse beschrieben, die in <xref:System.Windows.Forms.Control?displayProperty=fullName> bereitgestellt werden.  Beim Behandeln eines Ereignisses sollten Autoren von Steuerelementen die geschützte `On`*EventName*\-Methode überschreiben, anstatt einen Delegaten an das Ereignis anzufügen.  Eine Übersicht über Ereignisse finden Sie unter [Raising Events from a Component](../Topic/Raising%20Events%20from%20a%20Component.md).  
  
> [!NOTE]
>  Wenn einem Ereignis keine Daten zugeordnet sind, wird eine Instanz der <xref:System.EventArgs>\-Basisklasse als Argument an die `On`*EventName*\-Methode übergeben.  
  
## Tastaturereignisse  
 Die Standardtastaturereignisse, die das Steuerelement behandeln kann, sind <xref:System.Windows.Forms.Control.KeyDown>, <xref:System.Windows.Forms.Control.KeyPress> und <xref:System.Windows.Forms.Control.KeyUp>.  
  
|Ereignisname|Zu überschreibende Methode|Ereignisbeschreibung|  
|------------------|--------------------------------|--------------------------|  
|`KeyDown`|`void OnKeyDown(KeyEventArgs)`|Wird nur ausgelöst, wenn eine Taste zum ersten Mal gedrückt wird.|  
|`KeyPress`|`void OnKeyPress`<br /><br /> `(KeyPressEventArgs)`|Wird jedes Mal ausgelöst, wenn eine Taste gedrückt wird.  Wenn eine Taste gedrückt gehalten wird, wird ein <xref:System.Windows.Forms.Control.KeyPress>\-Ereignis mit der im Betriebssystem definierten Wiederholungsrate ausgelöst.|  
|`KeyUp`|`void OnKeyUp(KeyEventArgs)`|Wird ausgelöst, wenn eine Taste losgelassen wird.|  
  
> [!NOTE]
>  Die Behandlung von Tastatureingaben ist erheblich komplexer als das Überschreiben der in der vorangehenden Tabelle angegebenen Ereignisse und geht über das hier behandelte Thema hinaus.  Weitere Informationen finden Sie unter [Benutzereingaben in Windows Forms](../../../../docs/framework/winforms/user-input-in-windows-forms.md).  
  
## Mausereignisse  
 Die Mausereignisse, die das Steuerelement behandeln kann, sind <xref:System.Windows.Forms.Control.MouseDown>, <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseHover>, <xref:System.Windows.Forms.Control.MouseLeave>, <xref:System.Windows.Forms.Control.MouseMove> und <xref:System.Windows.Forms.Control.MouseUp>.  
  
|Ereignisname|Zu überschreibende Methode|Ereignisbeschreibung|  
|------------------|--------------------------------|--------------------------|  
|`MouseDown`|`void OnMouseDown(MouseEventArgs)`|Wird ausgelöst, wenn die Maustaste gedrückt wird, während der Mauszeiger sich über dem Steuerelement befindet.|  
|`MouseEnter`|`void OnMouseEnter(EventArgs)`|Wird ausgelöst, wenn der Mauszeiger zum ersten Mal in den Bereich des Steuerelements bewegt wird.|  
|`MouseHover`|`void OnMouseHover(EventArgs)`|Wird ausgelöst, wenn der Mauszeiger auf das Steuerelement zeigt.|  
|`MouseLeave`|`void OnMouseLeave(EventArgs)`|Wird ausgelöst, wenn der Mauszeiger den Bereich des Steuerelements verlässt.|  
|`MouseMove`|`void OnMouseMove(MouseEventArgs)`|Wird ausgelöst, wenn der Mauszeiger den Bereich des Steuerelements betritt.|  
|`MouseUp`|`void OnMouseUp(MouseEventArgs)`|Wird ausgelöst, wenn die Maustaste losgelassen wird, während der Mauszeiger sich über dem Steuerelement befindet bzw. der Mauszeiger den Bereich des Steuerelements verlässt.|  
  
 Im folgenden Codefragment wird ein Beispiel für das Überschreiben des <xref:System.Windows.Forms.Control.MouseDown>\-Ereignisses gezeigt.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#7)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#7)]  
  
 Im folgenden Codefragment wird ein Beispiel für das Überschreiben des <xref:System.Windows.Forms.Control.MouseMove>\-Ereignisses gezeigt.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#8)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#8)]  
  
 Im folgenden Codefragment wird ein Beispiel für das Überschreiben des <xref:System.Windows.Forms.Control.MouseUp>\-Ereignisses gezeigt.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#9)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#9)]  
  
 Den vollständigen Quellcode für das `FlashTrackBar`\-Beispiel finden Sie unter [Gewusst wie: Erstellen eines Windows Forms\-Steuerelements, das den Fortschritt anzeigt](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
## Siehe auch  
 [Ereignisse in Windows Forms\-Steuerelementen](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)   
 [Definieren eines Ereignisses](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)   
 [Ereignisse](../../../../docs/standard/events/index.md)   
 [Benutzereingaben in Windows Forms](../../../../docs/framework/winforms/user-input-in-windows-forms.md)