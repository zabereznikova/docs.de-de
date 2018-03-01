---
title: 'Gewusst wie: Sicherstellen, dass ein GridSplitter sichtbar ist'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GridSplitter control [WPF], ensuring visibility of
ms.assetid: 0a62a964-89c8-48f0-9023-5df721a8cf47
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0b7587a093b2b43856a05693bb785a0465211782
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-make-sure-that-a-gridsplitter-is-visible"></a>Gewusst wie: Sicherstellen, dass ein GridSplitter sichtbar ist
Dieses Beispiel zeigt, wie Sie sicherstellen, eine <xref:System.Windows.Controls.GridSplitter> -Steuerelement nicht ausgeblendet ist, durch den andere Steuerelemente in einem <xref:System.Windows.Controls.Grid>.  
  
## <a name="example"></a>Beispiel  
 Die <xref:System.Windows.Controls.Panel.Children%2A> von einem <xref:System.Windows.Controls.Grid> Steuerelement gerendert werden, in der Reihenfolge, in der sie im Markup oder-Code definiert sind. <xref:System.Windows.Controls.GridSplitter>Steuerelemente können von anderen Steuerelementen ausgeblendet werden, wenn Sie diese nicht als die letzten Elemente im Definieren der <xref:System.Windows.Controls.Panel.Children%2A> Auflistung oder wenn Sie anderen Steuerelementen einen höheren <xref:System.Windows.Controls.Panel.ZIndexProperty>.  
  
 Um zu verhindern, dass ausgeblendete <xref:System.Windows.Controls.GridSplitter> Steuerelemente, führen Sie eine der folgenden.  
  
-   Stellen Sie sicher, dass <xref:System.Windows.Controls.GridSplitter> Steuerelemente werden als letzte <xref:System.Windows.Controls.Panel.Children%2A> hinzugefügt, um die <xref:System.Windows.Controls.Grid>. Das folgende Beispiel zeigt die <xref:System.Windows.Controls.GridSplitter> als das letzte Element in der <xref:System.Windows.Controls.Panel.Children%2A> Auflistung von der <xref:System.Windows.Controls.Grid>.  
  
 [!code-xaml[GridSplitterSnips#GridSplitterLastChild](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterlastchild)]  
  
-   Legen Sie die <xref:System.Windows.Controls.Panel.ZIndexProperty> auf die <xref:System.Windows.Controls.GridSplitter> höher als ein Steuerelement sein, die andernfalls ausblendet. Das folgende Beispiel gibt die <xref:System.Windows.Controls.GridSplitter> steuern eine höhere <xref:System.Windows.Controls.Panel.ZIndexProperty> als die <xref:System.Windows.Controls.Button> Steuerelement.  
  
 [!code-xaml[GridSplitterSnips#GridSplitterZIndex](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterzindex)]  
  
-   Legen Sie Seitenränder für das Steuerelement, das andernfalls verdecken würde die <xref:System.Windows.Controls.GridSplitter> , damit die <xref:System.Windows.Controls.GridSplitter> verfügbar gemacht wird. Im folgenden Beispiel wird die Ränder auf ein Steuerelement, das andernfalls überlagert würde und Ausblenden der <xref:System.Windows.Controls.GridSplitter>.  
  
 [!code-xaml[GridSplitterSnips#GridSplitterMargin](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplittermargin)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.GridSplitter>  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)
