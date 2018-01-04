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
