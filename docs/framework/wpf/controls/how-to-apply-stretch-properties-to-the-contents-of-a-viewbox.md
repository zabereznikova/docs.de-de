---
title: 'Gewusst wie: Anwenden von Stretch-Eigenschaften auf den Inhalt einer Viewbox'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StretchDirection properties [WPF]
- Stretch properties [WPF]
- controls [WPF], Viewbox
- Viewbox control [WPF]
ms.assetid: b9c22ef4-bce4-4300-9e0c-8260b7db83cc
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f6e93c744a8d7c294556e80f0ac4bf1f973ea5c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-apply-stretch-properties-to-the-contents-of-a-viewbox"></a>Gewusst wie: Anwenden von Stretch-Eigenschaften auf den Inhalt einer Viewbox
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird gezeigt, wie zum Ändern des Werts von der <xref:System.Windows.Controls.Viewbox.StretchDirection%2A> und <xref:System.Windows.Controls.Viewbox.Stretch%2A> Eigenschaften einer <xref:System.Windows.Controls.Viewbox>.  
  
 Im ersten Beispiel wird [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] zum Definieren einer <xref:System.Windows.Controls.Viewbox> Element. Weist eine <xref:System.Windows.FrameworkElement.MaxWidth%2A> und <xref:System.Windows.FrameworkElement.MaxHeight%2A> von 400. Das Beispiel schachtelt einen <xref:System.Windows.Controls.Image> Element innerhalb der <xref:System.Windows.Controls.Viewbox>. <xref:System.Windows.Controls.Button>Elemente, die Eigenschaftswerte für entsprechen, den <xref:System.Windows.Controls.Viewbox.Stretch%2A> und <xref:System.Windows.Controls.StretchDirection> Enumerationen bearbeitet das ausdehnen Verhalten des geschachtelten <xref:System.Windows.Controls.Image>.  
  
 [!code-xaml[viewboxStretchLayoutSamp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/viewboxStretchLayoutSamp/CSharp/Window1.xaml#1)]  
  
 Der folgende Code-Behind-Dateihandles der <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignisse, die der vorherigen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Beispiel definiert.  
  
 [!code-csharp[viewboxStretchLayoutSamp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/viewboxStretchLayoutSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[viewboxStretchLayoutSamp#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/viewboxStretchLayoutSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.Viewbox>  
 <xref:System.Windows.Media.Stretch>  
 <xref:System.Windows.Controls.StretchDirection>
