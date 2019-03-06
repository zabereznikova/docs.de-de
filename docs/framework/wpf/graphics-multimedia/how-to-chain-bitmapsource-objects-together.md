---
title: 'Vorgehensweise: Verketten von BitmapSource-Objekten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BitmapSource objects [WPF], chaining
- graphics [WPF], chaining BitmapSource objects
- chaining BitmapSource objects [WPF]
ms.assetid: 32d88853-395b-4855-9685-51a482a3b421
ms.openlocfilehash: 403a2a8683e65fd71df89befd59744ac3fe6200c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377520"
---
# <a name="how-to-chain-bitmapsource-objects-together"></a><span data-ttu-id="eae28-102">Vorgehensweise: Verketten von BitmapSource-Objekten</span><span class="sxs-lookup"><span data-stu-id="eae28-102">How to: Chain BitmapSource Objects Together</span></span>
<span data-ttu-id="eae28-103">Dieses Beispiel zeigt, wie Sie eine Reihe von Effekten auf eine Bildquelle durch Verkettung anwenden können mehrere <xref:System.Windows.Media.Imaging.BitmapSource> abgeleitete Objekte miteinander verkettet.</span><span class="sxs-lookup"><span data-stu-id="eae28-103">This example shows how you can apply a variety of effects to an image source by chaining multiple <xref:System.Windows.Media.Imaging.BitmapSource> derived objects together.</span></span>  
  
 <span data-ttu-id="eae28-104">Im folgenden Beispiel wird das Pixelformat der Bildquelle durch Verkettung gekippt und geändert.</span><span class="sxs-lookup"><span data-stu-id="eae28-104">The following example uses chaining to flip and change the pixel format of the source of an image.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eae28-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eae28-105">Example</span></span>  
 [!code-xaml[ImagingSnippetGallery_snip#ChainedBitmapSourcesXamlExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_snip/CS/ChainedBitmapSourcesExample.xaml#chainedbitmapsourcesxamlexamplewholepage)]  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#ChainedBitmapSourcesCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/ChainedBitmapSourcesExample.cs#chainedbitmapsourcescodeexamplewholepage)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#ChainedBitmapSourcesCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/ChainedBitmapSourcesExample.vb#chainedbitmapsourcescodeexamplewholepage)]
