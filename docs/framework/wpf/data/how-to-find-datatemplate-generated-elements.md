---
title: 'Vorgehensweise: Suchen von Elementen, die mit einer DataTemplate-Klasse generiert wurden'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- finding DataTemplate elements [WPF]
- DataTemplate [WPF]
ms.assetid: bfcd564e-5e9e-451e-8641-a9b5c3cfac90
ms.openlocfilehash: de5a4937feabdb4486d9dcf9d5e5bfddd2356690
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089171"
---
# <a name="how-to-find-datatemplate-generated-elements"></a>Vorgehensweise: Suchen von Elementen, die mit einer DataTemplate-Klasse generiert wurden
In diesem Beispiel zeigt, wie Sie Elemente, die vom generierten eine <xref:System.Windows.DataTemplate>.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel besteht eine <xref:System.Windows.Controls.ListBox> , gebunden ist, auf einige [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten:  
  
 [!code-xaml[FindGeneratedItems#LB](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#lb)]  
  
 Die <xref:System.Windows.Controls.ListBox> verwendet die folgenden <xref:System.Windows.DataTemplate>:  
  
 [!code-xaml[FindGeneratedItems#DT](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#dt)]  
  
 Wenn Sie abrufen möchten die <xref:System.Windows.Controls.TextBlock> vom generierten Elements der <xref:System.Windows.DataTemplate> eines bestimmten <xref:System.Windows.Controls.ListBoxItem>, benötigen Sie die <xref:System.Windows.Controls.ListBoxItem>, finden Sie die <xref:System.Windows.Controls.ContentPresenter> innerhalb der <xref:System.Windows.Controls.ListBoxItem>, und rufen Sie anschließend <xref:System.Windows.FrameworkTemplate.FindName%2A> auf die <xref:System.Windows.DataTemplate> die festgelegt ist, <xref:System.Windows.Controls.ContentPresenter>. Das folgende Beispiel zeigt, wie Sie diese Schritte ausführen. Zu Demonstrationszwecken in diesem Beispiel erstellt ein Meldungsfeld, das den Text zeigt Inhalt der <xref:System.Windows.DataTemplate>-TextBlock generiert.  
  
 [!code-csharp[FindGeneratedItems#DTFindElement](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#dtfindelement)]
 [!code-vb[FindGeneratedItems#DTFindElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#dtfindelement)]  
  
 Im folgenden wird die Implementierung von `FindVisualChild`, verwendet der <xref:System.Windows.Media.VisualTreeHelper> Methoden:  
  
 [!code-csharp[FindGeneratedItems#FVC](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#fvc)]
 [!code-vb[FindGeneratedItems#FVC](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#fvc)]  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Suchen von Elementen, die mit einer ControlTemplate generiert wurden](../controls/how-to-find-controltemplate-generated-elements.md)
- [Übersicht über die Datenbindung](data-binding-overview.md)
- [Gewusst wie-Themen](data-binding-how-to-topics.md)
- [Erstellen von Formaten und Vorlagen](../controls/styling-and-templating.md)
- [WPF-XAML-Namescopes](../advanced/wpf-xaml-namescopes.md)
- [Strukturen in WPF](../advanced/trees-in-wpf.md)
