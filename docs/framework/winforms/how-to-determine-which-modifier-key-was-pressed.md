---
title: 'Gewusst wie: Ermitteln der gedrückten Modifizierertaste'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- keyboard input
- shift keys
- events [Windows Forms], mouse
- Keys.ControlKey enumeration member
- keys [Windows Forms], control keys
- user input [Windows Forms], checking for keyboard
- keys [Windows Forms], determining last pressed
- keys [Windows Forms], shift keys
- keys [Windows Forms], modifier keys
- control keys
- keys [Windows Forms], alt keys
- alt keys
- Keys.Shift enumeration member
- events [Windows Forms], keyboard
- keyboards [Windows Forms], keyboard input
- Keys.Alt enumeration member
- modifier keys
ms.assetid: 1e184048-0ae3-4067-a200-d4ba31dbc2cb
ms.openlocfilehash: f73dea640bc2059353b2a250188b901f360ea750
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "44037268"
---
# <a name="how-to-determine-which-modifier-key-was-pressed"></a>Gewusst wie: Ermitteln der gedrückten Modifizierertaste
Wenn Sie eine Anwendung, die die Tastaturanschläge des Benutzers akzeptiert erstellen, können Sie auch Zusatztasten wie die Tasten UMSCHALT, ALT und STRG überwachen möchten. Wenn eine Taste in Kombination mit anderen Schlüsseln oder Mausklicks gedrückt wird, kann Ihre Anwendung entsprechend reagieren. Z. B. wenn die Buchstaben S gedrückt wird, einfach dadurch möglicherweise ein "s" auf dem Bildschirm angezeigt werden, aber wenn die Tasten STRG + S gedrückt werden, kann das aktuelle Dokument gespeichert werden. Verarbeitet die <xref:System.Windows.Forms.Control.KeyDown> -Ereignis, das <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> Eigenschaft der <xref:System.Windows.Forms.KeyEventArgs> empfangen vom Ereignis-Handler legt die Modifizierertasten gedrückt sind. Sie können auch die <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> Eigenschaft <xref:System.Windows.Forms.KeyEventArgs> gibt das Zeichen, die auch alle Zusatztasten, die mit einem bitweisen OR kombiniert gedrückt wurde. Aber wenn Sie behandeln die <xref:System.Windows.Forms.Control.KeyPress> Ereignis oder ein Mausereignis der Ereignishandler empfängt diese Informationen nicht. In diesem Fall müssen Sie verwenden die <xref:System.Windows.Forms.Control.ModifierKeys%2A> Eigenschaft der <xref:System.Windows.Forms.Control> Klasse. In beiden Fällen müssen Sie ein bitweises AND des entsprechenden ausführen <xref:System.Windows.Forms.Keys> Wert und der Wert, die Sie testen. Die <xref:System.Windows.Forms.Keys> Enumeration bietet Variationen der einzelnen Schlüssel Modifizierer, daher es wichtig ist, dass Sie den bitweisen ausführen und mit dem richtigen Wert. Beispielsweise wird durch die UMSCHALTTASTE gedrückt dargestellt <xref:System.Windows.Forms.Keys.Shift>, <xref:System.Windows.Forms.Keys.ShiftKey>, <xref:System.Windows.Forms.Keys.RShiftKey> und <xref:System.Windows.Forms.Keys.LShiftKey> UMSCHALT zu testen, wie Sie Modifizierertaste wird der korrekte Wert <xref:System.Windows.Forms.Keys.Shift>. Auf ähnliche Weise, STRG und ALT-Taste als Modifizierer Sie testen sollten verwenden die <xref:System.Windows.Forms.Keys.Control> und <xref:System.Windows.Forms.Keys.Alt> Werte.  
  
> [!NOTE]
>  Visual Basic-Programmierer können auch Zugriff auf wichtige Informationen über die <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A> Eigenschaft  
  
### <a name="to-determine-which-modifier-key-was-pressed"></a>Um zu bestimmen, welche Zusatztaste gedrückt wurde  
  
-   Verwenden Sie den bitweisen `AND` -Operator mit der <xref:System.Windows.Forms.Control.ModifierKeys%2A> -Eigenschaft und den Wert der <xref:System.Windows.Forms.Keys> Enumeration, um zu bestimmen, ob eine bestimmte Modifizierertaste gedrückt wird. Im folgenden Codebeispiel wird veranschaulicht, um festzustellen, ob die UMSCHALT-Taste, innerhalb gedrückt wird einer <xref:System.Windows.Forms.Control.KeyPress> -Ereignishandler.  
  
     [!code-cpp[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/cpp/form1.cpp#5)]
     [!code-csharp[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/VB/form1.vb#5)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Keys>  
 <xref:System.Windows.Forms.Control.ModifierKeys%2A>  
 [Tastatureingaben in einer Windows Forms-Anwendung](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)  
 [Gewusst wie: bestimmen, ob die FESTSTELLTASTE aktiviert ist, in Visual Basic](https://msdn.microsoft.com/library/91e60f5c-dd61-4222-ba5f-39af803afd8c)
