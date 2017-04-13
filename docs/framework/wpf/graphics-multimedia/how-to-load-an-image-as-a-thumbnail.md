---
title: "Gewusst wie: Laden eines Bilds als Miniaturansicht | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Bilder, Laden als Miniaturen"
  - "Laden von Bildern als Miniaturen"
  - "Miniaturansichten, Laden von Bildern als"
ms.assetid: 02e055a0-54df-499a-b8b6-ab6ff7535cff
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Gewusst wie: Laden eines Bilds als Miniaturansicht
In den folgenden Beispielen wird gezeigt, wie ein <xref:System.Windows.Controls.Image> als Miniaturansicht geladen wird, um Anwendungsspeicherplatz zu sparen.  
  
## Beispiel  
 In den folgenden Beispielen wird die <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A>\-Eigenschaft eines <xref:System.Windows.Media.Imaging.BitmapImage> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] festgelegt, um den zum Laden des Bilds erforderlichen Arbeitsspeicher zu reduzieren.  
  
 [!code-xml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## Beispiel  
 In den folgenden Beispielen wird die <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A>\-Eigenschaft eines <xref:System.Windows.Media.Imaging.BitmapImage> im Code festgelegt, um den zum Laden des Bilds erforderlichen Arbeitsspeicher zu reduzieren.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## Siehe auch  
 [Übersicht über die Bildverarbeitung](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)