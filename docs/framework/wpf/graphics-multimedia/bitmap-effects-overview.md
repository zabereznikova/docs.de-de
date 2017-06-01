---
title: "&#220;bersicht &#252;ber Bitmapeffekte | Microsoft Docs"
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
  - "Bitmapeffekte"
ms.assetid: 23cb338e-4b59-4b52-b294-96431f9c9568
caps.latest.revision: 34
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 31
---
# &#220;bersicht &#252;ber Bitmapeffekte
Mit Bitmapeffekten können Designer und Entwickler visuelle Effekte auf gerenderte [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]\-Inhalte anwenden.  Mit Bitmapeffekten können sie z. B. einfach einen <xref:System.Windows.Media.Effects.DropShadowBitmapEffect>\-Effekt oder Weichzeichnereffekt auf ein Bild oder eine Schaltfläche anwenden.  
  
> [!IMPORTANT]
>  In [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] oder höher ist die <xref:System.Windows.Media.Effects.BitmapEffect>\-Klasse veraltet.  Wenn Sie versuchen, die <xref:System.Windows.Media.Effects.BitmapEffect>\-Klasse zu verwenden, wird aufgrund der veralteten Klasse eine Ausnahme ausgelöst.  Die nicht veraltete Alternative zur <xref:System.Windows.Media.Effects.BitmapEffect>\-Klasse ist die <xref:System.Windows.Media.Effects.Effect>\-Klasse.  In den meisten Situationen ist die <xref:System.Windows.Media.Effects.Effect>\-Klasse bedeutend schneller.  
  
   
  
<a name="wpf_effects"></a>   
## WPF\-Bitmapeffekte  
 Bitmapeffekte \(<xref:System.Windows.Media.Effects.BitmapEffect>\-Objekt\) sind einfache Pixelverarbeitungsvorgänge.  Ein Bitmapeffekt akzeptiert eine <xref:System.Windows.Media.Imaging.BitmapSource> als Eingabe und erzeugt eine neue <xref:System.Windows.Media.Imaging.BitmapSource> nach Anwenden des Effekts, z. B. eines Weichzeichners oder Schlagschattens.  Jeder Bitmapeffekt macht Eigenschaften verfügbar, die die Filtereigenschaften steuern können, z. B. <xref:System.Windows.Media.Effects.BlurBitmapEffect.Radius%2A> von <xref:System.Windows.Media.Effects.BlurBitmapEffect>.  
  
 Als Spezialfall können in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Effekte als Eigenschaften für aktive <xref:System.Windows.Media.Visual>\-Objekte festgelegt werden, z. B. eine <xref:System.Windows.Controls.Button> oder ein <xref:System.Windows.Controls.TextBox>.  Die Pixelverarbeitung wird angewendet und zur Laufzeit gerendert.  In diesem Fall wird zur Renderingzeit ein <xref:System.Windows.Media.Visual> automatisch in die <xref:System.Windows.Media.Imaging.BitmapSource>\-Entsprechung konvertiert und dient als Eingabe für den <xref:System.Windows.Media.Effects.BitmapEffect>.  Die Ausgabe ersetzt das Standardrenderingverhalten des <xref:System.Windows.Media.Visual>\-Objekts.  Aus diesem Grund erzwingen <xref:System.Windows.Media.Effects.BitmapEffect>\-Objekte, dass visuelle Objekte ausschließlich in der Software gerendert werden, d. h.  visuelle Objekte müssen ohne Hardwarebeschleunigung auskommen, wenn Effekte angewendet werden.  
  
-   <xref:System.Windows.Media.Effects.BlurBitmapEffect> simuliert ein Objekt, das unscharf angezeigt wird.  
  
-   <xref:System.Windows.Media.Effects.OuterGlowBitmapEffect> erstellt einen farbigen Lichthof um die Umgrenzung eines Objekts.  
  
-   <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> erstellt einen Schatten hinter einem Objekt.  
  
-   <xref:System.Windows.Media.Effects.BevelBitmapEffect> erstellt eine Abschrägung, die die Oberfläche eines Bilds entsprechend einer angegebenen Kurve erhöht.  
  
-   <xref:System.Windows.Media.Effects.EmbossBitmapEffect> erstellt ein Bump\-Mapping eines <xref:System.Windows.Media.Visual>\-Objekts, um den Eindruck von Tiefe und Textur von einer animierten Lichtquelle zu vermitteln.  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Bitmapeffekte werden im Softwaremodus gerendert.  Jedes Objekt, das einen Effekt anwendet, wird auch in der Software gerendert.  Die Leistung wird am stärksten beeinträchtigt, wenn Bitmapeffekte für große visuelle Objekte verwendet oder Eigenschaften eines Bitmapeffekts animiert werden.  Das bedeutet nicht, dass Sie überhaupt keine Bitmapeffekte auf diese Art einsetzen sollten, aber Sie sollten vorsichtig damit umgehen und mit gründlichen Tests sicherstellen, dass die Benutzerfreundlichkeit erhalten bleibt.  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Bitmapeffekte unterstützen keine Ausführung unter teilweiser Vertrauenswürdigkeit.  Eine Anwendung muss über Berechtigungen für volle Vertrauenswürdigkeit verfügen, um Bitmapeffekte zu verwenden.  
  
<a name="applyeffects"></a>   
## So wird eine Effekt angewendet  
 <xref:System.Windows.Media.Effects.BitmapEffect> ist eine Eigenschaft für <xref:System.Windows.Media.Visual>.  Daher ist das Anwenden von Effekten auf visuelle Objekte, z. B. <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Image>, <xref:System.Windows.Media.DrawingVisual> oder <xref:System.Windows.UIElement>, so einfach wie das Festlegen einer Eigenschaft.  <xref:System.Windows.UIElement.BitmapEffect%2A> kann auf ein einzelnes <xref:System.Windows.Media.Effects.BitmapEffect>\-Objekt festgelegt werden, oder mehrere Effekte können mithilfe des <xref:System.Windows.Media.Effects.BitmapEffectGroup>\-Objekts verkettet werden.  
  
 Im folgenden Beispiel wird die Anwendung eines <xref:System.Windows.Media.Effects.BitmapEffect> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] veranschaulicht.  
  
 [!code-xml[EffectsGallery_snip#BlurSimpleExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blursimpleexample.xaml#blursimpleexampleinline)]  
  
 Im folgenden Beispiel wird die Anwendung eines <xref:System.Windows.Media.Effects.BitmapEffect> in Code veranschaulicht.  
  
 [!code-csharp[EffectsGallery_snip#CodeBehindBlurCodeBehindExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blurcodebehindexample.xaml.cs#codebehindblurcodebehindexampleinline)]  
  
> [!NOTE]
>  Wenn ein <xref:System.Windows.Media.Effects.BitmapEffect> auf einen Layoutcontainer angewendet wird, z. B. <xref:System.Windows.Controls.DockPanel> oder <xref:System.Windows.Controls.Canvas>, wird der Effekt auf die visuelle Struktur des Elements oder visuellen Objekts angewendet, einschließlich aller untergeordneter Elemente.  
  
<a name="customeffects"></a>   
## Erstellen von benutzerdefinierten Effekten  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] stellt auch nicht verwaltete Schnittstellen bereit, um benutzerdefinierte Effekte zu erstellen, die in verwalteten [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Anwendungen verwendet werden können.  Weiteres Referenzmaterial zum Erstellen von benutzerdefinierten Bitmapeffekten finden Sie in der Dokumentation [Nicht verwaltete WPF\-Bitmapeffekte](_wibe_lh).  
  
## Siehe auch  
 <xref:System.Windows.Media.Effects.BitmapEffectGroup>   
 <xref:System.Windows.Media.Effects.BitmapEffectInput>   
 <xref:System.Windows.Media.Effects.BitmapEffectCollection>   
 [Unmanaged WPF Bitmap Effect](_wibe_lh)   
 [Übersicht über die Bildverarbeitung](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)   
 [Sicherheit](../../../../docs/framework/wpf/security-wpf.md)   
 [Übersicht über das WPF\-Grafikrendering](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)   
 [2D\-Grafiken und Bildverarbeitung](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)