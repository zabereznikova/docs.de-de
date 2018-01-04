---
title: 'Gewusst wie: Verwenden der BetweenShowDelay-Eigenschaft'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ToolTip control [WPF], BetweenShowDelay time property
- BetweenShowDelay time property [WPF]
ms.assetid: 984ea76d-f2a2-4326-a02e-f97ec3d036d6
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dfd4bb4c9e26361e5b8f573d06449b090497acd6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-betweenshowdelay-property"></a><span data-ttu-id="ac9a6-102">Gewusst wie: Verwenden der BetweenShowDelay-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="ac9a6-102">How to: Use the BetweenShowDelay Property</span></span>
<span data-ttu-id="ac9a6-103">Dieses Beispiel zeigt, wie die <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> endzeiteigenschaft, sodass schnell QuickInfos angezeigt werden – mit nur wenig oder keine Verzögerung – Wenn ein Benutzer den Mauszeiger von einer QuickInfo bewegt direkt in eine andere.</span><span class="sxs-lookup"><span data-stu-id="ac9a6-103">This example shows how to use the <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> time property so that tooltips appear quickly—with little or no delay—when a user moves the mouse pointer from one tooltip directly to another.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac9a6-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ac9a6-104">Example</span></span>  
 <span data-ttu-id="ac9a6-105">Im folgenden Beispiel die <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> Eigenschaft auf eine Sekunde (1000 Millisekunden) festgelegt ist und die <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> festgelegt ist, auf zwei Sekunden (2000 Millisekunden) für die QuickInfo beider <xref:System.Windows.Shapes.Ellipse> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="ac9a6-105">In the following example, the <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> property is set to one second (1000 milliseconds) and the <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> is set to two seconds (2000 milliseconds) for the tooltips of both <xref:System.Windows.Shapes.Ellipse> controls.</span></span> <span data-ttu-id="ac9a6-106">Wenn Sie die QuickInfo für eine Schaltfläche mit den Auslassungszeichen angezeigt, und klicken Sie dann den Mauszeiger auf einen anderen Ellipse innerhalb von zwei Sekunden und Anhalten darauf, zeigt die QuickInfo für die zweite Ellipse sofort an.</span><span class="sxs-lookup"><span data-stu-id="ac9a6-106">If you display the tooltip for one of the ellipses and then move the mouse pointer to another ellipse within two seconds and pause on it, the tooltip of the second ellipse displays immediately.</span></span>  
  
 <span data-ttu-id="ac9a6-107">In den folgenden Szenarien die <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> angewendet wird, wodurch die QuickInfo für die zweite Ellipse warten Sie mindestens eine Sekunde, bevor er angezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="ac9a6-107">In either of the following scenarios, the <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> applies, which causes the tooltip for the second ellipse to wait one second before it appears:</span></span>  
  
-   <span data-ttu-id="ac9a6-108">Wenn die Zeit zum Verschieben ist für die zweite Schaltfläche mehr als zwei Sekunden.</span><span class="sxs-lookup"><span data-stu-id="ac9a6-108">If the time it takes to move to the second button is more than two seconds.</span></span>  
  
-   <span data-ttu-id="ac9a6-109">Wenn die QuickInfo am Anfang des Zeitintervalls für die erste Ellipse nicht sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="ac9a6-109">If the tooltip is not visible at the beginning of the time interval for the first ellipse.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
[!code-xaml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
## <a name="see-also"></a><span data-ttu-id="ac9a6-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac9a6-110">See Also</span></span>  
 <xref:System.Windows.Controls.ToolTip>  
 <xref:System.Windows.Controls.ToolTipService>  
 [<span data-ttu-id="ac9a6-111">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="ac9a6-111">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)  
 [<span data-ttu-id="ac9a6-112">Übersicht über QuickInfo</span><span class="sxs-lookup"><span data-stu-id="ac9a6-112">ToolTip Overview</span></span>](../../../../docs/framework/wpf/controls/tooltip-overview.md)
