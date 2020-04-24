---
title: 'Gewusst wie: Suchen von Elementen, die mit einer DataTemplate generiert wurden'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- finding DataTemplate elements [WPF]
- DataTemplate [WPF]
ms.assetid: bfcd564e-5e9e-451e-8641-a9b5c3cfac90
ms.openlocfilehash: 3b222880aa4eda32502e3dcece2fa5c0b57b7a51
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646431"
---
# <a name="how-to-find-datatemplate-generated-elements"></a>Gewusst wie: Suchen von Elementen, die mit einer DataTemplate generiert wurden
In diesem Beispiel wird gezeigt, wie <xref:System.Windows.DataTemplate>Elemente gefunden werden, die von einer generiert werden.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel gibt <xref:System.Windows.Controls.ListBox> es eine, die an einige XML-Daten gebunden ist:  
  
 [!code-xaml[FindGeneratedItems#LB](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#lb)]  
  
 Die <xref:System.Windows.Controls.ListBox> verwendet <xref:System.Windows.DataTemplate>die folgenden:  
  
 [!code-xaml[FindGeneratedItems#DT](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#dt)]  
  
 Wenn <xref:System.Windows.Controls.TextBlock> Sie das von einem <xref:System.Windows.DataTemplate> bestimmten <xref:System.Windows.Controls.ListBoxItem>generierte Element abrufen <xref:System.Windows.Controls.ListBoxItem>möchten, <xref:System.Windows.Controls.ContentPresenter> müssen <xref:System.Windows.Controls.ListBoxItem>Sie die <xref:System.Windows.FrameworkTemplate.FindName%2A> abrufen, <xref:System.Windows.DataTemplate> die innerhalb <xref:System.Windows.Controls.ContentPresenter>des suchen, und dann die aufrufen, die für diese festgelegt ist. Das folgende Beispiel zeigt, wie diese Schritte ausgeführt werden. Zu Demonstrationszwecken wird in diesem Beispiel ein Meldungsfeld erstellt, das den Textinhalt des <xref:System.Windows.DataTemplate>-generierten Textblocks anzeigt.  
  
 [!code-csharp[FindGeneratedItems#DTFindElement](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#dtfindelement)]
 [!code-vb[FindGeneratedItems#DTFindElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#dtfindelement)]  
  
 Im Folgenden finden `FindVisualChild`Sie die <xref:System.Windows.Media.VisualTreeHelper> Implementierung von , die die Methoden verwendet:  
  
 [!code-csharp[FindGeneratedItems#FVC](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#fvc)]
 [!code-vb[FindGeneratedItems#FVC](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#fvc)]  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Suchen von Elementen, die mit einer ControlTemplate generiert wurden](../controls/how-to-find-controltemplate-generated-elements.md)
- [Datenbindung sübersicht](../../../desktop-wpf/data/data-binding-overview.md)
- [Themen zur Vorgehensweise](data-binding-how-to-topics.md)
- [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [WPF-XAML-Namescopes](../advanced/wpf-xaml-namescopes.md)
- [Strukturen in WPF](../advanced/trees-in-wpf.md)
