---
title: 'Vorgehensweise: Suchen des Quellelements in einem Ereignishandler'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source element in event handlers [WPF]
- event handlers [WPF], finding source element in
ms.assetid: 85f71c5a-b714-4c65-9711-7d905c2bbe98
ms.openlocfilehash: 4cdf1434f2d341cbc1e65541fd02ab4b5cad194d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536736"
---
# <a name="how-to-find-the-source-element-in-an-event-handler"></a>Vorgehensweise: Suchen des Quellelements in einem Ereignishandler
Dieses Beispiel zeigt, wie Sie das Quellelement in einem Ereignishandler.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignishandler, die in einer CodeBehind-Datei deklariert wird. Wenn ein Benutzer die Schaltfläche, der der Handler zugeordnet ist klickt, ändert der Handler einen Eigenschaftswert an. Der Handlercode verwendet die <xref:System.Windows.RoutedEventArgs.Source%2A> Eigenschaft von die Routingereignisdaten, die in den Ereignisargumenten gemeldet wird, so ändern Sie die <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaftswert auf die <xref:System.Windows.RoutedEventArgs.Source%2A> Element.  
  
 [!code-xaml[RoutedEventSource#XAMLHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml#xamlhandler)]  
  
 [!code-csharp[RoutedEventSource#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventSource#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventSource/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.RoutedEventArgs>
- [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
- [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)
