---
title: 'Gewusst wie: Suchen des Quellelements in einem Ereignishandler'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source element in event handlers [WPF]
- event handlers [WPF], finding source element in
ms.assetid: 85f71c5a-b714-4c65-9711-7d905c2bbe98
ms.openlocfilehash: c3ae893cd7fd7780854d6eb6ffd682feadb5c5a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544000"
---
# <a name="how-to-find-the-source-element-in-an-event-handler"></a><span data-ttu-id="31179-102">Gewusst wie: Suchen des Quellelements in einem Ereignishandler</span><span class="sxs-lookup"><span data-stu-id="31179-102">How to: Find the Source Element in an Event Handler</span></span>
<span data-ttu-id="31179-103">Dieses Beispiel zeigt, wie Sie die Source-Element in einem Ereignishandler zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="31179-103">This example shows how to find the source element in an event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31179-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="31179-104">Example</span></span>  
 <span data-ttu-id="31179-105">Das folgende Beispiel zeigt eine <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignishandler, der in einer Code-Behind-Datei deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="31179-105">The following example shows a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler that is declared in a code-behind file.</span></span> <span data-ttu-id="31179-106">Wenn ein Benutzer die Schaltfläche, der der Handler angefügt ist klickt, ändert der Handler einen Eigenschaftswert.</span><span class="sxs-lookup"><span data-stu-id="31179-106">When a user clicks the button that the handler is attached to, the handler changes a property value.</span></span> <span data-ttu-id="31179-107">Der Handlercode verwendet die <xref:System.Windows.RoutedEventArgs.Source%2A> Eigenschaft Routingereignis Daten, die in den Ereignisargumenten gemeldet wird, so ändern Sie die <xref:System.Windows.FrameworkElement.Width%2A> -Eigenschaftenwert der <xref:System.Windows.RoutedEventArgs.Source%2A> Element.</span><span class="sxs-lookup"><span data-stu-id="31179-107">The handler code uses the <xref:System.Windows.RoutedEventArgs.Source%2A> property of the routed event data that is reported in the event arguments to change the <xref:System.Windows.FrameworkElement.Width%2A> property value on the <xref:System.Windows.RoutedEventArgs.Source%2A> element.</span></span>  
  
 [!code-xaml[RoutedEventSource#XAMLHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml#xamlhandler)]  
  
 [!code-csharp[RoutedEventSource#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventSource#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventSource/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a><span data-ttu-id="31179-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31179-108">See Also</span></span>  
 <xref:System.Windows.RoutedEventArgs>  
 [<span data-ttu-id="31179-109">Übersicht über Routingereignisse</span><span class="sxs-lookup"><span data-stu-id="31179-109">Routed Events Overview</span></span>](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [<span data-ttu-id="31179-110">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="31179-110">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)
