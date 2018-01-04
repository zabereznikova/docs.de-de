---
title: 'Gewusst wie: Durchsuchen eines Storyboards'
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
- Storyboards [WPF], seeking
- seeking Storyboards [WPF]
ms.assetid: 887bb39a-0c2a-4ae8-956d-1d9f6f8ebbfc
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 521674fd735c70387f2857cd5c7c12ddea1380b0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-seek-a-storyboard"></a><span data-ttu-id="0ee82-102">Gewusst wie: Durchsuchen eines Storyboards</span><span class="sxs-lookup"><span data-stu-id="0ee82-102">How to: Seek a Storyboard</span></span>
<span data-ttu-id="0ee82-103">Das folgende Beispiel zeigt, wie Sie die <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> Methode von einer <xref:System.Windows.Media.Animation.Storyboard> springen zu einer beliebigen Position in einer Storyboard-Animation.</span><span class="sxs-lookup"><span data-stu-id="0ee82-103">The following example shows how to use the <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> method of a <xref:System.Windows.Media.Animation.Storyboard> to jump to any position in a storyboard animation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ee82-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0ee82-104">Example</span></span>  
 <span data-ttu-id="0ee82-105">Im Folgenden finden Sie das XAML-Markup des Beispiels.</span><span class="sxs-lookup"><span data-stu-id="0ee82-105">Below is the XAML markup for the sample.</span></span>  
  
 [!code-xaml[SeekStoryboard_snip#SeekStoryboardExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardExample.xaml#seekstoryboardexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="0ee82-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0ee82-106">Example</span></span>  
 <span data-ttu-id="0ee82-107">Es folgt der Code, der zusammen mit dem oben angegebenen XAML-Code verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0ee82-107">Below is the code used with the XAML code above.</span></span>  
  
 [!code-csharp[SeekStoryboard_snip#SeekStoryboardCodeBehindExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardExample.xaml.cs#seekstoryboardcodebehindexamplewholepage)]
 [!code-vb[SeekStoryboard_snip#SeekStoryboardCodeBehindExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SeekStoryboard_snip/VisualBasic/SeekStoryboardExample.xaml.vb#seekstoryboardcodebehindexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="0ee82-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0ee82-108">See Also</span></span>  
 [<span data-ttu-id="0ee82-109">Synchrones Suchen von Storyboards</span><span class="sxs-lookup"><span data-stu-id="0ee82-109">Seek a Storyboard Synchronously</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-seek-a-storyboard-synchronously.md)
