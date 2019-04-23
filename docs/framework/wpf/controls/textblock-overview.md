---
title: Übersicht über TextBlock
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], TextBlock
- TextBlock control [WPF]
ms.assetid: 24720bca-341a-4b03-8a6b-7a678023b10a
ms.openlocfilehash: ce7da2b9c9c8e2a3a24d3acf18396ca447ac3f27
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59772727"
---
# <a name="textblock-overview"></a>Übersicht über TextBlock
Die <xref:System.Windows.Controls.TextBlock> Steuerelement bietet flexible textunterstützung für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen. Es eignet sich hauptsächlich für einfache [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Szenarios, in denen nicht mehr Text als ein Absatz benötigt wird. Unterstützt eine Reihe von Eigenschaften, mit denen präzise gesteuert, wie z. B. <xref:System.Windows.Controls.TextBlock.FontFamily%2A>, <xref:System.Windows.Controls.TextBlock.FontSize%2A>, <xref:System.Windows.Controls.TextBlock.FontWeight%2A>, <xref:System.Windows.Controls.TextBlock.TextEffects%2A>, und <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>. Text-Inhalt kann hinzugefügt werden, mithilfe der <xref:System.Windows.Controls.TextBlock.Text%2A> Eigenschaft. Bei der Verwendung in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] wird der Inhalt zwischen dem öffnenden und dem schließenden Tag implizit als Text des Elements hinzugefügt.  
  
 Ein <xref:System.Windows.Controls.TextBlock> Element kann instanziiert werden, sehr einfach mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[TextBlockSnip_XAML#2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBlockSnip_XAML/CS/default.xaml#2)]  
  
 Auf ähnliche Weise die Verwendung von der <xref:System.Windows.Controls.TextBlock> Element im Code ist relativ einfach.  
  
 [!code-csharp[TextBlockSnip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBlockSnip/CSharp/TextBlockSnips.cs#1)]
 [!code-vb[TextBlockSnip#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBlockSnip/VisualBasic/TextBlockSnips.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.Label>
