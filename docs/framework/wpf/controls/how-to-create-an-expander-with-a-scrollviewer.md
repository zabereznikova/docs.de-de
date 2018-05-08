---
title: 'Gewusst wie: Erstellen eines Expanders mit einem ScrollViewer'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Expander
- ScrollViewer control [WPF], with Expander control
- Expander control [WPF], creating
- controls [WPF], ScrollViewer
ms.assetid: 2ad124d2-2406-4157-aaf2-64e067298f01
ms.openlocfilehash: 6c014d4f6a12bfb58c2ae68f580f632c9478c82f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-an-expander-with-a-scrollviewer"></a>Gewusst wie: Erstellen eines Expanders mit einem ScrollViewer
In diesem Beispiel wird gezeigt, wie zum Erstellen einer <xref:System.Windows.Controls.Expander> Steuerelement, das komplexen Inhalt, z. B. ein Bild und Text enthält. Dieses Beispiel enthält auch den Inhalt der <xref:System.Windows.Controls.Expander> in einer <xref:System.Windows.Controls.ScrollViewer> Steuerelement.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird gezeigt, wie zum Erstellen einer <xref:System.Windows.Controls.Expander>. Im Beispiel wird eine <xref:System.Windows.Controls.Primitives.BulletDecorator> Steuerelement, das ein Bild und Text enthält, um zu definieren die <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>. Ein <xref:System.Windows.Controls.ScrollViewer> Steuerelement stellt eine Methode für den erweiterten Inhalt zu scrollen.  
  
 Beachten Sie, dass im Beispiel die <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaft auf die <xref:System.Windows.Controls.ScrollViewer> statt auf den Inhalt. Wenn die <xref:System.Windows.FrameworkElement.Height%2A> festgelegt ist, auf dem Inhalt der <xref:System.Windows.Controls.ScrollViewer> lässt sich nicht auf der Benutzer den Inhalt einen Bildlauf durchführen. Die <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaft wird festgelegt, auf die <xref:System.Windows.Controls.Expander> -Steuerelement, und diese Einstellung gilt für die <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> und den erweiterten Inhalt.  
  
 [!code-xaml[ExpanderRichContent#CreateExpander](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#createexpander)]  
  
 [!code-csharp[ExpanderRichContent#CreateExpanderCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#createexpandercode)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.Expander>  
 [Übersicht über Expander-Steuerelemente](../../../../docs/framework/wpf/controls/expander-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/controls/expander-how-to-topics.md)
