---
title: 'Gewusst wie: Behandeln des ScrollChanged-Ereignisses'
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
- ScrollViewer control [WPF], raising ScrollChanged events
- ScrollChanged events [WPF]
ms.assetid: 42c695d8-ee28-49d4-80fd-fc71e9be7f29
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c1b90566fd3f962a1e3a383c4edd93f09e6206c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-handle-the-scrollchanged-event"></a><span data-ttu-id="44fcf-102">Gewusst wie: Behandeln des ScrollChanged-Ereignisses</span><span class="sxs-lookup"><span data-stu-id="44fcf-102">How to: Handle the ScrollChanged Event</span></span>
## <a name="example"></a><span data-ttu-id="44fcf-103">Beispiel</span><span class="sxs-lookup"><span data-stu-id="44fcf-103">Example</span></span>  
 <span data-ttu-id="44fcf-104">In diesem Beispiel wird gezeigt, wie behandelt die <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> -Ereignis für ein <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="44fcf-104">This example shows how to handle the <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> event of a <xref:System.Windows.Controls.ScrollViewer>.</span></span>  
  
 <span data-ttu-id="44fcf-105">Ein <xref:System.Windows.Documents.FlowDocument> Element mit <xref:System.Windows.Documents.Paragraph> Teile ist definiert [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44fcf-105">A <xref:System.Windows.Documents.FlowDocument> element with <xref:System.Windows.Documents.Paragraph> parts is defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="44fcf-106">Wenn die <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> Ereignis tritt auf, aufgrund von Benutzerinteraktionen, wird ein Handler aufgerufen und Text geschrieben wird ein <xref:System.Windows.Controls.TextBlock> , der angibt, der das Ereignis aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="44fcf-106">When the <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> event occurs due to user interaction, a handler is invoked, and text is written to a <xref:System.Windows.Controls.TextBlock> indicating that the event has occurred.</span></span>  
  
 [!code-xaml[scrollchangedeventargsLayout#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/scrollchangedeventargsLayout/CSharp/Window1.xaml#1)]  
[!code-xaml[scrollchangedeventargsLayout#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/scrollchangedeventargsLayout/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[scrollchangedeventargsLayout#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/scrollchangedeventargsLayout/CSharp/Window1.xaml.cs#3)]
 [!code-vb[scrollchangedeventargsLayout#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/scrollchangedeventargsLayout/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="44fcf-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="44fcf-107">See Also</span></span>  
 <xref:System.Windows.Controls.ScrollViewer>  
 <xref:System.Windows.Controls.ScrollViewer.ScrollChanged>  
 <xref:System.Windows.Controls.ScrollChangedEventHandler>  
 <xref:System.Windows.Controls.ScrollChangedEventArgs>
