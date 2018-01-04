---
title: 'Gewusst wie: Verbessern der Bildlaufleistung eines Listenfelds'
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
- ListBox control [WPF], reusing item containers
- ListBox control [WPF], improving scrolling performance
ms.assetid: 1e2bf8f3-c8ce-47f7-a400-a7fe11d1a848
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 58435948a3ddd8042b95b30b8d6cbdba984f34d5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-improve-the-scrolling-performance-of-a-listbox"></a>Gewusst wie: Verbessern der Bildlaufleistung eines Listenfelds
Wenn eine <xref:System.Windows.Controls.ListBox> viele Elemente enthält, die Benutzerantwort Schnittstelle kann langsam sein, wenn ein Benutzer einen Bildlauf der <xref:System.Windows.Controls.ListBox> verwenden das Mausrad oder ziehen den Ziehpunkt einer Bildlaufleiste. Sie können die Leistung verbessern die <xref:System.Windows.Controls.ListBox> beim Bildlauf durch Festlegen der `VirtualizingStackPanel.VirtualizationMode` angefügten Eigenschaft, um <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.  
  
## <a name="example"></a>Beispiel  
  
## <a name="description"></a>Beschreibung  
Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.ListBox> und legt die `VirtualizingStackPanel.VirtualizationMode` angefügten Eigenschaft, um <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> zur Verbesserung der Leistung während des Bildlaufs.  
  
## <a name="code"></a>Code  
 [!code-xaml[RecycleItemContainerShippets#VirtualizationMode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizationmode)]  
  
 Das folgende Beispiel zeigt den Daten, die im vorherigen Beispiel verwendet.  
  
 [!code-csharp[RecycleItemContainerShippets#ListBoxData](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#listboxdata)]
 [!code-vb[RecycleItemContainerShippets#ListBoxData](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#listboxdata)]
