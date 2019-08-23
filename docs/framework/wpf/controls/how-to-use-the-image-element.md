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
ms.openlocfilehash: 164eee7c10d9e388c6e6ee695af479ca2d6974b3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69958327"
---
# <a name="how-to-use-the-image-element"></a>Vorgehensweise: Verwenden des Bildelements
In diesem Beispiel wird gezeigt, wie Sie mit dem <xref:System.Windows.Controls.Image> -Element Bilder in eine Anwendung einschließen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein Bild auf eine Breite von 200 Pixel gerendert wird. In diesem [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]-Beispielwerden die Attributsyntax und die Syntax der Eigenschaftstags dazu verwendet, um das Bild zu definieren. Weitere Informationen über Attributsyntax und Eigenschaftensyntax finden Sie unter [Übersicht über Abhängigkeitseigenschaften](../advanced/dependency-properties-overview.md). Eine <xref:System.Windows.Media.Imaging.BitmapImage> wird verwendet, um die Quelldaten des Bilds zu definieren, und wird explizit für das Beispiel für die Syntax der Eigenschafts Tags definiert. Außerdem <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> <xref:System.Windows.Media.Imaging.BitmapImage> wird der von auf <xref:System.Windows.FrameworkElement.Width%2A> dieselbe<xref:System.Windows.Controls.Image>Breite wie der des festgelegt. Hiermit wird sichergestellt, dass die Mindestmenge an Arbeitsspeicher zum Rendern des Bilds verwendet wird.  
  
> [!NOTE]
> Wenn Sie die Größe eines gerenderten Bilds angeben möchten, geben Sie im Allgemeinen nur <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> oder, aber nicht beides an. Wenn Sie nur eines angeben, wird das Seitenverhältnis des Bilds beibehalten. Andernfalls wird das Bild möglicherweise unerwartet gestreckt oder verzerrt. Um das streckungs Verhalten des Bilds zu steuern <xref:System.Windows.Controls.Image.Stretch%2A> , <xref:System.Windows.Controls.Image.StretchDirection%2A> verwenden Sie die Eigenschaften und.  
  
> [!NOTE]
> Wenn Sie die Größe eines <xref:System.Windows.FrameworkElement.Width%2A> Bilds entweder mit oder <xref:System.Windows.FrameworkElement.Height%2A>angeben, sollten Sie entweder <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> oder <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelHeight%2A> auf dieselbe entsprechende Größe festlegen.  
  
 Die <xref:System.Windows.Controls.Image.Stretch%2A> -Eigenschaft bestimmt, wie die Bildquelle gestreckt wird, um das Bildelement auszufüllen. Weitere Informationen finden Sie unter der <xref:System.Windows.Media.Stretch>-Enumeration.  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein Bild mithilfe von Code auf eine Breite von 200 Pixel gerendert wird.  
  
> [!NOTE]
> Das <xref:System.Windows.Media.Imaging.BitmapImage> Festlegen von Eigenschaften muss innerhalb eines <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> - <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> und-Blocks erfolgen.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über die Bildverarbeitung](../graphics-multimedia/imaging-overview.md)
