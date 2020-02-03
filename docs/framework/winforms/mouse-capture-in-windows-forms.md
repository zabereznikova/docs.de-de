---
title: Mausaufzeichnung
ms.date: 03/30/2017
helpviewer_keywords:
- mouse [Windows Forms], capture
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
ms.openlocfilehash: 10583f074831b16dce3c713b4ac9a76c7005c9f5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741022"
---
# <a name="mouse-capture-in-windows-forms"></a><span data-ttu-id="ddb33-102">Mauserfassung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ddb33-102">Mouse Capture in Windows Forms</span></span>
<span data-ttu-id="ddb33-103">Die *Maus Aufzeichnung* verweist auf, wenn ein Steuerelement den Befehl für alle Maus Eingaben annimmt.</span><span class="sxs-lookup"><span data-stu-id="ddb33-103">*Mouse capture* refers to when a control takes command of all mouse input.</span></span> <span data-ttu-id="ddb33-104">Wenn ein Steuerelement die Maus erfasst hat, empfängt es Maus Eingaben, unabhängig davon, ob sich der Zeiger innerhalb seines Rahmens befindet.</span><span class="sxs-lookup"><span data-stu-id="ddb33-104">When a control has captured the mouse, it receives mouse input whether or not the pointer is within its borders.</span></span>  
  
## <a name="setting-mouse-capture"></a><span data-ttu-id="ddb33-105">Festlegen der Maus Aufzeichnung</span><span class="sxs-lookup"><span data-stu-id="ddb33-105">Setting Mouse Capture</span></span>  
 <span data-ttu-id="ddb33-106">In Windows Forms die Maus vom Steuerelement aufgezeichnet, wenn der Benutzer eine Maustaste auf ein Steuerelement drückt, und die Maus wird vom-Steuerelement losgelassen, wenn der Benutzer die Maustaste loslässt.</span><span class="sxs-lookup"><span data-stu-id="ddb33-106">In Windows Forms the mouse is captured by the control when the user presses a mouse button on a control, and the mouse is released by the control when the user releases the mouse button.</span></span>  
  
 <span data-ttu-id="ddb33-107">Die <xref:System.Windows.Forms.Control.Capture%2A>-Eigenschaft der <xref:System.Windows.Forms.Control>-Klasse gibt an, ob ein Steuerelement die Maus erfasst hat.</span><span class="sxs-lookup"><span data-stu-id="ddb33-107">The <xref:System.Windows.Forms.Control.Capture%2A> property of the <xref:System.Windows.Forms.Control> class specifies whether a control has captured the mouse.</span></span> <span data-ttu-id="ddb33-108">Behandeln Sie das <xref:System.Windows.Forms.Control.MouseCaptureChanged>-Ereignis, um zu bestimmen, wann ein Steuerelement die Maus Aufzeichnung verliert.</span><span class="sxs-lookup"><span data-stu-id="ddb33-108">To determine when a control loses mouse capture, handle the <xref:System.Windows.Forms.Control.MouseCaptureChanged> event.</span></span>  
  
 <span data-ttu-id="ddb33-109">Nur im Vordergrund Fenster kann die Maus erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="ddb33-109">Only the foreground window can capture the mouse.</span></span> <span data-ttu-id="ddb33-110">Wenn ein Hintergrund Fenster versucht, die Maus zu erfassen, empfängt das Fenster nur Meldungen für Mausereignisse, die auftreten, wenn sich der Mauszeiger innerhalb des sichtbaren Teils des Fensters befindet.</span><span class="sxs-lookup"><span data-stu-id="ddb33-110">When a background window attempts to capture the mouse, the window receives messages only for mouse events that occur when the mouse pointer is within the visible portion of the window.</span></span> <span data-ttu-id="ddb33-111">Auch wenn das Vordergrund Fenster die Maus erfasst hat, kann der Benutzer weiterhin auf ein anderes Fenster klicken, um ihn in den Vordergrund zu bringen.</span><span class="sxs-lookup"><span data-stu-id="ddb33-111">Also, even if the foreground window has captured the mouse, the user can still click another window, bringing it to the foreground.</span></span> <span data-ttu-id="ddb33-112">Wenn die Maus aufgezeichnet wird, funktionieren Tastenkombinationen nicht.</span><span class="sxs-lookup"><span data-stu-id="ddb33-112">When the mouse is captured, shortcut keys do not work.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddb33-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ddb33-113">See also</span></span>

- [<span data-ttu-id="ddb33-114">Mauseingabe in einer Windows Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="ddb33-114">Mouse Input in a Windows Forms Application</span></span>](mouse-input-in-a-windows-forms-application.md)
