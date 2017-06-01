---
title: "Gewusst wie: Zuschneiden eines Bilds | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Klassen, CroppedBitmap"
  - "CroppedBitmap-Klasse"
  - "Zuschneiden von Bildern"
  - "Bilder, Zuschneiden"
ms.assetid: c6bba109-c6e7-4cf8-bfe6-9cf8d01bb4fc
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Zuschneiden eines Bilds
Dieses Beispiel zeigt, wie Sie ein Bild mithilfe von <xref:System.Windows.Media.Imaging.CroppedBitmap> zuschneiden.  
  
 <xref:System.Windows.Media.Imaging.CroppedBitmap> wird hauptsächlich verwendet, wenn Sie eine zugeschnittene Version eines Bilds codieren, um sie in einer Datei zu speichern.  Informationen zum Zuschneiden eines Bilds zu Anzeigezwecken finden Sie im Thema [Create a Clip Region](http://msdn.microsoft.com/de-de/56e4bed6-78d7-4292-b917-d72d0b3e4376).  
  
## Beispiel  
 Der folgende [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Code definiert Ressourcen, die in den Beispielen darunter verwendet werden.  
  
 [!code-xml[imageelementexample#CroppedXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml1)]  
  
 Im folgenden Beispiel wird ein Bild mit einer <xref:System.Windows.Media.Imaging.CroppedBitmap> als Quelle erstellt.  
  
 [!code-xml[imageelementexample#CroppedXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml2)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp1)]
 [!code-vb[imageelementexample#CroppedCSharp1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp1)]  
  
 Die <xref:System.Windows.Media.Imaging.CroppedBitmap> kann auch als Quelle einer anderen <xref:System.Windows.Media.Imaging.CroppedBitmap> verwendet werden, um das Zuschneiden zu verketten.  Beachten Sie, dass <xref:System.Windows.Media.Imaging.CroppedBitmap.SourceRect%2A> Werte verwendet, die sich relativ zur zugeschnittenen Quellbitmap verhalten, nicht zum ursprünglichen Bild.  
  
 [!code-xml[imageelementexample#CroppedXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml3)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp2)]
 [!code-vb[imageelementexample#CroppedCSharp2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp2)]  
  
## Siehe auch  
 [Create a Clip Region](http://msdn.microsoft.com/de-de/56e4bed6-78d7-4292-b917-d72d0b3e4376)