---
title: 'Gewusst wie: Durchsuchen eines Storyboards'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], seeking
- seeking Storyboards [WPF]
ms.assetid: 887bb39a-0c2a-4ae8-956d-1d9f6f8ebbfc
ms.openlocfilehash: 656a5cb38461f71698a312e6382a3a9c29158cc5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560276"
---
# <a name="how-to-seek-a-storyboard"></a>Gewusst wie: Durchsuchen eines Storyboards
Das folgende Beispiel zeigt, wie Sie die <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> Methode von einer <xref:System.Windows.Media.Animation.Storyboard> springen zu einer beliebigen Position in einer Storyboard-Animation.  
  
## <a name="example"></a>Beispiel  
 Im Folgenden finden Sie das XAML-Markup des Beispiels.  
  
 [!code-xaml[SeekStoryboard_snip#SeekStoryboardExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardExample.xaml#seekstoryboardexamplewholepage)]  
  
## <a name="example"></a>Beispiel  
 Es folgt der Code, der zusammen mit dem oben angegebenen XAML-Code verwendet wird.  
  
 [!code-csharp[SeekStoryboard_snip#SeekStoryboardCodeBehindExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardExample.xaml.cs#seekstoryboardcodebehindexamplewholepage)]
 [!code-vb[SeekStoryboard_snip#SeekStoryboardCodeBehindExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SeekStoryboard_snip/VisualBasic/SeekStoryboardExample.xaml.vb#seekstoryboardcodebehindexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch  
 [Synchrones Suchen von Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-seek-a-storyboard-synchronously.md)
