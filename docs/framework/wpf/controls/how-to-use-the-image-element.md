---
title: "Gewusst wie: Verwenden des Image-Elements | Microsoft Docs"
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
  - "BitmapImage-Klasse"
  - "Klassen, BitmapImage"
  - "Steuerelemente, Bild"
  - "Image-Steuerelement"
  - "Rendern von Bildern"
ms.assetid: 5b92e74b-1b56-4756-ac64-d5e9e08d9854
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Gewusst wie: Verwenden des Image-Elements
Dieses Beispiel zeigt, wie Sie mit dem <xref:System.Windows.Controls.Image>\-Element Bilder in eine Anwendung einbetten.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein Bild auf eine Breite von 200 Pixel gerendert wird.  In diesem [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Beispiel werden sowohl Attributsyntax als auch Eigenschaftensyntax für die Definition des Bilds verwendet.  Weitere Informationen über Attributsyntax und Eigenschaftensyntax finden Sie unter [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  Ein <xref:System.Windows.Media.Imaging.BitmapImage> wird zur Definition der Quelldaten des Bilds verwendet und für das Eigenschaftensyntaxbeispiel explizit definiert.  Darüber hinaus wird die <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> von <xref:System.Windows.Media.Imaging.BitmapImage> auf dieselbe Breite festgelegt wie die <xref:System.Windows.FrameworkElement.Width%2A> von <xref:System.Windows.Controls.Image>.  Hierdurch wird sichergestellt, dass zum Rendern des Bilds so wenig Speicher wie möglich benötigt wird.  
  
> [!NOTE]
>  Im Allgemeinen gilt: Geben Sie zur Definition der Größe eines gerenderten Bilds die <xref:System.Windows.FrameworkElement.Width%2A> oder die <xref:System.Windows.FrameworkElement.Height%2A> an, jedoch nicht beide Werte.  Das [Seitenverhältnis](GTMT) des Bilds bleibt erhalten, wenn Sie nur einen Wert angeben.  Andernfalls wird das Bild möglicherweise gestreckt oder verzerrt.  Um das Streckverhalten des Bilds zu steuern, verwenden Sie die Eigenschaften <xref:System.Windows.Controls.Image.Stretch%2A> und <xref:System.Windows.Controls.Image.StretchDirection%2A>.  
  
> [!NOTE]
>  Wenn Sie die Größe eines Bilds mit dem Wert <xref:System.Windows.FrameworkElement.Width%2A> oder <xref:System.Windows.FrameworkElement.Height%2A> angeben, müssen Sie <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> bzw. <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelHeight%2A> auf die entsprechende Größe setzen.  
  
 Mit der <xref:System.Windows.Controls.Image.Stretch%2A>\-Eigenschaft wird festgelegt, wie die Bildquelle gestreckt wird, um das Image\-Element auszufüllen.  Weitere Informationen finden Sie unter der <xref:System.Windows.Media.Stretch>\-Enumeration.  
  
 [!code-xml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein Bild auf eine Breite von 200 Pixel mithilfe von Code gerendert wird.  
  
> [!NOTE]
>  Sie müssen die <xref:System.Windows.Media.Imaging.BitmapImage>\-Eigenschaften in einem <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A>\-\/<xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A>\-Block festlegen.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## Siehe auch  
 [Übersicht über die Bildverarbeitung](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)