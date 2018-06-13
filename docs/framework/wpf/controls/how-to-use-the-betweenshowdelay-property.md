---
title: 'Gewusst wie: Verwenden der BetweenShowDelay-Eigenschaft'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolTip control [WPF], BetweenShowDelay time property
- BetweenShowDelay time property [WPF]
ms.assetid: 984ea76d-f2a2-4326-a02e-f97ec3d036d6
ms.openlocfilehash: 7d48fb859ec6d37abd2490bc718d58cbdaa67f13
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552713"
---
# <a name="how-to-use-the-betweenshowdelay-property"></a>Gewusst wie: Verwenden der BetweenShowDelay-Eigenschaft
Dieses Beispiel zeigt, wie die <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> endzeiteigenschaft, sodass schnell QuickInfos angezeigt werden – mit nur wenig oder keine Verzögerung – Wenn ein Benutzer den Mauszeiger von einer QuickInfo bewegt direkt in eine andere.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel die <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> Eigenschaft auf eine Sekunde (1000 Millisekunden) festgelegt ist und die <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> festgelegt ist, auf zwei Sekunden (2000 Millisekunden) für die QuickInfo beider <xref:System.Windows.Shapes.Ellipse> Steuerelemente. Wenn Sie die QuickInfo für eine Schaltfläche mit den Auslassungszeichen angezeigt, und klicken Sie dann den Mauszeiger auf einen anderen Ellipse innerhalb von zwei Sekunden und Anhalten darauf, zeigt die QuickInfo für die zweite Ellipse sofort an.  
  
 In den folgenden Szenarien die <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> angewendet wird, wodurch die QuickInfo für die zweite Ellipse warten Sie mindestens eine Sekunde, bevor er angezeigt wird:  
  
-   Wenn die Zeit zum Verschieben ist für die zweite Schaltfläche mehr als zwei Sekunden.  
  
-   Wenn die QuickInfo am Anfang des Zeitintervalls für die erste Ellipse nicht sichtbar ist.  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
[!code-xaml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.ToolTip>  
 <xref:System.Windows.Controls.ToolTipService>  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)  
 [Übersicht über QuickInfo](../../../../docs/framework/wpf/controls/tooltip-overview.md)
