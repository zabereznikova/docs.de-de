---
title: Mauserfassung in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- mouse [Windows Forms], capture
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
ms.openlocfilehash: afb58df99ea30f5e7e6ab5b9156af195d273c44d
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57712707"
---
# <a name="mouse-capture-in-windows-forms"></a><span data-ttu-id="a5150-102">Mauserfassung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a5150-102">Mouse Capture in Windows Forms</span></span>
<span data-ttu-id="a5150-103">*Erfassen von Mausereignissen* bezieht sich auf, wenn ein Befehl, der alle Mauseingabe hat.</span><span class="sxs-lookup"><span data-stu-id="a5150-103">*Mouse capture* refers to when a control takes command of all mouse input.</span></span> <span data-ttu-id="a5150-104">Wenn ein Steuerelement die Maus erfasst hat, empfängt es Mauseingaben, und zwar unabhängig davon, ob der Zeiger innerhalb seiner Grenzen befindet.</span><span class="sxs-lookup"><span data-stu-id="a5150-104">When a control has captured the mouse, it receives mouse input whether or not the pointer is within its borders.</span></span>  
  
## <a name="setting-mouse-capture"></a><span data-ttu-id="a5150-105">Die Erfassung von Mauseingaben festlegen</span><span class="sxs-lookup"><span data-stu-id="a5150-105">Setting Mouse Capture</span></span>  
 <span data-ttu-id="a5150-106">In Windows Forms ist die Maus vom Steuerelement erfasst, wenn der Benutzer eine Maustaste auf einem Steuerelement drückt, und die Maus vom Steuerelement freigegeben wird, wenn der Benutzer die Maustaste loslässt.</span><span class="sxs-lookup"><span data-stu-id="a5150-106">In Windows Forms the mouse is captured by the control when the user presses a mouse button on a control, and the mouse is released by the control when the user releases the mouse button.</span></span>  
  
 <span data-ttu-id="a5150-107">Die <xref:System.Windows.Forms.Control.Capture%2A> Eigenschaft der <xref:System.Windows.Forms.Control> Klasse gibt an, ob ein Steuerelement die Maus erfasst hat.</span><span class="sxs-lookup"><span data-stu-id="a5150-107">The <xref:System.Windows.Forms.Control.Capture%2A> property of the <xref:System.Windows.Forms.Control> class specifies whether a control has captured the mouse.</span></span> <span data-ttu-id="a5150-108">Um zu bestimmen, wenn ein Steuerelement die Mausauswahl verliert, behandelt der <xref:System.Windows.Forms.Control.MouseCaptureChanged> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="a5150-108">To determine when a control loses mouse capture, handle the <xref:System.Windows.Forms.Control.MouseCaptureChanged> event.</span></span>  
  
 <span data-ttu-id="a5150-109">Nur das Vordergrundfenster kann die Maus erfassen.</span><span class="sxs-lookup"><span data-stu-id="a5150-109">Only the foreground window can capture the mouse.</span></span> <span data-ttu-id="a5150-110">Wenn einem Hintergrundfenster versucht, die die Maus erfassen, empfängt das Fenster Nachrichten nur von den Mausereignissen, die auftreten, wenn der Mauszeiger in den sichtbaren Teil des Fensters befindet.</span><span class="sxs-lookup"><span data-stu-id="a5150-110">When a background window attempts to capture the mouse, the window receives messages only for mouse events that occur when the mouse pointer is within the visible portion of the window.</span></span> <span data-ttu-id="a5150-111">Darüber hinaus auch, wenn das Vordergrundfenster die Maus erfasst hat, kann der Benutzer noch einem anderen Fenster klicken es in den Vordergrund zu bringen.</span><span class="sxs-lookup"><span data-stu-id="a5150-111">Also, even if the foreground window has captured the mouse, the user can still click another window, bringing it to the foreground.</span></span> <span data-ttu-id="a5150-112">Wenn die Maus erfasst wird, funktionieren Tastenkombinationen nicht.</span><span class="sxs-lookup"><span data-stu-id="a5150-112">When the mouse is captured, shortcut keys do not work.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5150-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5150-113">See also</span></span>
- [<span data-ttu-id="a5150-114">Mauseingabe in einer Windows Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="a5150-114">Mouse Input in a Windows Forms Application</span></span>](mouse-input-in-a-windows-forms-application.md)
