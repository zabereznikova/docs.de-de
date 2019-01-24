---
title: 'Vorgehensweise: Erstellen eines Expanders mit einem ScrollViewer'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Expander
- ScrollViewer control [WPF], with Expander control
- Expander control [WPF], creating
- controls [WPF], ScrollViewer
ms.assetid: 2ad124d2-2406-4157-aaf2-64e067298f01
ms.openlocfilehash: 8d21c7ec0172dca23f218a0d710c3976872f162c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54681962"
---
# <a name="how-to-create-an-expander-with-a-scrollviewer"></a>Vorgehensweise: Erstellen eines Expanders mit einem ScrollViewer
Dieses Beispiel zeigt, wie Sie erstellen eine <xref:System.Windows.Controls.Expander> -Steuerelement, das komplexen Inhalt, z. B. ein Bild und Text enthält. Dieses Beispiel enthält auch den Inhalt der <xref:System.Windows.Controls.Expander> in einem <xref:System.Windows.Controls.ScrollViewer> Steuerelement.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie erstellen eine <xref:System.Windows.Controls.Expander>. Im Beispiel wird eine <xref:System.Windows.Controls.Primitives.BulletDecorator> Steuerelement, das ein Bild und Text enthält, um zu definieren die <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>. Ein <xref:System.Windows.Controls.ScrollViewer> Steuerelement stellt eine Methode zum Durchführen eines Bildlaufs des erweiterten Inhalts.  
  
 Beachten Sie, die im Beispiel wird die <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaft für die <xref:System.Windows.Controls.ScrollViewer> anstelle von auf dem Inhalt. Wenn die <xref:System.Windows.FrameworkElement.Height%2A> festgelegt ist, auf dem Inhalt der <xref:System.Windows.Controls.ScrollViewer> lässt sich nicht auf der Benutzer den Inhalt einen Bildlauf durchführen. Die <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaft wird festgelegt, auf die <xref:System.Windows.Controls.Expander> Kontrolle und diese Einstellung gilt für die <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> und den erweiterten Inhalt.  
  
 [!code-xaml[ExpanderRichContent#CreateExpander](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#createexpander)]  
  
 [!code-csharp[ExpanderRichContent#CreateExpanderCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#createexpandercode)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Controls.Expander>
- [Übersicht über Expander-Steuerelemente](../../../../docs/framework/wpf/controls/expander-overview.md)
- [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/controls/expander-how-to-topics.md)
