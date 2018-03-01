---
title: Mauserfassung in Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- mouse [Windows Forms], capture
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7cc62780579c852aaa637a3ccc13ce2929423868
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="mouse-capture-in-windows-forms"></a><span data-ttu-id="7bfc0-102">Mauserfassung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7bfc0-102">Mouse Capture in Windows Forms</span></span>
<span data-ttu-id="7bfc0-103">*Mauseingaben* bezieht sich auf, wenn ein Befehl, der alle Mauseingaben hat.</span><span class="sxs-lookup"><span data-stu-id="7bfc0-103">*Mouse capture* refers to when a control takes command of all mouse input.</span></span> <span data-ttu-id="7bfc0-104">Wenn ein Steuerelement die Maus erfasst hat, empfängt es Mauseingaben, und zwar unabhängig davon, ob der Zeiger innerhalb seiner Grenzen befindet.</span><span class="sxs-lookup"><span data-stu-id="7bfc0-104">When a control has captured the mouse, it receives mouse input whether or not the pointer is within its borders.</span></span>  
  
## <a name="setting-mouse-capture"></a><span data-ttu-id="7bfc0-105">Festlegen von Mauseingaben</span><span class="sxs-lookup"><span data-stu-id="7bfc0-105">Setting Mouse Capture</span></span>  
 <span data-ttu-id="7bfc0-106">In Windows Forms ist die Maus vom Steuerelement erfasst, wenn der Benutzer eine Maustaste für ein Steuerelement drückt, und die Maus vom Steuerelement freigegeben, wenn der Benutzer die Maustaste loslässt.</span><span class="sxs-lookup"><span data-stu-id="7bfc0-106">In Windows Forms the mouse is captured by the control when the user presses a mouse button on a control, and the mouse is released by the control when the user releases the mouse button.</span></span>  
  
 <span data-ttu-id="7bfc0-107">Die <xref:System.Windows.Forms.Control.Capture%2A> Eigenschaft von der <xref:System.Windows.Forms.Control> Klasse angibt, ob ein Steuerelement die Maus erfasst hat.</span><span class="sxs-lookup"><span data-stu-id="7bfc0-107">The <xref:System.Windows.Forms.Control.Capture%2A> property of the <xref:System.Windows.Forms.Control> class specifies whether a control has captured the mouse.</span></span> <span data-ttu-id="7bfc0-108">Um zu bestimmen, wenn ein Steuerelement keine Mauseingaben mehr erfasst, verarbeitet die <xref:System.Windows.Forms.Control.MouseCaptureChanged> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="7bfc0-108">To determine when a control loses mouse capture, handle the <xref:System.Windows.Forms.Control.MouseCaptureChanged> event.</span></span>  
  
 <span data-ttu-id="7bfc0-109">Nur Vordergrundfenster kann die Maus erfassen.</span><span class="sxs-lookup"><span data-stu-id="7bfc0-109">Only the foreground window can capture the mouse.</span></span> <span data-ttu-id="7bfc0-110">Wenn ein Hintergrundfenster versucht, das die Maus erfasst, empfängt das Fenster Nachrichten nur für Mausereignisse, die auftreten, wenn der Mauszeiger innerhalb der sichtbare Teil des Fensters befindet.</span><span class="sxs-lookup"><span data-stu-id="7bfc0-110">When a background window attempts to capture the mouse, the window receives messages only for mouse events that occur when the mouse pointer is within the visible portion of the window.</span></span> <span data-ttu-id="7bfc0-111">Darüber hinaus auch, wenn das Fenster im Vordergrund die Maus erfasst hat, kann der Benutzer noch ein weiteres Fenster klicken er in den Vordergrund gestellt.</span><span class="sxs-lookup"><span data-stu-id="7bfc0-111">Also, even if the foreground window has captured the mouse, the user can still click another window, bringing it to the foreground.</span></span> <span data-ttu-id="7bfc0-112">Wenn die Maus erfasst sind, funktionieren Tastenkombinationen nicht.</span><span class="sxs-lookup"><span data-stu-id="7bfc0-112">When the mouse is captured, shortcut keys do not work.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bfc0-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7bfc0-113">See Also</span></span>  
 [<span data-ttu-id="7bfc0-114">Mauseingabe in einer Windows Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="7bfc0-114">Mouse Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)
