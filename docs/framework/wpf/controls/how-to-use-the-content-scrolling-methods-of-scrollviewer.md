---
title: 'Vorgehensweise: Verwenden der ScrollViewer-Bildlaufmethoden'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- IScrollInfo interface [WPF]
- scrolling methods [WPF]
- ScrollViewer control [WPF], scrolling methods
ms.assetid: 4708cc65-6510-45f8-82e6-30b0d3e30045
ms.openlocfilehash: e81c63de16d09de8435d5ec49a013bf8dc5927cd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697303"
---
# <a name="how-to-use-the-content-scrolling-methods-of-scrollviewer"></a><span data-ttu-id="cdb04-102">Vorgehensweise: Verwenden der ScrollViewer-Bildlaufmethoden</span><span class="sxs-lookup"><span data-stu-id="cdb04-102">How to: Use the Content-Scrolling Methods of ScrollViewer</span></span>
<span data-ttu-id="cdb04-103">Dieses Beispiel zeigt, wie Sie mit der Bildlaufmethoden des der <xref:System.Windows.Controls.ScrollViewer> Element.</span><span class="sxs-lookup"><span data-stu-id="cdb04-103">This example shows how to use the scrolling methods of the <xref:System.Windows.Controls.ScrollViewer> element.</span></span> <span data-ttu-id="cdb04-104">Diese Methoden bieten inkrementellen Bildlauf in Inhalten, indem Zeile oder Seite einem <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="cdb04-104">These methods provide incremental scrolling of content, either by line or by page, in a <xref:System.Windows.Controls.ScrollViewer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cdb04-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cdb04-105">Example</span></span>  
 <span data-ttu-id="cdb04-106">Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.ScrollViewer> mit dem Namen `sv1`, das ein untergeordnetes Element hostet <xref:System.Windows.Controls.TextBlock> Element.</span><span class="sxs-lookup"><span data-stu-id="cdb04-106">The following example creates a <xref:System.Windows.Controls.ScrollViewer> named `sv1`, which hosts a child <xref:System.Windows.Controls.TextBlock> element.</span></span> <span data-ttu-id="cdb04-107">Da die <xref:System.Windows.Controls.TextBlock> ist größer als das übergeordnete Element <xref:System.Windows.Controls.ScrollViewer>, Bildlaufleisten angezeigt werden, um einen Bildlauf zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="cdb04-107">Because the <xref:System.Windows.Controls.TextBlock> is larger than the parent <xref:System.Windows.Controls.ScrollViewer>, scroll bars appear in order to enable scrolling.</span></span> <span data-ttu-id="cdb04-108"><xref:System.Windows.Controls.Button> Elemente, die die verschiedenen Bildlaufmethoden darstellen, die auf der linken Seite in einem separaten angedockt sind <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="cdb04-108"><xref:System.Windows.Controls.Button> elements that represent the various scrolling methods are docked on the left in a separate <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="cdb04-109">Jede <xref:System.Windows.Controls.Button> in die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei ruft eine zugeordnete benutzerdefinierte Methode, die in Scrollverhalten steuert <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="cdb04-109">Each <xref:System.Windows.Controls.Button> in the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file calls a related custom method that controls scrolling behavior in <xref:System.Windows.Controls.ScrollViewer>.</span></span>  
  
 [!code-xaml[ScrollViewerMethods#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="cdb04-110">Im folgenden Beispiel wird die <xref:System.Windows.Controls.ScrollViewer.LineUp%2A> und <xref:System.Windows.Controls.ScrollViewer.LineDown%2A> Methoden.</span><span class="sxs-lookup"><span data-stu-id="cdb04-110">The following example uses the <xref:System.Windows.Controls.ScrollViewer.LineUp%2A> and <xref:System.Windows.Controls.ScrollViewer.LineDown%2A> methods.</span></span>  
  
 [!code-csharp[ScrollViewerMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ScrollViewerMethods#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewerMethods/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="cdb04-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cdb04-111">See also</span></span>

- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.StackPanel>
