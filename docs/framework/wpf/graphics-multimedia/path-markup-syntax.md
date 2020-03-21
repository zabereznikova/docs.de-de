---
title: Pfadmarkupsyntax
ms.date: 03/30/2017
helpviewer_keywords:
- attribute usage in XAML [WPF]
- XAML [WPF], attribute usage
- graphics [WPF], PathGeometry class
- XAML [WPF], object element usage
ms.assetid: b8586241-a02d-486e-9223-e1e98e047f41
ms.openlocfilehash: adcedcea6c8d6d988021cbbccf87bd25a042fd16
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181858"
---
# <a name="path-markup-syntax"></a>Pfadmarkupsyntax
Pfade werden in [Shapes und Basic Drawing in WPF Overview](shapes-and-basic-drawing-in-wpf-overview.md) und der [Geometrieübersicht](geometry-overview.md)erläutert, in diesem Thema wird jedoch detailliert [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]die leistungsstarke und komplexe Minisprache beschrieben, mit der Sie Pfadgeometrien mithilfe von kompakter angeben können.  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>Voraussetzungen  
 Um dieses Thema zu verstehen, sollten Sie <xref:System.Windows.Media.Geometry> mit den grundlegenden Funktionen von Objekten vertraut sein. Weitere Informationen finden Sie in der [Geometrieübersicht](geometry-overview.md).  
  
<a name="abouthisdocument"></a>
## <a name="streamgeometry-and-pathfigurecollection-mini-languages"></a>StreamGeometry- und PathFigureCollection-Minisprachen  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]bietet zwei Klassen, die Minisprachen zum <xref:System.Windows.Media.StreamGeometry> <xref:System.Windows.Media.PathFigureCollection>Beschreiben geometrischer Pfade bereitstellen: und .  
  
- Sie verwenden <xref:System.Windows.Media.StreamGeometry> die Minisprache, wenn <xref:System.Windows.Media.Geometry>Sie eine <xref:System.Windows.UIElement.Clip%2A> Eigenschaft des <xref:System.Windows.UIElement> Typs festlegen, z. B. die Eigenschaft eines oder die <xref:System.Windows.Shapes.Path.Data%2A> Eigenschaft eines <xref:System.Windows.Shapes.Path> Elements. Im folgenden Beispiel wird die <xref:System.Windows.Media.StreamGeometry>Attributsyntax zum Erstellen einer verwendet.  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMStreamGeometryAttributeSyntaxInline](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmstreamgeometryattributesyntaxinline)]  
  
- Sie verwenden <xref:System.Windows.Media.PathFigureCollection> die Minisprache, <xref:System.Windows.Media.PathGeometry.Figures%2A> wenn <xref:System.Windows.Media.PathGeometry>Sie die Eigenschaft einer festlegen. Im folgenden Beispiel wird eine <xref:System.Windows.Media.PathFigureCollection> Attributsyntax <xref:System.Windows.Media.PathGeometry>zum Erstellen einer für erstellt.  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMPathFigureCollectionAttributeSyntaxInline](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmpathfigurecollectionattributesyntaxinline)]  
  
 Wie Sie aus den vorangehenden Beispielen sehen können, sind die beiden Minisprachen sehr ähnlich. Es ist immer möglich, <xref:System.Windows.Media.PathGeometry> eine in jeder Situation <xref:System.Windows.Media.StreamGeometry>zu verwenden, in der Sie eine verwenden könnten; welche sollten Sie also verwenden? Verwenden <xref:System.Windows.Media.StreamGeometry> Sie eine, wenn Sie den Pfad nach dem Erstellen nicht ändern müssen. Verwenden <xref:System.Windows.Media.PathGeometry> Sie eine, wenn Sie den Pfad ändern müssen.  
  
 Weitere Informationen zu den <xref:System.Windows.Media.PathGeometry> <xref:System.Windows.Media.StreamGeometry> Unterschieden zwischen und Objekten finden Sie in der [Geometrieübersicht](geometry-overview.md).  
  
### <a name="a-note-about-white-space"></a>Anmerkung zu Leerzeichen  
 Aus Platzgründen wird ein einzelnes Leerzeichen in den folgenden Syntaxabschnitten dargestellt, aber mehrere Leerzeichen sind überall dort zulässig, wo ein einzelnes Leerzeichen angezeigt wird.  
  
 Zwei Zahlen müssen eigentlich nicht durch ein Komma oder Leerzeichen getrennt werden, aber dies kann nur geschehen, wenn die resultierende Zeichenfolge eindeutig ist. Zum Beispiel `2..3` sind es eigentlich zwei Zahlen: "2." und „.3“. Ebenso `2-3` ist "2" und "-3". Auch vor oder nach Befehlen sind keine Leerzeichen erforderlich.  
  
### <a name="syntax"></a>Syntax  
 Die [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Attributverwendungssyntax <xref:System.Windows.Media.StreamGeometry> für a <xref:System.Windows.Media.FillRule> besteht aus einem optionalen Wert und einer oder mehreren Abbildungsbeschreibungen.  
  
|StreamGeometry XAML-Attributverwendung|  
|-----------------------------------------|  
|`<`*Objekteigenschaft* *property* `="` `fillRule`[ `figureDescription` `figureDescription`] [ ]*`" ... />`|  
  
 Die [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Attributverwendungssyntax <xref:System.Windows.Media.PathFigureCollection> für a besteht aus einer oder mehreren Abbildungsbeschreibungen.  
  
|PathFigureCollection XAML-Attributverwendung|  
|-----------------------------------------------|  
|`<`*Objekteigenschaft* `="` *property* `figureDescription` `figureDescription`[ ]*`" ... />`|  
  
|Begriff|Beschreibung|  
|----------|-----------------|  
|*fillRule*|<xref:System.Windows.Media.FillRule?displayProperty=nameWithType><br /><br /> Gibt an, <xref:System.Windows.Media.StreamGeometry> ob <xref:System.Windows.Media.FillRule.EvenOdd> <xref:System.Windows.Media.FillRule.Nonzero> <xref:System.Windows.Media.PathGeometry.FillRule%2A>der die oder verwendet.<br /><br /> -   `F0`gibt die <xref:System.Windows.Media.FillRule.EvenOdd> Füllregel an.<br />-   `F1`gibt die <xref:System.Windows.Media.FillRule.Nonzero> Füllregel an.<br /><br /> Wenn Sie diesen Befehl weglassen, verwendet der Unterpfad das Standardverhalten, <xref:System.Windows.Media.FillRule.EvenOdd>d. h. . Wenn Sie diesen Befehl angeben, müssen Sie ihn zunächst platzieren.|  
|*figureDescription*|Eine aus einem Move-Befehl, Draw-Befehl und einem optionalen Close-Befehl bestehende Figur.<br /><br /> `moveCommand` `drawCommands`  `[` `closeCommand` `]`|  
|*moveCommand*|Ein Move-Befehl, der den Startpunkt der Figur angibt. Weitere Informationen finden Sie im Abschnitt [Befehl verschieben.](#themovecommand)|  
|*drawCommands*|Mindestens ein Draw-Befehl, der den Inhalt der Figur beschreibt. Weitere Informationen finden Sie im Abschnitt Zeichnen von [Befehlen.](#drawcommands)|  
|*closeCommand*|Ein optionaler Close-Befehl, der die Figur schließt. Weitere Informationen finden Sie im Abschnitt [Befehl schließen.](#closecommand)|  
  
<a name="themovecommand"></a>
## <a name="move-command"></a>Move-Befehl  
 Gibt den Ausgangspunkt einer neuen Figur an.  
  
|Syntax|  
|------------|  
|`M`*startPoint*<br /><br /> - oder -<br /><br /> `m`*startPoint*|  
  
|Begriff|Beschreibung|  
|----------|-----------------|  
|*startPoint*|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Der Ausgangspunkt einer neuen Figur.|  
  
 Eine Großbuchstabes gibt `M` an, dass `startPoint` es sich um einen absoluten Wert handelt. eine Kleinbuchstabeium `m` gibt an, dass `startPoint` es sich um einen Offset zum vorherigen Punkt handelt, oder (0,0), wenn keiner vorhanden ist. Wenn Sie nach dem Move-Befehl mehrere Punkte auflisten, wird eine Linie zu diesen Punkten gezeichnet, obwohl Sie den Line-Befehl angegeben haben.  
  
<a name="drawcommands"></a>
## <a name="draw-commands"></a>Draw-Befehle  
 Ein Draw-Befehl kann aus mehreren Shape-Befehlen bestehen. Die folgenden Shape-Befehle sind verfügbar: Linie, horizontale Linie, vertikale Linie, kubische Bézierkurve, quadratische Bézierkurve, glatte kubische Bézierkurve, glatte quadratische Bézierkurve und elliptischer Bogen.  
  
 Sie geben jeden Befehl unter Verwendung eines Großbuchstabens oder eines Kleinbuchstabens ein: Großbuchstaben geben absolute Werte an, und Kleinbuchstaben geben relative Werte an: Die Kontrollpunkte für dieses Segment sind abhängig vom Endpunkt des vorherigen Beispiels. Wenn Sie sequenziell mehr als einen Befehl desselben Typs eingeben, können Sie den doppelten Befehlseintrag weglassen. ist z. `L 100,200 300,400` `L 100,200 L 300,400`B. gleichbedeutend mit . In der folgenden Tabelle werden die **Befehle zum Verschieben** und Zeichnen **beschrieben.**  
  
### <a name="line-command"></a>Line-Befehl  
 Erstellt eine gerade Linie zwischen dem aktuellen Punkt und dem angegebenen Endpunkt. `l 20 30`und `L 20,30` sind Beispiele für gültige **Zeilenbefehle.**  
  
|Syntax|  
|------------|  
|`L`*endPoint*<br /><br /> - oder -<br /><br /> `l`*endPoint*|  
  
|Begriff|Beschreibung|  
|----------|-----------------|  
|*Endpunkt*|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Der Endpunkt der Linie.|  

Eine Großbuchstabes gibt `L` an, dass `endPoint` es sich um einen absoluten Wert handelt. eine Kleinbuchstabeium `l` gibt an, dass `endPoint` es sich um einen Offset zum vorherigen Punkt handelt, oder (0,0), wenn keiner vorhanden ist.

### <a name="horizontal-line-command"></a>Befehl für eine horizontale Linie  
 Erstellt eine horizontale Linie zwischen dem aktuellen Punkt und der angegebenen x-Koordinate. `H 90` ist ein Beispiel für einen gültigen Befehl für eine horizontale Linie.

|Syntax|  
|------------|  
|`H`  *X*<br /><br /> - oder -<br /><br /> `h`  *X*|  
  
|Begriff|Beschreibung|  
|----------|-----------------|  
|*X*|<xref:System.Double?displayProperty=nameWithType><br /><br /> Die x-Koordinate des Endpunkts der Linie.|  
  
Eine Großbuchstabes gibt `H` an, dass `x` es sich um einen absoluten Wert handelt. eine Kleinbuchstabeium `h` gibt an, dass `x` es sich um einen Offset zum vorherigen Punkt handelt, oder (0,0), wenn keiner vorhanden ist.
  
### <a name="vertical-line-command"></a>Befehl für vertikale Linie  
 Erstellt eine vertikale Linie zwischen dem aktuellen Punkt und der angegebenen y-Koordinate. `v 90` ist ein Beispiel für einen gültigen Befehl für eine vertikale Linie.

|Syntax|  
|------------|  
|`V`  *y*<br /><br /> - oder -<br /><br /> `v`  *y*|  
  
|Begriff|Beschreibung|  
|----------|-----------------|  
|*y*|<xref:System.Double?displayProperty=nameWithType><br /><br /> Die y-Koordinate des Endpunkts der Linie.|  

Eine Großbuchstabes gibt `V` an, dass `y` es sich um einen absoluten Wert handelt. eine Kleinbuchstabeium `v` gibt an, dass `y` es sich um einen Offset zum vorherigen Punkt handelt, oder (0,0), wenn keiner vorhanden ist.  

### <a name="cubic-bezier-curve-command"></a>Befehl Kubischer Bézierkurve  
 Erstellt eine kubische Bézierkurve zwischen dem aktuellen Punkt und dem`controlPoint`angegebenen `controlPoint`Endpunkt mithilfe der beiden angegebenen Kontrollpunkte ( 1 und 2). `C 100,200 200,400 300,200` ist ein Beispiel für einen gültigen Kurvenbefehl.  
  
|Syntax|  
|------------|  
|`C``controlPoint`1`controlPoint`2`endPoint`<br /><br /> - oder -<br /><br /> `c``controlPoint`1`controlPoint`2`endPoint`|  
  
|Begriff|Beschreibung|  
|----------|-----------------|  
|`controlPoint`1|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Der erste Kontrollpunkt der Kurve, der die beginnende Tangente der Kurve bestimmt.|  
|`controlPoint`2|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Der zweite Kontrollpunkt der Kurve, der die endende Tangente der Kurve bestimmt.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Der Punkt, bis zu dem die Kurve gezeichnet wird.|  
  
### <a name="quadratic-bezier-curve-command"></a>Quadratisches Bézier-Kurven-Befehl  
 Erstellt eine quadratische Bézierkurve zwischen dem aktuellen Punkt und dem angegebenen`controlPoint`Endpunkt mithilfe des angegebenen Kontrollpunkts ( ). `q 100,200 300,200`ist ein Beispiel für einen gültigen quadratischen Bézier-Kurvenbefehl.  
  
|Syntax|  
|------------|  
|`Q` `controlPoint` `endPoint`<br /><br /> - oder -<br /><br /> `q` `controlPoint` `endPoint`|  
  
|Begriff|Beschreibung|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Der Kontrollpunkt der Kurve, der die beginnende und endende Tangente der Kurve bestimmt.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Der Punkt, bis zu dem die Kurve gezeichnet wird.|  
  
### <a name="smooth-cubic-bezier-curve-command"></a>Glatte kubische Bézierkurve Befehl  
 Erstellt eine kubische Bézierkurve zwischen dem aktuellen Punkt und dem angegebenen Endpunkt. Der erste Kontrollpunkt soll die Reflektion des zweiten Kontrollpunkts des vorherigen Befehls relativ zum aktuellen Punkt sein. Wenn es keinen vorherigen Befehl gibt oder wenn der vorherige Befehl kein Kubischer Bézier-Kurvenbefehl oder ein glatter kubischer Bézier-Kurve-Befehl war, gehen Sie davon aus, dass der erste Kontrollpunkt mit dem aktuellen Punkt zusammenfällt. Der zweite Kontrollpunkt, der Kontrollpunkt für das Ende `controlPoint`der Kurve, wird durch 2 angegeben. Beispielsweise `S 100,200 200,300` ist ein gültiger Befehl für eine glatte kubische Bézierkurve.  
  
|Syntax|  
|------------|  
|`S``controlPoint`2`endPoint`<br /><br /> - oder -<br /><br /> `s``controlPoint`2`endPoint`|  
  
|Begriff|Beschreibung|  
|----------|-----------------|  
|`controlPoint`2|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Der Kontrollpunkt der Kurve, der die endende Tangente der Kurve bestimmt.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Der Punkt, bis zu dem die Kurve gezeichnet wird.|  
  
### <a name="smooth-quadratic-bezier-curve-command"></a>Smooth quadratische Bézier-Kurve Befehl  
 Erstellt eine quadratische Bézierkurve zwischen dem aktuellen Punkt und dem angegebenen Endpunkt. Der Kontrollpunkt soll die Reflektion des Kontrollpunkts des vorherigen Befehls relativ zum aktuellen Punkt sein. Wenn kein vorheriger Befehl vorhanden ist oder der vorherige Befehl kein Befehl für eine quadratische Bézierkurve und kein Befehl für eine glatte quadratische Bézierkurve war, fällt der Kontrollpunkt mit dem aktuellen Punkt zusammen.  
  
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
 Beschreibt die x- und y-Koordinaten eines Punktes, an dem (0,0) die obere linke Ecke ist.
  
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
  
 Infinity  
 Stellt <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>dar .  
  
 minus unendlich  
 Stellt <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>dar .  
  
 NaN  
 Stellt <xref:System.Double.NaN?displayProperty=nameWithType>dar .  
  
 Sie können auch die wissenschaftliche Schreibweise verwenden. `+1.e17` ist zum Beispiel ein gültiger Wert.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.StreamGeometry>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.PathFigureCollection>
- [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Übersicht über die Geometrie](geometry-overview.md)
- [How-to-Themen](geometries-how-to-topics.md)
