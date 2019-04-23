---
title: 'Vorgehensweise: Verwenden des Bildelements'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Image
- Image control [WPF]
- rendering images [WPF]
ms.assetid: 5b92e74b-1b56-4756-ac64-d5e9e08d9854
ms.openlocfilehash: 967159894e25721bdf380f851712e91d76088f87
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59205302"
---
# <a name="how-to-use-the-image-element"></a>Vorgehensweise: Verwenden des Bildelements
Dieses Beispiel zeigt, wie Sie Bilder in einer Anwendung einfügen, mit der <xref:System.Windows.Controls.Image> Element.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein Bild auf eine Breite von 200 Pixel gerendert wird. In diesem [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]-Beispielwerden die Attributsyntax und die Syntax der Eigenschaftstags dazu verwendet, um das Bild zu definieren. Weitere Informationen über Attributsyntax und Eigenschaftensyntax finden Sie unter [Übersicht über Abhängigkeitseigenschaften](../advanced/dependency-properties-overview.md). Ein <xref:System.Windows.Media.Imaging.BitmapImage> wird zum Definieren der Quelldaten des Bilds verwendet und für die Eigenschaft Tag Syntaxbeispiel explizit definiert. Darüber hinaus die <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> von der <xref:System.Windows.Media.Imaging.BitmapImage> festgelegt ist, auf die gleiche Breite wie die <xref:System.Windows.FrameworkElement.Width%2A> von der <xref:System.Windows.Controls.Image>. Hiermit wird sichergestellt, dass die Mindestmenge an Arbeitsspeicher zum Rendern des Bilds verwendet wird.  
  
> [!NOTE]
>  Im Allgemeinen, wenn Sie die Größe eines gerenderten Bilds angeben möchten, geben Sie nur die <xref:System.Windows.FrameworkElement.Width%2A> oder <xref:System.Windows.FrameworkElement.Height%2A> jedoch nicht beides. Wenn Sie nur eines angeben, wird das Seitenverhältnis des Bilds beibehalten. Andernfalls wird das Bild möglicherweise unerwartet gestreckt oder verzerrt. Steuern Sie das Image streckungsverhalten, verwenden Sie die <xref:System.Windows.Controls.Image.Stretch%2A> und <xref:System.Windows.Controls.Image.StretchDirection%2A> Eigenschaften.  
  
> [!NOTE]
>  Wenn Sie die Größe eines Bilds angeben, mit einem <xref:System.Windows.FrameworkElement.Width%2A> oder <xref:System.Windows.FrameworkElement.Height%2A>, Sie sollten auch festlegen, entweder <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> oder <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelHeight%2A> auf dieselbe Größe.  
  
 Die <xref:System.Windows.Controls.Image.Stretch%2A> Eigenschaft bestimmt, wie die Bildquelle gestreckt wird, um das Image-Element auszufüllen. Weitere Informationen finden Sie unter der <xref:System.Windows.Media.Stretch>-Enumeration.  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein Bild mithilfe von Code auf eine Breite von 200 Pixel gerendert wird.  
  
> [!NOTE]
>  Festlegen von <xref:System.Windows.Media.Imaging.BitmapImage> Eigenschaften müssen ausgeführt werden, in einem <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> und <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> Block.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über die Bildverarbeitung](../graphics-multimedia/imaging-overview.md)
