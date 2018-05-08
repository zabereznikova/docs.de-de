---
title: 'Gewusst wie: Verwenden des Image-Elements'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Image
- Image control [WPF]
- rendering images [WPF]
ms.assetid: 5b92e74b-1b56-4756-ac64-d5e9e08d9854
ms.openlocfilehash: 11481533af7b3ad75b571f9f97251c123e0af1b7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-the-image-element"></a>Gewusst wie: Verwenden des Image-Elements
In diesem Beispiel wird gezeigt, wie Bilder in einer Anwendung enthalten die <xref:System.Windows.Controls.Image> Element.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein Bild auf eine Breite von 200 Pixel gerendert wird. In diesem [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]-Beispielwerden die Attributsyntax und die Syntax der Eigenschaftstags dazu verwendet, um das Bild zu definieren. Weitere Informationen über Attributsyntax und Eigenschaftensyntax finden Sie unter [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md). Ein <xref:System.Windows.Media.Imaging.BitmapImage> wird verwendet, um das Image-Quelldaten definieren und für die Eigenschaft Tag Syntaxbeispiel wird explizit definiert ist. Darüber hinaus die <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> von der <xref:System.Windows.Media.Imaging.BitmapImage> festgelegt ist, auf die gleiche Breite wie die <xref:System.Windows.FrameworkElement.Width%2A> von der <xref:System.Windows.Controls.Image>. Hiermit wird sichergestellt, dass die Mindestmenge an Arbeitsspeicher zum Rendern des Bilds verwendet wird.  
  
> [!NOTE]
>  Im Allgemeinen, wenn Sie die Größe eines gerenderten Bilds angeben möchten, geben Sie nur die <xref:System.Windows.FrameworkElement.Width%2A> oder <xref:System.Windows.FrameworkElement.Height%2A> aber nicht beides. Wenn Sie nur eines angeben, wird das Seitenverhältnis des Bilds beibehalten. Andernfalls wird das Bild möglicherweise unerwartet gestreckt oder verzerrt. Um das Bild zu steuern des Verhaltens Strecken, verwenden Sie die <xref:System.Windows.Controls.Image.Stretch%2A> und <xref:System.Windows.Controls.Image.StretchDirection%2A> Eigenschaften.  
  
> [!NOTE]
>  Beim Angeben der Größe eines Bilds mit <xref:System.Windows.FrameworkElement.Width%2A> oder <xref:System.Windows.FrameworkElement.Height%2A>, Sie sollten auch festlegen, entweder <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> oder <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelHeight%2A> auf die entsprechende Größe.  
  
 Die <xref:System.Windows.Controls.Image.Stretch%2A> Eigenschaft bestimmt, wie die Bildquelle gestreckt wird, um das Image-Element zu füllen. Weitere Informationen finden Sie unter der <xref:System.Windows.Media.Stretch>-Enumeration.  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein Bild mithilfe von Code auf eine Breite von 200 Pixel gerendert wird.  
  
> [!NOTE]
>  Festlegen von <xref:System.Windows.Media.Imaging.BitmapImage> Eigenschaften müssen erfolgen, innerhalb einer <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> und <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> Block.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Bildverarbeitung](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
