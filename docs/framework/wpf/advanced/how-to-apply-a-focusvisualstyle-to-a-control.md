---
title: 'Gewusst wie: Anwenden eines FocusVisualStyle auf ein Steuerelement'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- properties [WPF], FocusVisualStyle
- FocusVisualStyle property [WPF]
ms.assetid: 363de99e-8ecc-438c-ac4a-f9147432ebd6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 41895974b7e6c128d979e362f2dcef1c68e0a5c0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-apply-a-focusvisualstyle-to-a-control"></a>Gewusst wie: Anwenden eines FocusVisualStyle auf ein Steuerelement
Dieses Beispiel zeigt, wie einen visuelle Stil des Fokus in Ressourcen erstellen und Anwenden der Formatvorlage auf ein Steuerelement mit der <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> Eigenschaft.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel definiert ein Format, das zusätzliche Kontrolle Compositing, die gilt nur erstellt, wenn das Steuerelement den Tastaturfokus wird die [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Dies erfolgt durch die Definition eines Stils mit einem <xref:System.Windows.Controls.ControlTemplate>, und klicken Sie dann auf diesem Format als Ressource verweisen, beim Festlegen der <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> Eigenschaft.  
  
 Ein externes Rechteck, einem Rahmen ähnelt befindet sich außerhalb des rechteckigen Bereichs. Sofern nicht anderweitig modifiziert wurde, verwendet die Größe des Formats der <xref:System.Windows.FrameworkElement.ActualHeight%2A> und <xref:System.Windows.FrameworkElement.ActualWidth%2A> des rechteckigen Steuerelements der visuellen Stil der Fokus wird angewendet. In diesem Beispiel wird die negative Werte für die <xref:System.Windows.FrameworkElement.Margin%2A> Rahmens außerhalb das Steuerelement mit Fokus etwas angezeigt werden soll.  
  
 [!code-xaml[FEFocusVisualStyle#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEFocusVisualStyle/CS/page1.xaml#xaml)]  
  
 Ein <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> ist additiv zu jeder Vorlage Steuerelementformats, der geliefert wird entweder von einem expliziten Stil oder einem Designstil der primäre Stil für ein Steuerelement kann weiterhin mit erstellt werden ein <xref:System.Windows.Controls.ControlTemplate> und Festlegen von diesem Format auf die <xref:System.Windows.FrameworkElement.Style%2A> Eigenschaft.  
  
 Fokus visuelle Stile einheitlich werden, über ein Design oder eine Benutzeroberfläche verwendet sollten, anstatt eine andere Definition für jedes Element den Fokus erhalten kann. Weitere Informationen finden Sie unter [Formatierung für den Fokus in Steuerelementen und FocusVisualStyle](../../../../docs/framework/wpf/advanced/styling-for-focus-in-controls-and-focusvisualstyle.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>  
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Fokusstile in Steuerelementen und FocusVisualStyle](../../../../docs/framework/wpf/advanced/styling-for-focus-in-controls-and-focusvisualstyle.md)
