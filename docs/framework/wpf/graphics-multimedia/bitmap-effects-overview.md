---
title: Übersicht über Bitmapeffekte
ms.date: 03/30/2017
helpviewer_keywords:
- bitmap effects [WPF]
ms.assetid: 23cb338e-4b59-4b52-b294-96431f9c9568
ms.openlocfilehash: 4a5e73f21d4ce4988f56c139d13038dca902b5b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186992"
---
# <a name="bitmap-effects-overview"></a>Übersicht über Bitmapeffekte
Bitmap-Effekte ermöglichen es Designern und Entwicklern, visuelle Effekte auf gerenderte Windows Presentation Foundation (WPF)-Inhalte anzuwenden. Mit Bitmapeffekten können Sie z. B. problemlos einen <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> Effekt oder einen Unschärfeeffekt auf ein Bild oder eine Schaltfläche anwenden.  
  
> [!IMPORTANT]
> In .NET Framework 4 oder <xref:System.Windows.Media.Effects.BitmapEffect> höher ist die Klasse veraltet. Wenn Sie versuchen, <xref:System.Windows.Media.Effects.BitmapEffect> die Klasse zu verwenden, erhalten Sie eine veraltete Ausnahme. Die nicht veraltete <xref:System.Windows.Media.Effects.BitmapEffect> Alternative zur <xref:System.Windows.Media.Effects.Effect> Klasse ist die Klasse. In den meisten <xref:System.Windows.Media.Effects.Effect> Situationen ist die Klasse deutlich schneller.  

<a name="wpf_effects"></a>
## <a name="wpf-bitmap-effects"></a>WPF-Bitmapeffekte  
 Bitmap-Effekte<xref:System.Windows.Media.Effects.BitmapEffect> (Objekt) sind einfache Pixelverarbeitungsvorgänge. Ein Bitmap-Effekt <xref:System.Windows.Media.Imaging.BitmapSource> nimmt eine als <xref:System.Windows.Media.Imaging.BitmapSource> Eingabe an und erzeugt nach dem Anwenden des Effekts einen neuen Effekt, z. B. eine Unschärfe oder ein Schlagschatten. Jeder Bitmapeffekt macht Eigenschaften verfügbar, die die <xref:System.Windows.Media.Effects.BlurBitmapEffect.Radius%2A> <xref:System.Windows.Media.Effects.BlurBitmapEffect>Filtereigenschaften steuern können, z. B. von .  
  
 Als Sonderfall können [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]in Effekte als Eigenschaften <xref:System.Windows.Media.Visual> für live lebende <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.TextBox>Objekte, z. B. ein oder , festgelegt werden. Die Pixelverarbeitung wird angewendet und zur Laufzeit gerendert. In diesem Fall wird a <xref:System.Windows.Media.Visual> zum Zeitpunkt des <xref:System.Windows.Media.Imaging.BitmapSource> Renderns automatisch in <xref:System.Windows.Media.Effects.BitmapEffect>sein Äquivalent konvertiert und als Eingabe an die eingespeist. Die Ausgabe ersetzt <xref:System.Windows.Media.Visual> das standardmäßige Renderingverhalten des Objekts. Aus diesem <xref:System.Windows.Media.Effects.BitmapEffect> Grund zwingen Objekte Visuals, nur in Software zu rendern, d.h. keine Hardwarebeschleunigung auf Visuals, wenn Effekte angewendet werden.  
  
- <xref:System.Windows.Media.Effects.BlurBitmapEffect>simuliert ein Objekt, das a-fokussiert angezeigt wird.  
  
- <xref:System.Windows.Media.Effects.OuterGlowBitmapEffect>erstellt einen Farbhalo um den Umfang eines Objekts.  
  
- <xref:System.Windows.Media.Effects.DropShadowBitmapEffect>erstellt einen Schatten hinter einem Objekt.  
  
- <xref:System.Windows.Media.Effects.BevelBitmapEffect>erstellt eine Abschrägung, die die Oberfläche eines Bildes entsprechend einer angegebenen Kurve erhöht.  
  
- <xref:System.Windows.Media.Effects.EmbossBitmapEffect>erstellt eine Bump-Mapping von a, <xref:System.Windows.Media.Visual> um den Eindruck von Tiefe und Textur von einer künstlichen Lichtquelle zu geben.  
  
> [!NOTE]
> WPF-Bitmapeffekte werden im Softwaremodus gerendert. Jedes Objekt, das einen Effekt anwendet, wird auch in der Software gerendert werden. Leistungseinbußen entstehen vor allem, wenn Bitmapeffekte bei großen visuellen Objekten oder beim Animieren von Eigenschaften eines Bitmapeffekts verwendet werden. Das heißt nicht, dass Sie keine Bitmapeffekte auf diese Weise verwenden dürfen, jedoch sollten Sie Vorsicht walten lassen und gründliche Tests durchführen, um sicherzustellen, dass Ihre Benutzer die Erfahrung erhalten, die Sie erwarten.  
  
> [!NOTE]
> WPF-Bitmapeffekte unterstützen keine teilweise Vertrauensausführung. Eine Anwendung muss volle Vertrauenswürdigkeit besitzen, um Bitmapeffekte zu verwenden.  
  
<a name="applyeffects"></a>
## <a name="how-to-apply-an-effect"></a>Vorgehensweise: Anwenden eines Effekts  
 <xref:System.Windows.Media.Effects.BitmapEffect>ist eine <xref:System.Windows.Media.Visual>Eigenschaft auf . Daher ist das Anwenden von <xref:System.Windows.Controls.Button>Effekten auf Visuals, z. B. eine , <xref:System.Windows.Controls.Image>, <xref:System.Windows.Media.DrawingVisual>oder <xref:System.Windows.UIElement>, so einfach wie das Festlegen einer Eigenschaft. <xref:System.Windows.UIElement.BitmapEffect%2A>kann auf ein <xref:System.Windows.Media.Effects.BitmapEffect> einzelnes Objekt festgelegt werden, oder <xref:System.Windows.Media.Effects.BitmapEffectGroup> mehrere Effekte können mithilfe des Objekts verkettet werden.  
  
 Im folgenden Beispiel wird <xref:System.Windows.Media.Effects.BitmapEffect> veranschaulicht, wie ein in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]angewendet wird.  
  
 [!code-xaml[EffectsGallery_snip#BlurSimpleExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blursimpleexample.xaml#blursimpleexampleinline)]  
  
 Im folgenden Beispiel wird <xref:System.Windows.Media.Effects.BitmapEffect> veranschaulicht, wie ein in Code angewendet wird.  
  
 [!code-csharp[EffectsGallery_snip#CodeBehindBlurCodeBehindExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blurcodebehindexample.xaml.cs#codebehindblurcodebehindexampleinline)]  
  
> [!NOTE]
> Wenn <xref:System.Windows.Media.Effects.BitmapEffect> ein auf einen Layoutcontainer <xref:System.Windows.Controls.DockPanel> angewendet <xref:System.Windows.Controls.Canvas>wird, z. B. oder , wird der Effekt auf die visuelle Struktur des Elements oder visual angewendet, einschließlich aller untergeordneten Elemente.  
  
<a name="customeffects"></a>
## <a name="creating-custom-effects"></a>Erstellen von benutzerdefinierten Effekten  
 WPF stellt auch nicht verwaltete Schnittstellen bereit, um benutzerdefinierte Effekte zu erstellen, die in verwalteten WPF-Anwendungen verwendet werden können. Weiteres Referenzmaterial zum Erstellen von benutzerdefinierten Bitmapeffekten fnden Sie in der Dokumentation [Unmanaged WPF Bitmap Effect (Nicht verwaltete WPF-Bitmapeffekte)](https://docs.microsoft.com/previous-versions/windows/desktop/wibe/-wibe-lh).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Media.Effects.BitmapEffectGroup>
- <xref:System.Windows.Media.Effects.BitmapEffectInput>
- <xref:System.Windows.Media.Effects.BitmapEffectCollection>
- [Nicht verwaltete WPF-Bitmapeffekte](https://docs.microsoft.com/previous-versions/windows/desktop/wibe/-wibe-lh)
- [Übersicht über die Bildverarbeitung](imaging-overview.md)
- [Sicherheit](../security-wpf.md)
- [Übersicht über das WPF-Grafikrendering](wpf-graphics-rendering-overview.md)
- [2D-Grafiken und Bildverarbeitung](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
