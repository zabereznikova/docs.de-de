---
title: 'Vorgehensweise: Durchführen eines Bildlaufs von Inhalten mithilfe der IScrollInfo-Schnittstelle'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ScrollViewer control [WPF], scrolling content
- scrolling content [WPF]
- IScrollInfo interface [WPF]
ms.assetid: d8700bef-a3f8-4c12-9de2-fc3b79f32cd3
ms.openlocfilehash: 49b3483750582aa51d1de418f745d931604d2786
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54637858"
---
# <a name="how-to-scroll-content-by-using-the-iscrollinfo-interface"></a>Vorgehensweise: Durchführen eines Bildlaufs von Inhalten mithilfe der IScrollInfo-Schnittstelle
Dieses Beispiel veranschaulicht das Scrollen von Inhalt mithilfe der <xref:System.Windows.Controls.Primitives.IScrollInfo> Schnittstelle.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Funktionen von der <xref:System.Windows.Controls.Primitives.IScrollInfo> Schnittstelle. Das Beispiel erstellt eine <xref:System.Windows.Controls.StackPanel> Element im [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , die in ein übergeordnetes Element geschachtelt ist <xref:System.Windows.Controls.ScrollViewer>. Die untergeordneten Elemente des der <xref:System.Windows.Controls.StackPanel> Bildlauf möglich logisch mithilfe von definierten Methoden den <xref:System.Windows.Controls.Primitives.IScrollInfo> Schnittstelle und die Umwandlung in die Instanz von <xref:System.Windows.Controls.StackPanel> (`sp1`) im Code.  
  
 [!code-xaml[IScrollInfoMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml#2)]  
  
 Jede <xref:System.Windows.Controls.Button> in die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei löst eine zugeordnete benutzerdefinierte Methode, die in Scrollverhalten steuert <xref:System.Windows.Controls.StackPanel>. Das folgende Beispiel zeigt, wie Sie mit der <xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> und <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A> Methoden es zeigt auch generisch wie alle Methoden, die die Positionierung verwenden, die die <xref:System.Windows.Controls.Primitives.IScrollInfo> -Klasse definiert.  
  
 [!code-csharp[IScrollInfoMethods#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.Primitives.IScrollInfo>
- <xref:System.Windows.Controls.StackPanel>
- [Übersicht über ScrollViewer](../../../../docs/framework/wpf/controls/scrollviewer-overview.md)
- [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/controls/scrollviewer-how-to-topics.md)
- [Übersicht über Panel-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)
