---
title: 'Vorgehensweise: Behandeln des ScrollChanged-Ereignisses'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ScrollViewer control [WPF], raising ScrollChanged events
- ScrollChanged events [WPF]
ms.assetid: 42c695d8-ee28-49d4-80fd-fc71e9be7f29
ms.openlocfilehash: 54f20a4b8c6e6fcc190257fcf5de4374415d68b4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771058"
---
# <a name="how-to-handle-the-scrollchanged-event"></a>Vorgehensweise: Behandeln des ScrollChanged-Ereignisses
## <a name="example"></a>Beispiel  
 Dieses Beispiel zeigt, wie behandelt die <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> Ereignis eine <xref:System.Windows.Controls.ScrollViewer>.  
  
 Ein <xref:System.Windows.Documents.FlowDocument> -Element mit <xref:System.Windows.Documents.Paragraph> Teile ist definiert [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Wenn die <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> Ereignis tritt auf, aufgrund der Interaktion des Benutzers, ein Handler aufgerufen und Text geschrieben wird eine <xref:System.Windows.Controls.TextBlock> , der angibt, die das Ereignis eingetreten ist.  
  
 [!code-xaml[scrollchangedeventargsLayout#1](~/samples/snippets/csharp/VS_Snippets_Wpf/scrollchangedeventargsLayout/CSharp/Window1.xaml#1)]  
[!code-xaml[scrollchangedeventargsLayout#2](~/samples/snippets/csharp/VS_Snippets_Wpf/scrollchangedeventargsLayout/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[scrollchangedeventargsLayout#3](~/samples/snippets/csharp/VS_Snippets_Wpf/scrollchangedeventargsLayout/CSharp/Window1.xaml.cs#3)]
 [!code-vb[scrollchangedeventargsLayout#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/scrollchangedeventargsLayout/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.ScrollViewer.ScrollChanged>
- <xref:System.Windows.Controls.ScrollChangedEventHandler>
- <xref:System.Windows.Controls.ScrollChangedEventArgs>
