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
# <a name="how-to-use-the-image-element"></a><span data-ttu-id="2308c-102">Vorgehensweise: Verwenden des Bildelements</span><span class="sxs-lookup"><span data-stu-id="2308c-102">How to: Use the Image Element</span></span>
<span data-ttu-id="2308c-103">In diesem Beispiel wird gezeigt, wie Sie mit dem <xref:System.Windows.Controls.Image> -Element Bilder in eine Anwendung einschließen.</span><span class="sxs-lookup"><span data-stu-id="2308c-103">This example shows how to include images in an application by using the <xref:System.Windows.Controls.Image> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2308c-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2308c-104">Example</span></span>  
 <span data-ttu-id="2308c-105">Im folgenden Beispiel wird veranschaulicht, wie ein Bild auf eine Breite von 200 Pixel gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="2308c-105">The following example shows how to render an image 200 pixels wide.</span></span> <span data-ttu-id="2308c-106">In diesem [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]-Beispielwerden die Attributsyntax und die Syntax der Eigenschaftstags dazu verwendet, um das Bild zu definieren.</span><span class="sxs-lookup"><span data-stu-id="2308c-106">In this [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example, both attribute syntax and property tag syntax are used to define the image.</span></span> <span data-ttu-id="2308c-107">Weitere Informationen über Attributsyntax und Eigenschaftensyntax finden Sie unter [Übersicht über Abhängigkeitseigenschaften](../advanced/dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2308c-107">For more information on attribute syntax and property syntax, see [Dependency Properties Overview](../advanced/dependency-properties-overview.md).</span></span> <span data-ttu-id="2308c-108">Eine <xref:System.Windows.Media.Imaging.BitmapImage> wird verwendet, um die Quelldaten des Bilds zu definieren, und wird explizit für das Beispiel für die Syntax der Eigenschafts Tags definiert.</span><span class="sxs-lookup"><span data-stu-id="2308c-108">A <xref:System.Windows.Media.Imaging.BitmapImage> is used to define the image's source data and is explicitly defined for the property tag syntax example.</span></span> <span data-ttu-id="2308c-109">Außerdem <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> <xref:System.Windows.Media.Imaging.BitmapImage> wird der von auf <xref:System.Windows.FrameworkElement.Width%2A> dieselbe<xref:System.Windows.Controls.Image>Breite wie der des festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2308c-109">In addition, the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> of the <xref:System.Windows.Media.Imaging.BitmapImage> is set to the same width as the <xref:System.Windows.FrameworkElement.Width%2A> of the <xref:System.Windows.Controls.Image>.</span></span> <span data-ttu-id="2308c-110">Hiermit wird sichergestellt, dass die Mindestmenge an Arbeitsspeicher zum Rendern des Bilds verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2308c-110">This is done to ensure that the minimum amount of memory is used rendering the image.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2308c-111">Wenn Sie die Größe eines gerenderten Bilds angeben möchten, geben Sie im Allgemeinen nur <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> oder, aber nicht beides an.</span><span class="sxs-lookup"><span data-stu-id="2308c-111">In general, if you want to specify the size of a rendered image, specify only the <xref:System.Windows.FrameworkElement.Width%2A> or the <xref:System.Windows.FrameworkElement.Height%2A> but not both.</span></span> <span data-ttu-id="2308c-112">Wenn Sie nur eines angeben, wird das Seitenverhältnis des Bilds beibehalten.</span><span class="sxs-lookup"><span data-stu-id="2308c-112">If you only specify one, the image's aspect ratio is preserved.</span></span> <span data-ttu-id="2308c-113">Andernfalls wird das Bild möglicherweise unerwartet gestreckt oder verzerrt.</span><span class="sxs-lookup"><span data-stu-id="2308c-113">Otherwise, the image may unexpectedly appear stretched or warped.</span></span> <span data-ttu-id="2308c-114">Um das streckungs Verhalten des Bilds zu steuern <xref:System.Windows.Controls.Image.Stretch%2A> , <xref:System.Windows.Controls.Image.StretchDirection%2A> verwenden Sie die Eigenschaften und.</span><span class="sxs-lookup"><span data-stu-id="2308c-114">To control the image's stretching behavior, use the <xref:System.Windows.Controls.Image.Stretch%2A> and <xref:System.Windows.Controls.Image.StretchDirection%2A> properties.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2308c-115">Wenn Sie die Größe eines <xref:System.Windows.FrameworkElement.Width%2A> Bilds entweder mit oder <xref:System.Windows.FrameworkElement.Height%2A>angeben, sollten Sie entweder <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> oder <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelHeight%2A> auf dieselbe entsprechende Größe festlegen.</span><span class="sxs-lookup"><span data-stu-id="2308c-115">When you specify the size of an image with either <xref:System.Windows.FrameworkElement.Width%2A> or <xref:System.Windows.FrameworkElement.Height%2A>, you should also set either <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> or <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelHeight%2A> to the same respective size.</span></span>  
  
 <span data-ttu-id="2308c-116">Die <xref:System.Windows.Controls.Image.Stretch%2A> -Eigenschaft bestimmt, wie die Bildquelle gestreckt wird, um das Bildelement auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="2308c-116">The <xref:System.Windows.Controls.Image.Stretch%2A> property determines how the image source is stretched to fill the image element.</span></span> <span data-ttu-id="2308c-117">Weitere Informationen finden Sie unter der <xref:System.Windows.Media.Stretch>-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="2308c-117">For more information, see the <xref:System.Windows.Media.Stretch> enumeration.</span></span>  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a><span data-ttu-id="2308c-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2308c-118">Example</span></span>  
 <span data-ttu-id="2308c-119">Im folgenden Beispiel wird veranschaulicht, wie ein Bild mithilfe von Code auf eine Breite von 200 Pixel gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="2308c-119">The following example shows how to render an image 200 pixels wide using code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2308c-120">Das <xref:System.Windows.Media.Imaging.BitmapImage> Festlegen von Eigenschaften muss innerhalb eines <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> - <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> und-Blocks erfolgen.</span><span class="sxs-lookup"><span data-stu-id="2308c-120">Setting <xref:System.Windows.Media.Imaging.BitmapImage> properties must be done within a <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> and <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> block.</span></span>  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a><span data-ttu-id="2308c-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2308c-121">See also</span></span>

- [<span data-ttu-id="2308c-122">Übersicht über die Bildverarbeitung</span><span class="sxs-lookup"><span data-stu-id="2308c-122">Imaging Overview</span></span>](../graphics-multimedia/imaging-overview.md)
