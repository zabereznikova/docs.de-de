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
# <a name="how-to-improve-the-scrolling-performance-of-a-listbox"></a><span data-ttu-id="9294e-102">Gewusst wie: Verbessern der Bildlaufleistung eines Listenfelds</span><span class="sxs-lookup"><span data-stu-id="9294e-102">How to: Improve the Scrolling Performance of a ListBox</span></span>
<span data-ttu-id="9294e-103">Wenn eine <xref:System.Windows.Controls.ListBox> viele Elemente enthält, die Benutzerantwort Schnittstelle kann langsam sein, wenn ein Benutzer einen Bildlauf der <xref:System.Windows.Controls.ListBox> verwenden das Mausrad oder ziehen den Ziehpunkt einer Bildlaufleiste.</span><span class="sxs-lookup"><span data-stu-id="9294e-103">If a <xref:System.Windows.Controls.ListBox> contains many items, the user interface response can be slow when a user scrolls the <xref:System.Windows.Controls.ListBox> by using the mouse wheel or dragging the thumb of a scrollbar.</span></span> <span data-ttu-id="9294e-104">Sie können die Leistung verbessern die <xref:System.Windows.Controls.ListBox> beim Bildlauf durch Festlegen der `VirtualizingStackPanel.VirtualizationMode` angefügten Eigenschaft, um <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9294e-104">You can improve the performance of the <xref:System.Windows.Controls.ListBox> when the user scrolls by setting the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9294e-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9294e-105">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="9294e-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9294e-106">Description</span></span>  
<span data-ttu-id="9294e-107">Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.ListBox> und legt die `VirtualizingStackPanel.VirtualizationMode` angefügten Eigenschaft, um <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> zur Verbesserung der Leistung während des Bildlaufs.</span><span class="sxs-lookup"><span data-stu-id="9294e-107">The following example creates a <xref:System.Windows.Controls.ListBox> and sets the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> to improve performance during scrolling.</span></span>  
  
## <a name="code"></a><span data-ttu-id="9294e-108">Code</span><span class="sxs-lookup"><span data-stu-id="9294e-108">Code</span></span>  
 [!code-xaml[RecycleItemContainerShippets#VirtualizationMode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizationmode)]  
  
 <span data-ttu-id="9294e-109">Das folgende Beispiel zeigt den Daten, die im vorherigen Beispiel verwendet.</span><span class="sxs-lookup"><span data-stu-id="9294e-109">The following example shows the data that the previous example uses.</span></span>  
  
 [!code-csharp[RecycleItemContainerShippets#ListBoxData](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#listboxdata)]
 [!code-vb[RecycleItemContainerShippets#ListBoxData](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#listboxdata)]
