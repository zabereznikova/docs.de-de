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
ms.openlocfilehash: d46a408bc1b5fc512905aa5bf176b13bd1511865
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556782"
---
# <a name="how-to-find-datatemplate-generated-elements"></a>Gewusst wie: Suchen von Elementen, die mit einer DataTemplate generiert wurden
In diesem Beispiel wird gezeigt, wie nach Elementen suchen, die generiert werden, indem Sie eine <xref:System.Windows.DataTemplate>.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird eine <xref:System.Windows.Controls.ListBox> , gebunden ist, um einige [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten:  
  
 [!code-xaml[FindGeneratedItems#LB](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#lb)]  
  
 Die <xref:System.Windows.Controls.ListBox> verwendet die folgenden <xref:System.Windows.DataTemplate>:  
  
 [!code-xaml[FindGeneratedItems#DT](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#dt)]  
  
 Wenn Sie abrufen möchten die <xref:System.Windows.Controls.TextBlock> vom generierten Elements der <xref:System.Windows.DataTemplate> eines bestimmten <xref:System.Windows.Controls.ListBoxItem>, benötigen Sie die <xref:System.Windows.Controls.ListBoxItem>, suchen die <xref:System.Windows.Controls.ContentPresenter> innerhalb der <xref:System.Windows.Controls.ListBoxItem>, und rufen Sie anschließend <xref:System.Windows.FrameworkTemplate.FindName%2A> auf der <xref:System.Windows.DataTemplate> die darauf festgelegt ist <xref:System.Windows.Controls.ContentPresenter>. Im folgende Beispiel wird gezeigt, wie Sie diese Schritte ausführen. Zu Demonstrationszwecken in diesem Beispiel erstellt ein Meldungsfeld mit dem Text an der Inhalt der <xref:System.Windows.DataTemplate>-TextBlock generiert.  
  
 [!code-csharp[FindGeneratedItems#DTFindElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#dtfindelement)]
 [!code-vb[FindGeneratedItems#DTFindElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#dtfindelement)]  
  
 Im folgenden wird die Implementierung der `FindVisualChild`, verwendet die <xref:System.Windows.Media.VisualTreeHelper> Methoden:  
  
 [!code-csharp[FindGeneratedItems#FVC](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#fvc)]
 [!code-vb[FindGeneratedItems#FVC](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#fvc)]  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Suchen von Elementen, die mit einer ControlTemplate generiert wurden](../../../../docs/framework/wpf/controls/how-to-find-controltemplate-generated-elements.md)  
 [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)  
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [WPF-XAML-Namescopes](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md)  
 [Strukturen in WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)
