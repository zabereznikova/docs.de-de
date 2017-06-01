---
title: "&#220;bersicht &#252;ber Durchl&#228;ssigkeitsmasken | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Pinsel, Durchlässigkeitsmasken"
  - "Masken, Durchlässigkeit"
  - "Durchlässigkeit, Masken"
ms.assetid: 22367fab-5f59-4583-abfd-db2bf86eaef7
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# &#220;bersicht &#252;ber Durchl&#228;ssigkeitsmasken
Mit Durchlässigkeitsmasken können Sie Teile eines Elements oder visuellen Objekts transparent bzw. teilweise transparent machen.  Um eine Durchlässigkeitsmaske zu erstellen, wenden Sie einen <xref:System.Windows.Media.Brush> auf die <xref:System.Windows.UIElement.OpacityMask%2A>\-Eigenschaft eines Elements oder <xref:System.Windows.Media.Visual> an.  Der Pinsel wird dem Element oder visuellen Objekt zugeordnet, und mit dem Durchlässigkeitswert jedes Pinselpixels wird die verbleibende Durchlässigkeit jedes entsprechenden Pixels des Elements oder visuellen Objekts bestimmt.  
  
 Dieses Thema enthält folgende Abschnitte.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
-   [Vorbereitungsmaßnahmen](#prereqs)  
  
-   [Erstellen von visuellen Effekten mit Durchlässigkeitsmasken](#opacitymasks)  
  
-   [Erstellen einer Durchlässigkeitsmaske](#creatingopacitymasks)  
  
-   [Verwenden eines Farbverlaufs als Durchlässigkeitsmaske](#creatingopacitymaskswithgradients)  
  
-   [Angeben von Farbverlaufsunterbrechungspunkten für eine Durchlässigkeitsmaske](#specifyinggradientcolors)  
  
-   [Verwenden eines Bilds als Durchlässigkeitsmaske](#usingimageasopacitymask)  
  
-   [Erstellen einer Durchlässigkeitsmaske aus einer Zeichnung](#drawingbrushasopacitymask)  
  
-   [Verwandte Themen](#seeAlsoToggle)  
  
<a name="prereqs"></a>   
## Vorbereitungsmaßnahmen  
 In dieser Übersicht wird davon ausgegangen, dass Sie mit <xref:System.Windows.Media.Brush>\-Objekten vertraut sind.  Eine Einführung in die Verwendung von Pinseln finden Sie unter [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  Weitere Informationen über <xref:System.Windows.Media.ImageBrush> und <xref:System.Windows.Media.DrawingBrush> finden Sie unter [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
<a name="opacitymasks"></a>   
## Erstellen von visuellen Effekten mit Durchlässigkeitsmasken  
 Eine Durchlässigkeitsmaske funktioniert so, dass ihre Inhalte dem Element oder visuellen Objekt zugeordnet werden.  Mit dem [Alphakanal](GTMT) von jedem Pinselpixel wird dann die verbleibende Durchlässigkeit der entsprechenden Pixel des Elements oder visuellen Objekts bestimmt. Die tatsächliche Pinselfarbe wird ignoriert.  Wenn ein bestimmter Teil des Pinsels transparent ist, wird der entsprechende Teil des Elements oder visuellen Objekts transparent.  Wenn ein bestimmter Teil des Pinsels nicht transparent ist, bleibt die Durchlässigkeit des entsprechenden Teils des Elements oder visuellen Objekts unverändert.  Die von der Durchlässigkeitsmaske angegebene Durchlässigkeit wird mit allen Durchlässigkeitseinstellungen im Element oder visuellen Objekt kombiniert.  Wenn z. B ein Element zu 25 Prozent deckend ist und eine Durchlässigkeitsmaske angewendet wird, die von vollständig deckend in vollständig transparent übergeht, ist das Ergebnis ein Element, das von 25 Prozent Durchlässigkeit in vollständige Transparenz übergeht.  
  
> [!NOTE]
>  Obwohl mit den Beispielen in dieser Übersicht die Verwendung von Durchlässigkeitsmasken für Bildelemente gezeigt wird, kann eine Durchlässigkeitsmaske auf jedes Element oder <xref:System.Windows.Media.Visual>, einschließlich Panels und Steuerelementen, angewendet werden.  
  
 Mit Durchlässigkeitsmasken lassen sich interessante visuelle Effekte erstellen. Zum Beispiel können Sie Bilder oder Schaltflächen erstellen, die ausgeblendet werden, Elementen Texturen hinzufügen oder Farbverläufe kombinieren, um glasähnliche Oberflächen zu erzeugen.  In der folgenden Abbildung wird die Verwendung einer Durchlässigkeitsmaske veranschaulicht.  Mit einem Hintergrund im Schachbrettmuster werden die transparenten Teile der Maske angezeigt.  
  
 ![Objekt mit einer LinearGradientBrush&#45;Deckkraftmaske](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-opacitymask-imageexample.png "wcpsdk\_graphicsmm\_opacitymask\_imageexample")  
Beispiel für eine Durchlässigkeitsmaske  
  
<a name="creatingopacitymasks"></a>   
## Erstellen einer Durchlässigkeitsmaske  
 Um eine Durchlässigkeitsmaske zu erstellen, erstellen Sie einen <xref:System.Windows.Media.Brush> und wenden ihn auf die <xref:System.Windows.UIElement.OpacityMask%2A>\-Eigenschaft eines Elements oder visuellen Elements an.  Sie können jeden Typ von <xref:System.Windows.Media.Brush> als Durchlässigkeitsmaske verwenden.  
  
-   <xref:System.Windows.Media.LinearGradientBrush>, <xref:System.Windows.Media.RadialGradientBrush>: Werden verwendet, um ein Element oder visuelles Element auszublenden.  
  
     Im folgenden Bild wird ein als Durchlässigkeitsmaske verwendeter <xref:System.Windows.Media.LinearGradientBrush> gezeigt.  
  
     ![Ein Objekt mit einer LinearGradiantBrush&#45;Deckkraftmaske](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-brushes-lineagradientopacitymasksingle.png "wcpsdk\_graphicsmm\_brushes\_lineagradientopacitymasksingle")  
Beispiel für eine Durchlässigkeitsmaske mit LinearGradientBrush  
  
-   <xref:System.Windows.Media.ImageBrush>: Wird verwendet, um Textureffekte und weiche oder ausgefranste Randeffekte zu erstellen.  
  
     Im folgenden Bild wird ein als Durchlässigkeitsmaske verwendeter <xref:System.Windows.Media.ImageBrush> gezeigt.  
  
     ![Objekt mit einer ImageBrush&#45;Deckkraftmaske](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-brushes-imageasopacitymasksingle.png "wcpsdk\_graphicsmm\_brushes\_imageasopacitymasksingle")  
Beispiel für eine Durchlässigkeitsmaske mit LinearGradientBrush  
  
-   <xref:System.Windows.Media.DrawingBrush>: Wird verwendet, um komplexe Durchlässigkeitsmasken aus Mustern von Formen, Bildern und Farbverläufen zu erstellen.  
  
     Im folgenden Bild wird ein als Durchlässigkeitsmaske verwendeter <xref:System.Windows.Media.DrawingBrush> gezeigt.  
  
     ![Objekt mit einer DrawingBrush&#45;Deckkraftmaske](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-drawingbrushasopacitymask-single.png "wcpsdk\_drawingbrushasopacitymask\_single")  
Beispiel für eine Durchlässigkeitsmaske mit DrawingBrush  
  
 Die Farbverlaufspinsel \(<xref:System.Windows.Media.LinearGradientBrush> und <xref:System.Windows.Media.RadialGradientBrush>\) sind für die Verwendung als Durchlässigkeitsmaske besonders gut geeignet.  Da ein <xref:System.Windows.Media.SolidColorBrush> einen Bereich mit einer einheitlichen Farbe füllt, werden damit keine optimalen Durchlässigkeitsmasken erzeugt. Wenn ein <xref:System.Windows.Media.SolidColorBrush> verwendet wird, entspricht dies dem Festlegen der <xref:System.Windows.UIElement.OpacityMask%2A>\-Eigenschaft des Elements oder visuellen Elements.  
  
<a name="creatingopacitymaskswithgradients"></a>   
## Verwenden eines Farbverlaufs als Durchlässigkeitsmaske  
 Um eine graduelle Füllung zu erstellen, werden zwei oder mehr Farbverlaufsunterbrechungspunkte angegeben.  Jeder Farbverlaufsunterbrechungspunkt beschreibt eine Farbe und eine Position \(weitere Informationen über das Erstellen und Verwenden von Farbverläufen finden Sie unter [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)\).  Es handelt sich um den gleichen Vorgang wie bei der Verwendung eines Farbverlaufs als Durchlässigkeitsmaske. Nur werden durch den Farbverlauf der Durchlässigkeitsmaske nicht Farben gemischt, sondern Alphakanalwerte.  Daher spielt die tatsächliche Farbe der Farbverlaufsinhalte keine Rolle. Nur der Alphakanal bzw. die Durchlässigkeit jeder Farbe ist relevant.  Im Folgenden finden Sie ein Beispiel.  
  
 <!-- TODO: review snippet reference [!code-xml[OpacityMasksExample#LinearGradientOpacityMaskonImage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksExample/CS/GradientBrushExample.xaml#lineargradientopacitymaskonimage)]  -->
 <!-- TODO: review snippet reference [!code-xml[OpacityMasksExample#LinearGradientOpacityMaskonImage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/OpacityMasksExample/XAML/GradientBrushExample.xaml#lineargradientopacitymaskonimage)]  -->  
  
<a name="specifyinggradientcolors"></a>   
## Angeben von Farbverlaufsunterbrechungspunkten für eine Durchlässigkeitsmaske  
 Im vorhergehenden Beispiel wird die systemdefinierte Farbe <xref:System.Windows.Media.Colors.Black%2A> als Startfarbe des Farbverlaufs verwendet.  Da alle Farben in der <xref:System.Windows.Media.Colors>\-Klasse, mit Ausnahme von <xref:System.Windows.Media.Colors.Transparent%2A>, vollständig deckend sind, kann mit ihnen einfach eine Startfarbe für eine Durchlässigkeitsmaske mit einem Farbverlauf definiert werden.  
  
 Zur zusätzlichen Kontrolle über Alphawerte beim Definieren einer Durchlässigkeitsmaske können Sie den Alphakanal von Farben mit der [!INCLUDE[TLA#tla_argb](../../../../includes/tlasharptla-argb-md.md)]\-Hexadezimalschreibweise in Markup oder mit der <xref:System.Windows.Media.Color.FromScRgb%2A?displayProperty=fullName>\-Methode angeben.  
  
<a name="argbsyntax"></a>   
### Angeben der Deckkraft einer Farbe in "XAML"  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] wird die [!INCLUDE[TLA2#tla_argb](../../../../includes/tla2sharptla-argb-md.md)]\-Hexadezimalnotation verwendet , um die Deckkraft einzelner Farben anzugeben.  Die [!INCLUDE[TLA2#tla_argb](../../../../includes/tla2sharptla-argb-md.md)]\-Hexadezimalnotation verwendet die folgende Syntax:  
  
 `#`**aa** *rrggbb*  
  
 In der vorangehenden Zeile steht *aa* für einen zweistelligen Hexadezimalwert, der verwendet wird, um die Deckkraft der Farbe anzugeben.  *rr*, *gg* und *bb* stehen jeweils für einen zweistelligen Hexadezimalwert, der verwendet wird, um die Anteile von Rot, Grün und Blau in einer Farbe anzugeben.  Jede Hexadezimalziffer kann einen Wert von 0\-9 oder A\-F haben.  0 \(null\) ist der kleinste Wert, und F ist der größte.  Der Alphawert 00 gibt eine Farbe an, die vollständig transparent ist, während ein Alphawert  FF eine vollständig deckende Farbe erzeugt.  Im folgenden Beispiel wird die [!INCLUDE[TLA2#tla_argb](../../../../includes/tla2sharptla-argb-md.md)]\-Hexadezimalnotation verwendet, um zwei Farben anzugeben.  Die erste Farbe ist vollständig deckend, während die zweite vollkommen transparent ist.  
  
 <!-- TODO: review snippet reference [!code-xml[OpacityMasksExample#AARRGGBBValueonOpacityMask](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksExample/CS/GradientBrushExample.xaml#aarrggbbvalueonopacitymask)]  -->
 <!-- TODO: review snippet reference [!code-xml[OpacityMasksExample#AARRGGBBValueonOpacityMask](../../../../samples/snippets/xaml/VS_Snippets_Wpf/OpacityMasksExample/XAML/GradientBrushExample.xaml#aarrggbbvalueonopacitymask)]  -->  
  
<a name="usingimageasopacitymask"></a>   
## Verwenden eines Bilds als Durchlässigkeitsmaske  
 Auch Bilder können als Durchlässigkeitsmaske verwendet werden.  Im folgenden Bild wird ein Beispiel dargestellt.  Mit einem Hintergrund im Schachbrettmuster werden die transparenten Teile der Maske angezeigt.  
  
 ![Ein Objekt mit einer ImageBrush&#45;Deckkraftmaske](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-imageasopacitymask.png "wcpsdk\_graphicsmm\_imageasopacitymask")  
Beispiel für eine Durchlässigkeitsmaske  
  
 Um ein Bild als Durchlässigkeitsmaske zu verwenden, verwenden Sie einen <xref:System.Windows.Media.ImageBrush>, der das Bild enthalten soll.  Wenn Sie ein Bild erstellen, das als Durchlässigkeitsmaske dienen soll, speichern Sie das Bild in einem Format, das mehrere Transparenzgrade unterstützt, z. B. [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)].  Das folgende Beispiel enthält den Code, mit dem die vorherige Abbildung erstellt wurde.  
  
 <!-- TODO: review snippet reference [!code-xml[OpacityMasksExample#UIElementOpacityMask](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksExample/CS/ImageBrushExample.xaml#uielementopacitymask)]  -->
 <!-- TODO: review snippet reference [!code-xml[OpacityMasksExample#UIElementOpacityMask](../../../../samples/snippets/xaml/VS_Snippets_Wpf/OpacityMasksExample/XAML/ImageBrushExample.xaml#uielementopacitymask)]  -->  
  
<a name="tilingimageopacitymask"></a>   
### Verwenden eines gekachelten Bilds als Durchlässigkeitsmaske  
 Im folgenden Beispiel wird dasselbe Bild mit einem anderen <xref:System.Windows.Media.ImageBrush> verwendet, aber mit den Unterteilungsfeatures des Pinsels werden Bildkacheln als Quadrat mit 500 Pixeln Größe erzeugt.  
  
 <!-- TODO: review snippet reference [!code-xml[OpacityMasksExample#TiledImageasOpacityMask](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksExample/CS/ImageBrushExample.xaml#tiledimageasopacitymask)]  -->
 <!-- TODO: review snippet reference [!code-xml[OpacityMasksExample#TiledImageasOpacityMask](../../../../samples/snippets/xaml/VS_Snippets_Wpf/OpacityMasksExample/XAML/ImageBrushExample.xaml#tiledimageasopacitymask)]  -->  
  
<a name="drawingbrushasopacitymask"></a>   
## Erstellen einer Durchlässigkeitsmaske aus einer Zeichnung  
 Zeichnungen können als Durchlässigkeitsmaske verwendet werden.  Die Formen innerhalb der Zeichnung können selbst mit Farbverläufen, Volltonfarben, Bildern und sogar anderen Zeichnungen gefüllt werden.  Im folgenden Bild wird ein Beispiel einer Zeichnung gezeigt, die als Durchlässigkeitsmaske verwendet wird.  Mit einem Hintergrund im Schachbrettmuster werden die transparenten Teile der Maske angezeigt.  
  
 ![Ein Objekt mit einer DrawingBrush&#45;Deckkraftmaske](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-drawingbrushasopacitymask.png "wcpsdk\_drawingbrushasopacitymask")  
Beispiel für eine Durchlässigkeitsmaske mit DrawingBrush  
  
 Um eine Zeichnung als Durchlässigkeitsmaske zu verwenden, verwenden Sie einen <xref:System.Windows.Media.DrawingBrush>, der die Zeichnung enthalten soll.  Das folgende Beispiel enthält den Code, mit dem die vorherige Abbildung erstellt wurde:  
  
 <!-- TODO: review snippet reference [!code-xml[OpacityMasksExample#OpacityMaskfromDrawing](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksExample/CS/DrawingBrushExample.xaml#opacitymaskfromdrawing)]  -->
 <!-- TODO: review snippet reference [!code-xml[OpacityMasksExample#OpacityMaskfromDrawing](../../../../samples/snippets/xaml/VS_Snippets_Wpf/OpacityMasksExample/XAML/DrawingBrushExample.xaml#opacitymaskfromdrawing)]  -->  
  
<a name="tileddrawingbrush"></a>   
### Verwenden einer gekachelten Zeichnung als Durchlässigkeitsmaske  
 Wie der <xref:System.Windows.Media.ImageBrush> kann auch der <xref:System.Windows.Media.DrawingBrush> so eingesetzt werden, dass die Zeichnung gekachelt angezeigt wird.  Im folgenden Beispiel wird mit einem Zeichenpinsel eine gekachelte Durchlässigkeitsmaske erstellt.  
  
 <!-- TODO: review snippet reference [!code-xml[OpacityMasksExample#TiledDrawingasOpacityMask](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksExample/CS/DrawingBrushExample.xaml#tileddrawingasopacitymask)]  -->
 <!-- TODO: review snippet reference [!code-xml[OpacityMasksExample#TiledDrawingasOpacityMask](../../../../samples/snippets/xaml/VS_Snippets_Wpf/OpacityMasksExample/XAML/DrawingBrushExample.xaml#tileddrawingasopacitymask)]  -->  
  
## Siehe auch  
 [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)   
 [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)