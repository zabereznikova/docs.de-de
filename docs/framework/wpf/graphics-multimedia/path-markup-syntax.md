---
title: Pfadmarkupsyntax
description: Erfahren Sie mehr über die leistungsstarke und komplexe Mini Sprache, die Sie zum Angeben von kompakten Pfadgeometrien in Windows Presentation Foundation (WPF) verwenden können.
ms.date: 03/30/2017
helpviewer_keywords:
- attribute usage in XAML [WPF]
- XAML [WPF], attribute usage
- graphics [WPF], PathGeometry class
- XAML [WPF], object element usage
ms.assetid: b8586241-a02d-486e-9223-e1e98e047f41
ms.openlocfilehash: 6d2778522b622f0b0dcb59673e793a6d772a4b4f
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853658"
---
# <a name="path-markup-syntax"></a>Pfadmarkupsyntax
Pfade finden Sie unter [Übersicht über die WPF-Übersicht](shapes-and-basic-drawing-in-wpf-overview.md) und die [Geometrie Übersicht](geometry-overview.md). in diesem Thema wird jedoch ausführlich die leistungsstarke und komplexe Mini Sprache beschrieben, die Sie verwenden können, um Pfadgeometrien mit kompakteren rechten anzugeben [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] .  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>Voraussetzungen  
 Um dieses Thema zu verstehen, sollten Sie mit den grundlegenden Features von <xref:System.Windows.Media.Geometry> Objekten vertraut sein. Weitere Informationen finden Sie in der [Übersicht über die Geometrie](geometry-overview.md).  
  
<a name="abouthisdocument"></a>
## <a name="streamgeometry-and-pathfigurecollection-mini-languages"></a>StreamGeometry- und PathFigureCollection-Minisprachen  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]stellt zwei Klassen bereit, die Mini Sprachen zur Beschreibung geometrischer Pfade bereitstellen: <xref:System.Windows.Media.StreamGeometry> und <xref:System.Windows.Media.PathFigureCollection> .  
  
- Sie verwenden die <xref:System.Windows.Media.StreamGeometry> Mini Sprache, wenn Sie eine Eigenschaft des Typs festlegen <xref:System.Windows.Media.Geometry> , z. b. die- <xref:System.Windows.UIElement.Clip%2A> Eigenschaft einer-Eigenschaft <xref:System.Windows.UIElement> oder die- <xref:System.Windows.Shapes.Path.Data%2A> Eigenschaft eines- <xref:System.Windows.Shapes.Path> Elements. Im folgenden Beispiel wird die-Attribut Syntax verwendet, um eine zu erstellen <xref:System.Windows.Media.StreamGeometry> .  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMStreamGeometryAttributeSyntaxInline](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmstreamgeometryattributesyntaxinline)]  
  
- <xref:System.Windows.Media.PathFigureCollection>Beim Festlegen der-Eigenschaft eines wird die Mini Sprache verwendet <xref:System.Windows.Media.PathGeometry.Figures%2A> <xref:System.Windows.Media.PathGeometry> . Im folgenden Beispiel wird eine-Attribut Syntax verwendet, um einen <xref:System.Windows.Media.PathFigureCollection> für ein zu erstellen <xref:System.Windows.Media.PathGeometry> .  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMPathFigureCollectionAttributeSyntaxInline](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmpathfigurecollectionattributesyntaxinline)]  
  
 Wie Sie aus den vorangehenden Beispielen sehen können, sind die beiden Minisprachen sehr ähnlich. Es ist immer möglich, einen in einer beliebigen Situation zu verwenden, in der <xref:System.Windows.Media.PathGeometry> Sie einen verwenden könnten <xref:System.Windows.Media.StreamGeometry> . Verwenden <xref:System.Windows.Media.StreamGeometry> Sie, wenn Sie den Pfad nach der Erstellung nicht ändern müssen <xref:System.Windows.Media.PathGeometry> . verwenden Sie, wenn Sie den Pfad ändern müssen.  
  
 Weitere Informationen zu den Unterschieden zwischen <xref:System.Windows.Media.PathGeometry> -und- <xref:System.Windows.Media.StreamGeometry> Objekten finden Sie in der Übersicht über die [Geometrie](geometry-overview.md).  
  
### <a name="a-note-about-white-space"></a>Anmerkung zu Leerzeichen  
 Aus Platzgründen wird ein einzelnes Leerzeichen in den folgenden Syntaxabschnitten dargestellt, aber mehrere Leerzeichen sind überall dort zulässig, wo ein einzelnes Leerzeichen angezeigt wird.  
  
 Zwei Zahlen müssen eigentlich nicht durch ein Komma oder Leerraum voneinander getrennt werden. Dies ist jedoch nur möglich, wenn die resultierende Zeichenfolge eindeutig ist. Beispielsweise `2..3` ist tatsächlich zwei Ziffern: "2". und „.3“. Auf ähnliche Weise `2-3` ist "2" und "-3". Auch vor oder nach Befehlen sind keine Leerzeichen erforderlich.  
  
### <a name="syntax"></a>Syntax  
 Die [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Syntax der Attribut Verwendung für einen <xref:System.Windows.Media.StreamGeometry> besteht aus einem optionalen <xref:System.Windows.Media.FillRule> Wert und einer oder mehreren Abbildung Beschreibungen.  
  
|StreamGeometry XAML-Attributverwendung|  
|-----------------------------------------|  
|`<`*Object* - *Eigenschaft* `="` [ `fillRule` ] `figureDescription` [ `figureDescription` ] *`" ... />`|  
  
 Die [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Syntax der Attribut Verwendung für einen <xref:System.Windows.Media.PathFigureCollection> besteht aus einer oder mehreren Abbildung Beschreibungen.  
  
|PathFigureCollection XAML-Attributverwendung|  
|-----------------------------------------------|  
|`<`*Object* - *Eigenschaft* `="` `figureDescription` [ `figureDescription` ] *`" ... />`|  
  
|Begriff|BESCHREIBUNG|  
|----------|-----------------|  
|*fillRule*|<xref:System.Windows.Media.FillRule?displayProperty=nameWithType><br /><br /> Gibt an, ob die das <xref:System.Windows.Media.StreamGeometry> oder die verwendet <xref:System.Windows.Media.FillRule.EvenOdd> <xref:System.Windows.Media.FillRule.Nonzero> <xref:System.Windows.Media.PathGeometry.FillRule%2A> .<br /><br /> -   `F0`Gibt die <xref:System.Windows.Media.FillRule.EvenOdd> Füllregel an.<br />-   `F1`Gibt die <xref:System.Windows.Media.FillRule.Nonzero> Füllregel an.<br /><br /> Wenn Sie diesen Befehl weglassen, verwendet der Unterpfad das Standardverhalten, d <xref:System.Windows.Media.FillRule.EvenOdd> . h.. Wenn Sie diesen Befehl angeben, müssen Sie ihn zunächst platzieren.|  
|*figureDescription*|Eine aus einem Move-Befehl, Draw-Befehl und einem optionalen Close-Befehl bestehende Figur.<br /><br /> `moveCommand` `drawCommands`  `[` `closeCommand` `]`|  
|*moveCommand*|Ein Move-Befehl, der den Startpunkt der Figur angibt. Weitere Informationen finden Sie im Abschnitt [Move Command](#themovecommand) .|  
|*drawCommands*|Mindestens ein Draw-Befehl, der den Inhalt der Figur beschreibt. Weitere Informationen finden Sie im Abschnitt [Zeichnen-Befehle](#drawcommands) .|  
|*closeCommand*|Ein optionaler Close-Befehl, der die Figur schließt. Weitere Informationen finden Sie im Abschnitt " [Schließen](#closecommand) ".|  
  
<a name="themovecommand"></a>
## <a name="move-command"></a>Move-Befehl  
 Gibt den Ausgangspunkt einer neuen Figur an.  
  
|Syntax|  
|------------|  
|`M`*Startpunkt*<br /><br /> - oder -<br /><br /> `m`*Startpunkt*|  
  
|Begriff|BESCHREIBUNG|  
|----------|-----------------|  
|*startPoint*|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Der Ausgangspunkt einer neuen Figur.|  
  
 Ein Großbuchstabe `M` gibt an, dass `startPoint` ein absoluter Wert ist. ein Kleinbuchstabe gibt an, `m` dass `startPoint` ein Offset zum vorherigen Punkt ist, oder (0,0), wenn kein Wert vorhanden ist. Wenn Sie nach dem Move-Befehl mehrere Punkte auflisten, wird eine Linie zu diesen Punkten gezeichnet, obwohl Sie den Line-Befehl angegeben haben.  
  
<a name="drawcommands"></a>
## <a name="draw-commands"></a>Draw-Befehle  
 Ein Draw-Befehl kann aus mehreren Shape-Befehlen bestehen. Die folgenden Shape-Befehle sind verfügbar: Linie, horizontale Linie, vertikale Linie, kubische Bézierkurve, quadratische Bézierkurve, glatte kubische Bézierkurve, glatte quadratische Bézierkurve und elliptischer Bogen.  
  
 Sie geben jeden Befehl unter Verwendung eines Großbuchstabens oder eines Kleinbuchstabens ein: Großbuchstaben geben absolute Werte an, und Kleinbuchstaben geben relative Werte an: Die Kontrollpunkte für dieses Segment sind abhängig vom Endpunkt des vorherigen Beispiels. Wenn Sie sequenziell mehr als einen Befehl desselben Typs eingeben, können Sie den doppelten Befehls Eintrag weglassen. beispielsweise `L 100,200 300,400` entspricht `L 100,200 L 300,400` . In der folgenden Tabelle werden die **Move** -und **Draw** -Befehle beschrieben.  
  
### <a name="line-command"></a>Line-Befehl  
 Erstellt eine gerade Linie zwischen dem aktuellen Punkt und dem angegebenen Endpunkt. `l 20 30`und `L 20,30` sind Beispiele für gültige **Zeilen** Befehle.  
  
|Syntax|  
|------------|  
|`L`*Endpunkt*<br /><br /> - oder -<br /><br /> `l`*Endpunkt*|  
  
|Begriff|BESCHREIBUNG|  
|----------|-----------------|  
|*Dreher*|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Der Endpunkt der Linie.|  

Ein Großbuchstabe `L` gibt an, dass `endPoint` ein absoluter Wert ist. ein Kleinbuchstabe gibt an, `l` dass `endPoint` ein Offset zum vorherigen Punkt ist, oder (0,0), wenn kein Wert vorhanden ist.

### <a name="horizontal-line-command"></a>Befehl für eine horizontale Linie  
 Erstellt eine horizontale Linie zwischen dem aktuellen Punkt und der angegebenen x-Koordinate. `H 90` ist ein Beispiel für einen gültigen Befehl für eine horizontale Linie.

|Syntax|  
|------------|  
|`H`  *Stuben*<br /><br /> - oder -<br /><br /> `h`  *Stuben*|  
  
|Begriff|BESCHREIBUNG|  
|----------|-----------------|  
|*x*|<xref:System.Double?displayProperty=nameWithType><br /><br /> Die x-Koordinate des Endpunkts der Linie.|  
  
Ein Großbuchstabe `H` gibt an, dass `x` ein absoluter Wert ist. ein Kleinbuchstabe gibt an, `h` dass `x` ein Offset zum vorherigen Punkt ist, oder (0,0), wenn kein Wert vorhanden ist.
  
### <a name="vertical-line-command"></a>Befehl für vertikale Linie  
 Erstellt eine vertikale Linie zwischen dem aktuellen Punkt und der angegebenen y-Koordinate. `v 90` ist ein Beispiel für einen gültigen Befehl für eine vertikale Linie.

|Syntax|  
|------------|  
|`V`  *Teenie*<br /><br /> - oder -<br /><br /> `v`  *Teenie*|  
  
|Begriff|BESCHREIBUNG|  
|----------|-----------------|  
|*Teenie*|<xref:System.Double?displayProperty=nameWithType><br /><br /> Die y-Koordinate des Endpunkts der Linie.|  

Ein Großbuchstabe `V` gibt an, dass `y` ein absoluter Wert ist. ein Kleinbuchstabe gibt an, `v` dass `y` ein Offset zum vorherigen Punkt ist, oder (0,0), wenn kein Wert vorhanden ist.  

### <a name="cubic-bezier-curve-command"></a>Befehl "kubisch Bezier Kurve"  
 Erstellt eine kubische Bezier-Kurve zwischen dem aktuellen Punkt und dem angegebenen Endpunkt, indem die beiden angegebenen Kontrollpunkte ( `controlPoint` 1 und `controlPoint` 2) verwendet werden. `C 100,200 200,400 300,200` ist ein Beispiel für einen gültigen Kurvenbefehl.  
  
|Syntax|  
|------------|  
|`C``controlPoint`1 `controlPoint` 2`endPoint`<br /><br /> - oder -<br /><br /> `c``controlPoint`1 `controlPoint` 2`endPoint`|  
  
|Begriff|BESCHREIBUNG|  
|----------|-----------------|  
|`controlPoint`1|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Der erste Kontrollpunkt der Kurve, der die beginnende Tangente der Kurve bestimmt.|  
|`controlPoint`2|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Der zweite Kontrollpunkt der Kurve, der die endende Tangente der Kurve bestimmt.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Der Punkt, bis zu dem die Kurve gezeichnet wird.|  
  
### <a name="quadratic-bezier-curve-command"></a>Befehl "Quadratic Bezier Curve"  
 Erstellt mithilfe des angegebenen Steuerungs Punkts () eine quadratische Bezier-Kurve zwischen dem aktuellen Punkt und dem angegebenen Endpunkt `controlPoint` . `q 100,200 300,200`ist ein Beispiel für einen gültigen Befehl für eine quadratische Bezier-Kurve.  
  
|Syntax|  
|------------|  
|`Q` `controlPoint` `endPoint`<br /><br /> - oder -<br /><br /> `q` `controlPoint` `endPoint`|  
  
|Begriff|BESCHREIBUNG|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Der Kontrollpunkt der Kurve, der die beginnende und endende Tangente der Kurve bestimmt.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Der Punkt, bis zu dem die Kurve gezeichnet wird.|  
  
### <a name="smooth-cubic-bezier-curve-command"></a>Befehl "glatte kubische Bezier-Kurve"  
 Erstellt eine kubische Bézierkurve zwischen dem aktuellen Punkt und dem angegebenen Endpunkt. Der erste Kontrollpunkt soll die Reflektion des zweiten Kontrollpunkts des vorherigen Befehls relativ zum aktuellen Punkt sein. Wenn kein vorheriger Befehl vorhanden ist oder wenn es sich bei dem vorherigen Befehl nicht um einen kubischen Bezier-Kurven Befehl oder einen Smooth kubischen Bezier-Kurven Befehl handelt, gehen Sie davon aus, dass der erste Kontrollpunkt mit dem aktuellen Punkt koincident ist. Der zweite Kontrollpunkt, der Kontrollpunkt für das Ende der Kurve, wird durch 2 angegeben `controlPoint` . Beispielsweise `S 100,200 200,300` ist ein gültiger Befehl für eine glatte kubische Bezier-Kurve.  
  
|Syntax|  
|------------|  
|`S``controlPoint`2`endPoint`<br /><br /> - oder -<br /><br /> `s``controlPoint`2`endPoint`|  
  
|Begriff|BESCHREIBUNG|  
|----------|-----------------|  
|`controlPoint`2|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Der Kontrollpunkt der Kurve, der die endende Tangente der Kurve bestimmt.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Der Punkt, bis zu dem die Kurve gezeichnet wird.|  
  
### <a name="smooth-quadratic-bezier-curve-command"></a>Smooth quadratischen Bezier-Kurven Befehl  
 Erstellt eine quadratische Bezier-Kurve zwischen dem aktuellen Punkt und dem angegebenen Endpunkt. Der Kontrollpunkt soll die Reflektion des Kontrollpunkts des vorherigen Befehls relativ zum aktuellen Punkt sein. Wenn kein vorheriger Befehl vorhanden ist oder der vorherige Befehl kein Befehl für eine quadratische Bézierkurve und kein Befehl für eine glatte quadratische Bézierkurve war, fällt der Kontrollpunkt mit dem aktuellen Punkt zusammen.  
  
|Syntax|  
|------------|  
|`T` `controlPoint` `endPoint`<br /><br /> - oder -<br /><br /> `t` `controlPoint` `endPoint`|  
  
|Begriff|BESCHREIBUNG|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Der Kontrollpunkt der Kurve, der die beginnende Tangente der Kurve bestimmt.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Der Punkt, bis zu dem die Kurve gezeichnet wird.|  
  
### <a name="elliptical-arc-command"></a>Befehl für elliptischen Bogen  
 Erstellt einen elliptischen Bogen zwischen dem aktuellen Punkt und dem angegebenen Endpunkt.  
  
|Syntax|  
|------------|  
|`A` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`<br /><br /> - oder -<br /><br /> `a` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`|  
  
|Begriff|BESCHREIBUNG|  
|----------|-----------------|  
|`size`|<xref:System.Windows.Size?displayProperty=nameWithType><br /><br /> Der X- und Y-Radius des Bogens.|  
|`rotationAngle`|<xref:System.Double?displayProperty=nameWithType><br /><br /> Die Drehung der Ellipse in Grad.|  
|`isLargeArcFlag`|Ist auf 1 festgelegt, wenn der Winkel des Bogens 180 Grad oder größer sein soll; andernfalls auf 0 festgelegt.|  
|`sweepDirectionFlag`|Ist auf 1 festgelegt, wenn der Bogen in einer Richtung mit positivem Winkel gezeichnet wird; andernfalls auf 0 festgelegt.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Der Punkt, bis zu dem der Bogen gezeichnet wird.|  
  
<a name="closecommand"></a>
## <a name="the-close-command"></a>Close-Befehl  
 Beendet die aktuelle Figur und erstellt eine Linie, die den aktuellen Punkt mit dem Startpunkt der Figur verbindet. Dieser Befehl erstellt einen LineJoin (Ecke) zwischen dem letzten Segment und dem ersten Segment der Figur.  
  
|Syntax|  
|------------|  
|`Z`<br /><br /> - oder -<br /><br /> `z`|  

<a name="pointsyntax"></a>
## <a name="point-syntax"></a>Punkt-Syntax  
 Beschreibt die x-und y-Koordinaten eines Punkts, wobei (0,0) die linke obere Ecke ist.
  
|Syntax|  
|------------|  
|`x` `,` `y`<br /><br /> - oder -<br /><br /> `x` `y`|  
  
|Begriff|BESCHREIBUNG|  
|----------|-----------------|  
|`x`|<xref:System.Double?displayProperty=nameWithType><br /><br /> Die x-Koordinate des Punkts.|  
|`y`|<xref:System.Double?displayProperty=nameWithType><br /><br /> Die y-Koordinate des Punkts.|  
  
<a name="specialvalues"></a>
## <a name="special-values"></a>Spezielle Werte  
 Anstelle eines numerischen Standardwerts können Sie auch die folgenden speziellen Werte verwenden. Die Werte werden nach Groß-/Kleinschreibung unterschieden.  
  
 Unendlich  
 Stellt dar <xref:System.Double.PositiveInfinity?displayProperty=nameWithType> .  
  
 minus unendlich  
 Stellt dar <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> .  
  
 NaN  
 Stellt dar <xref:System.Double.NaN?displayProperty=nameWithType> .  
  
 Sie können auch die wissenschaftliche Schreibweise verwenden. `+1.e17` ist zum Beispiel ein gültiger Wert.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.StreamGeometry>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.PathFigureCollection>
- [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Übersicht über die Geometrie](geometry-overview.md)
- [Artikel zu Vorgehensweisen](geometries-how-to-topics.md)
