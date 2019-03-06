---
title: 'Vorgehensweise: Verwenden der BetweenShowDelay-Eigenschaft'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolTip control [WPF], BetweenShowDelay time property
- BetweenShowDelay time property [WPF]
ms.assetid: 984ea76d-f2a2-4326-a02e-f97ec3d036d6
ms.openlocfilehash: e0653fbcb8eb052b12be7344ffe239431b67a951
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57370969"
---
# <a name="how-to-use-the-betweenshowdelay-property"></a><span data-ttu-id="1d46c-102">Vorgehensweise: Verwenden der BetweenShowDelay-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="1d46c-102">How to: Use the BetweenShowDelay Property</span></span>
<span data-ttu-id="1d46c-103">Dieses Beispiel zeigt, wie Sie mit der <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> endzeiteigenschaft, sodass die QuickInfos schnell angezeigt werden – mit nur wenig oder keine Verzögerung, wenn ein Benutzer den Mauszeiger von einer QuickInfo bewegt direkt in einen anderen.</span><span class="sxs-lookup"><span data-stu-id="1d46c-103">This example shows how to use the <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> time property so that tooltips appear quickly—with little or no delay—when a user moves the mouse pointer from one tooltip directly to another.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d46c-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1d46c-104">Example</span></span>  
 <span data-ttu-id="1d46c-105">Im folgenden Beispiel die <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> Eigenschaft einer Sekunde (1000 Millisekunden) festgelegt ist und die <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> festgelegt ist, auf zwei Sekunden (2000 Millisekunden) für die QuickInfo beider <xref:System.Windows.Shapes.Ellipse> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="1d46c-105">In the following example, the <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> property is set to one second (1000 milliseconds) and the <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> is set to two seconds (2000 milliseconds) for the tooltips of both <xref:System.Windows.Shapes.Ellipse> controls.</span></span> <span data-ttu-id="1d46c-106">Wenn Sie die QuickInfo für eine der Ellipse, und klicken Sie dann den Mauszeiger auf einen anderen Ellipse innerhalb von zwei Sekunden "und" Pause darauf, zeigt die QuickInfo für die zweite Ellipse sofort.</span><span class="sxs-lookup"><span data-stu-id="1d46c-106">If you display the tooltip for one of the ellipses and then move the mouse pointer to another ellipse within two seconds and pause on it, the tooltip of the second ellipse displays immediately.</span></span>  
  
 <span data-ttu-id="1d46c-107">In der folgenden beiden Szenarien die <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> angewendet wird, wodurch die QuickInfo für den zweiten Ellipse mit einer Sekunde, bevor sie angezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="1d46c-107">In either of the following scenarios, the <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> applies, which causes the tooltip for the second ellipse to wait one second before it appears:</span></span>  
  
-   <span data-ttu-id="1d46c-108">Wenn die Zeit, um zu verschieben, ist die zweite Schaltfläche mehr als zwei Sekunden.</span><span class="sxs-lookup"><span data-stu-id="1d46c-108">If the time it takes to move to the second button is more than two seconds.</span></span>  
  
-   <span data-ttu-id="1d46c-109">Wenn die QuickInfo am Anfang des Zeitintervalls für die erste Ellipse nicht sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="1d46c-109">If the tooltip is not visible at the beginning of the time interval for the first ellipse.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
[!code-xaml[ToolTipService#NoToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
## <a name="see-also"></a><span data-ttu-id="1d46c-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1d46c-110">See also</span></span>
- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [<span data-ttu-id="1d46c-111">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="1d46c-111">How-to Topics</span></span>](tooltip-how-to-topics.md)
- [<span data-ttu-id="1d46c-112">Übersicht über QuickInfo</span><span class="sxs-lookup"><span data-stu-id="1d46c-112">ToolTip Overview</span></span>](tooltip-overview.md)
