---
title: 'Gewusst wie: Suchen des Quellelements in einem Ereignishandler'
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
- source element in event handlers [WPF]
- event handlers [WPF], finding source element in
ms.assetid: 85f71c5a-b714-4c65-9711-7d905c2bbe98
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d62d657b886b867481088e32fe1dd0614377e146
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-find-the-source-element-in-an-event-handler"></a>Gewusst wie: Suchen des Quellelements in einem Ereignishandler
Dieses Beispiel zeigt, wie Sie die Source-Element in einem Ereignishandler zu ermitteln.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignishandler, der in einer Code-Behind-Datei deklariert ist. Wenn ein Benutzer die Schaltfläche, der der Handler angefügt ist klickt, ändert der Handler einen Eigenschaftswert. Der Handlercode verwendet die <xref:System.Windows.RoutedEventArgs.Source%2A> Eigenschaft Routingereignis Daten, die in den Ereignisargumenten gemeldet wird, so ändern Sie die <xref:System.Windows.FrameworkElement.Width%2A> -Eigenschaftenwert der <xref:System.Windows.RoutedEventArgs.Source%2A> Element.  
  
 [!code-xaml[RoutedEventSource#XAMLHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml#xamlhandler)]  
  
 [!code-csharp[RoutedEventSource#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventSource#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventSource/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.RoutedEventArgs>  
 [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)
