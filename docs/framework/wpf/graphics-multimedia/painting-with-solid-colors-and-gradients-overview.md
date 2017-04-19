---
title: "&#220;bersicht &#252;ber das Zeichnen mit Volltonfarben und Farbverl&#228;ufen | Microsoft Docs"
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
  - "Pinsel, Zeichnen mit Farbverlauf"
  - "Pinsel, Zeichnen mit Volltonfarben"
  - "Farbverläufe, Zeichnen mit"
  - "Zeichnen mit Farbverlauf"
  - "Zeichnen mit Volltonfarben"
  - "Volltonfarben, Zeichnen mit"
ms.assetid: f5b182f3-c5c7-4cbe-9f2f-65e690d08255
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# &#220;bersicht &#252;ber das Zeichnen mit Volltonfarben und Farbverl&#228;ufen
In diesem Thema wird beschrieben, wie die Objekte <xref:System.Windows.Media.SolidColorBrush>, <xref:System.Windows.Media.LinearGradientBrush> und <xref:System.Windows.Media.RadialGradientBrush> verwendet werden, um mit Volltonfarben, linearen Farbverläufen und radialen Farbverläufen zu zeichnen.  
  
   
  
<a name="solidcolor"></a>   
## Zeichnen eines Bereichs mit einer Volltonfarbe  
 Einer der am häufigsten verwendeten Vorgänge auf allen Plattformen ist, einen Bereich mit Volltonfarbe \(solid <xref:System.Windows.Media.Color>\) zu zeichnen.  Um diese Aufgabe auszuführen, stellt [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] die <xref:System.Windows.Media.SolidColorBrush>\-Klasse bereit.  In den folgenden Abschnitten werden die verschiedenen Möglichkeiten beschrieben, mit einem <xref:System.Windows.Media.SolidColorBrush> zu zeichnen.  
  
<a name="solidcolorinxaml"></a>   
### Verwenden eines SolidColorBrush in "XAML"  
 Um in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] einen Bereich mit einer Volltonfarbe zu zeichnen, verwenden Sie eine der folgenden Optionen.  
  
-   Wählen Sie einen vordefinierten Volltonfarbenpinsel über den Namen aus.  Zum Beispiel können Sie den <xref:System.Windows.Controls.Control.Background%2A> einer Schaltfläche auf "Red" oder "MediumBlue" festlegen.  Eine Liste anderer vordefinierter Volltonfarbenpinsel finden Sie in den statischen Eigenschaften der <xref:System.Windows.Media.Brushes>\-Klasse.  Im Folgenden finden Sie ein Beispiel.  
  
     [!code-xml[BrushOverviewExamples_snip#SolidColorBrushNamedColor1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/SolidColorBrushExample.xaml#solidcolorbrushnamedcolor1xaml)]  
  
-   Wählen Sie eine Farbe aus der 32\-Bit\-Farbpalette aus, indem Sie die Anteile von Rot, Grün und Blau festlegen, aus denen sich eine Volltonfarbe zusammensetzt.  Das Format zum Festlegen einer Farbe aus der 32\-Bit\-Palette ist "*\#rrggbb*", wobei mit dem zweistelligen Hexadezimalwert *rr* der relative Anteil von Rot, mit *gg* der Anteil von Grün und mit *bb* der Anteil von Blau festgelegt wird.  Zusätzlich kann die Farbe im Format "\#*aarrggbb*" angegeben werden, wobei *aa* für den *Alpha*wert, also die Transparenz, der Farbe steht.  Dieser Ansatz ermöglicht es Ihnen, Farben zu erstellen, die teilweise transparent sind.  Im folgenden Beispiel wird der <xref:System.Windows.Controls.Control.Background%2A> eines <xref:System.Windows.Controls.Button>\-Elements mithilfe der Hexadezimalnotation auf vollständig deckendes Rot festgelegt.  
  
     [!code-xml[BrushOverviewExamples_snip#SolidColorBrushHex1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/SolidColorBrushExample.xaml#solidcolorbrushhex1xaml)]  
  
-   Verwenden Sie die Syntax für Eigenschaftentags, um einen <xref:System.Windows.Media.SolidColorBrush> zu beschreiben.  Diese Syntax ist ausführlicher, aber ermöglicht es Ihnen, zusätzliche Einstellungen anzugeben, z. B. die Deckkraft des Pinsels.  Im folgenden Beispiel werden die <xref:System.Windows.Controls.Control.Background%2A>\-Eigenschaften von zwei <xref:System.Windows.Controls.Button>\-Elementen auf vollständig deckendes Rot festgelegt.  Die Farbe des ersten Pinsels wird mit einem vordefinierten Farbnamen beschrieben.  Die Farbe des zweiten Pinsels wird mithilfe der Hexadezimalnotation beschrieben.  
  
     [!code-xml[BrushOverviewExamples_snip#SolidColorBrushPropertyTag1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/SolidColorBrushExample.xaml#solidcolorbrushpropertytag1xaml)]  
  
<a name="solidcolorsincode"></a>   
### Zeichnen mit einem SolidColorBrush in Code  
 Um einen Bereich mit einer Volltonfarbe in Code zu zeichnen, verwenden Sie eine der folgenden Optionen.  
  
-   Verwenden Sie einen der vordefinierten Pinsel, die von der <xref:System.Windows.Media.Brushes>\-Klasse bereitgestellt werden.  Im folgenden Beispiel wird der <xref:System.Windows.Controls.Control.Background%2A> eines <xref:System.Windows.Controls.Button>\-Elements auf <xref:System.Windows.Media.Brushes.Red%2A> festgelegt.  
  
     [!code-csharp[BrushOverviewExamples_snip#SolidColorBrushPredefinedBrush1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushpredefinedbrush1csharp)]  
  
-   Erstellen Sie einen <xref:System.Windows.Media.SolidColorBrush>, und legen Sie seine <xref:System.Windows.Media.SolidColorBrush.Color%2A>\-Eigenschaft mit einer <xref:System.Windows.Media.Color>\-Struktur fest.  Sie können eine vordefinierte Farbe aus der <xref:System.Windows.Media.Colors>\-Klasse verwenden oder eine <xref:System.Windows.Media.Color> mithilfe der statischen <xref:System.Windows.Media.Color.FromArgb%2A>\-Methode erstellen.  
  
     Das folgende Beispiel zeigt, wie die <xref:System.Windows.Media.SolidColorBrush.Color%2A>\-Eigenschaft für einen <xref:System.Windows.Media.SolidColorBrush> mit einer vordefinierten Farbe festgelegt wird.  
  
     [!code-csharp[BrushOverviewExamples_snip#SolidColorBrushPredefinedColor1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushpredefinedcolor1csharp)]  
  
 Die statische <xref:System.Windows.Media.Color.FromArgb%2A>\-Methode ermöglicht es Ihnen, die roten, grünen, und blauen [Alpha](GTMT)werte der Farbe anzugeben.  Der typische Bereich für jeden dieser Werte ist 0\-255.  Beispielsweise gibt der [Alpha](GTMT)wert 0 \(null\) an, dass die Farbe vollständig transparent ist, während der Wert 255 angibt, dass die Farbe vollständig deckend ist.  Ebenso gibt der Wert 0 für die Farbe Rot an, dass eine Farbe keinen Rotanteil hat, während bei einem Wert von 255 der maximale Rotanteil erreicht wird.  Im folgenden Beispiel wird die Farbe eines Pinsels beschrieben, indem rote, grüne, und blaue Alphawerte angegeben werden.  
  
 [!code-csharp[BrushOverviewExamples_snip#SolidColorBrushfromArgbExample1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushfromargbexample1csharp)]  
  
 Weitere Möglichkeiten zum Angeben von Farben finden Sie im <xref:System.Windows.Media.Color>\-Referenzthema.  
  
<a name="gradient"></a>   
## Zeichnen eines Bereichs mit einem Farbverlauf  
 Ein Farbverlaufspinsel zeichnet einen Bereich mit mehreren Farben, die sich an einer Achse miteinander vermischen.  Sie können Farbverlaufspinsel verwenden, um Eindrücke von Licht und Schatten zu erzeugen und den Steuerelementen ein dreidimensionales Aussehen zu geben.  Sie können sie auch verwenden, um Glas, Chrom, Wasser und andere glatte Oberflächen zu simulieren.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt zwei Typen von Farbverlaufspinseln bereit: <xref:System.Windows.Media.LinearGradientBrush> und <xref:System.Windows.Media.RadialGradientBrush>.  
  
<a name="lineargradientbrush"></a>   
## Lineare Farbverläufe  
 Ein <xref:System.Windows.Media.LinearGradientBrush> zeichnet einen Bereich mit einem an einer Zeile definierten Farbverlauf, der *Farbverlaufsachse*.  Sie können die Farben des Farbverlaufs und ihren Speicherort an der Farbverlaufsachse mithilfe von <xref:System.Windows.Media.GradientStop>\-Objekten angeben.  Sie können auch die Farbverlaufsachse ändern. Dies ermöglicht Ihnen, horizontale und vertikale Farbverläufe zu erstellen und die Richtung des Farbverlaufs umzukehren.  Die Farbverlaufsachse wird im nächsten Abschnitt beschrieben.  Standardmäßig wird ein diagonaler Farbverlauf erstellt.  
  
 Das folgende Beispiel zeigt den Code, mit dem ein linearer Farbverlauf mit vier Farben erstellt wird.  
  
 [!code-xml[GradientBrushExamples_snip#DiagonalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 Dieser Code erzeugt den folgenden Farbverlauf:  
  
 ![Ein diagonaler, linearer Farbverlauf](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-diaglgradient-nolabel.png "wcpsdk\_graphicsmm\_diaglgradient\_nolabel")  
  
 **Hinweis:** Die Beispiele für Farbverläufe in diesem Thema verwenden das Standardkoordinatensystem zum Festlegen von Startpunkten und Endpunkten.  Das Standardkoordinatensystem ist relativ zu einem umgebenden Rechteck: 0 gibt 0 Prozent des umgebenden Rechtecks an, und 1 gibt 100 Prozent des umgebenden Rechtecks an.  Sie können dieses Koordinatensystem ändern, indem Sie den Wert der <xref:System.Windows.Media.GradientBrush.MappingMode%2A>\-Eigenschaft auf den Wert <xref:System.Windows.Media.BrushMappingMode> festlegen.  Ein absolutes Koordinatensystem ist nicht relativ zu einem umgebenden Rechteck.  Werte werden direkt im lokalen Raum interpretiert.  
  
 Der <xref:System.Windows.Media.GradientStop> ist der Grundbaustein eines Farbverlaufspinsels.  Ein Farbverlaufsunterbrechungspunkt gibt eine <xref:System.Windows.Media.GradientStop.Color%2A> für einen <xref:System.Windows.Media.GradientStop.Offset%2A> an der Farbverlaufsachse an.  
  
-   Die <xref:System.Windows.Media.GradientStop.Color%2A>\-Eigenschaft des Farbverlaufsunterbrechungspunkts gibt die Farbe des Farbverlaufsunterbrechungspunkts an.  Sie können die Farbe festlegen, indem Sie eine vordefinierte Farbe verwenden \(bereitgestellt von der <xref:System.Windows.Media.Colors>\-Klasse\) oder indem Sie ScRGB\-Werte oder ARGB\-Werte angeben.  In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] können Sie auch die Hexadezimalnotation verwenden, um eine Farbe zu beschreiben.  Weitere Informationen finden Sie in der <xref:System.Windows.Media.Color>\-Struktur.  
  
-   Die <xref:System.Windows.Media.GradientStop.Offset%2A>\-Eigenschaft des Farbverlaufsunterbrechungspunkts gibt die Position der Farbe des Farbverlaufsunterbrechungspunkts auf der Farbverlaufsachse an.  Der Offset ist ein <xref:System.Double> zwischen 0 und 1.  Je näher der Offsetwert des Farbverlaufsstopps bei 0 \(null\) liegt, desto näher befindet sich die Farbe am Beginn des Farbverlaufs.  Je näher der Offsetwert des Farbverlaufsunterbrechungspunkts bei 1 liegt, desto näher befindet sich die Farbe am Ende des Farbverlaufs.  
  
 Die Farbe jedes Punkts zwischen Farbverlaufsunterbrechungspunkten wird als eine Kombination der Farben, die durch die zwei umschließenden Farbverlaufsunterbrechungspunkte angegeben werden, linear interpoliert.  In der folgenden Abbildung werden die Farbverlaufsunterbrechungspunkte aus dem vorherigen Beispiel hervorgehoben.  Die Kreise markieren die Position der Farbverlaufsunterbrechungspunkte, und eine gestrichelte Linie zeigt die Farbverlaufsachse an.  
  
 ![Farbverlaufstopps in einem linearen Farbverlauf](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-4gradientstops.png "wcpsdk\_graphicsmm\_4gradientstops")  
  
 Der erste Farbverlaufsunterbrechungspunkt gibt die Farbe Gelb bei einem Offset von `0.0` an.  Der zweite Farbverlaufsunterbrechungspunkt gibt die Farbe Rot bei einem Offset von `0.25` an.  Die Farbe der Punkte zwischen diesen zwei Punkten ändert sich allmählich von Gelb zu Rot, wenn Sie sich von links nach rechts entlang der Farbverlaufsachse bewegen.  Der dritte Farbverlaufsunterbrechungspunkt gibt die Farbe Blau bei einem Offset von `0.75` an.  Die Farbe der Punkte zwischen dem zweiten und dem dritten Farbverlaufsunterbrechungspunkt ändert sich allmählich von Rot zu Blau.  Der vierte Farbverlaufsunterbrechungspunkt gibt die Farbe Gelbgrün bei einem Offset von `1.0` an.  Die Farbe der Punkte zwischen dem dritten und dem vierten Farbverlaufsunterbrechungspunkt ändert sich allmählich von Blau zu Gelbgrün.  
  
<a name="gradientaxis"></a>   
### Die Farbverlaufsachse  
 Wie bereits erwähnt, befinden sich die Farbverlaufsunterbrechungspunkte eines Pinsels mit linearem Farbverlauf auf einer Linie, der Farbverlaufsachse.  Sie können die Ausrichtung und die Größe der Linie mit der <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A>\-Eigenschaft und der <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A>\-Eigenschaft des Pinsels ändern.  Durch Bearbeiten von <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> und <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> des Pinsels können Sie unter anderem horizontale und vertikale Farbverläufe erstellen, die Richtung des Farbverlaufs umkehren und die Farbverlaufsausdehnung verringern.  
  
 Standardmäßig sind der <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> und der <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> des Pinsels mit linearem Farbverlauf relativ zum Bereich, der gezeichnet wird.  Der Punkt \(0,0\) stellt die obere linke Ecke und der Punkt \(1,1\) die untere rechte Ecke des Bereichs dar, der gezeichnet wird.  Der <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> von einem <xref:System.Windows.Media.LinearGradientBrush> ist standardmäßig \(0,0\), und der <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> ist standardmäßig \(1,1\), wodurch ein diagonaler Farbverlauf von der oberen linken zur unteren rechten Ecke des gezeichneten Bereichs erstellt wird.  Die folgende Abbildung zeigt die Farbverlaufsachse eines Pinsels mit linearem Farbverlauf mit dem Standard\-<xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> und dem Standard\-<xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A>.  
  
 ![Farbverlaufachse für einen diagonalen linearen Farbverlauf](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-diagonalgradientaxis.png "wcpsdk\_graphicsmm\_diagonalgradientaxis")  
  
 Das folgende Beispiel zeigt, wie ein horizontaler Farbverlauf erstellt wird, indem der <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> und der <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> des Pinsels angegeben werden.  Beachten Sie, dass die Farbverlaufsunterbrechungspunkte die gleichen sind wie in den vorherigen Beispielen. Der Farbverlauf wurde ganz einfach von diagonal in horizontal geändert, indem der <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> und der <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> geändert wurden.  
  
 [!code-xml[GradientBrushExamples_snip#HorizontalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 Die folgende Abbildung zeigt den Farbverlauf, der erstellt wird.  Die Farbverlaufsachse wird mit einer gestrichelten Linie markiert, die Farbverlaufsunterbrechungspunkte mit Kreisen.  
  
 ![Farbverlaufachse für einen horizontalen linearen Farbverlauf](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-horizontalgradient.png "wcpsdk\_graphicsmm\_horizontalgradient")  
  
 Im nächsten Beispiel wird gezeigt, wie ein vertikaler Farbverlauf erstellt wird.  
  
 [!code-xml[GradientBrushExamples_snip#VerticalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 Die folgende Abbildung zeigt den Farbverlauf, der erstellt wird.  Die Farbverlaufsachse wird mit einer gestrichelten Linie markiert, die Farbverlaufsunterbrechungspunkte mit Kreisen.  
  
 ![Farbverlaufachse für einen vertikalen Farbverlauf](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-verticalgradient.png "wcpsdk\_graphicsmm\_verticalgradient")  
  
<a name="radialgradients"></a>   
## Strahlenförmige Farbverläufe  
 Ein <xref:System.Windows.Media.RadialGradientBrush> zeichnet genau wie ein <xref:System.Windows.Media.LinearGradientBrush> einen Bereich mit Farben, die an einer Achse ineinander übergehen.  Die vorherigen Beispiele haben gezeigt, dass die Achse eines Pinsels mit linearem Farbverlauf eine gerade Linie ist.  Die Achse eines Pinsels mit radialem Farbverlauf wird durch einen Kreis definiert; seine Farben "strahlen" von seinem Ursprung aus nach außen.  
  
 Im folgenden Beispiel wird ein Pinsel mit radialem Farbverlauf verwendet, um das Innere eines Rechtecks zu zeichnen.  
  
 [!code-xml[GradientBrushExamples_snip#RadialGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/RadialGradientBrushExample.xaml#radialgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#RadialGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/RadialGradientBrushExample.cs#radialgradient1csharp)]  
  
 In der folgenden Abbildung wird der im vorherigen Beispiel erstellte Farbverlauf dargestellt.  Die Farbverlaufsunterbrechungspunkte des Pinsels wurden hervorgehoben.  Beachten Sie, dass trotz der unterschiedlichen Ergebnisse die Farbverlaufsunterbrechungspunkte die gleichen sind wie in den vorherigen Beispielen mit linearem Farbverlauf.  
  
 ![Farbverlaufstopps in einem radialen Farbverlauf](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk\_graphicsmm\_4gradientstops\_rg")  
  
 Der <xref:System.Windows.Media.RadialGradientBrush.GradientOrigin%2A> gibt den Ausgangspunkt der Farbverlaufsachse eines Pinsels mit radialem Farbverlauf an.  Die Farbverlaufsachse strahlt vom Farbverlaufsursprung zum Farbverlaufskreis aus.  Der Farbverlaufskreis eines Pinsels wird von den Eigenschaften <xref:System.Windows.Media.RadialGradientBrush.Center%2A>, <xref:System.Windows.Media.RadialGradientBrush.RadiusX%2A> und <xref:System.Windows.Media.RadialGradientBrush.RadiusY%2A> definiert.  
  
 Die folgende Abbildung zeigt mehrere radiale Farbverläufe mit verschiedenen Einstellungen für <xref:System.Windows.Media.RadialGradientBrush.GradientOrigin%2A>, <xref:System.Windows.Media.RadialGradientBrush.Center%2A>, <xref:System.Windows.Media.RadialGradientBrush.RadiusX%2A> und <xref:System.Windows.Media.RadialGradientBrush.RadiusY%2A>.  
  
 ![RadialGradientBrush&#45;Einstellungen](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-originscirclesandradii.png "wcpsdk\_graphicsmm\_originscirclesandradii")  
  
        RadialGradientBrushes mit verschiedenen Einstellungen für GradientOrigin, Center, RadiusX und RadiusY  
  
<a name="specifyinggradientcolors"></a>   
## Festlegen von transparenten oder teilweise transparenten Farbverlaufsunterbrechungspunkten  
 Da Farbverlaufsunterbrechungspunkte keine Opacity\-Eigenschaft besitzen, müssen Sie den Alphakanal für Farben mithilfe der [!INCLUDE[TLA#tla_argb](../../../../includes/tlasharptla-argb-md.md)]\-Hexadezimalnotation in Markup angeben oder die <xref:System.Windows.Media.Color.FromScRgb%2A?displayProperty=fullName>\-Methode verwenden, um transparente oder teilweise transparente Farbverlaufsunterbrechungspunkte zu erstellen.  In den folgenden Abschnitten wird erklärt, wie teilweise transparente Farbverlaufsunterbrechungspunkte in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und Code erstellt werden.  Informationen über das Festlegen der Deckkraft des gesamten Pinsels finden Sie im Abschnitt [Angeben der Deckkraft eines Pinsels](#brushesAndOpacity).  
  
<a name="argbsyntax"></a>   
### Angeben der Deckkraft einer Farbe in "XAML"  
 In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] wird die [!INCLUDE[TLA2#tla_argb](../../../../includes/tla2sharptla-argb-md.md)]\-Hexadezimalnotation verwendet , um die Deckkraft einzelner Farben anzugeben.  Die [!INCLUDE[TLA2#tla_argb](../../../../includes/tla2sharptla-argb-md.md)]\-Hexadezimalnotation verwendet die folgende Syntax:  
  
 `#`**aa** *rrggbb*  
  
 In der vorangehenden Zeile steht *aa* für einen zweistelligen Hexadezimalwert, der verwendet wird, um die Deckkraft der Farbe anzugeben.  *rr*, *gg* und *bb* stehen jeweils für einen zweistelligen Hexadezimalwert, der verwendet wird, um die Anteile von Rot, Grün und Blau in einer Farbe anzugeben.  Jede Hexadezimalziffer kann einen Wert von 0\-9 oder A\-F haben.  0 \(null\) ist der kleinste Wert, und F ist der größte.  Der Alphawert 00 gibt eine Farbe an, die vollständig transparent ist, während ein Alphawert  FF eine vollständig deckende Farbe erzeugt.  Im folgenden Beispiel wird die [!INCLUDE[TLA2#tla_argb](../../../../includes/tla2sharptla-argb-md.md)]\-Hexadezimalnotation verwendet, um zwei Farben anzugeben.  Die erste Farbe ist teilweise transparent \(sie hat einen Alphawert von 20\), während die zweite Farbe vollständig deckend ist.  
  
 [!code-xml[GradientBrushExamples_snip#TransparentGradientStopExample1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/GradientStopsExample.xaml#transparentgradientstopexample1xaml)]  
  
<a name="fromscrgbsyntax"></a>   
### Angeben der Deckkraft einer Farbe in Code  
 Wenn Sie Code verwenden, ermöglicht Ihnen die statische <xref:System.Windows.Media.Color.FromArgb%2A>\-Methode, einen Alphawert beim Erstellen einer Farbe anzugeben.  Diese Methode verwendet vier Parameter des Typs <xref:System.Byte>.  Der erste Parameter gibt den Alphakanal der ersten Farbe an, während die drei anderen Parameter die Rot\-, Grün\- und Blauwerte der Farbe angeben.  Jeder Wert sollte zwischen 0 und einschließlich 255 liegen.  Der Alphawert 0 gibt an, dass eine Farbe vollständig transparent ist, während bei einem Alphawert  von 255 die Farbe vollständig deckend ist.  Im folgenden Beispiel werden mithilfe der <xref:System.Windows.Media.Color.FromArgb%2A>\-Methode zwei Farben erzeugt.  Die erste Farbe ist teilweise transparent \(sie hat einen Alphawert von 32\), während die zweite Farbe vollständig deckend ist.  
  
 [!code-csharp[GradientBrushExamples_snip#TransparentGradientStopExample1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/GradientStopsExample.cs#transparentgradientstopexample1csharp)]  
  
 Alternativ können Sie die <xref:System.Windows.Media.Color.FromScRgb%2A>\-Methode verwenden, bei der Sie mithilfe von ScRGB\-Werten eine Farbe erzeugen.  
  
<a name="otherbrushes"></a>   
## Zeichnen mit Bildern, Zeichnungen, grafischen Elementen und Mustern  
 Die Klassen <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush> und <xref:System.Windows.Media.VisualBrush> ermöglichen es Ihnen, einen Bereich mit Bildern, Zeichnungen oder grafischen Elementen zu zeichnen.  Informationen über das Zeichnen mit Bildern, Zeichnungen und Mustern finden Sie unter [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
## Siehe auch  
 <xref:System.Windows.Media.Brush>   
 <xref:System.Windows.Media.SolidColorBrush>   
 <xref:System.Windows.Media.LinearGradientBrush>   
 <xref:System.Windows.Media.RadialGradientBrush>   
 [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)   
 [Übersicht über Pinseltransformationen](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md)   
 [Renderingebenen für Grafiken](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md)