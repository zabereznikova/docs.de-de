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
# <a name="how-to-seek-a-storyboard"></a>Vorgehensweise: Durchsuchen eines Storyboards
Das folgende Beispiel zeigt, wie Sie mit der <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> Methode eine <xref:System.Windows.Media.Animation.Storyboard> springen zu einer beliebigen Position in einer Storyboard-Animation.  
  
## <a name="example"></a>Beispiel  
 Im Folgenden finden Sie das XAML-Markup des Beispiels.  
  
 [!code-xaml[SeekStoryboard_snip#SeekStoryboardExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardExample.xaml#seekstoryboardexamplewholepage)]  
  
## <a name="example"></a>Beispiel  
 Es folgt der Code, der zusammen mit dem oben angegebenen XAML-Code verwendet wird.  
  
 [!code-csharp[SeekStoryboard_snip#SeekStoryboardCodeBehindExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardExample.xaml.cs#seekstoryboardcodebehindexamplewholepage)]
 [!code-vb[SeekStoryboard_snip#SeekStoryboardCodeBehindExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SeekStoryboard_snip/VisualBasic/SeekStoryboardExample.xaml.vb#seekstoryboardcodebehindexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch
- [Synchrones Suchen von Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-seek-a-storyboard-synchronously.md)
