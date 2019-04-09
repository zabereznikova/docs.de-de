---
title: 'Vorgehensweise: Verwenden der BetweenShowDelay-Eigenschaft'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolTip control [WPF], BetweenShowDelay time property
- BetweenShowDelay time property [WPF]
ms.assetid: 984ea76d-f2a2-4326-a02e-f97ec3d036d6
ms.openlocfilehash: b6d55c72c8264546949833fc086937a8b1fe2540
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59139593"
---
# <a name="how-to-use-the-betweenshowdelay-property"></a>Vorgehensweise: Verwenden der BetweenShowDelay-Eigenschaft
Dieses Beispiel zeigt, wie Sie mit der <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> endzeiteigenschaft, sodass die QuickInfos schnell angezeigt werden – mit nur wenig oder keine Verzögerung, wenn ein Benutzer den Mauszeiger von einer QuickInfo bewegt direkt in einen anderen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel die <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> Eigenschaft einer Sekunde (1000 Millisekunden) festgelegt ist und die <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> festgelegt ist, auf zwei Sekunden (2000 Millisekunden) für die QuickInfo beider <xref:System.Windows.Shapes.Ellipse> Steuerelemente. Wenn Sie die QuickInfo für eine der Ellipse, und klicken Sie dann den Mauszeiger auf einen anderen Ellipse innerhalb von zwei Sekunden "und" Pause darauf, zeigt die QuickInfo für die zweite Ellipse sofort.  
  
 In der folgenden beiden Szenarien die <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> angewendet wird, wodurch die QuickInfo für den zweiten Ellipse mit einer Sekunde, bevor sie angezeigt wird:  
  
-   Wenn die Zeit, um zu verschieben, ist die zweite Schaltfläche mehr als zwei Sekunden.  
  
-   Wenn die QuickInfo am Anfang des Zeitintervalls für die erste Ellipse nicht sichtbar ist.  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
[!code-xaml[ToolTipService#NoToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [Gewusst wie-Themen](tooltip-how-to-topics.md)
- [Übersicht über die QuickInfo](tooltip-overview.md)
