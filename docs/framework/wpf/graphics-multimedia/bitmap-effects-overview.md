---
title: Übersicht über Bitmapeffekte
ms.date: 03/30/2017
helpviewer_keywords:
- bitmap effects [WPF]
ms.assetid: 23cb338e-4b59-4b52-b294-96431f9c9568
ms.openlocfilehash: 97b878621d5aa1860cd955755d9bbc344b95b993
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44080594"
---
# <a name="bitmap-effects-overview"></a>Übersicht über Bitmapeffekte
Mit Bitmapeffekten können Designer und Entwickler visuelle Effekte anwenden, an Windows Presentation Foundation (WPF) Inhalt gerendert. Z. B. Bitmapeffekten können Sie ganz einfach Anwenden einer <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> Auswirkung oder einen Weichzeichnereffekt auf ein Bild oder eine Schaltfläche.  
  
> [!IMPORTANT]
>  In der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] oder höher, die <xref:System.Windows.Media.Effects.BitmapEffect> Klasse ist veraltet. Wenn Sie versuchen, Sie verwenden die <xref:System.Windows.Media.Effects.BitmapEffect> -Klasse, erhalten Sie eine veraltete Ausnahme. Die nicht veraltete Alternative zu den <xref:System.Windows.Media.Effects.BitmapEffect> -Klasse ist die <xref:System.Windows.Media.Effects.Effect> Klasse. In den meisten Fällen die <xref:System.Windows.Media.Effects.Effect> Klasse ist bedeutend schneller.  
  
  
  
<a name="wpf_effects"></a>   
## <a name="wpf-bitmap-effects"></a>WPF-Bitmapeffekte  
 Bitmapeffekte (<xref:System.Windows.Media.Effects.BitmapEffect> Objekt) sind einfache Pixelverarbeitungsvorgänge Verarbeitungsvorgänge. Ein Bitmapeffekt akzeptiert eine <xref:System.Windows.Media.Imaging.BitmapSource> als Eingabe und erzeugt eine neue <xref:System.Windows.Media.Imaging.BitmapSource> nach dem Anwenden des Effekts, z. B. eine Weichzeichners oder Schlagschattens. Jeder Bitmapeffekt macht Eigenschaften, wie z. B. die Filtereigenschaften steuern können <xref:System.Windows.Media.Effects.BlurBitmapEffect.Radius%2A> von <xref:System.Windows.Media.Effects.BlurBitmapEffect>.  
  
 Als Sonderfall in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], Effekte für festgelegt werden können als Eigenschaften live <xref:System.Windows.Media.Visual> Objekte, z. B. eine <xref:System.Windows.Controls.Button> oder <xref:System.Windows.Controls.TextBox>. Die Pixelverarbeitung wird angewendet und zur Laufzeit gerendert. In diesem Fall zum Zeitpunkt des Rendering eine <xref:System.Windows.Media.Visual> automatisch in konvertiert die <xref:System.Windows.Media.Imaging.BitmapSource> entspricht und dient als Eingabe für die <xref:System.Windows.Media.Effects.BitmapEffect>. Die Ausgabe ersetzt die <xref:System.Windows.Media.Visual> Standardrenderingverhalten des Objekts. Dies ist deshalb <xref:System.Windows.Media.Effects.BitmapEffect> Objekte erzwingen, dass visuelle Objekte in der Software gerendert werden nur also keine Hardwarebeschleunigung auf visuellen Objekten Wenn Effekte angewendet werden.  
  
-   <xref:System.Windows.Media.Effects.BlurBitmapEffect> simuliert ein Objekt, das Out-of-Focus angezeigt wird.  
  
-   <xref:System.Windows.Media.Effects.OuterGlowBitmapEffect> erstellt einen Ring aus Farbe um den Umriss eines Objekts an.  
  
-   <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> erstellt einen Schatten hinter einem Objekt.  
  
-   <xref:System.Windows.Media.Effects.BevelBitmapEffect> erstellt eine Abschrägung, die die Oberfläche eines Bilds gemäß einer definierten Wölbung erhöht.  
  
-   <xref:System.Windows.Media.Effects.EmbossBitmapEffect> erstellt einen Bumpmappingeffekt einer <xref:System.Windows.Media.Visual> , die den Eindruck von Tiefe und Textur aus einer künstlichen Lichtquelle zu vermitteln.  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Bitmapeffekte werden im Softwaremodus gerendert. Jedes Objekt, das einen Effekt anwendet, wird auch in der Software gerendert werden. Leistungseinbußen entstehen vor allem, wenn Bitmapeffekte bei großen visuellen Objekten oder beim Animieren von Eigenschaften eines Bitmapeffekts verwendet werden. Das heißt nicht, dass Sie keine Bitmapeffekte auf diese Weise verwenden dürfen, jedoch sollten Sie Vorsicht walten lassen und gründliche Tests durchführen, um sicherzustellen, dass Ihre Benutzer die Erfahrung erhalten, die Sie erwarten.  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Bitmapeffekte unterstützen keine teilweise vertrauenswürdige Ausführung. Eine Anwendung muss volle Vertrauenswürdigkeit besitzen, um Bitmapeffekte zu verwenden.  
  
<a name="applyeffects"></a>   
## <a name="how-to-apply-an-effect"></a>Vorgehensweise: Anwenden eines Effekts  
 <xref:System.Windows.Media.Effects.BitmapEffect> eine Eigenschaft <xref:System.Windows.Media.Visual>. Aus diesem Grund das Anwenden von Effekten auf visuellen Elemente, wie z. B. eine <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Image>, <xref:System.Windows.Media.DrawingVisual>, oder <xref:System.Windows.UIElement>, ist so einfach wie das Festlegen einer Eigenschaft. <xref:System.Windows.UIElement.BitmapEffect%2A> kann festgelegt werden, um ein einzelnes <xref:System.Windows.Media.Effects.BitmapEffect> Objekt oder mehrere Effekte können mithilfe von verkettet werden die <xref:System.Windows.Media.Effects.BitmapEffectGroup> Objekt.  
  
 Das folgende Beispiel veranschaulicht das Anwenden einer <xref:System.Windows.Media.Effects.BitmapEffect> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
 [!code-xaml[EffectsGallery_snip#BlurSimpleExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blursimpleexample.xaml#blursimpleexampleinline)]  
  
 Das folgende Beispiel veranschaulicht das Anwenden einer <xref:System.Windows.Media.Effects.BitmapEffect> im Code.  
  
 [!code-csharp[EffectsGallery_snip#CodeBehindBlurCodeBehindExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blurcodebehindexample.xaml.cs#codebehindblurcodebehindexampleinline)]  
  
> [!NOTE]
>  Wenn eine <xref:System.Windows.Media.Effects.BitmapEffect> wird z. B. auf einen Layoutcontainer angewendet <xref:System.Windows.Controls.DockPanel> oder <xref:System.Windows.Controls.Canvas>, der Effekt der visuellen Struktur des Elements oder visuellen Element, einschließlich aller untergeordneten Elemente angewendet wird.  
  
<a name="customeffects"></a>   
## <a name="creating-custom-effects"></a>Erstellen von benutzerdefinierten Effekten  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] bietet außerdem nicht verwaltete Schnittstellen zum Erstellen von benutzerdefinierter Effekten, die in verwalteten [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Anwendungen verwendet werden können. Weiteres Referenzmaterial zum Erstellen von benutzerdefinierten Bitmapeffekten fnden Sie in der Dokumentation [Unmanaged WPF Bitmap Effect (Nicht verwaltete WPF-Bitmapeffekte)](https://docs.microsoft.com/previous-versions/windows/desktop/wibe/-wibe-lh).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.Effects.BitmapEffectGroup>  
 <xref:System.Windows.Media.Effects.BitmapEffectInput>  
 <xref:System.Windows.Media.Effects.BitmapEffectCollection>  
 [Nicht verwaltete WPF-Bitmapeffekte](https://docs.microsoft.com/previous-versions/windows/desktop/wibe/-wibe-lh)  
 [Übersicht über die Bildverarbeitung](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)  
 [Sicherheit](../../../../docs/framework/wpf/security-wpf.md)  
 [Übersicht über das WPF-Grafikrendering](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)  
 [2D-Grafiken und Bildverarbeitung](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)
