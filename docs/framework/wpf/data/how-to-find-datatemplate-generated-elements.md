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
ms.openlocfilehash: f9265e3f7b287e1e8c264e89325f7c9649eebe2c
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459132"
---
# <a name="how-to-find-datatemplate-generated-elements"></a>Gewusst wie: Suchen von Elementen, die mit einer DataTemplate generiert wurden
In diesem Beispiel wird gezeigt, wie Sie nach Elementen suchen, die von einem <xref:System.Windows.DataTemplate>generiert werden.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel gibt es eine <xref:System.Windows.Controls.ListBox>, die an einige [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten gebunden ist:  
  
 [!code-xaml[FindGeneratedItems#LB](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#lb)]  
  
 Der <xref:System.Windows.Controls.ListBox> verwendet folgende <xref:System.Windows.DataTemplate>:  
  
 [!code-xaml[FindGeneratedItems#DT](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#dt)]  
  
 Wenn Sie das <xref:System.Windows.Controls.TextBlock> Element abrufen möchten, das von der <xref:System.Windows.DataTemplate> eines bestimmten <xref:System.Windows.Controls.ListBoxItem>generiert wird, müssen Sie die <xref:System.Windows.Controls.ListBoxItem>abrufen, die <xref:System.Windows.Controls.ContentPresenter> in diesem <xref:System.Windows.Controls.ListBoxItem>suchen und dann <xref:System.Windows.FrameworkTemplate.FindName%2A> für den <xref:System.Windows.DataTemplate> aufrufen, der auf festgelegt ist. Diese <xref:System.Windows.Controls.ContentPresenter>. Im folgenden Beispiel wird gezeigt, wie diese Schritte ausgeführt werden. Zu Demonstrationszwecken wird in diesem Beispiel ein Meldungs Feld erstellt, in dem der Text Inhalt des <xref:System.Windows.DataTemplate>generierten Textblocks angezeigt wird.  
  
 [!code-csharp[FindGeneratedItems#DTFindElement](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#dtfindelement)]
 [!code-vb[FindGeneratedItems#DTFindElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#dtfindelement)]  
  
 Im folgenden finden Sie die Implementierung von `FindVisualChild`, die die <xref:System.Windows.Media.VisualTreeHelper>-Methoden verwendet:  
  
 [!code-csharp[FindGeneratedItems#FVC](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#fvc)]
 [!code-vb[FindGeneratedItems#FVC](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#fvc)]  
  
## <a name="see-also"></a>Siehe auch

- [Gewusst wie: Suchen von Elementen, die mit einer ControlTemplate generiert wurden](../controls/how-to-find-controltemplate-generated-elements.md)
- [Übersicht zur Datenbindung](data-binding-overview.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
- [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [WPF-XAML-Namescopes](../advanced/wpf-xaml-namescopes.md)
- [Strukturen in WPF](../advanced/trees-in-wpf.md)
