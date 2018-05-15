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
ms.openlocfilehash: 1c89149fc07f89028b21fa513fd84dee4e890968
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-determine-which-modifier-key-was-pressed"></a><span data-ttu-id="ee888-102">Gewusst wie: Ermitteln der gedrückten Modifizierertaste</span><span class="sxs-lookup"><span data-stu-id="ee888-102">How to: Determine Which Modifier Key Was Pressed</span></span>
<span data-ttu-id="ee888-103">Wenn Sie eine Anwendung, die Tastatureingaben des Benutzers annimmt erstellen, können Sie auch für Zusatztasten z. B. die Tasten UMSCHALT, ALT und STRG überwachen möchten.</span><span class="sxs-lookup"><span data-stu-id="ee888-103">When you create an application that accepts the user's keystrokes, you may also want to monitor for modifier keys such as the SHIFT, ALT, and CTRL keys.</span></span> <span data-ttu-id="ee888-104">Wenn eine Taste in Kombination mit anderen Schlüsseln oder Mausklicks gedrückt wird, kann Ihre Anwendung entsprechend reagieren.</span><span class="sxs-lookup"><span data-stu-id="ee888-104">When a modifier key is pressed in combination with other keys, or with mouse clicks, your application can respond appropriately.</span></span> <span data-ttu-id="ee888-105">Z. B. wenn die Buchstaben S gedrückt wird, einfach dadurch möglicherweise eines "s" auf dem Bildschirm angezeigt werden, aber wenn Sie die Tasten STRG + S gedrückt werden, kann das aktuelle Dokument gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="ee888-105">For example, if the letter S is pressed, this may simply cause an "s" to appear on the screen, but if the keys CTRL+S are pressed, the current document may be saved.</span></span> <span data-ttu-id="ee888-106">Wenn Sie behandeln die <xref:System.Windows.Forms.Control.KeyDown> -Ereignis der <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> Eigenschaft von der <xref:System.Windows.Forms.KeyEventArgs> empfangen vom Ereignis Handler gibt an, welche Modifizierertasten.</span><span class="sxs-lookup"><span data-stu-id="ee888-106">If you handle the <xref:System.Windows.Forms.Control.KeyDown> event, the <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> property of the <xref:System.Windows.Forms.KeyEventArgs> received by the event handler specifies which modifier keys are pressed.</span></span> <span data-ttu-id="ee888-107">Alternativ können Sie die <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> Eigenschaft <xref:System.Windows.Forms.KeyEventArgs> gibt das Zeichen an, die auch alle mit einem bitweisen OR kombinierten Zusatztasten gedrückt wurde.</span><span class="sxs-lookup"><span data-stu-id="ee888-107">Alternatively, the <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> property of <xref:System.Windows.Forms.KeyEventArgs> specifies the character that was pressed as well as any modifier keys combined with a bitwise OR.</span></span> <span data-ttu-id="ee888-108">Jedoch, wenn Sie behandeln die <xref:System.Windows.Forms.Control.KeyPress> Ereignis oder ein Mausereignis der Ereignishandler empfängt diese Informationen nicht.</span><span class="sxs-lookup"><span data-stu-id="ee888-108">However, if you are handling the <xref:System.Windows.Forms.Control.KeyPress> event or a mouse event, the event handler does not receive this information.</span></span> <span data-ttu-id="ee888-109">In diesem Fall müssen Sie verwenden die <xref:System.Windows.Forms.Control.ModifierKeys%2A> Eigenschaft von der <xref:System.Windows.Forms.Control> Klasse.</span><span class="sxs-lookup"><span data-stu-id="ee888-109">In this case, you must use the <xref:System.Windows.Forms.Control.ModifierKeys%2A> property of the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="ee888-110">In beiden Fällen müssen Sie eine bitweise AND-Operation der entsprechenden ausführen <xref:System.Windows.Forms.Keys> Wert und der zu überprüfende Wert.</span><span class="sxs-lookup"><span data-stu-id="ee888-110">In either case, you must perform a bitwise AND of the appropriate <xref:System.Windows.Forms.Keys> value and the value you are testing.</span></span> <span data-ttu-id="ee888-111">Die <xref:System.Windows.Forms.Keys> Enumeration bietet Variationen des jeweiligen Schlüssels Modifizierer, daher ist es wichtig, dass Sie den bitweisen ausführen und mit dem richtigen Wert.</span><span class="sxs-lookup"><span data-stu-id="ee888-111">The <xref:System.Windows.Forms.Keys> enumeration offers variations of each modifier key, so it is important that you perform the bitwise AND with the correct value.</span></span> <span data-ttu-id="ee888-112">Beispielsweise wird durch die UMSCHALTTASTE gedrückt dargestellt <xref:System.Windows.Forms.Keys.Shift>, <xref:System.Windows.Forms.Keys.ShiftKey>, <xref:System.Windows.Forms.Keys.RShiftKey> und <xref:System.Windows.Forms.Keys.LShiftKey> den richtigen Wert UMSCHALT zu testen, wie eine Modifizierertaste ist <xref:System.Windows.Forms.Keys.Shift>.</span><span class="sxs-lookup"><span data-stu-id="ee888-112">For example, the SHIFT key is represented by <xref:System.Windows.Forms.Keys.Shift>, <xref:System.Windows.Forms.Keys.ShiftKey>, <xref:System.Windows.Forms.Keys.RShiftKey> and <xref:System.Windows.Forms.Keys.LShiftKey> The correct value to test SHIFT as a modifier key is <xref:System.Windows.Forms.Keys.Shift>.</span></span> <span data-ttu-id="ee888-113">Auf ähnliche Weise, STRG und ALT als Modifizierer Sie testen, die zu verwendende der <xref:System.Windows.Forms.Keys.Control> und <xref:System.Windows.Forms.Keys.Alt> bzw. die Werte.</span><span class="sxs-lookup"><span data-stu-id="ee888-113">Similarly, to test for CTLR and ALT as modifiers you should use the <xref:System.Windows.Forms.Keys.Control> and <xref:System.Windows.Forms.Keys.Alt> values, respectively.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ee888-114">Visual Basic-Programmierer können auch Zugriff auf wichtige Informationen über die <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A> Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="ee888-114">Visual Basic programmers can also access key information through the <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A> property</span></span>  
  
### <a name="to-determine-which-modifier-key-was-pressed"></a><span data-ttu-id="ee888-115">Zum Ermitteln der gedrückten Modifizierertaste wurde</span><span class="sxs-lookup"><span data-stu-id="ee888-115">To determine which modifier key was pressed</span></span>  
  
-   <span data-ttu-id="ee888-116">Verwenden Sie den bitweisen `AND` -Operator mit dem <xref:System.Windows.Forms.Control.ModifierKeys%2A> Eigenschaft und den Wert der <xref:System.Windows.Forms.Keys> Enumeration, um zu bestimmen, ob eine bestimmte Taste gedrückt wird.</span><span class="sxs-lookup"><span data-stu-id="ee888-116">Use the bitwise `AND` operator with the <xref:System.Windows.Forms.Control.ModifierKeys%2A> property and a value of the <xref:System.Windows.Forms.Keys> enumeration to determine whether a particular modifier key is pressed.</span></span> <span data-ttu-id="ee888-117">Im folgenden Codebeispiel wird veranschaulicht, um festzustellen, ob die UMSCHALTTASTE, innerhalb gedrückt wird einer <xref:System.Windows.Forms.Control.KeyPress> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="ee888-117">The following code example shows how to determine whether the SHIFT key is pressed within a <xref:System.Windows.Forms.Control.KeyPress> event handler.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/cpp/form1.cpp#5)]
     [!code-csharp[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/VB/form1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="ee888-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ee888-118">See Also</span></span>  
 <xref:System.Windows.Forms.Keys>  
 <xref:System.Windows.Forms.Control.ModifierKeys%2A>  
 [<span data-ttu-id="ee888-119">Tastatureingaben in einer Windows Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="ee888-119">Keyboard Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)  
 [<span data-ttu-id="ee888-120">Vorgehensweise: Bestimmen Sie, ob die FESTSTELLTASTE aktiviert ist, in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ee888-120">How to: Determine If CapsLock is On in Visual Basic</span></span>](http://msdn.microsoft.com/library/91e60f5c-dd61-4222-ba5f-39af803afd8c)
