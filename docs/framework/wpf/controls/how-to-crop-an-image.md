---
title: 'Gewusst wie: Zuschneiden eines Bilds'
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
- images [WPF], cropping
- cropping images [WPF]
ms.assetid: c6bba109-c6e7-4cf8-bfe6-9cf8d01bb4fc
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6de7914a1226381da763b3348d1794453fe93b02
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-crop-an-image"></a>Gewusst wie: Zuschneiden eines Bilds
In diesem Beispiel wird gezeigt, wie ein Bild mit einzubeziehende <xref:System.Windows.Media.Imaging.CroppedBitmap>.  
  
 <xref:System.Windows.Media.Imaging.CroppedBitmap>wird in erster Linie verwendet, wenn eine zugeschnittene Version eines Bilds Codierung out in eine Datei zu speichern. Zum Zuschneiden eines Bilds zu Anzeigezwecken finden Sie die [Erstellen eines Clippingbereichs](http://msdn.microsoft.com/en-us/56e4bed6-78d7-4292-b917-d72d0b3e4376) Thema.  
  
## <a name="example"></a>Beispiel  
 Die folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Ressourcen in den Beispielen unten definiert.  
  
 [!code-xaml[imageelementexample#CroppedXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml1)]  
  
 Das folgende Beispiel erstellt ein Abbild mithilfe einer <xref:System.Windows.Media.Imaging.CroppedBitmap> als Quelle.  
  
 [!code-xaml[imageelementexample#CroppedXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml2)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp1)]
 [!code-vb[imageelementexample#CroppedCSharp1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp1)]  
  
 Die <xref:System.Windows.Media.Imaging.CroppedBitmap> kann auch verwendet werden, als Quelle eines anderen <xref:System.Windows.Media.Imaging.CroppedBitmap>, das Zuschneiden zu verketten. Beachten Sie, dass die <xref:System.Windows.Media.Imaging.CroppedBitmap.SourceRect%2A> werden verwendet, die relativ zu der Quelle, die mithilfe einer Bitmap und nicht das erste Bild zugeschnitten sind.  
  
 [!code-xaml[imageelementexample#CroppedXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml3)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp2)]
 [!code-vb[imageelementexample#CroppedCSharp2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp2)]  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen eines Clippingbereichs](http://msdn.microsoft.com/en-us/56e4bed6-78d7-4292-b917-d72d0b3e4376)
