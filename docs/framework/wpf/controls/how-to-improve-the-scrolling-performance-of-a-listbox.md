---
title: 'Vorgehensweise: Verbessern der Bildlaufleistung eines Listenfelds'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListBox control [WPF], reusing item containers
- ListBox control [WPF], improving scrolling performance
ms.assetid: 1e2bf8f3-c8ce-47f7-a400-a7fe11d1a848
ms.openlocfilehash: a9d1ca1d8ac2ef830984408f3052eb0ed0987c5d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364553"
---
# <a name="how-to-improve-the-scrolling-performance-of-a-listbox"></a>Vorgehensweise: Verbessern der Bildlaufleistung eines Listenfelds
Wenn eine <xref:System.Windows.Controls.ListBox> viele Elemente enthält, Reaktion der Benutzeroberfläche kann langsam sein, wenn ein Benutzer einen Bildlauf der <xref:System.Windows.Controls.ListBox> durch das Mausrad verwenden, oder ziehen das Thumb-Steuerelement eine Bildlaufleiste. Sie können die Leistung verbessern die <xref:System.Windows.Controls.ListBox> Wenn der Benutzer scrollt durch Festlegen der `VirtualizingStackPanel.VirtualizationMode` angefügte Eigenschaft zu <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.  
  
## <a name="example"></a>Beispiel  
  
## <a name="description"></a>Beschreibung  
Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.ListBox> und legt die `VirtualizingStackPanel.VirtualizationMode` angefügten Eigenschaft, um <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> zur Verbesserung der Leistung während des Bildlaufs.  
  
## <a name="code"></a>Code  
 [!code-xaml[RecycleItemContainerShippets#VirtualizationMode](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizationmode)]  
  
 Das folgende Beispiel zeigt den Daten, die im vorherigen Beispiel verwendet.  
  
 [!code-csharp[RecycleItemContainerShippets#ListBoxData](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#listboxdata)]
 [!code-vb[RecycleItemContainerShippets#ListBoxData](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#listboxdata)]
