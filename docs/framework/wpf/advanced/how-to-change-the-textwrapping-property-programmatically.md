---
title: 'Vorgehensweise: Programmgesteuertes Ändern der TextWrapping-Eigenschaft'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], changing TextWrapping property programmatically
- TextWrapping property [WPF], changing programmatically
ms.assetid: 30d25554-4c82-4df9-a8d6-35683a4a13bb
ms.openlocfilehash: 21ca31d24121492fe6927cd533d5b3c0785b5a28
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59095840"
---
# <a name="how-to-change-the-textwrapping-property-programmatically"></a>Vorgehensweise: Programmgesteuertes Ändern der TextWrapping-Eigenschaft
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie zum Ändern des Werts, der die <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> Eigenschaft programmgesteuert.  
  
 Drei <xref:System.Windows.Controls.Button> Elemente befinden sich in einem <xref:System.Windows.Controls.StackPanel> Element im [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Jede <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignis für eine <xref:System.Windows.Controls.Button> mit einem Ereignishandler im Code entspricht. Die Ereignishandler verwenden den gleichen Namen wie die <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> Wert auf `txt2` Wenn auf die Schaltfläche geklickt wird. Außerdem wird der Text in `txt1` (eine <xref:System.Windows.Controls.TextBlock> nicht angezeigt, der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]) aktualisiert, um die Änderung in der Eigenschaft widerzuspiegeln.  
  
 [!code-xaml[TextWrapProperty#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml#1)]  
  
 [!code-csharp[TextWrapProperty#2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextWrapProperty/CSharp/Window1.xaml.cs#2)]
 [!code-vb[TextWrapProperty#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml.vb#2)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>
- <xref:System.Windows.TextWrapping>
