---
title: 'Vorgehensweise: Anwenden von Stretch-Eigenschaften auf den Inhalt einer Viewbox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StretchDirection properties [WPF]
- Stretch properties [WPF]
- controls [WPF], Viewbox
- Viewbox control [WPF]
ms.assetid: b9c22ef4-bce4-4300-9e0c-8260b7db83cc
ms.openlocfilehash: 9ddf3e8fb0c1a75c8917dfd50876f9259e292fb1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54711719"
---
# <a name="how-to-apply-stretch-properties-to-the-contents-of-a-viewbox"></a>Vorgehensweise: Anwenden von Stretch-Eigenschaften auf den Inhalt einer Viewbox
## <a name="example"></a>Beispiel  
 Dieses Beispiel zeigt, wie Sie den Wert ändern der <xref:System.Windows.Controls.Viewbox.StretchDirection%2A> und <xref:System.Windows.Controls.Viewbox.Stretch%2A> Eigenschaften eine <xref:System.Windows.Controls.Viewbox>.  
  
 Im ersten Beispiel wird [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] zum Definieren einer <xref:System.Windows.Controls.Viewbox> Element. Weist eine <xref:System.Windows.FrameworkElement.MaxWidth%2A> und <xref:System.Windows.FrameworkElement.MaxHeight%2A> 400. Das Beispiel schachtelt einen <xref:System.Windows.Controls.Image> Element innerhalb der <xref:System.Windows.Controls.Viewbox>. <xref:System.Windows.Controls.Button> Elemente, die die Eigenschaftswerte für entsprechen, den <xref:System.Windows.Controls.Viewbox.Stretch%2A> und <xref:System.Windows.Controls.StretchDirection> Enumerationen ändern das stretching Verhalten des geschachtelten <xref:System.Windows.Controls.Image>.  
  
 [!code-xaml[viewboxStretchLayoutSamp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/viewboxStretchLayoutSamp/CSharp/Window1.xaml#1)]  
  
 Der folgende Code-Behind-Datei verarbeitet die <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignisse, die den vorherigen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Beispiel definiert.  
  
 [!code-csharp[viewboxStretchLayoutSamp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/viewboxStretchLayoutSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[viewboxStretchLayoutSamp#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/viewboxStretchLayoutSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Controls.Viewbox>
- <xref:System.Windows.Media.Stretch>
- <xref:System.Windows.Controls.StretchDirection>
