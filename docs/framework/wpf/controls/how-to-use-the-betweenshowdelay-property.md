---
title: 'Vorgehensweise: Verwenden der BetweenShowDelay-Eigenschaft'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolTip control [WPF], BetweenShowDelay time property
- BetweenShowDelay time property [WPF]
ms.assetid: 984ea76d-f2a2-4326-a02e-f97ec3d036d6
ms.openlocfilehash: ee9c532f8b2eeddb2c798df53e1864e8f543638b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564057"
---
# <a name="how-to-use-the-betweenshowdelay-property"></a>Vorgehensweise: Verwenden der BetweenShowDelay-Eigenschaft
Dieses Beispiel zeigt, wie Sie mit der <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> endzeiteigenschaft, sodass die QuickInfos schnell angezeigt werden – mit nur wenig oder keine Verzögerung, wenn ein Benutzer den Mauszeiger von einer QuickInfo bewegt direkt in einen anderen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel die <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> Eigenschaft einer Sekunde (1000 Millisekunden) festgelegt ist und die <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> festgelegt ist, auf zwei Sekunden (2000 Millisekunden) für die QuickInfo beider <xref:System.Windows.Shapes.Ellipse> Steuerelemente. Wenn Sie die QuickInfo für eine der Ellipse, und klicken Sie dann den Mauszeiger auf einen anderen Ellipse innerhalb von zwei Sekunden "und" Pause darauf, zeigt die QuickInfo für die zweite Ellipse sofort.  
  
 In der folgenden beiden Szenarien die <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> angewendet wird, wodurch die QuickInfo für den zweiten Ellipse mit einer Sekunde, bevor sie angezeigt wird:  
  
-   Wenn die Zeit, um zu verschieben, ist die zweite Schaltfläche mehr als zwei Sekunden.  
  
-   Wenn die QuickInfo am Anfang des Zeitintervalls für die erste Ellipse nicht sichtbar ist.  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
[!code-xaml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)
- [Übersicht über QuickInfo](../../../../docs/framework/wpf/controls/tooltip-overview.md)
