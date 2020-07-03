---
title: Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen
description: Erfahren Sie, wie Sie-Objekte verwenden, um mit voll Tonfarben, linearen Farbverläufen und radialen Farbverläufen in Windows Presentation Foundation (WPF) zu zeichnen.
ms.date: 03/30/2017
helpviewer_keywords:
- solid colors [WPF], painting with
- painting with gradients [WPF]
- gradients [WPF], painting with
- brushes [WPF], painting with solid colors
- brushes [WPF], painting with gradients
- painting with solid colors [WPF]
ms.assetid: f5b182f3-c5c7-4cbe-9f2f-65e690d08255
ms.openlocfilehash: 957593d758afda06db106c99f6695294d4f84f73
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853671"
---
# <a name="painting-with-solid-colors-and-gradients-overview"></a>Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen

In diesem Thema wird beschrieben, wie Sie <xref:System.Windows.Media.SolidColorBrush> <xref:System.Windows.Media.LinearGradientBrush> mit-,-und- <xref:System.Windows.Media.RadialGradientBrush> Objekten mit voll Tonfarben, linearen Farbverläufen und radialen Farbverläufen zeichnen können.

<a name="solidcolor"></a>

## <a name="painting-an-area-with-a-solid-color"></a>Zeichnen einen Bereich mit einer Volltonfarbe

Einer der gängigsten Vorgänge auf einer beliebigen Plattform ist das Zeichnen eines Bereichs mit einem soliden <xref:System.Windows.Media.Color> . Zum Ausführen dieser Aufgabe [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stellt die- <xref:System.Windows.Media.SolidColorBrush> Klasse bereit. In den folgenden Abschnitten werden die verschiedenen Methoden zum Zeichnen mit einem beschrieben <xref:System.Windows.Media.SolidColorBrush> .

<a name="solidcolorinxaml"></a>

### <a name="using-a-solidcolorbrush-in-xaml"></a>Verwenden eines SolidColorBrush in „XAML“

Zum Zeichnen eines Bereichs mit einer Volltonfarbe in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], verwenden Sie eine der folgenden Optionen.

- Wählen Sie einen vordefinierten Volltonfarbenpinsel über den Namen aus.  Beispielsweise können Sie eine Schaltfläche <xref:System.Windows.Controls.Control.Background%2A> auf "Red" oder "MediumBlue" festlegen.  Eine Liste mit anderen vordefinierten Pinsel Farben finden Sie in den statischen Eigenschaften der- <xref:System.Windows.Media.Brushes> Klasse. Im Folgenden finden Sie ein Beispiel.

  [!code-xaml[BrushOverviewExamples_snip#SolidColorBrushNamedColor1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/SolidColorBrushExample.xaml#solidcolorbrushnamedcolor1xaml)]

- Wählen Sie eine Farbe aus der 32-Bit-Farbpalette aus, indem Sie die Anteile von Rot, Grün und Blau festlegen, aus denen sich eine Volltonfarbe zusammensetzt.  Das Format zum Festlegen einer Farbe aus der 32-Bit-Palette ist „*#rrggbb*“, wobei mit dem zweistelligen Hexadezimalwert *rr* der relative Anteil von Rot, mit *gg* der Anteil von Grün und *bb* der Anteil von Blau festgelegt wird.  Darüber hinaus kann die Farbe im Format „#*Aarrggbb*“ angegeben werden, wobei *aa* für den *Alpha*wert, also die Transparenz der Farbe, steht. Dieser Ansatz ermöglicht Ihnen die Erstellung von Farben, die teilweise transparent sind.  Im folgenden Beispiel <xref:System.Windows.Controls.Control.Background%2A> wird der eines <xref:System.Windows.Controls.Button> mit hexadezimal Schreibweise auf vollständig deckendes Rot festgelegt.

  [!code-xaml[BrushOverviewExamples_snip#SolidColorBrushHex1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/SolidColorBrushExample.xaml#solidcolorbrushhex1xaml)]

- Verwenden Sie die Eigenschaft Tagsyntax, um eine zu beschreiben <xref:System.Windows.Media.SolidColorBrush> . Diese Syntax ist ausführlicher, jedoch können Sie zusätzliche Einstellungen, z.B. die Deckkraft des Pinsels, angeben. Im folgenden Beispiel <xref:System.Windows.Controls.Control.Background%2A> werden die Eigenschaften von zwei- <xref:System.Windows.Controls.Button> Elementen auf vollständig deckendes Rot festgelegt. Die Farbe des ersten Pinsels wird mit einem vordefinierten Farbnamen beschrieben. Die Farbe des zweiten Pinsels wird mithilfe der Hexadezimalschreibweise beschrieben.

  [!code-xaml[BrushOverviewExamples_snip#SolidColorBrushPropertyTag1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/SolidColorBrushExample.xaml#solidcolorbrushpropertytag1xaml)]

<a name="solidcolorsincode"></a>

### <a name="painting-with-a-solidcolorbrush-in-code"></a>Zeichnen mit einem SolidColorBrush in Code

Zum Zeichnen eines Bereichs mit einer Volltonfarbe in Code, verwenden Sie eine der folgenden Optionen.

- Verwenden Sie eines der vordefinierten Pinsel, die von der-Klasse bereitgestellt werden <xref:System.Windows.Media.Brushes> . Im folgenden Beispiel <xref:System.Windows.Controls.Control.Background%2A> wird der eines <xref:System.Windows.Controls.Button> auf festgelegt <xref:System.Windows.Media.Brushes.Red%2A> .

  [!code-csharp[BrushOverviewExamples_snip#SolidColorBrushPredefinedBrush1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushpredefinedbrush1csharp)]

- Erstellen Sie einen, <xref:System.Windows.Media.SolidColorBrush> und legen Sie seine- <xref:System.Windows.Media.SolidColorBrush.Color%2A> Eigenschaft mithilfe einer- <xref:System.Windows.Media.Color> Struktur fest Sie können eine vordefinierte Farbe aus der-Klasse verwenden, <xref:System.Windows.Media.Colors> oder Sie können <xref:System.Windows.Media.Color> mithilfe der statischen-Methode ein erstellen <xref:System.Windows.Media.Color.FromArgb%2A> .

  Im folgenden Beispiel wird gezeigt, wie die- <xref:System.Windows.Media.SolidColorBrush.Color%2A> Eigenschaft eines <xref:System.Windows.Media.SolidColorBrush> mit einer vordefinierten Farbe festgelegt wird.

  [!code-csharp[BrushOverviewExamples_snip#SolidColorBrushPredefinedColor1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushpredefinedcolor1csharp)]

Mit dem statischen <xref:System.Windows.Media.Color.FromArgb%2A> können Sie die Werte Alpha, rot, grün und blau der Farbe angeben. Der normale Bereich für jeden der folgenden Werte ist 0 bis 255. Beispielsweise gibt der Alphawert 0 an, dass eine Farbe völlig transparent, während der Wert 255 angibt, dass sie vollständig deckend ist. Entsprechend gibt der Wert 0 für die Farbe Rot an, dass eine Farbe keinen Rotanteil hat, während der Wert 255 angibt, dass eine Farbe den maximalen Rotanteil aufweist.  Im folgenden Beispiel wird die Farbe eines Pinsels beschrieben, indem rote, grüne und blaue Alphawert angegeben werden.

[!code-csharp[BrushOverviewExamples_snip#SolidColorBrushfromArgbExample1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushfromargbexample1csharp)]

Weitere Methoden zum Angeben von Farben finden Sie im <xref:System.Windows.Media.Color> Referenz Thema.

<a name="gradient"></a>

## <a name="painting-an-area-with-a-gradient"></a>Zeichnen eines Bereichs mit einem Farbverlauf

Ein Farbverlaufspinsel zeichnet einen Bereich mit mehreren Farben, die sich auf einer Achse miteinander vermischen. Sie können Farbverlaufspinsel verwenden, um Eindrücke von Licht und Schatten zu erzeugen und den Steuerelementen ein dreidimensionales Aussehen zu verleihen. Sie können Sie auch verwenden, um Glas, Chrom, Wasser und andere glatte Oberflächen zu simulieren.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]stellt zwei Typen von Farbverlaufs Pinsel bereit: <xref:System.Windows.Media.LinearGradientBrush> und <xref:System.Windows.Media.RadialGradientBrush> .

<a name="lineargradientbrush"></a>

## <a name="linear-gradients"></a>Lineare Farbverläufe

Ein <xref:System.Windows.Media.LinearGradientBrush> zeichnet einen Bereich mit einem Farbverlauf, der entlang einer Linie definiert ist, der *Farbverlaufs Achse*.  Mithilfe von-Objekten geben Sie die Farben des Farbverlaufs und deren Position entlang der Farbverlaufs Achse an <xref:System.Windows.Media.GradientStop> .  Sie können auch die Farbverlaufsachse ändern. Dies ermöglicht Ihnen, horizontale und vertikale Farbverläufe zu erstellen und die Richtung des Farbverlaufs umzukehren. Die Farbverlaufsachse wird im nächsten Abschnitt beschrieben. Standardmäßig wird ein diagonaler Farbverlauf erstellt.

Das folgende Beispiel zeigt den Code, der einen linearen Farbverlauf mit vier Farben erstellt.

[!code-xaml[GradientBrushExamples_snip#DiagonalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]

[!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]

Dieser Code erzeugt den folgenden Farbverlauf:

![Ein diagonaler, linearer Farbverlauf](./media/wcpsdk-graphicsmm-diaglgradient-nolabel.jpg "wcpsdk_graphicsmm_diaglgradient_nolabel")

> [!NOTE]
> Die Farbverlaufs Beispiele in diesem Thema verwenden das Standard Koordinatensystem zum Festlegen von Startpunkten und Endpunkten. Das Standardkoordinatensystem ist relativ zu einem umgebenden Feld: 0 gibt 0 Prozent des umgebenden Felds und 1 gibt 100 Prozent des umgebenden Felds an. Sie können dieses Koordinatensystem ändern, indem Sie die- <xref:System.Windows.Media.GradientBrush.MappingMode%2A> Eigenschaft auf den Wert festlegen <xref:System.Windows.Media.BrushMappingMode.Absolute> . Ein absolutes Koordinatensystem ist nicht relativ zu einem umgebenden Feld. Werte werden direkt im lokalen Raum interpretiert.

Der <xref:System.Windows.Media.GradientStop> ist der Grundbaustein eines Farbverlaufs Pinsels.  Ein Farbverlaufs Ende gibt ein <xref:System.Windows.Media.GradientStop.Color%2A> an einem <xref:System.Windows.Media.GradientStop.Offset%2A> entlang der Farbverlaufs Achse an.

- Die-Eigenschaft des Farbverlaufs Stopps <xref:System.Windows.Media.GradientStop.Color%2A> gibt die Farbe des Farbverlaufs Stopps an. Sie können die Farbe festlegen, indem Sie eine vordefinierte Farbe (die von der-Klasse bereitgestellt wird <xref:System.Windows.Media.Colors> ) verwenden oder ScRGB-oder ARGB-Werte angeben. In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] können Sie auch die Hexadezimalschreibweise verwenden, um eine Farbe zu beschreiben. Weitere Informationen finden Sie in der- <xref:System.Windows.Media.Color> Struktur.

- Die-Eigenschaft des Farbverlaufs Stopps <xref:System.Windows.Media.GradientStop.Offset%2A> gibt die Position der Farbe des Farbverlaufs Stopps auf der Farbverlaufs Achse an. Der Offset liegt <xref:System.Double> zwischen 0 und 1. Je näher ist Offsetwert des Farbverlaufsstopps bei 0 liegt, desto näher befindet sich die Farbe am Beginn des Farbverlaufs. Je näher ist Offsetwert des Farbverlaufsstopps bei 1 liegt, desto näher befindet sich die Farbe am Ende des Farbverlaufs.

Die Farbe der einzelnen Punkte zwischen den Farbverlaufsstopps wird linear als eine Kombination der von den beiden umgebenden Farbverlaufsstopps angegebenen Farben interpoliert. Die folgende Abbildung zeigt die im vorherigen Beispiel erstellten Farbverlaufsstopps. Die Kreise markieren die Position der Farbverlaufsstopps, und eine gestrichelte Linie zeigt die Farbverlaufsachse an.

![Farbverlaufstopps in einem linearen Farbverlauf](./media/wcpsdk-graphicsmm-4gradientstops.png "wcpsdk_graphicsmm_4gradientstops")

Der erste Farbverlaufsstopp gibt die Farbe Gelb bei einem Offset von `0.0` an.  Der zweite Farbverlaufsstopp gibt die Farbe Rot bei einem Offset von `0.25` an.  Die Farbe der Punkte zwischen diesen zwei Stopps ändert sich allmählich von Gelb zu Rot, wenn Sie sich von links nach rechts auf der Farbverlaufsachse bewegen.  Der dritte Farbverlaufsstopp gibt die Farbe Blau bei einem Offset von `0.75` an.  Die Farbe der Punkte zwischen dem zweiten und dritten Farbverlaufsstopp ändert sich allmählich von Rot zu Blau. Der vierte Farbverlaufsstopp gibt die Farbe Gelbgrün bei einem Offset von `1.0` an. Die Farbe der Punkte zwischen dem dritten und vierten Farbverlaufsstopp ändert sich allmählich von Blau zu Gelbgrün.

<a name="gradientaxis"></a>

### <a name="the-gradient-axis"></a>Die Farbverlaufsachse

Wie bereits erwähnt, befinden sich die Farbverlaufsstopps eines Pinsel mit linearem Farbverlauf auf einer Linie, der Farbverlaufsachse. Sie können die Ausrichtung und die Größe der Linie mithilfe der-und-Eigenschaften des Pinsels ändern <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> . Durch die Bearbeitung des Pinsels <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> und <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> können Sie horizontale und vertikale Farbverläufe erstellen, die Richtung des Farbverlaufs umkehren, die Verlaufs Verteilung und vieles mehr umkehren.

Standardmäßig sind die und der lineare Farbverlaufs Pinsel <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> relativ zum Bereich, der gezeichnet wird. Der Punkt (0,0) stellt die obere linke Ecke und der Punkt (1,1) die untere rechte Ecke des Bereichs dar, der gezeichnet wird. Der Standardwert <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> von <xref:System.Windows.Media.LinearGradientBrush> ist (0,0), und der Standardwert <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> ist (1,1). Dadurch wird ein diagonaler Farbverlauf erstellt, beginnend mit der linken oberen Ecke und der Erweiterung auf die untere rechte Ecke des gezeichneten Bereichs. Die folgende Abbildung zeigt die Farbverlaufs Achse eines linearen Farbverlaufs Pinsels mit der Standardeinstellung <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> und <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> .

![Farbverlaufachse für einen diagonalen linearen Farbverlauf](./media/wcpsdk-graphicsmm-diagonalgradientaxis.png "wcpsdk_graphicsmm_diagonalgradientaxis")

Im folgenden Beispiel wird gezeigt, wie ein horizontaler Farbverlauf erstellt wird, indem der Pinsel und angegeben werden <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> . Beachten Sie, dass die Farbverlaufs Stopps mit denen in den vorherigen Beispielen übereinstimmen. durch einfaches Ändern von <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> und wurde <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> der Farbverlauf von diagonal in horizontal geändert.

[!code-xaml[GradientBrushExamples_snip#HorizontalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]

[!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]

Die folgende Abbildung zeigt den erstellten Farbverlauf. Die Farbverlaufsachse wird mit einer gestrichelten Linie, und die Farbverlaufsstopps mit Kreisen gekennzeichnet.

![Farbverlaufachse für einen horizontalen linearen Farbverlauf](./media/wcpsdk-graphicsmm-horizontalgradient.jpg "wcpsdk_graphicsmm_horizontalgradient")

Das nächste Beispiel veranschaulicht die Erstellung eines vertikalen Farbverlaufs.

[!code-xaml[GradientBrushExamples_snip#VerticalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]

[!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]

Die folgende Abbildung zeigt den erstellten Farbverlauf. Die Farbverlaufsachse wird mit einer gestrichelten Linie, und die Farbverlaufsstopps mit Kreisen gekennzeichnet.

![Farbverlaufachse für einen vertikalen Farbverlauf](./media/wcpsdk-graphicsmm-verticalgradient.jpg "wcpsdk_graphicsmm_verticalgradient")

<a name="radialgradients"></a>

## <a name="radial-gradients"></a>Strahlenförmige Farbverläufe

Wie <xref:System.Windows.Media.LinearGradientBrush> <xref:System.Windows.Media.RadialGradientBrush> bei einem zeichnet ein Bereich mit Farben, die sich entlang einer Achse vermischen. In den vorherigen Beispielen wurde gezeigt, dass die Achse eines Pinsels mit linearem Farbverlauf eine gerade Linie ist. Die Achse eines Pinsels mit strahlenförmigem Farbverlauf wird durch einen Kreis definiert. Seine Farben „strahlen“ von seinem Ursprung nach außen.

Im folgenden Beispiel wird ein Pinsel mit strahlenförmigem Farbverlauf verwendet, um das Innere eines Rechtecks zu zeichnen.

[!code-xaml[GradientBrushExamples_snip#RadialGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/RadialGradientBrushExample.xaml#radialgradient1xaml)]

[!code-csharp[GradientBrushExamples_snip#RadialGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/RadialGradientBrushExample.cs#radialgradient1csharp)]

Die folgende Abbildung zeigt den im vorherigen Beispiel erstellten Farbverlauf. Die Farbverlaufsstopps des Pinsels wurden hervorgehoben. Beachten Sie, dass trotz der unterschiedlichen Ergebnisse die Farbverlaufsstopps in diesem Beispiel identisch mit den Farbverlaufsstopps in den vorherigen Beispielen mit linearem Farbverlauf sind.

![Farbverlaufstopps in einem radialen Farbverlauf](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")

Der <xref:System.Windows.Media.RadialGradientBrush.GradientOrigin%2A> gibt den Startpunkt der Farbverlaufs Achse eines radialen Farbverlaufs an. Die Farbverlaufsachse strahlt vom Farbverlaufsursprung zum Farbverlaufskreis aus. Der Farbverlaufs Kreis eines Pinsels wird durch seine- <xref:System.Windows.Media.RadialGradientBrush.Center%2A> , <xref:System.Windows.Media.RadialGradientBrush.RadiusX%2A> -und- <xref:System.Windows.Media.RadialGradientBrush.RadiusY%2A> Eigenschaften definiert.

Die folgende Abbildung zeigt mehrere radiale Farbverläufe mit unterschiedlichen <xref:System.Windows.Media.RadialGradientBrush.GradientOrigin%2A> Einstellungen für, <xref:System.Windows.Media.RadialGradientBrush.Center%2A> , <xref:System.Windows.Media.RadialGradientBrush.RadiusX%2A> und <xref:System.Windows.Media.RadialGradientBrush.RadiusY%2A> .

![RadialGradientBrush-Einstellungen](./media/wcpsdk-graphicsmm-originscirclesandradii.gif "wcpsdk_graphicsmm_originscirclesandradii") RadialGradientBrush mit unterschiedlichen GradientOrigin-, Center-, radiingx-und radiey-Einstellungen.

<a name="specifyinggradientcolors"></a>

## <a name="specifying-transparent-or-partially-transparent-gradient-stops"></a>Angeben transparenter oder teilweise transparenter Farbverlaufsstopps

Da Farbverlaufs Stopps keine Deckkraft Eigenschaft bereitstellen, müssen Sie den Alphakanal der Farben mithilfe der ARGB-hexadezimal Schreibweise in Markup angeben oder die- <xref:System.Windows.Media.Color.FromScRgb%2A?displayProperty=nameWithType> Methode verwenden, um Verlaufs Stopps zu erstellen, die transparent oder teilweise transparent sind. In den folgenden Abschnitten wird erläutert, wie teilweise transparente Farbverlaufsstopps in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und Code erstellt werden.

<a name="argbsyntax"></a>

### <a name="specifying-color-opacity-in-xaml"></a>Angeben der Deckkraft einer Farbe in „XAML“

In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] verwenden Sie die hexadezimale Notation ARGB, um die Deckkraft einzelner Farben anzugeben. Bei der ARGB-hexadezimal Notation wird die folgende Syntax verwendet:

`#` **aa** *rrggbb*

*aa* in der vorherigen Zeile stellt einen zweistelligen Hexadezimalwert dar, der verwendet wird, um die Deckkraft der Farbe anzugeben. *rr*, *gg* und *bb* repräsentieren jeweils einen zweistelligen Hexadezimalwert, der die Anteile von Rot, Grün und Blau einer Farbe angibt. Jede Hexadezimalziffer kann einen Wert von 0-9 bzw. A-F haben. 0 ist der kleinste und F der größte Wert. Der Alphawert 00 gibt eine Farbe an, die vollständig transparent ist, während ein Alphawert FF eine vollständig deckende Farbe erstellt.  Im folgenden Beispiel wird die hexadezimale ARGB-Notation verwendet, um zwei Farben anzugeben. Die erste ist teilweise transparent (sie hat einen Alphawert von X20), während die zweite vollständig deckend ist.

[!code-xaml[GradientBrushExamples_snip#TransparentGradientStopExample1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/GradientStopsExample.xaml#transparentgradientstopexample1xaml)]

<a name="fromscrgbsyntax"></a>

### <a name="specifying-color-opacity-in-code"></a>Angeben der Deckkraft einer Farbe in Code

Wenn Sie Code verwenden, können Sie mit der statischen- <xref:System.Windows.Media.Color.FromArgb%2A> Methode einen Alphawert angeben, wenn Sie eine Farbe erstellen. Die-Methode benötigt vier Parameter vom Typ <xref:System.Byte> . Der erste Parameter gibt den Alphakanal der Farbe an. Die anderen drei Parameter geben die Rot-, Grün- und Blauwerte der Farbe an. Jeder Wert sollte zwischen einschließlich 0 und 255 liegen. Beispielsweise gibt der Alphawert 0 an, dass eine Farbe völlig transparent ist, während der Wert 255 angibt, dass sie vollständig deckend ist. Im folgenden Beispiel wird die- <xref:System.Windows.Media.Color.FromArgb%2A> Methode verwendet, um zwei Farben zu entwickeln. Die erste ist teilweise transparent (sie hat einen Alphawert von 32), während die zweite vollständig deckend ist.

[!code-csharp[GradientBrushExamples_snip#TransparentGradientStopExample1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/GradientStopsExample.cs#transparentgradientstopexample1csharp)]

Alternativ können Sie die- <xref:System.Windows.Media.Color.FromScRgb%2A> Methode verwenden, mit der Sie ScRGB-Werte verwenden können, um eine Farbe zu erstellen.

<a name="otherbrushes"></a>

## <a name="painting-with-images-drawings-visuals-and-patterns"></a>Zeichnen mit Bildern, Zeichnungen, visuellen Elementen und Mustern

<xref:System.Windows.Media.ImageBrush><xref:System.Windows.Media.DrawingBrush> <xref:System.Windows.Media.VisualBrush> mit den Klassen, und können Sie einen Bereich mit Bildern, Zeichnungen oder visuellen Elementen zeichnen. Informationen über Zeichnen mit Bildern, Zeichnungen und Mustern finden Sie unter [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](painting-with-images-drawings-and-visuals.md).

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Brush>
- <xref:System.Windows.Media.SolidColorBrush>
- <xref:System.Windows.Media.LinearGradientBrush>
- <xref:System.Windows.Media.RadialGradientBrush>
- [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](painting-with-images-drawings-and-visuals.md)
- [Übersicht über Pinseltransformationen](brush-transformation-overview.md)
- [Renderingebenen für Grafiken](../advanced/graphics-rendering-tiers.md)
