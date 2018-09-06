---
title: Pfadmarkupsyntax
ms.date: 03/30/2017
helpviewer_keywords:
- attribute usage in XAML [WPF]
- XAML [WPF], attribute usage
- graphics [WPF], PathGeometry class
- XAML [WPF], object element usage
ms.assetid: b8586241-a02d-486e-9223-e1e98e047f41
ms.openlocfilehash: d681cd15fa3daa3698edc5e0ad3d3c2669c1dfdf
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43804531"
---
# <a name="path-markup-syntax"></a>Pfadmarkupsyntax
Pfade finden Sie im [Formen und Grundlegendes Zeichnen in WPF (Übersicht)](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md) und [Übersicht über die Geometrie](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md), jedoch in diesem Thema wird ausführlich die leistungsstarke und komplexe Minisprache Sie den Pfad angeben können Pfadgeometrien kompakter unter Verwendung [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Um dieses Thema zu verstehen, sollten Sie mit den grundlegenden Funktionen von vertraut sein <xref:System.Windows.Media.Geometry> Objekte. Weitere Informationen finden Sie unter den [Übersicht über die Geometrie](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
<a name="abouthisdocument"></a>   
## <a name="streamgeometry-and-pathfigurecollection-mini-languages"></a>StreamGeometry- und PathFigureCollection-Minisprachen  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt zwei Klassen, die Minisprachen für die Beschreibung von geometrischen Pfaden bereitstellen: <xref:System.Windows.Media.StreamGeometry> und <xref:System.Windows.Media.PathFigureCollection>.  
  
-   Sie verwenden die <xref:System.Windows.Media.StreamGeometry> Minisprache beim Festlegen einer Eigenschaft vom Typ <xref:System.Windows.Media.Geometry>, wie z. B. die <xref:System.Windows.UIElement.Clip%2A> Eigenschaft eine <xref:System.Windows.UIElement> oder <xref:System.Windows.Shapes.Path.Data%2A> Eigenschaft eine <xref:System.Windows.Shapes.Path> Element. Im folgenden Beispiel wird eine Attributsyntax zum Erstellen einer <xref:System.Windows.Media.StreamGeometry>.  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMStreamGeometryAttributeSyntaxInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmstreamgeometryattributesyntaxinline)]  
  
-   Sie verwenden die <xref:System.Windows.Media.PathFigureCollection> Minisprache beim Festlegen der <xref:System.Windows.Media.PathGeometry.Figures%2A> Eigenschaft eine <xref:System.Windows.Media.PathGeometry>. Im folgende Beispiel wird eine Attributsyntax verwendet, zum Erstellen einer <xref:System.Windows.Media.PathFigureCollection> für eine <xref:System.Windows.Media.PathGeometry>.  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMPathFigureCollectionAttributeSyntaxInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmpathfigurecollectionattributesyntaxinline)]  
  
 Wie Sie aus den vorangehenden Beispielen sehen können, sind die beiden Minisprachen sehr ähnlich. Ist es immer möglich, verwenden eine <xref:System.Windows.Media.PathGeometry> in einer Situation, in denen Sie können, eine <xref:System.Windows.Media.StreamGeometry>; dies der Fall ist welche sollten Sie verwenden? Verwenden Sie eine <xref:System.Windows.Media.StreamGeometry> verwenden, wenn Sie nicht so ändern Sie den Pfad nach dem Erstellen, müssen eine <xref:System.Windows.Media.PathGeometry> , wenn Sie den Pfad ändern müssen.  
  
 Weitere Informationen zu den Unterschieden zwischen <xref:System.Windows.Media.PathGeometry> und <xref:System.Windows.Media.StreamGeometry> Objekten finden Sie die [Übersicht über die Geometrie](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
### <a name="a-note-about-white-space"></a>Anmerkung zu Leerzeichen  
 Aus Platzgründen wird ein einzelnes Leerzeichen in den folgenden Syntaxabschnitten dargestellt, aber mehrere Leerzeichen sind überall dort zulässig, wo ein einzelnes Leerzeichen angezeigt wird.  
  
 Zwei Zahlen müssen nicht unbedingt durch ein Komma oder ein Leerzeichen getrennt werden, aber dies kann nur durchgeführt werden, wenn die resultierende Zeichenfolge eindeutig ist. Z. B. `2..3` besteht aus zwei Zahlen: "2". und „.3“. Auf ähnliche Weise `2-3` ist "2" und "-3". Auch vor oder nach Befehlen sind keine Leerzeichen erforderlich.  
  
### <a name="syntax"></a>Syntax  
 Die [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Syntax für das Attribut ein <xref:System.Windows.Media.StreamGeometry> besteht aus einem optionalen <xref:System.Windows.Media.FillRule> Wert sowie Beschreibungen zu ermitteln.  
  
|StreamGeometry XAML-Attributverwendung|  
|-----------------------------------------|  
|`<` *Objekt* *Eigenschaft* `="`[ `fillRule`] `figureDescription`[ `figureDescription`] * `" ... />`|  
  
 Die [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Syntax für das Attribut ein <xref:System.Windows.Media.PathFigureCollection> besteht aus mindestens einer figurbeschreibung.  
  
|PathFigureCollection XAML-Attributverwendung|  
|-----------------------------------------------|  
|`<` *Objekt* *Eigenschaft* `="` `figureDescription`[ `figureDescription`] * `" ... />`|  
  
|Begriff|Beschreibung|  
|----------|-----------------|  
|*fillRule*|<xref:System.Windows.Media.FillRule?displayProperty=nameWithType><br /><br /> Gibt an, ob die <xref:System.Windows.Media.StreamGeometry> verwendet die <xref:System.Windows.Media.FillRule.EvenOdd> oder <xref:System.Windows.Media.FillRule.Nonzero> <xref:System.Windows.Media.PathGeometry.FillRule%2A>.<br /><br /> -   `F0` Gibt an, die <xref:System.Windows.Media.FillRule.EvenOdd> -Füllregel fest.<br />-   `F1` Gibt an, die <xref:System.Windows.Media.FillRule.Nonzero> -Füllregel fest.<br /><br /> Wenn Sie diesen Befehl weglassen, verwendet der untergeordnete Pfad das Standardverhalten, handelt es sich <xref:System.Windows.Media.FillRule.EvenOdd>. Wenn Sie diesen Befehl angeben, müssen Sie ihn zunächst platzieren.|  
|*figureDescription*|Eine aus einem Move-Befehl, Draw-Befehl und einem optionalen Close-Befehl bestehende Figur.<br /><br /> `moveCommand` `drawCommands`  `[` `closeCommand` `]`|  
|*moveCommand*|Ein Move-Befehl, der den Startpunkt der Figur angibt. Finden Sie unter den [Move-Befehl](#themovecommand) Abschnitt.|  
|*drawCommands*|Mindestens ein Draw-Befehl, der den Inhalt der Figur beschreibt. Finden Sie unter den [Draw-Befehle](#drawcommands) Abschnitt.|  
|*closeCommand*|Ein optionaler Close-Befehl, der die Figur schließt. Finden Sie unter den [Close-Befehl](#closecommand) Abschnitt.|  
  
<a name="themovecommand"></a>   
## <a name="move-command"></a>Move-Befehl  
 Gibt den Ausgangspunkt einer neuen Figur an.  
  
|Syntax|  
|------------|  
|`M` *startPoint*<br /><br /> - oder -<br /><br /> `m` *startPoint*|  
  
|Begriff|Beschreibung|  
|----------|-----------------|  
|*startPoint*|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Der Ausgangspunkt einer neuen Figur.|  
  
 Ein großgeschriebenes `M` gibt an, dass `startPoint` ist ein absoluter Wert ist ein klein geschriebenes `m` gibt an, dass `startPoint` um einen Offset zum vorherigen Punkt handelt oder um (0,0), falls keiner vorhanden ist. Wenn Sie nach dem Move-Befehl mehrere Punkte auflisten, wird eine Linie zu diesen Punkten gezeichnet, obwohl Sie den Line-Befehl angegeben haben.  
  
<a name="drawcommands"></a>   
## <a name="draw-commands"></a>Draw-Befehle  
 Ein Draw-Befehl kann aus mehreren Shape-Befehlen bestehen. Die folgenden Shape-Befehle sind verfügbar: Linie, horizontale Linie, vertikale Linie, kubische Bézierkurve, quadratische Bézierkurve, glatte kubische Bézierkurve, glatte quadratische Bézierkurve und elliptischer Bogen.  
  
 Sie geben jeden Befehl unter Verwendung eines Großbuchstabens oder eines Kleinbuchstabens ein: Großbuchstaben geben absolute Werte an, und Kleinbuchstaben geben relative Werte an: Die Kontrollpunkte für dieses Segment sind abhängig vom Endpunkt des vorherigen Beispiels. Wenn Sie nacheinander mehrere Befehle desselben Typs eingeben möchten, können Sie den doppelten Befehlseintrag auslassen; z. B. `L 100,200 300,400` entspricht `L 100,200 L 300,400`. Die folgende Tabelle beschreibt die **verschieben** und **zeichnen** Befehle.  
  
### <a name="line-command"></a>Line-Befehl  
 Erstellt eine gerade Linie zwischen dem aktuellen Punkt und dem angegebenen Endpunkt. `l 20 30` und `L 20,30` sind Beispiele für gültige **Zeile** Befehle.  
  
|Syntax|  
|------------|  
|`L` *endPoint*<br /><br /> - oder -<br /><br /> `l` *endPoint*|  
  
|Begriff|Beschreibung|  
|----------|-----------------|  
|*endPoint*|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Der Endpunkt der Linie.|  

Ein großgeschriebenes `L` gibt an, dass `endPoint` ist ein absoluter Wert ist ein klein geschriebenes `l` gibt an, dass `endPoint` um einen Offset zum vorherigen Punkt handelt oder um (0,0), falls keiner vorhanden ist.

### <a name="horizontal-line-command"></a>Befehl für eine horizontale Linie  
 Erstellt eine horizontale Linie zwischen dem aktuellen Punkt und der angegebenen x-Koordinate. `H 90` ist ein Beispiel für einen gültigen Befehl für eine horizontale Linie.

  
|Syntax|  
|------------|  
|`H`  *x*<br /><br /> - oder -<br /><br /> `h`  *x*|  
  
|Begriff|Beschreibung|  
|----------|-----------------|  
|*w*|<xref:System.Double?displayProperty=nameWithType><br /><br /> Die x-Koordinate des Endpunkts der Linie.|  
  
Ein großgeschriebenes `H` gibt an, dass `x` ist ein absoluter Wert ist ein klein geschriebenes `h` gibt an, dass `x` um einen Offset zum vorherigen Punkt handelt oder um (0,0), falls keiner vorhanden ist.
  
### <a name="vertical-line-command"></a>Befehl für vertikale Linie  
 Erstellt eine vertikale Linie zwischen dem aktuellen Punkt und der angegebenen y-Koordinate. `v 90` ist ein Beispiel für einen gültigen Befehl für eine vertikale Linie.

  
|Syntax|  
|------------|  
|`V`  *y*<br /><br /> - oder -<br /><br /> `v`  *y*|  
  
|Begriff|Beschreibung|  
|----------|-----------------|  
|*y*|<xref:System.Double?displayProperty=nameWithType><br /><br /> Die y-Koordinate des Endpunkts der Linie.|  

Ein großgeschriebenes `V` gibt an, dass `y` ist ein absoluter Wert ist ein klein geschriebenes `v` gibt an, dass `y` um einen Offset zum vorherigen Punkt handelt oder um (0,0), falls keiner vorhanden ist.  
    
### <a name="cubic-bezier-curve-command"></a>Kubische Bezier-Kurve-Befehl  
 Erstellt eine kubische Bezier-Kurve zwischen dem aktuellen Punkt und dem angegebenen Endpunkt mit den zwei angegebenen Kontrollpunkten (`controlPoint`1 und `controlPoint`2). `C 100,200 200,400 300,200` ist ein Beispiel für einen gültigen Kurvenbefehl.  
  
|Syntax|  
|------------|  
|`C` `controlPoint`1`controlPoint`2`endPoint`<br /><br /> - oder -<br /><br /> `c` `controlPoint`1`controlPoint`2`endPoint`|  
  
|Begriff|Beschreibung|  
|----------|-----------------|  
|`controlPoint`1|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Der erste Kontrollpunkt der Kurve, der die beginnende Tangente der Kurve bestimmt.|  
|`controlPoint`2|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Der zweite Kontrollpunkt der Kurve, der die endende Tangente der Kurve bestimmt.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Der Punkt, bis zu dem die Kurve gezeichnet wird.|  
  
### <a name="quadratic-bezier-curve-command"></a>Quadratischen Bezier-Kurve-Befehl  
 Erstellt eine quadratische Bezier-Kurve zwischen dem aktuellen Punkt und dem angegebenen Endpunkt mithilfe des angegebenen Kontrollpunkts (`controlPoint`). `q 100,200 300,200` ist ein Beispiel für einen gültigen quadratischen Bezier-Kurve-Befehl.  
  
|Syntax|  
|------------|  
|`Q` `controlPoint` `endPoint`<br /><br /> - oder -<br /><br /> `q` `controlPoint` `endPoint`|  
  
|Begriff|Beschreibung|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Der Kontrollpunkt der Kurve, der die beginnende und endende Tangente der Kurve bestimmt.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Der Punkt, bis zu dem die Kurve gezeichnet wird.|  
  
### <a name="smooth-cubic-bezier-curve-command"></a>Smooth kubische Bezier-Kurve Befehl  
 Erstellt eine kubische Bézierkurve zwischen dem aktuellen Punkt und dem angegebenen Endpunkt. Der erste Kontrollpunkt soll die Reflektion des zweiten Kontrollpunkts des vorherigen Befehls relativ zum aktuellen Punkt sein. Ausgegangen Sie wenn es keinen vorherigen Befehl, oder wenn der vorherige Befehl keinen kubische Bezier-Kurve-Befehl oder ein smooth kubische Bezier-Kurve-Befehl wurde, wird davon, dass der erste Kontrollpunkt, mit dem aktuellen Punkt ist. Der zweite Kontrollpunkt, der Kontrollpunkt für das Ende der Kurve, wird angegeben, indem `controlPoint`2. Z. B. `S 100,200 200,300` ist ein gültiger smooth kubische Bezier-kurvenbefehl.  
  
|Syntax|  
|------------|  
|`S` `controlPoint`2`endPoint`<br /><br /> - oder -<br /><br /> `s` `controlPoint`2`endPoint`|  
  
|Begriff|Beschreibung|  
|----------|-----------------|  
|`controlPoint`2|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Der Kontrollpunkt der Kurve, der die endende Tangente der Kurve bestimmt.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Der Punkt, bis zu dem die Kurve gezeichnet wird.|  
  
### <a name="smooth-quadratic-bezier-curve-command"></a>Smooth quadratischen Bezier-Kurve Befehl  
 Erstellt eine quadratische Bezierkurve zwischen dem aktuellen Punkt und dem angegebenen Endpunkt. Der Kontrollpunkt soll die Reflektion des Kontrollpunkts des vorherigen Befehls relativ zum aktuellen Punkt sein. Wenn kein vorheriger Befehl vorhanden ist oder der vorherige Befehl kein Befehl für eine quadratische Bézierkurve und kein Befehl für eine glatte quadratische Bézierkurve war, fällt der Kontrollpunkt mit dem aktuellen Punkt zusammen.  
  
|Syntax|  
|------------|  
|`T` `controlPoint` `endPoint`<br /><br /> - oder -<br /><br /> `t` `controlPoint` `endPoint`|  
  
|Begriff|Beschreibung|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Der Kontrollpunkt der Kurve, der die beginnende Tangente der Kurve bestimmt.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Der Punkt, bis zu dem die Kurve gezeichnet wird.|  
  
### <a name="elliptical-arc-command"></a>Befehl für elliptischen Bogen  
 Erstellt einen elliptischen Bogen zwischen dem aktuellen Punkt und dem angegebenen Endpunkt.  
  
|Syntax|  
|------------|  
|`A` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`<br /><br /> - oder -<br /><br /> `a` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`|  
  
|Begriff|Beschreibung|  
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
|`Z`<br /><br /> - oder -<br /><br /> `z`|  

<a name="pointsyntax"></a>   
## <a name="point-syntax"></a>Punkt-Syntax  
 Beschreibt die x- und y-Koordinaten eines Punkts, in denen (0,0) wird von die linke obere Ecke.
  
|Syntax|  
|------------|  
|`x` `,` `y`<br /><br /> - oder -<br /><br /> `x` `y`|  
  
|Begriff|Beschreibung|  
|----------|-----------------|  
|`x`|<xref:System.Double?displayProperty=nameWithType><br /><br /> Die x-Koordinate des Punkts.|  
|`y`|<xref:System.Double?displayProperty=nameWithType><br /><br /> Die y-Koordinate des Punkts.|  
  
<a name="specialvalues"></a>   
## <a name="special-values"></a>Spezielle Werte  
 Anstelle eines numerischen Standardwerts können Sie auch die folgenden speziellen Werte verwenden. Die Groß-/Kleinschreibung muss bei diesen Werten berücksichtigt werden.  
  
 Unendlich  
 Stellt <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.  
  
 minus unendlich  
 Stellt <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>.  
  
 NaN  
 Stellt <xref:System.Double.NaN?displayProperty=nameWithType>.  
  
 Sie können auch die wissenschaftliche Schreibweise verwenden. Z. B. `+1.e17` ist ein gültiger Wert.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Shapes.Path>  
 <xref:System.Windows.Media.StreamGeometry>  
 <xref:System.Windows.Media.PathGeometry>  
 <xref:System.Windows.Media.PathFigureCollection>  
 [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)  
 [Übersicht über Geometrien](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/graphics-multimedia/geometries-how-to-topics.md)
