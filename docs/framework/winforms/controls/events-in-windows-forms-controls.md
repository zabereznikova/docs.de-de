---
title: Ereignisse in Windows Forms-Steuerelementen
ms.date: 03/30/2017
helpviewer_keywords:
- events [Windows Forms], custom controls (using code)
- custom controls [Windows Forms], events overview (using code)
ms.assetid: 7e3d1379-87aa-437c-afce-c99454eff30e
ms.openlocfilehash: 253783f50fdbef0890ea16baa9ac996b63795ed8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54716962"
---
# <a name="events-in-windows-forms-controls"></a><span data-ttu-id="6d114-102">Ereignisse in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="6d114-102">Events in Windows Forms Controls</span></span>
<span data-ttu-id="6d114-103">Ein Windows Forms-Steuerelement erbt mehr als sechzig Ereignisse von <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6d114-103">A Windows Forms control inherits more than sixty events from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6d114-104">Dazu gehören die <xref:System.Windows.Forms.Control.Paint> -Ereignis, das bewirkt, dass ein Steuerelement gezeichnet werden soll, die Ereignisse im Zusammenhang mit der Anzeige eines Fenster, z. B. die <xref:System.Windows.Forms.Control.Resize> und <xref:System.Windows.Forms.Control.Layout> Ereignisse und Ereignisse, die mit Maus und Tastatur auf niedriger Ebene.</span><span class="sxs-lookup"><span data-stu-id="6d114-104">These include the <xref:System.Windows.Forms.Control.Paint> event, which causes a control to be drawn, events related to displaying a window, such as the <xref:System.Windows.Forms.Control.Resize> and <xref:System.Windows.Forms.Control.Layout> events, and low-level mouse and keyboard events.</span></span> <span data-ttu-id="6d114-105">Einige Ereignisse auf niedriger Ebene werden von synthetisiert <xref:System.Windows.Forms.Control> in semantische Ereignisse, z. B. <xref:System.Windows.Forms.Control.Click> und <xref:System.Windows.Forms.Control.DoubleClick>.</span><span class="sxs-lookup"><span data-stu-id="6d114-105">Some low-level events are synthesized by <xref:System.Windows.Forms.Control> into semantic events such as <xref:System.Windows.Forms.Control.Click> and <xref:System.Windows.Forms.Control.DoubleClick>.</span></span> <span data-ttu-id="6d114-106">Weitere Informationen zu geerbten Ereignissen finden Sie unter <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="6d114-106">For details about inherited events, see <xref:System.Windows.Forms.Control>.</span></span>  
  
 <span data-ttu-id="6d114-107">Wenn das benutzerdefinierte Steuerelement geerbte Ereignisfunktionen überschreiben muss, hängen Sie keinen Delegaten an, sondern überschreiben Sie die geerbte Methode `On`*EventName*.</span><span class="sxs-lookup"><span data-stu-id="6d114-107">If your custom control needs to override inherited event functionality, override the inherited `On`*EventName* method instead of attaching a delegate.</span></span> <span data-ttu-id="6d114-108">Wenn Sie mit dem Ereignismodell in .NET Framework nicht vertraut sind, finden Sie unter [Auslösen von Ereignissen aus einer Komponente](https://msdn.microsoft.com/library/9aebf605-a87d-470b-b7c8-f9abfc8360a0) weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="6d114-108">If you are not familiar with the event model in the .NET Framework, see [Raising Events from a Component](https://msdn.microsoft.com/library/9aebf605-a87d-470b-b7c8-f9abfc8360a0).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d114-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d114-109">See also</span></span>
- [<span data-ttu-id="6d114-110">Überschreiben der OnPaint-Methode</span><span class="sxs-lookup"><span data-stu-id="6d114-110">Overriding the OnPaint Method</span></span>](../../../../docs/framework/winforms/controls/overriding-the-onpaint-method.md)
- [<span data-ttu-id="6d114-111">Behandeln von Benutzereingaben</span><span class="sxs-lookup"><span data-stu-id="6d114-111">Handling User Input</span></span>](../../../../docs/framework/winforms/controls/handling-user-input.md)
- [<span data-ttu-id="6d114-112">Definieren eines Ereignisses</span><span class="sxs-lookup"><span data-stu-id="6d114-112">Defining an Event</span></span>](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)
- [<span data-ttu-id="6d114-113">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="6d114-113">Events</span></span>](../../../../docs/standard/events/index.md)
