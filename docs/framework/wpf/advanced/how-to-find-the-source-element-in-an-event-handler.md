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
ms.openlocfilehash: e9746683ec5b7ad142591c2b419f9af21be8d69c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-find-the-source-element-in-an-event-handler"></a><span data-ttu-id="b5f75-102">Gewusst wie: Suchen des Quellelements in einem Ereignishandler</span><span class="sxs-lookup"><span data-stu-id="b5f75-102">How to: Find the Source Element in an Event Handler</span></span>
<span data-ttu-id="b5f75-103">Dieses Beispiel zeigt, wie Sie die Source-Element in einem Ereignishandler zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="b5f75-103">This example shows how to find the source element in an event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5f75-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b5f75-104">Example</span></span>  
 <span data-ttu-id="b5f75-105">Das folgende Beispiel zeigt eine <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignishandler, der in einer Code-Behind-Datei deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="b5f75-105">The following example shows a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler that is declared in a code-behind file.</span></span> <span data-ttu-id="b5f75-106">Wenn ein Benutzer die Schaltfläche, der der Handler angefügt ist klickt, ändert der Handler einen Eigenschaftswert.</span><span class="sxs-lookup"><span data-stu-id="b5f75-106">When a user clicks the button that the handler is attached to, the handler changes a property value.</span></span> <span data-ttu-id="b5f75-107">Der Handlercode verwendet die <xref:System.Windows.RoutedEventArgs.Source%2A> Eigenschaft Routingereignis Daten, die in den Ereignisargumenten gemeldet wird, so ändern Sie die <xref:System.Windows.FrameworkElement.Width%2A> -Eigenschaftenwert der <xref:System.Windows.RoutedEventArgs.Source%2A> Element.</span><span class="sxs-lookup"><span data-stu-id="b5f75-107">The handler code uses the <xref:System.Windows.RoutedEventArgs.Source%2A> property of the routed event data that is reported in the event arguments to change the <xref:System.Windows.FrameworkElement.Width%2A> property value on the <xref:System.Windows.RoutedEventArgs.Source%2A> element.</span></span>  
  
 [!code-xaml[RoutedEventSource#XAMLHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml#xamlhandler)]  
  
 [!code-csharp[RoutedEventSource#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventSource#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventSource/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a><span data-ttu-id="b5f75-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b5f75-108">See Also</span></span>  
 <xref:System.Windows.RoutedEventArgs>  
 [<span data-ttu-id="b5f75-109">Übersicht über Routingereignisse</span><span class="sxs-lookup"><span data-stu-id="b5f75-109">Routed Events Overview</span></span>](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [<span data-ttu-id="b5f75-110">Themen zur Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="b5f75-110">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)
