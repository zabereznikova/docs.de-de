---
title: 'Gewusst wie: Programmgesteuertes Ändern der TextWrapping-Eigenschaft'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], changing TextWrapping property programmatically
- TextWrapping property [WPF], changing programmatically
ms.assetid: 30d25554-4c82-4df9-a8d6-35683a4a13bb
ms.openlocfilehash: 1b0f039f0484d1d1e73c3c12af06e0faffbce1cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543328"
---
# <a name="how-to-change-the-textwrapping-property-programmatically"></a>Gewusst wie: Programmgesteuertes Ändern der TextWrapping-Eigenschaft
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie zum Ändern des Werts, der die <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> Eigenschaft programmgesteuert.  
  
 Drei <xref:System.Windows.Controls.Button> Elemente befinden sich innerhalb einer <xref:System.Windows.Controls.StackPanel> Element im [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Jede <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignis für eine <xref:System.Windows.Controls.Button> entspricht einem Ereignishandler im Code. Die Ereignishandler verwenden den gleichen Namen wie die <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> Wert auf `txt2` Wenn die Schaltfläche geklickt wird. Außerdem wird der Text in `txt1` (eine <xref:System.Windows.Controls.TextBlock> nicht angezeigt, der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]) wird aktualisiert, um die Änderung in der Eigenschaft.  
  
 [!code-xaml[TextWrapProperty#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml#1)]  
  
 [!code-csharp[TextWrapProperty#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextWrapProperty/CSharp/Window1.xaml.cs#2)]
 [!code-vb[TextWrapProperty#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml.vb#2)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>  
 <xref:System.Windows.TextWrapping>
