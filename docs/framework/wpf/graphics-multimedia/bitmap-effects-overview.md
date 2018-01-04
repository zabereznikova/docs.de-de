---
title: "Übersicht über Bitmapeffekte"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: bitmap effects [WPF]
ms.assetid: 23cb338e-4b59-4b52-b294-96431f9c9568
caps.latest.revision: "34"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0f642c699a0ecf3e3cce328363f90110766002e0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="bitmap-effects-overview"></a>Übersicht über Bitmapeffekte
Mit Bitmapeffekten können Designer und Entwickler visuelle Effekte auf gerenderten [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]-Inhalt anwenden. Beispielsweise Bitmapeffekte können Sie problemlos Anwenden einer <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> Effekt oder Weichzeichnereffekt auf ein Bild oder eine Schaltfläche.  
  
> [!IMPORTANT]
>  In der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] oder höher, die <xref:System.Windows.Media.Effects.BitmapEffect> Klasse ist veraltet. Wenn Sie versuchen, verwenden Sie die <xref:System.Windows.Media.Effects.BitmapEffect> -Klasse, erhalten Sie eine Ausnahme veraltete. Die nicht veraltete Alternative zu den <xref:System.Windows.Media.Effects.BitmapEffect> Klasse ist die <xref:System.Windows.Media.Effects.Effect> Klasse. In den meisten Fällen die <xref:System.Windows.Media.Effects.Effect> Klasse ist bedeutend schneller.  
  
  
  
<a name="wpf_effects"></a>   
## <a name="wpf-bitmap-effects"></a>WPF-Bitmapeffekte  
 Bitmapeffekte (<xref:System.Windows.Media.Effects.BitmapEffect> Objekt) sind einfache Pixel Verarbeitungsvorgänge. Akzeptiert ein Bitmapeffekt eine <xref:System.Windows.Media.Imaging.BitmapSource> als Eingabe und erzeugt ein neues <xref:System.Windows.Media.Imaging.BitmapSource> nach dem Anwenden des Effekts, z. B. einen Schatten Blur oder Drop. Jeder Bitmapeffekt macht die Eigenschaften, z. B. die Filtereigenschaften steuern können <xref:System.Windows.Media.Effects.BlurBitmapEffect.Radius%2A> von <xref:System.Windows.Media.Effects.BlurBitmapEffect>.  
  
 Ein Sonderfall in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], Effekte können festgelegt werden als Eigenschaften in live <xref:System.Windows.Media.Visual> Objekte, z. B. eine <xref:System.Windows.Controls.Button> oder <xref:System.Windows.Controls.TextBox>. Die Pixelverarbeitung wird angewendet und zur Laufzeit gerendert. In diesem Fall zum Zeitpunkt des Renderings eine <xref:System.Windows.Media.Visual> automatisch konvertiert wird, um seine <xref:System.Windows.Media.Imaging.BitmapSource> entspricht und dient als Eingabe für die <xref:System.Windows.Media.Effects.BitmapEffect>. Die Ausgabe ersetzt die <xref:System.Windows.Media.Visual> objektspezifischen standardmäßige Renderingverhalten. Deswegen <xref:System.Windows.Media.Effects.BitmapEffect> Objekte erzwingen visuelle Elemente auf die in der Software gerendert nur also keine Hardwarebeschleunigung visuelle Elemente, wenn Effekte angewendet werden.  
  
-   <xref:System.Windows.Media.Effects.BlurBitmapEffect>simuliert ein Objekt, das Out-of-Focus angezeigt wird.  
  
-   <xref:System.Windows.Media.Effects.OuterGlowBitmapEffect>erstellt einen Lichthof Farbe, um den Umriss eines Objekts an.  
  
-   <xref:System.Windows.Media.Effects.DropShadowBitmapEffect>erstellt einen Schatten hinter einem Objekt an.  
  
-   <xref:System.Windows.Media.Effects.BevelBitmapEffect>erstellt eine Abschrägung, durch die die Oberfläche eines Bilds gemäß einer angegebenen Kurve erhöht.  
  
-   <xref:System.Windows.Media.Effects.EmbossBitmapEffect>erstellt ein bumpmapping des eine <xref:System.Windows.Media.Visual> um den Eindruck von Tiefe und Textur von einer künstlichen Lichtquelle zu vermitteln.  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Bitmapeffekte werden im Softwaremodus gerendert. Jedes Objekt, das einen Effekt anwendet, wird auch in der Software gerendert werden. Leistungseinbußen entstehen vor allem, wenn Bitmapeffekte bei großen visuellen Objekten oder beim Animieren von Eigenschaften eines Bitmapeffekts verwendet werden. Das heißt nicht, dass Sie keine Bitmapeffekte auf diese Weise verwenden dürfen, jedoch sollten Sie Vorsicht walten lassen und gründliche Tests durchführen, um sicherzustellen, dass Ihre Benutzer die Erfahrung erhalten, die Sie erwarten.  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Bitmapeffekte unterstützen keine teilweise vertrauenswürdige Ausführung. Eine Anwendung muss volle Vertrauenswürdigkeit besitzen, um Bitmapeffekte zu verwenden.  
  
<a name="applyeffects"></a>   
## <a name="how-to-apply-an-effect"></a>Vorgehensweise: Anwenden eines Effekts  
 <xref:System.Windows.Media.Effects.BitmapEffect>ist eine Eigenschaft im <xref:System.Windows.Media.Visual>. Aus diesem Grund Effekten zu visuellen Elementen, wie z. B. eine <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Image>, <xref:System.Windows.Media.DrawingVisual>, oder <xref:System.Windows.UIElement>, ist genauso einfach wie das Festlegen einer Eigenschaft. <xref:System.Windows.UIElement.BitmapEffect%2A>kann festgelegt werden, um ein einzelnes <xref:System.Windows.Media.Effects.BitmapEffect> Objekt oder mehrere Effekte können verkettet mithilfe der <xref:System.Windows.Media.Effects.BitmapEffectGroup> Objekt.  
  
 Das folgende Beispiel veranschaulicht das Anwenden einer <xref:System.Windows.Media.Effects.BitmapEffect> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
 [!code-xaml[EffectsGallery_snip#BlurSimpleExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blursimpleexample.xaml#blursimpleexampleinline)]  
  
 Das folgende Beispiel veranschaulicht das Anwenden einer <xref:System.Windows.Media.Effects.BitmapEffect> im Code.  
  
 [!code-csharp[EffectsGallery_snip#CodeBehindBlurCodeBehindExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blurcodebehindexample.xaml.cs#codebehindblurcodebehindexampleinline)]  
  
> [!NOTE]
>  Wenn eine <xref:System.Windows.Media.Effects.BitmapEffect> wird z. B. auf einem Layoutcontainer angewendet <xref:System.Windows.Controls.DockPanel> oder <xref:System.Windows.Controls.Canvas>, die Auswirkung der visuellen Struktur des Elements oder visuellen Element, einschließlich aller seiner untergeordneten Elemente angewendet wird.  
  
<a name="customeffects"></a>   
## <a name="creating-custom-effects"></a>Erstellen von benutzerdefinierten Effekten  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] bietet außerdem nicht verwaltete Schnittstellen zum Erstellen von benutzerdefinierter Effekten, die in verwalteten [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Anwendungen verwendet werden können. Weiteres Referenzmaterial zum Erstellen von benutzerdefinierten Bitmapeffekten fnden Sie in der Dokumentation [Unmanaged WPF Bitmap Effect (Nicht verwaltete WPF-Bitmapeffekte)](https://msdn.microsoft.com/library/ms735092.aspx).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.Effects.BitmapEffectGroup>  
 <xref:System.Windows.Media.Effects.BitmapEffectInput>  
 <xref:System.Windows.Media.Effects.BitmapEffectCollection>  
 [Nicht verwaltete WPF-Bitmapeffekt](https://msdn.microsoft.com/library/ms735092.aspx)  
 [Übersicht über die Bildverarbeitung](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)  
 [Sicherheit](../../../../docs/framework/wpf/security-wpf.md)  
 [Übersicht über das WPF-Grafikrendering](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)  
 [2D-Grafiken und Bildverarbeitung](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)
