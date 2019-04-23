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
ms.openlocfilehash: 9a49878c9ad8313903df4506796998fd43e2e749
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59104558"
---
# <a name="how-to-find-the-source-element-in-an-event-handler"></a><span data-ttu-id="2cfc4-102">Vorgehensweise: Suchen des Quellelements in einem Ereignishandler</span><span class="sxs-lookup"><span data-stu-id="2cfc4-102">How to: Find the Source Element in an Event Handler</span></span>
<span data-ttu-id="2cfc4-103">Dieses Beispiel zeigt, wie Sie das Quellelement in einem Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="2cfc4-103">This example shows how to find the source element in an event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2cfc4-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2cfc4-104">Example</span></span>  
 <span data-ttu-id="2cfc4-105">Das folgende Beispiel zeigt eine <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignishandler, die in einer CodeBehind-Datei deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="2cfc4-105">The following example shows a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler that is declared in a code-behind file.</span></span> <span data-ttu-id="2cfc4-106">Wenn ein Benutzer die Schaltfläche, der der Handler zugeordnet ist klickt, ändert der Handler einen Eigenschaftswert an.</span><span class="sxs-lookup"><span data-stu-id="2cfc4-106">When a user clicks the button that the handler is attached to, the handler changes a property value.</span></span> <span data-ttu-id="2cfc4-107">Der Handlercode verwendet die <xref:System.Windows.RoutedEventArgs.Source%2A> Eigenschaft von die Routingereignisdaten, die in den Ereignisargumenten gemeldet wird, so ändern Sie die <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaftswert auf die <xref:System.Windows.RoutedEventArgs.Source%2A> Element.</span><span class="sxs-lookup"><span data-stu-id="2cfc4-107">The handler code uses the <xref:System.Windows.RoutedEventArgs.Source%2A> property of the routed event data that is reported in the event arguments to change the <xref:System.Windows.FrameworkElement.Width%2A> property value on the <xref:System.Windows.RoutedEventArgs.Source%2A> element.</span></span>  
  
 [!code-xaml[RoutedEventSource#XAMLHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml#xamlhandler)]  
  
 [!code-csharp[RoutedEventSource#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventSource#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventSource/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a><span data-ttu-id="2cfc4-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2cfc4-108">See also</span></span>

- <xref:System.Windows.RoutedEventArgs>
- [<span data-ttu-id="2cfc4-109">Übersicht über Routingereignisse</span><span class="sxs-lookup"><span data-stu-id="2cfc4-109">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="2cfc4-110">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="2cfc4-110">How-to Topics</span></span>](events-how-to-topics.md)
