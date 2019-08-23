---
title: 'Vorgehensweise: Bestimmen, welche Zusatztaste gedrückt wurde'
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
ms.openlocfilehash: 37fa897f5a2e1c65cbd5db9189f1500e3427c920
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964309"
---
# <a name="how-to-determine-which-modifier-key-was-pressed"></a>Vorgehensweise: Bestimmen, welche Zusatztaste gedrückt wurde
Wenn Sie eine Anwendung erstellen, die die Tastatureingaben des Benutzers akzeptiert, können Sie auch auf Modifizierertasten wie die UMSCHALTTASTE, die Alt-Taste und die STRG-Taste überwachen. Wenn eine Modifizierertaste in Kombination mit anderen Schlüsseln oder mit Mausklicks gedrückt wird, kann die Anwendung entsprechend reagieren. Wenn z. b. der Buchstabe S gedrückt ist, kann dies dazu führen, dass auf dem Bildschirm nur ein "s" angezeigt wird, aber wenn die Tasten STRG + S gedrückt werden, kann das aktuelle Dokument gespeichert werden. Wenn Sie das <xref:System.Windows.Forms.Control.KeyDown> -Ereignis behandeln, <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> gibt die- <xref:System.Windows.Forms.KeyEventArgs> Eigenschaft des-Objekts, das vom Ereignishandler empfangen wird, an, welche Modifizierertasten gedrückt werden. Alternativ gibt die <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> -Eigenschaft <xref:System.Windows.Forms.KeyEventArgs> von das Zeichen an, das gedrückt wurde, sowie alle Modifizierertasten, die mit einem bitweisen OR kombiniert wurden. Wenn Sie jedoch das <xref:System.Windows.Forms.Control.KeyPress> -Ereignis oder ein Maus Ereignis verarbeiten, empfängt der Ereignishandler diese Informationen nicht. In diesem Fall müssen Sie die <xref:System.Windows.Forms.Control.ModifierKeys%2A> -Eigenschaft <xref:System.Windows.Forms.Control> der-Klasse verwenden. In beiden Fällen müssen Sie ein bitweises and mit dem entsprechenden <xref:System.Windows.Forms.Keys> Wert und dem zu testenden Wert ausführen. Die <xref:System.Windows.Forms.Keys> -Enumeration bietet Variationen der einzelnen modifiziererschlüssel. Daher ist es wichtig, dass Sie das bitweise and mit dem korrekten Wert ausführen. Die UMSCHALTTASTE wird z. b. durch <xref:System.Windows.Forms.Keys.Shift> <xref:System.Windows.Forms.Keys.RShiftKey> , <xref:System.Windows.Forms.Keys.ShiftKey>und <xref:System.Windows.Forms.Keys.LShiftKey> den korrekten Wert zum Testen der Umschalttaste dargestellt, wenn eine Modifizierertaste ist <xref:System.Windows.Forms.Keys.Shift>. Entsprechend sollten Sie zum Testen von STRG und alt als modifiziererer den- <xref:System.Windows.Forms.Keys.Control> Wert <xref:System.Windows.Forms.Keys.Alt> und den-Wert verwenden.  
  
> [!NOTE]
> Visual Basic Programmierer können auch über die <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A> -Eigenschaft auf Schlüsselinformationen zugreifen.  
  
### <a name="to-determine-which-modifier-key-was-pressed"></a>So bestimmen Sie, welche Modifizierertaste gedrückt wurde  
  
- Verwenden Sie den bitweisen `AND` Operator mit der <xref:System.Windows.Forms.Control.ModifierKeys%2A> <xref:System.Windows.Forms.Keys> -Eigenschaft und einem Wert der-Enumeration, um zu bestimmen, ob eine bestimmte Modifizierertaste gedrückt wird. Im folgenden Codebeispiel wird veranschaulicht, wie bestimmt wird, ob die UMSCHALTTASTE innerhalb <xref:System.Windows.Forms.Control.KeyPress> eines-Ereignis Handlers gedrückt wird.  
  
     [!code-cpp[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/cpp/form1.cpp#5)]
     [!code-csharp[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/VB/form1.vb#5)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.ModifierKeys%2A>
- [Tastatureingaben in einer Windows Forms-Anwendung](keyboard-input-in-a-windows-forms-application.md)
- [Vorgehensweise: Stellen Sie fest, ob CapsLock in Visual Basic](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9c9d1fz9(v=vs.100))
