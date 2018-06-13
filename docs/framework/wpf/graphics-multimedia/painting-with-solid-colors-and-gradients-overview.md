---
title: Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen
ms.date: 03/30/2017
helpviewer_keywords:
- solid colors [WPF], painting with
- painting with gradients [WPF]
- gradients [WPF], painting with
- brushes [WPF], painting with solid colors
- brushes [WPF], painting with gradients
- painting with solid colors [WPF]
ms.assetid: f5b182f3-c5c7-4cbe-9f2f-65e690d08255
ms.openlocfilehash: cea4b2dbd17178a6943b0f4a84182e65232330fb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566781"
---
# <a name="painting-with-solid-colors-and-gradients-overview"></a>Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen
Dieses Thema beschreibt, wie <xref:System.Windows.Media.SolidColorBrush>, <xref:System.Windows.Media.LinearGradientBrush>, und <xref:System.Windows.Media.RadialGradientBrush> Objekte mit Volltonfarben, linearer Farbverläufe und radialen Farbverläufen gezeichnet.  
  

  
<a name="solidcolor"></a>   
## <a name="painting-an-area-with-a-solid-color"></a>Zeichnen einen Bereich mit einer Volltonfarbe  
 Eine der am häufigsten verwendeten Vorgänge auf allen Plattformen ist einen Bereich mit einer einfarbigen gezeichnet <xref:System.Windows.Media.Color>. Zur Ausführung dieser Aufgabe [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet die <xref:System.Windows.Media.SolidColorBrush> Klasse. Die folgenden Abschnitte beschreiben die verschiedenen Methoden zum Zeichnen einer <xref:System.Windows.Media.SolidColorBrush>.  
  
<a name="solidcolorinxaml"></a>   
### <a name="using-a-solidcolorbrush-in-xaml"></a>Verwenden eines SolidColorBrush in „XAML“  
 Zum Zeichnen eines Bereichs mit einer Volltonfarbe in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], verwenden Sie eine der folgenden Optionen.  
  
-   Wählen Sie einen vordefinierten Volltonfarbenpinsel über den Namen aus.  Sie können z. B. einer Schaltfläche festlegen <xref:System.Windows.Controls.Control.Background%2A> "Red" oder "MediumBlue".  Eine Liste anderer volltonfarbpinsel vordefiniert, finden Sie unter die statischen Eigenschaften der der <xref:System.Windows.Media.Brushes> Klasse. Nachfolgend finden Sie ein Beispiel:  
  
     [!code-xaml[BrushOverviewExamples_snip#SolidColorBrushNamedColor1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/SolidColorBrushExample.xaml#solidcolorbrushnamedcolor1xaml)]  
  
-   Wählen Sie eine Farbe aus der 32-Bit-Farbpalette aus, indem Sie die Anteile von Rot, Grün und Blau festlegen, aus denen sich eine Volltonfarbe zusammensetzt.  Das Format zum Festlegen einer Farbe aus der 32-Bit-Palette ist „*#rrggbb*“, wobei mit dem zweistelligen Hexadezimalwert *rr* der relative Anteil von Rot, mit *gg* der Anteil von Grün und *bb* der Anteil von Blau festgelegt wird.  Darüber hinaus kann die Farbe im Format „#*Aarrggbb*“ angegeben werden, wobei *aa* für den *Alpha*wert, also die Transparenz der Farbe, steht. Dieser Ansatz ermöglicht Ihnen die Erstellung von Farben, die teilweise transparent sind.  Im folgenden Beispiel die <xref:System.Windows.Controls.Control.Background%2A> von einem <xref:System.Windows.Controls.Button> auf vollständig deckendes Rot hexadezimaler Schreibweise festgelegt ist.  
  
     [!code-xaml[BrushOverviewExamples_snip#SolidColorBrushHex1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/SolidColorBrushExample.xaml#solidcolorbrushhex1xaml)]  
  
-   Eigenschaftensyntax verwenden, um beschreiben eine <xref:System.Windows.Media.SolidColorBrush>. Diese Syntax ist ausführlicher, jedoch können Sie zusätzliche Einstellungen, z.B. die Deckkraft des Pinsels, angeben. Im folgenden Beispiel die <xref:System.Windows.Controls.Control.Background%2A> Eigenschaften von zwei <xref:System.Windows.Controls.Button> Elemente auf vollständig deckendes Rot festgelegt werden. Die Farbe des ersten Pinsels wird mit einem vordefinierten Farbnamen beschrieben. Die Farbe des zweiten Pinsels wird mithilfe der Hexadezimalschreibweise beschrieben.  
  
     [!code-xaml[BrushOverviewExamples_snip#SolidColorBrushPropertyTag1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/SolidColorBrushExample.xaml#solidcolorbrushpropertytag1xaml)]  
  
<a name="solidcolorsincode"></a>   
### <a name="painting-with-a-solidcolorbrush-in-code"></a>Zeichnen mit einem SolidColorBrush in Code  
 Zum Zeichnen eines Bereichs mit einer Volltonfarbe in Code, verwenden Sie eine der folgenden Optionen.  
  
-   Verwenden Sie eine der vordefinierten Pinsel bereitgestellt, die durch die <xref:System.Windows.Media.Brushes> Klasse. Im folgenden Beispiel die <xref:System.Windows.Controls.Control.Background%2A> von einem <xref:System.Windows.Controls.Button> festgelegt ist, um <xref:System.Windows.Media.Brushes.Red%2A>.  
  
     [!code-csharp[BrushOverviewExamples_snip#SolidColorBrushPredefinedBrush1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushpredefinedbrush1csharp)]  
  
-   Erstellen einer <xref:System.Windows.Media.SolidColorBrush> und legen Sie seine <xref:System.Windows.Media.SolidColorBrush.Color%2A> Eigenschaft mit einem <xref:System.Windows.Media.Color> Struktur. Können Sie eine vordefinierte Farben aus der <xref:System.Windows.Media.Colors> erstellen Klasse oder eine <xref:System.Windows.Media.Color> mithilfe der statischen <xref:System.Windows.Media.Color.FromArgb%2A> Methode.  
  
     Das folgende Beispiel zeigt, wie Sie festlegen der <xref:System.Windows.Media.SolidColorBrush.Color%2A> Eigenschaft eine <xref:System.Windows.Media.SolidColorBrush> mit einer vordefinierten Farbe.  
  
     [!code-csharp[BrushOverviewExamples_snip#SolidColorBrushPredefinedColor1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushpredefinedcolor1csharp)]  
  
 Die statische <xref:System.Windows.Media.Color.FromArgb%2A> ermöglicht Ihnen das Festlegen der Farbe Alpha-, Rot-, Grün- und Blau-Werte. Der normale Bereich für jeden der folgenden Werte ist 0 bis 255. Beispielsweise gibt der Alphawert 0 an, dass eine Farbe völlig transparent, während der Wert 255 angibt, dass sie vollständig deckend ist. Entsprechend gibt der Wert 0 für die Farbe Rot an, dass eine Farbe keinen Rotanteil hat, während der Wert 255 angibt, dass eine Farbe den maximalen Rotanteil aufweist.  Im folgenden Beispiel wird die Farbe eines Pinsels beschrieben, indem rote, grüne und blaue Alphawert angegeben werden.  
  
 [!code-csharp[BrushOverviewExamples_snip#SolidColorBrushfromArgbExample1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushfromargbexample1csharp)]  
  
 Weitere Möglichkeiten zum Farbe angeben, finden Sie unter der <xref:System.Windows.Media.Color> Referenzthema.  
  
<a name="gradient"></a>   
## <a name="painting-an-area-with-a-gradient"></a>Zeichnen eines Bereichs mit einem Farbverlauf  
 Ein Farbverlaufspinsel zeichnet einen Bereich mit mehreren Farben, die sich auf einer Achse miteinander vermischen. Sie können Farbverlaufspinsel verwenden, um Eindrücke von Licht und Schatten zu erzeugen und den Steuerelementen ein dreidimensionales Aussehen zu verleihen. Sie können Sie auch verwenden, um Glas, Chrom, Wasser und andere glatte Oberflächen zu simulieren.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet zwei Arten von Farbverlaufspinsel: <xref:System.Windows.Media.LinearGradientBrush> und <xref:System.Windows.Media.RadialGradientBrush>.  
  
<a name="lineargradientbrush"></a>   
## <a name="linear-gradients"></a>Lineare Farbverläufe  
 Ein <xref:System.Windows.Media.LinearGradientBrush> zeichnet einen Bereich mit einem Farbverlauf entlang einer Linie definiert die *Farbverlaufachse*.  Sie geben die Farben des Farbverlaufs und ihre Position entlang der Farbverlaufsachse mithilfe <xref:System.Windows.Media.GradientStop> Objekte.  Sie können auch die Farbverlaufsachse ändern. Dies ermöglicht Ihnen, horizontale und vertikale Farbverläufe zu erstellen und die Richtung des Farbverlaufs umzukehren. Die Farbverlaufsachse wird im nächsten Abschnitt beschrieben. Standardmäßig wird ein diagonaler Farbverlauf erstellt.  
  
 Das folgende Beispiel zeigt den Code, der einen linearen Farbverlauf mit vier Farben erstellt.  
  
 [!code-xaml[GradientBrushExamples_snip#DiagonalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 Dieser Code erzeugt den folgenden Farbverlauf:  
  
 ![Ein diagonaler, linearer Farbverlauf](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-diaglgradient-nolabel.jpg "Wcpsdk_graphicsmm_diaglgradient_nolabel")  
  
 **Hinweis:** Die Beispiele für Farbverläufe in diesem Thema verwenden das Standardkoordinatensystem zum Festlegen der Start- und Endpunkten. Das Standardkoordinatensystem ist relativ zu einem umgebenden Feld: 0 gibt 0 Prozent des umgebenden Felds und 1 gibt 100 Prozent des umgebenden Felds an. Sie können dieses Koordinatensystems ändern, durch Festlegen der <xref:System.Windows.Media.GradientBrush.MappingMode%2A> -Eigenschaft auf den Wert <xref:System.Windows.Media.BrushMappingMode.Absolute>. Ein absolutes Koordinatensystem ist nicht relativ zu einem umgebenden Feld. Werte werden direkt im lokalen Raum interpretiert.  
  
 Die <xref:System.Windows.Media.GradientStop> ist der grundlegende Baustein eines Farbverlaufspinsels.  Ein Farbverlaufsstopps gibt eine <xref:System.Windows.Media.GradientStop.Color%2A> an eine <xref:System.Windows.Media.GradientStop.Offset%2A> entlang der Farbverlaufsachse.  
  
-   Die Farbverlaufsstopps <xref:System.Windows.Media.GradientStop.Color%2A> Eigenschaft gibt die Farbe des Farbverlaufsstopps. Sie können die Farbe mit einer vordefinierten Farbe festlegen (gebotenen der <xref:System.Windows.Media.Colors> Klasse) oder indem Sie ScRGB oder ARGB-Werte angeben. In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] können Sie auch die Hexadezimalschreibweise verwenden, um eine Farbe zu beschreiben. Weitere Informationen finden Sie unter der <xref:System.Windows.Media.Color> Struktur.  
  
-   Die Farbverlaufsstopps <xref:System.Windows.Media.GradientStop.Offset%2A> Eigenschaft gibt die Position der Farbe des Farbverlaufsstopps auf der Farbverlaufsachse. Der Offset ist ein <xref:System.Double> , die reicht von 0 bis 1. Je näher ist Offsetwert des Farbverlaufsstopps bei 0 liegt, desto näher befindet sich die Farbe am Beginn des Farbverlaufs. Je näher ist Offsetwert des Farbverlaufsstopps bei 1 liegt, desto näher befindet sich die Farbe am Ende des Farbverlaufs.  
  
 Die Farbe jedes Punkts zwischen Farbverlaufsstopps wird als eine Kombination der Farben, die durch die zwei umschließenden Farbverlaufsstopps angegeben werden, linear interpoliert. Die folgende Abbildung zeigt die im vorherigen Beispiel erstellten Farbverlaufsstopps. Die Kreise markieren die Position der Farbverlaufsstopps, und eine gestrichelte Linie zeigt die Farbverlaufsachse an.  
  
 ![Farbverlaufstopps in einem linearen Farbverlauf](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-4gradientstops.png "Wcpsdk_graphicsmm_4gradientstops")  
  
 Der erste Farbverlaufsstopp gibt die Farbe Gelb bei einem Offset von `0.0` an.  Der zweite Farbverlaufsstopp gibt die Farbe Rot bei einem Offset von `0.25` an.  Die Farbe der Punkte zwischen diesen zwei Stopps ändert sich allmählich von Gelb zu Rot, wenn Sie sich von links nach rechts auf der Farbverlaufsachse bewegen.  Der dritte Farbverlaufsstopp gibt die Farbe Blau bei einem Offset von `0.75` an.  Die Farbe der Punkte zwischen dem zweiten und dritten Farbverlaufsstopp ändert sich allmählich von Rot zu Blau. Der vierte Farbverlaufsstopp gibt die Farbe Gelbgrün bei einem Offset von `1.0` an. Die Farbe der Punkte zwischen dem dritten und vierten Farbverlaufsstopp ändert sich allmählich von Blau zu Gelbgrün.  
  
<a name="gradientaxis"></a>   
### <a name="the-gradient-axis"></a>Die Farbverlaufsachse  
 Wie bereits erwähnt, befinden sich die Farbverlaufsstopps eines Pinsel mit linearem Farbverlauf auf einer Linie, der Farbverlaufsachse. Sie können ändern, die Ausrichtung und die Größe der Zeile mit dem Pinsel <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> und <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> Eigenschaften. Durch Bearbeiten des Pinsels <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> und <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A>können erstellen Sie horizontale und vertikale Farbverläufe Farbverlauf Richtung umkehren, reduzieren die gradient Weiterverbreitung und vieles mehr.  
  
 Wird standardmäßig der linearen Farbverlaufspinsel des <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> und <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> sind relativ zum Bereich gezeichnet wird. Der Punkt (0,0) stellt die obere linke Ecke und der Punkt (1,1) die untere rechte Ecke des Bereichs dar, der gezeichnet wird. Die Standardeinstellung <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> von einer <xref:System.Windows.Media.LinearGradientBrush> ist (0,0) und den Standardwert <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> ist (1,1), erstellt einen diagonalen Farbverlauf in der oberen linken Ecke auf der unteren rechten Ecke der Bereich gezeichnet wird. Die folgende Abbildung zeigt die Farbverlaufsachse des mit einem linearen Farbverlaufspinsel <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> und <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A>.  
  
 ![Farbverlaufsachse für einen diagonalen linearen Farbverlauf](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-diagonalgradientaxis.png "Wcpsdk_graphicsmm_diagonalgradientaxis")  
  
 Im folgende Beispiel wird gezeigt, wie zum Erstellen einer horizontalen Farbverlauf durch Angabe des Pinsels <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> und <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A>. Beachten Sie, dass die Farbverlaufsstopps wie im vorherigen Beispiel identisch sind; indem Sie einfach ändern die <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> und <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A>, wurde der Farbverlauf von Diagonal zu Horizontal geändert.  
  
 [!code-xaml[GradientBrushExamples_snip#HorizontalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 Die folgende Abbildung zeigt den erstellten Farbverlauf. Die Farbverlaufsachse wird mit einer gestrichelten Linie, und die Farbverlaufsstopps mit Kreisen gekennzeichnet.  
  
 ![Farbverlaufsachse für einen horizontalen linearen Farbverlauf](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-horizontalgradient.jpg "Wcpsdk_graphicsmm_horizontalgradient")  
  
 Das nächste Beispiel veranschaulicht die Erstellung eines vertikalen Farbverlaufs.  
  
 [!code-xaml[GradientBrushExamples_snip#VerticalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 Die folgende Abbildung zeigt den erstellten Farbverlauf. Die Farbverlaufsachse wird mit einer gestrichelten Linie, und die Farbverlaufsstopps mit Kreisen gekennzeichnet.  
  
 ![Farbverlaufsachse für einen vertikalen Farbverlauf](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-verticalgradient.jpg "Wcpsdk_graphicsmm_verticalgradient")  
  
<a name="radialgradients"></a>   
## <a name="radial-gradients"></a>Strahlenförmige Farbverläufe  
 Wie eine <xref:System.Windows.Media.LinearGradientBrush>ein <xref:System.Windows.Media.RadialGradientBrush> zeichnet einen Bereich mit Farben, die auf einer Achse ineinander. In den vorherigen Beispielen wurde gezeigt, dass die Achse eines Pinsels mit linearem Farbverlauf eine gerade Linie ist. Die Achse eines Pinsels mit strahlenförmigem Farbverlauf wird durch einen Kreis definiert. Seine Farben „strahlen“ von seinem Ursprung nach außen.  
  
 Im folgenden Beispiel wird ein Pinsel mit strahlenförmigem Farbverlauf verwendet, um das Innere eines Rechtecks zu zeichnen.  
  
 [!code-xaml[GradientBrushExamples_snip#RadialGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/RadialGradientBrushExample.xaml#radialgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#RadialGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/RadialGradientBrushExample.cs#radialgradient1csharp)]  
  
 Die folgende Abbildung zeigt den im vorherigen Beispiel erstellten Farbverlauf. Die Farbverlaufsstopps des Pinsels wurden hervorgehoben. Beachten Sie, dass trotz der unterschiedlichen Ergebnisse die Farbverlaufsstopps in diesem Beispiel identisch mit den Farbverlaufsstopps in den vorherigen Beispielen mit linearem Farbverlauf sind.  
  
 ![Farbverlaufstopps in einem radialen Farbverlauf](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-4gradientstops-rg.png "Wcpsdk_graphicsmm_4gradientstops_rg")  
  
 Die <xref:System.Windows.Media.RadialGradientBrush.GradientOrigin%2A> gibt den Ausgangspunkt einer radialen Farbverlauf Farbverlaufsachse des Pinsels angeben. Die Farbverlaufsachse strahlt vom Farbverlaufsursprung zum Farbverlaufskreis aus. Farbverlauf Kreis des Pinsels wird definiert, indem seine <xref:System.Windows.Media.RadialGradientBrush.Center%2A>, <xref:System.Windows.Media.RadialGradientBrush.RadiusX%2A>, und <xref:System.Windows.Media.RadialGradientBrush.RadiusY%2A> Eigenschaften.  
  
 Die folgende Abbildung zeigt mehrere radiale Farbverläufe mit unterschiedlichen <xref:System.Windows.Media.RadialGradientBrush.GradientOrigin%2A>, <xref:System.Windows.Media.RadialGradientBrush.Center%2A>, <xref:System.Windows.Media.RadialGradientBrush.RadiusX%2A>, und <xref:System.Windows.Media.RadialGradientBrush.RadiusY%2A> Einstellungen.  
  
 ![RadialGradientBrush-Einstellungen](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-originscirclesandradii.gif "Wcpsdk_graphicsmm_originscirclesandradii")  
RadialGradientBrushes mit unterschiedlichen GradientOrigin-, Center-, RadiusX- und RadiusY-Einstellungen.  
  
<a name="specifyinggradientcolors"></a>   
## <a name="specifying-transparent-or-partially-transparent-gradient-stops"></a>Angeben transparenter oder teilweise transparenter Farbverlaufsstopps  
 Da Farbverlaufsstopps Opacity-Eigenschaft nicht angeben, müssen Sie angeben, den alpha-Kanal mit [!INCLUDE[TLA#tla_argb](../../../../includes/tlasharptla-argb-md.md)] Hexadezimalnotation im Markup oder die Verwendung der <xref:System.Windows.Media.Color.FromScRgb%2A?displayProperty=nameWithType> Methode, um Farbverlaufsstopps zu erstellen, die transparent oder teilweise transparent sind. In den folgenden Abschnitten wird erläutert, wie teilweise transparente Farbverlaufsstopps in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und Code erstellt werden.  
  
<a name="argbsyntax"></a>   
### <a name="specifying-color-opacity-in-xaml"></a>Angeben der Deckkraft einer Farbe in „XAML“  
 In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] wird die [!INCLUDE[TLA2#tla_argb](../../../../includes/tla2sharptla-argb-md.md)]-Hexadezimalschreibweise verwendet, um die Deckkraft einzelner Farben anzugeben. Die [!INCLUDE[TLA2#tla_argb](../../../../includes/tla2sharptla-argb-md.md)]-Hexadezimalschreibweise verwendet die folgende Syntax:  
  
 `#` **aa** *rrggbb*  
  
 *aa* in der vorherigen Zeile stellt einen zweistelligen Hexadezimalwert dar, der verwendet wird, um die Deckkraft der Farbe anzugeben. *rr*, *gg* und *bb* repräsentieren jeweils einen zweistelligen Hexadezimalwert, der die Anteile von Rot, Grün und Blau einer Farbe angibt. Jede Hexadezimalziffer kann einen Wert von 0-9 bzw. A-F haben. 0 ist der kleinste und F der größte Wert. Der Alphawert 00 gibt eine Farbe an, die vollständig transparent ist, während ein Alphawert FF eine vollständig deckende Farbe erstellt.  Im folgenden Beispiel wird die [!INCLUDE[TLA2#tla_argb](../../../../includes/tla2sharptla-argb-md.md)]-Hexadezimalschreibweise verwendet, um zwei Farben anzugeben. Die erste ist teilweise transparent (sie hat einen Alphawert von X20), während die zweite vollständig deckend ist.  
  
 [!code-xaml[GradientBrushExamples_snip#TransparentGradientStopExample1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/GradientStopsExample.xaml#transparentgradientstopexample1xaml)]  
  
<a name="fromscrgbsyntax"></a>   
### <a name="specifying-color-opacity-in-code"></a>Angeben der Deckkraft einer Farbe in Code  
 Bei Verwendung von Code, der statischen <xref:System.Windows.Media.Color.FromArgb%2A> Methode ermöglicht es Ihnen, einen alpha Wert angeben, wenn Sie eine Farbe zu erstellen. Die Methode nimmt vier Parameter vom Typ <xref:System.Byte>. Der erste Parameter gibt den Alphakanal der Farbe an. Die anderen drei Parameter geben die Rot-, Grün- und Blauwerte der Farbe an. Jeder Wert sollte zwischen einschließlich 0 und 255 liegen. Beispielsweise gibt der Alphawert 0 an, dass eine Farbe völlig transparent ist, während der Wert 255 angibt, dass sie vollständig deckend ist. Im folgenden Beispiel die <xref:System.Windows.Media.Color.FromArgb%2A> Methode wird verwendet, um zwei Farben zu erzeugen. Die erste ist teilweise transparent (sie hat einen Alphawert von 32), während die zweite vollständig deckend ist.  
  
 [!code-csharp[GradientBrushExamples_snip#TransparentGradientStopExample1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/GradientStopsExample.cs#transparentgradientstopexample1csharp)]  
  
 Alternativ können Sie verwenden die <xref:System.Windows.Media.Color.FromScRgb%2A> -Methode, die Ihnen ermöglicht, ScRGB Werte verwenden, um eine Farbe zu erstellen.  
  
<a name="otherbrushes"></a>   
## <a name="painting-with-images-drawings-visuals-and-patterns"></a>Zeichnen mit Bildern, Zeichnungen, visuellen Elementen und Mustern  
 <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, und <xref:System.Windows.Media.VisualBrush> Klassen ermöglichen es Ihnen, einen Bereich mit Bildern, Zeichnungen oder visuellen Elementen gezeichnet. Informationen über Zeichnen mit Bildern, Zeichnungen und Mustern finden Sie unter [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.Brush>  
 <xref:System.Windows.Media.SolidColorBrush>  
 <xref:System.Windows.Media.LinearGradientBrush>  
 <xref:System.Windows.Media.RadialGradientBrush>  
 [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [Übersicht über Pinseltransformationen](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md)  
 [Renderingebenen für Grafiken](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md)
