---
title: 'Vorgehensweise: Durchsuchen eines Storyboards'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], seeking
- seeking Storyboards [WPF]
ms.assetid: 887bb39a-0c2a-4ae8-956d-1d9f6f8ebbfc
ms.openlocfilehash: 440b2dd157b56a1616f7137b1e311cb981b33861
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54604456"
---
# <a name="how-to-seek-a-storyboard"></a><span data-ttu-id="a9a8e-102">Vorgehensweise: Durchsuchen eines Storyboards</span><span class="sxs-lookup"><span data-stu-id="a9a8e-102">How to: Seek a Storyboard</span></span>
<span data-ttu-id="a9a8e-103">Das folgende Beispiel zeigt, wie Sie mit der <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> Methode eine <xref:System.Windows.Media.Animation.Storyboard> springen zu einer beliebigen Position in einer Storyboard-Animation.</span><span class="sxs-lookup"><span data-stu-id="a9a8e-103">The following example shows how to use the <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> method of a <xref:System.Windows.Media.Animation.Storyboard> to jump to any position in a storyboard animation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9a8e-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a9a8e-104">Example</span></span>  
 <span data-ttu-id="a9a8e-105">Im Folgenden finden Sie das XAML-Markup des Beispiels.</span><span class="sxs-lookup"><span data-stu-id="a9a8e-105">Below is the XAML markup for the sample.</span></span>  
  
 [!code-xaml[SeekStoryboard_snip#SeekStoryboardExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardExample.xaml#seekstoryboardexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="a9a8e-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a9a8e-106">Example</span></span>  
 <span data-ttu-id="a9a8e-107">Es folgt der Code, der zusammen mit dem oben angegebenen XAML-Code verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a9a8e-107">Below is the code used with the XAML code above.</span></span>  
  
 [!code-csharp[SeekStoryboard_snip#SeekStoryboardCodeBehindExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardExample.xaml.cs#seekstoryboardcodebehindexamplewholepage)]
 [!code-vb[SeekStoryboard_snip#SeekStoryboardCodeBehindExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SeekStoryboard_snip/VisualBasic/SeekStoryboardExample.xaml.vb#seekstoryboardcodebehindexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="a9a8e-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9a8e-108">See also</span></span>
- [<span data-ttu-id="a9a8e-109">Synchrones Suchen von Storyboards</span><span class="sxs-lookup"><span data-stu-id="a9a8e-109">Seek a Storyboard Synchronously</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-seek-a-storyboard-synchronously.md)
