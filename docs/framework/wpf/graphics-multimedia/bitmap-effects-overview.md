---
title: Übersicht über Bitmapeffekte
ms.date: 03/30/2017
helpviewer_keywords:
- bitmap effects [WPF]
ms.assetid: 23cb338e-4b59-4b52-b294-96431f9c9568
ms.openlocfilehash: f2fa42d5d63cad6a71efd259416dad3416bf2d72
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69935302"
---
# <a name="bitmap-effects-overview"></a>Übersicht über Bitmapeffekte
Mit Bitmapeffekten können Designer und Entwickler visuelle Effekte auf gerenderten Windows Presentation Foundation (WPF)-Inhalt anwenden. Mit Bitmapeffekten können Sie z. b <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> . problemlos einen Effekt oder einen Weichzeichnereffekt auf ein Bild oder eine Schaltfläche anwenden.  
  
> [!IMPORTANT]
> In .NET Framework 4 oder höher ist die <xref:System.Windows.Media.Effects.BitmapEffect> -Klasse veraltet. Wenn Sie versuchen, die <xref:System.Windows.Media.Effects.BitmapEffect> -Klasse zu verwenden, erhalten Sie eine veraltete Ausnahme. Die nicht veraltete Alternative zur <xref:System.Windows.Media.Effects.BitmapEffect> -Klasse ist die <xref:System.Windows.Media.Effects.Effect> -Klasse. In den meisten Fällen ist <xref:System.Windows.Media.Effects.Effect> die Klasse erheblich schneller.  

<a name="wpf_effects"></a>   
## <a name="wpf-bitmap-effects"></a>WPF-Bitmapeffekte  
 Bitmapeffekte (<xref:System.Windows.Media.Effects.BitmapEffect> -Objekt) sind einfache Pixel Verarbeitungsvorgänge. Ein Bitmapeffekt nimmt einen <xref:System.Windows.Media.Imaging.BitmapSource> als Eingabe an und erzeugt nach dem Anwenden des Effekts einen neuen <xref:System.Windows.Media.Imaging.BitmapSource> , z. b. einen weich-oder Schlag Schatten. Jeder Bitmapeffekt macht Eigenschaften verfügbar, die die Filtereigenschaften <xref:System.Windows.Media.Effects.BlurBitmapEffect.Radius%2A> Steuern <xref:System.Windows.Media.Effects.BlurBitmapEffect>können, z. b. von.  
  
 Als Sonderfall können Effekte in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]als Eigenschaften für Live <xref:System.Windows.Media.Visual> - <xref:System.Windows.Controls.Button> Objekte, z. b. oder <xref:System.Windows.Controls.TextBox>, festgelegt werden. Die Pixelverarbeitung wird angewendet und zur Laufzeit gerendert. In diesem Fall wird zum Zeitpunkt des Renderings automatisch <xref:System.Windows.Media.Visual> ein in seine <xref:System.Windows.Media.Imaging.BitmapSource> -Entsprechung konvertiert und als Eingabe an die <xref:System.Windows.Media.Effects.BitmapEffect>übertragen. Die Ausgabe ersetzt das <xref:System.Windows.Media.Visual> standardmäßige Renderingverhalten des Objekts. Aus diesem Grund <xref:System.Windows.Media.Effects.BitmapEffect> ist es von Objekten erzwungen, dass visuelle Elemente nur in Software dargestellt werden, d. h. keine Hardwarebeschleunigung bei visuellen Elementen  
  
- <xref:System.Windows.Media.Effects.BlurBitmapEffect>simuliert ein Objekt, das außerhalb des Fokus erscheint.  
  
- <xref:System.Windows.Media.Effects.OuterGlowBitmapEffect>erstellt einen Halo der Farbe um den Umkreis eines Objekts.  
  
- <xref:System.Windows.Media.Effects.DropShadowBitmapEffect>erstellt einen Schatten hinter einem Objekt.  
  
- <xref:System.Windows.Media.Effects.BevelBitmapEffect>erstellt eine Abschrägung, die die Oberfläche eines Bilds gemäß einer angegebenen Kurve auslöst.  
  
- <xref:System.Windows.Media.Effects.EmbossBitmapEffect>erstellt eine Bump-Zuordnung <xref:System.Windows.Media.Visual> eines, um den Eindruck von Tiefe und Textur von einer künstlichen Lichtquelle zu vermitteln.  
  
> [!NOTE]
> [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Bitmapeffekte werden im Softwaremodus gerendert. Jedes Objekt, das einen Effekt anwendet, wird auch in der Software gerendert werden. Leistungseinbußen entstehen vor allem, wenn Bitmapeffekte bei großen visuellen Objekten oder beim Animieren von Eigenschaften eines Bitmapeffekts verwendet werden. Das heißt nicht, dass Sie keine Bitmapeffekte auf diese Weise verwenden dürfen, jedoch sollten Sie Vorsicht walten lassen und gründliche Tests durchführen, um sicherzustellen, dass Ihre Benutzer die Erfahrung erhalten, die Sie erwarten.  
  
> [!NOTE]
> [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Bitmapeffekte unterstützen keine teilweise vertrauenswürdige Ausführung. Eine Anwendung muss volle Vertrauenswürdigkeit besitzen, um Bitmapeffekte zu verwenden.  
  
<a name="applyeffects"></a>   
## <a name="how-to-apply-an-effect"></a>Vorgehensweise: Anwenden eines Effekts  
 <xref:System.Windows.Media.Effects.BitmapEffect>ist eine Eigenschaft für <xref:System.Windows.Media.Visual>. Daher ist das Anwenden von Effekten auf visuelle Elemente <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Image>wie z. <xref:System.Windows.UIElement>b.,, <xref:System.Windows.Media.DrawingVisual>oder, genauso einfach wie das Festlegen einer Eigenschaft. <xref:System.Windows.UIElement.BitmapEffect%2A>kann auf ein einzelnes <xref:System.Windows.Media.Effects.BitmapEffect> Objekt festgelegt werden, oder mehrere Effekte können mithilfe des <xref:System.Windows.Media.Effects.BitmapEffectGroup> -Objekts verkettet werden.  
  
 Im folgenden Beispiel wird veranschaulicht, wie ein <xref:System.Windows.Media.Effects.BitmapEffect> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]angewendet wird.  
  
 [!code-xaml[EffectsGallery_snip#BlurSimpleExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blursimpleexample.xaml#blursimpleexampleinline)]  
  
 Im folgenden Beispiel wird veranschaulicht, wie ein <xref:System.Windows.Media.Effects.BitmapEffect> im Code angewendet wird.  
  
 [!code-csharp[EffectsGallery_snip#CodeBehindBlurCodeBehindExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blurcodebehindexample.xaml.cs#codebehindblurcodebehindexampleinline)]  
  
> [!NOTE]
> Wenn ein <xref:System.Windows.Media.Effects.BitmapEffect> auf einen Layoutcontainer angewendet wird, <xref:System.Windows.Controls.DockPanel> z. <xref:System.Windows.Controls.Canvas>b. oder, wird der Effekt auf die visuelle Struktur des Elements oder visuellen Elements angewendet, einschließlich aller untergeordneten Elemente.  
  
<a name="customeffects"></a>   
## <a name="creating-custom-effects"></a>Erstellen von benutzerdefinierten Effekten  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] bietet außerdem nicht verwaltete Schnittstellen zum Erstellen von benutzerdefinierter Effekten, die in verwalteten [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Anwendungen verwendet werden können. Weiteres Referenzmaterial zum Erstellen von benutzerdefinierten Bitmapeffekten fnden Sie in der Dokumentation [Unmanaged WPF Bitmap Effect (Nicht verwaltete WPF-Bitmapeffekte)](https://docs.microsoft.com/previous-versions/windows/desktop/wibe/-wibe-lh).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Effects.BitmapEffectGroup>
- <xref:System.Windows.Media.Effects.BitmapEffectInput>
- <xref:System.Windows.Media.Effects.BitmapEffectCollection>
- [Nicht verwalteter WPF-Bitmapeffekt](https://docs.microsoft.com/previous-versions/windows/desktop/wibe/-wibe-lh)
- [Übersicht über die Bildverarbeitung](imaging-overview.md)
- [Sicherheit](../security-wpf.md)
- [Übersicht über das WPF-Grafikrendering](wpf-graphics-rendering-overview.md)
- [2D-Grafiken und Bildverarbeitung](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
